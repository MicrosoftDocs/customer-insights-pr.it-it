---
title: Esperimenti con Azure Machine Learning
description: Utilizzare modelli basati su Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e37eec503c9df83ef72497e22afa1266296e642c
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881743"
---
# <a name="use-azure-machine-learning-based-models"></a>Utilizzare modelli basati su Azure Machine Learning

I dati unificati in Dynamics 365 Customer Insights sono una fonte per la creazione di modelli di Machine Learning che possono generare ulteriori informazioni aziendali. Customer Insights si integra con Azure Machine Learning per usare i tuoi modelli personalizzati.

## <a name="prerequisites"></a>Prerequisiti

- Accesso a Customer Insights
- Abbonamento attivo ad Azure Enterprise
- [Profili cliente unificati](data-unification.md)
- [Esportazione di entità nell'archivio BLOB di Azure](export-azure-blob-storage.md) configurata

## <a name="set-up-azure-machine-learning-workspace"></a>Configurare l'area di lavoro di Azure Machine Learning

1. Vedi [Creare un'area di lavoro di Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) per diverse opzioni per creare l'area di lavoro. Per le migliori prestazioni, crea l'area di lavoro in un'area di Azure geograficamente più vicina al tuo ambiente Customer Insights.

1. Accedi all'area di lavoro tramite [Azure Machine Learning Studio](https://ml.azure.com/). Esistono vari [modi di interagire](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) con l'area di lavoro.

## <a name="work-with-azure-machine-learning-designer"></a>Utilizzare la finestra di progettazione di Azure Machine Learning

La progettazione di Azure Machine Learning offre un'area di disegno visiva in cui è possibile trascinare e rilasciare set di dati e moduli. Una pipeline batch creata mediante la finestra di progettazione può essere integrata in Customer Insights se configurata di conseguenza. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Utilizzare l'SDK di Azure Machine Learning

I data scientist e gli sviluppatori di intelligenza artificiale utilizzano l'[SDK di Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) per creare flussi di lavoro di apprendimento automatico. Attualmente, i modelli il cui training è stato eseguito con l'SDK non possono essere integrati direttamente con Customer Insights. Una pipeline di inferenza batch che utilizza quel modello è necessaria per l'integrazione di Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Requisiti della pipeline batch per l'integrazione con Customer Insights

### <a name="dataset-configuration"></a>Configurazione di set di dati

Per utilizzare dati di entità di Customer Insights nella pipeline di inferenza batch devi creare set di dati. Questi set di dati devono essere registrati nell'area di lavoro. Al momento, supportiamo solo [set di dati tabulari](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in formato .csv. I set di dati che corrispondono a dati di entità devono essere parametrizzati come parametro della pipeline.
   
* Parametri del set di dati nella finestra di progettazione
   
     Nella finestra di progettazione, apri **Seleziona colonne in set di dati** e seleziona **Imposta come parametro di pipeline** dove fornisci un nome per il parametro.

     > [!div class="mx-imgBorder"]
     > ![Parametrizzazione del set di dati nella finestra di progettazione.](media/intelligence-designer-dataset-parameters.png "Parametrizzazione del set di dati nella finestra di progettazione")
   
* Parametro del set di dati nell'SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Pipeline di inferenza batch
  
* Nella finestra di progettazione, puoi utilizzare una pipeline di training per creare o aggiornare una pipeline di inferenza. Attualmente, sono supportate solo le pipeline di inferenza batch.

* Con l'SDK, puoi pubblicare la pipeline su un endpoint. Attualmente Customer Insights si integra con la pipeline predefinita in un endpoint di pipeline batch nell'area di lavoro di Machine Learning.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importare i dati della pipeline in Customer Insights

* La finestra di progettazione fornisce il [modulo Esporta dati](/azure/machine-learning/algorithm-module-reference/export-data) che consente di esportare l'output di una pipeline nell'archiviazione di Azure. Attualmente, il modulo deve utilizzare il tipo di archivio dati **Archivio BLOB di Azure** e parametrizzare l'**Archivio dati** e il relativo **Percorso**. Customer Insights sovrascrive entrambi questi parametri durante l'esecuzione della pipeline con un datastore e un percorso accessibile al prodotto.
   > [!div class="mx-imgBorder"]
   > ![Configurazione del modulo Esporta dati.](media/intelligence-designer-importdata.png "Configurazione del modulo Esporta dati")
   
* Quando scrivi l'output di inferenza utilizzando codice, puoi caricare l'output nel percorso in un *archivio dati registrato* nell'area di lavoro. Se il percorso e l'archivio dati sono parametrizzati nella pipeline, Customer Insights sarà in grado di leggere e importare l'output di inferenza. Attualmente è supportato un singolo output tabulare in formato csv. Il percorso deve includere la directory e il nome di file.

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]