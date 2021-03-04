---
title: Modelli di Machine Learning personalizzati | Microsoft Docs
description: Utilizzare modelli personalizzati da Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267239"
---
# <a name="custom-machine-learning-models"></a>Modelli di Machine Learning personalizzati

**Intelligenza** > **Modelli personalizzati** consente di gestire flussi di lavoro basati sui modelli di Azure Machine Learning. I flussi di lavoro ti consentono di scegliere i dati mediante i quali generare informazioni dettagliate e di mappare i risultati ai dati cliente unificati. Per ulteriori informazioni sulla creazione di modelli di Machine Learning personalizzati, vedi [Utilizzare i modelli basati su Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsabile

Le previsioni offrono funzionalità per creare migliori esperienze cliente nonché migliorare le capacità aziendali e i flussi di ricavi. Ti consigliamo vivamente di equilibrare il valore della previsione rispetto all'impatto che ha e alle tendenze che possono essere introdotte in modo etico. Ulteriori informazioni su come Microsoft [assicura una IA responsabile](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Puoi anche ottenere informazioni su [tecniche e processi per un machine learning responsabile](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifico per Azure Machine Learning.

## <a name="prerequisites"></a>Prerequisiti

- Attualmente, questa funzionalità supporta i servizi Web pubblicati tramite [Machine Learning Studio (versione classica)](https://studio.azureml.net) e le [pipeline batch di Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Devi disporre di un account di archiviazione di Azure Data Lake Gen2 associato all'istanza di Azure Studio per usare questa funzionalità. Per altre informazioni, vedi [Creare un account di archiviazione di Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Aggiungere un nuovo flusso di lavoro

1. Vai a **Intelligenza** > **Modelli personalizzati** e seleziona **Nuovo flusso di lavoro**.

1. Assegna al tuo modello personalizzato un nome riconoscibile nel campo **Nome**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot del riquadro Nuovo flusso di lavoro](media/new-workflowv2.png "Screenshot del riquadro Nuovo flusso di lavoro")

1. Seleziona l'organizzazione che contiene il servizio Web in **Tenant che contiene il servizio Web**.

1. Se l'abbonamento di Azure Machine Learning si trova in un tenant diverso da Customer Insights, seleziona **Accedi** con le tue credenziali per l'organizzazione selezionata.

1. Seleziona le **Aree di lavoro** associate al tuo servizio web. Sono elencate due sezioni, una per Azure Machine Learning v1 (Machine Learning Studio (versione classica)) e Azure Machine Learning v2 (Azure Machine Learning). Se non sei sicuro qual è l'area di lavoro appropriata per il servizio web Machine Learning Studio (versione classica), seleziona **Qualsiasi**.

1. Scegli il servizio Web Machine Learning Studio (versione classica) o la pipeline Azure Machine Learning nell'elenco a discesa **Servizio Web che contiene il modello**. Quindi seleziona **Avanti**.
   - Leggi gli articoli sulla [pubblicazione di un servizio web in Machine Learning Studio (versione classica)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Leggi gli articoli sulla [pubblicazione di una pipeline in Azure Machine Learning utilizzando la finestra di progettazione](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) o [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). La tua pipeline deve essere pubblicata in un [endpoint di pipeline](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Per ogni **Input servizio Web**, seleziona l'**Entità** corrispondente di Audience Insights e seleziona **Avanti**.
   > [!NOTE]
   > Il flusso di lavoro del modello personalizzato applicherà l'euristica per mappare i campi di input del servizio Web agli attributi dell'entità in base al nome e al tipo di dati del campo. Verrà visualizzato un errore se un campo del servizio Web non può essere mappato a un'entità.

   > [!div class="mx-imgBorder"]
   > ![Configurare un flusso di lavoro](media/intelligence-screen2-updated.png "Configurare un flusso di lavoro")
   
1. Nel passaggio **Parametri di output del modello**, imposta le seguenti proprietà:
   - Machine Learning Studio (versione classica)
      1. Immetti il **Nome dell'entità** di output in cui desideri inserire i risultati di output del servizio Web.
   - Azure Machine Learning
      1. Immetti il **Nome dell'entità** di output in cui desideri inserire i risultati di output della pipeline.
      1. Seleziona il **Nome parametro archivio dati di output** della pipeline batch dal menu a discesa.
      1. Seleziona il **Nome parametro percorso di output** della pipeline batch dal menu a discesa.
      
      > [!div class="mx-imgBorder"]
      > ![Riquadro dei parametri di output del modello](media/intelligence-screen3-outputparameters.png "Riquadro dei parametri di output del modello")

1. Seleziona l'attributo corrispondente nell'elenco a discesa **ID cliente nei risultati** che identifica i clienti e seleziona **Salva**.
   
   > [!div class="mx-imgBorder"]
   > ![Riquadro Correla risultati ai dati del cliente](media/intelligence-screen4-relatetocustomer.png "Riquadro Correla risultati ai dati del cliente")

1. Vedrai la schermata **Flusso di lavoro salvato** con dettagli sul flusso di lavoro.    
   Se hai configurato un flusso di lavoro per una pipeline di Azure Machine Learning, Audience Insights assocerà l'area di lavoro che contiene la pipeline. Audience insights otterrà un ruolo **Collaboratore** nell'area di lavoro di Azure.

1. Seleziona **Fatto**.

1. Ora puoi eseguire il flusso di lavoro nella pagina **Modelli personalizzati**.

## <a name="edit-a-workflow"></a>Modificare un flusso di lavoro

1. Nella pagina **Modelli personalizzati**, seleziona i puntini di sospensione verticali nella colonna **Azioni** accanto a un flusso di lavoro precedentemente creato e seleziona **Modifica**.

1. Puoi aggiornare il nome riconoscibile del flusso di lavoro nel campo **Nome visualizzato**, ma non puoi modificare il servizio Web o la pipeline configurato. Seleziona **Avanti**.

1. Per ogni **Input servizio Web**, puoi aggiornare l'**Entità** corrispondente di Audience Insights. Quindi seleziona **Avanti**.

1. Nel passaggio **Parametri di output del modello**, imposta le seguenti proprietà:
   - Machine Learning Studio (versione classica)
      1. Immetti il **Nome dell'entità** di output in cui desideri inserire i risultati di output del servizio Web.
   - Azure Machine Learning
      1. Immetti il **Nome dell'entità** di output in cui desideri inserire i risultati di output della pipeline.
      1. Seleziona **Nome parametro archivio dati di output** per la pipeline di test.
      1. Seleziona il **Nome parametro percorso di output** per la pipeline di test.

1. Seleziona l'attributo corrispondente nell'elenco a discesa **ID cliente nei risultati** che identifica i clienti e seleziona **Salva**.
   Devi scegliere un attributo nell'output di inferenza con valori simili alla colonna ID cliente dell'entità Cliente. Se non hai una colonna di questo tipo nel tuo set di dati, scegli un attributo che identifichi in modo univoco la riga.

## <a name="run-a-workflow"></a>Eseguire un flusso di lavoro

1. Nella pagina **Modelli personalizzati**, seleziona i puntini di sospensione verticali nella colonna **Azioni** accanto a un flusso di lavoro precedentemente creato.

1. Seleziona **Esegui**.

Il flusso di lavoro viene inoltre eseguito automaticamente con ogni aggiornamento pianificato. Altre informazioni sulla [configurazione degli aggiornamenti pianificati](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Eliminare un flusso di lavoro

1. Nella pagina **Modelli personalizzati**, seleziona i puntini di sospensione verticali nella colonna **Azioni** accanto a un flusso di lavoro precedentemente creato.

1. Seleziona **Elimina** e conferma l'operazione.

Il flusso di lavoro verrà eliminato. L'[entità](entities.md) creata durante la creazione del flusso di lavoro verrà conservata e può essere visualizzata dalla pagina **Entità**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]