---
title: Esperimenti con Azure Machine Learning
description: Utilizzare modelli basati su Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668773"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="9d350-103">Utilizzare modelli basati su Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="9d350-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="9d350-104">I dati unificati in Dynamics 365 Customer Insights sono una fonte per la creazione di modelli di Machine Learning che possono generare ulteriori informazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="9d350-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="9d350-105">Customer Insights si integra con Machine Learning Studio (versione classica) e Azure Machine Learning per l'uso di modelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="9d350-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="9d350-106">Fai riferimento a [Esperimenti con Machine Learning Studio (versione classica)](machine-learning-studio-experiments.md) per esempi di esperimenti basati su Machine Learning Studio (versione classica).</span><span class="sxs-lookup"><span data-stu-id="9d350-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9d350-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9d350-107">Prerequisites</span></span>

- <span data-ttu-id="9d350-108">Accesso a Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9d350-108">Access to Customer Insights</span></span>
- <span data-ttu-id="9d350-109">Abbonamento attivo ad Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d350-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="9d350-110">Profili cliente unificati</span><span class="sxs-lookup"><span data-stu-id="9d350-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="9d350-111">[Esportazione di entità nell'archivio BLOB di Azure](export-azure-blob-storage.md) configurata</span><span class="sxs-lookup"><span data-stu-id="9d350-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="9d350-112">Configurare l'area di lavoro di Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="9d350-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="9d350-113">Vedi [Creare un'area di lavoro di Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) per diverse opzioni per creare l'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d350-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="9d350-114">Per le migliori prestazioni, crea l'area di lavoro in un'area di Azure geograficamente più vicina al tuo ambiente Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9d350-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="9d350-115">Accedi all'area di lavoro tramite [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="9d350-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="9d350-116">Esistono vari [modi di interagire](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) con l'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d350-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="9d350-117">Utilizzare la finestra di progettazione di Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="9d350-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="9d350-118">La finestra di progettazione Azure Machine Learning fornisce un canvas visivo dove puoi trascinare e rilasciare set di dati e moduli, simile a Machine Learning Studio (versione classica).</span><span class="sxs-lookup"><span data-stu-id="9d350-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="9d350-119">Una pipeline batch creata mediante la finestra di progettazione può essere integrata in Customer Insights se configurata di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="9d350-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="9d350-120">Utilizzare l'SDK di Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="9d350-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="9d350-121">I data scientist e gli sviluppatori di intelligenza artificiale utilizzano l'[SDK di Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) per creare flussi di lavoro di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="9d350-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="9d350-122">Attualmente, i modelli il cui training è stato eseguito con l'SDK non possono essere integrati direttamente con Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9d350-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="9d350-123">Una pipeline di inferenza batch che utilizza quel modello è necessaria per l'integrazione di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9d350-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="9d350-124">Requisiti della pipeline batch per l'integrazione con Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9d350-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="9d350-125">Configurazione di set di dati</span><span class="sxs-lookup"><span data-stu-id="9d350-125">Dataset Configuration</span></span>

<span data-ttu-id="9d350-126">Per utilizzare dati di entità di Customer Insights nella pipeline di inferenza batch devi creare set di dati.</span><span class="sxs-lookup"><span data-stu-id="9d350-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="9d350-127">Questi set di dati devono essere registrati nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d350-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="9d350-128">Al momento, supportiamo solo [set di dati tabulari](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in formato .csv.</span><span class="sxs-lookup"><span data-stu-id="9d350-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="9d350-129">I set di dati che corrispondono a dati di entità devono essere parametrizzati come parametro della pipeline.</span><span class="sxs-lookup"><span data-stu-id="9d350-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="9d350-130">Parametri del set di dati nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="9d350-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="9d350-131">Nella finestra di progettazione, apri **Seleziona colonne in set di dati** e seleziona **Imposta come parametro di pipeline** dove fornisci un nome per il parametro.</span><span class="sxs-lookup"><span data-stu-id="9d350-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="9d350-132">![Parametrizzazione del set di dati nella finestra di progettazione](media/intelligence-designer-dataset-parameters.png "Parametrizzazione del set di dati nella finestra di progettazione")</span><span class="sxs-lookup"><span data-stu-id="9d350-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="9d350-133">Parametro del set di dati nell'SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="9d350-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="9d350-134">Pipeline di inferenza batch</span><span class="sxs-lookup"><span data-stu-id="9d350-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="9d350-135">Nella finestra di progettazione, puoi utilizzare una pipeline di training per creare o aggiornare una pipeline di inferenza.</span><span class="sxs-lookup"><span data-stu-id="9d350-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="9d350-136">Attualmente, sono supportate solo le pipeline di inferenza batch.</span><span class="sxs-lookup"><span data-stu-id="9d350-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="9d350-137">Con l'SDK, puoi pubblicare la pipeline su un endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d350-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="9d350-138">Attualmente Customer Insights si integra con la pipeline predefinita in un endpoint di pipeline batch nell'area di lavoro di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="9d350-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="9d350-139">Importare i dati della pipeline in Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9d350-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="9d350-140">La finestra di progettazione fornisce il [modulo Esporta dati](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) che consente di esportare l'output di una pipeline nell'archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="9d350-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="9d350-141">Attualmente, il modulo deve utilizzare il tipo di archivio dati **Archivio BLOB di Azure** e parametrizzare l'**Archivio dati** e il relativo **Percorso**.</span><span class="sxs-lookup"><span data-stu-id="9d350-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="9d350-142">Customer Insights sovrascrive entrambi questi parametri durante l'esecuzione della pipeline con un datastore e un percorso accessibile al prodotto.</span><span class="sxs-lookup"><span data-stu-id="9d350-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d350-143">![Configurazione del modulo Esporta dati](media/intelligence-designer-importdata.png "Configurazione del modulo Esporta dati")</span><span class="sxs-lookup"><span data-stu-id="9d350-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="9d350-144">Quando scrivi l'output di inferenza utilizzando codice, puoi caricare l'output nel percorso in un *archivio dati registrato* nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d350-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="9d350-145">Se il percorso e l'archivio dati sono parametrizzati nella pipeline, Customer Insights sarà in grado di leggere e importare l'output di inferenza.</span><span class="sxs-lookup"><span data-stu-id="9d350-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="9d350-146">Attualmente è supportato un singolo output tabulare in formato csv.</span><span class="sxs-lookup"><span data-stu-id="9d350-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="9d350-147">Il percorso deve includere la directory e il nome di file.</span><span class="sxs-lookup"><span data-stu-id="9d350-147">The path must include the directory and filename.</span></span>

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
