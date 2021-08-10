---
title: Modelli di Machine Learning personalizzati | Microsoft Docs
description: Utilizzare modelli personalizzati da Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 72ccb2d86c698939d0ff018b4d36203e793df9ae
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554853"
---
# <a name="custom-machine-learning-models"></a>Modelli di Machine Learning personalizzati

**Intelligenza** > **Modelli personalizzati** consente di gestire flussi di lavoro basati sui modelli di Azure Machine Learning. I flussi di lavoro ti consentono di scegliere i dati mediante i quali generare informazioni dettagliate e di mappare i risultati ai dati cliente unificati. Per ulteriori informazioni sulla creazione di modelli di Machine Learning personalizzati, vedi [Utilizzare i modelli basati su Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsabile

Le previsioni offrono funzionalità per creare migliori esperienze cliente nonché migliorare le capacità aziendali e i flussi di ricavi. Ti consigliamo vivamente di equilibrare il valore della previsione rispetto all'impatto che ha e alle tendenze che possono essere introdotte in modo etico. Ulteriori informazioni su come Microsoft [assicura una IA responsabile](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Puoi anche ottenere informazioni su [tecniche e processi per un machine learning responsabile](/azure/machine-learning/concept-responsible-ml) specifico per Azure Machine Learning.

## <a name="prerequisites"></a>Prerequisiti

- Attualmente, questa funzionalità supporta i servizi Web pubblicati tramite [Machine Learning Studio (versione classica)](https://studio.azureml.net) e le [pipeline batch di Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).

- Devi disporre di un account di archiviazione di Azure Data Lake Gen2 associato all'istanza di Azure Studio per usare questa funzionalità. Per altre informazioni, vedi [Creare un account di archiviazione di Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Per le aree di lavoro di Azure Machine Learning con pipeline, sono necessarie le autorizzazioni di accesso proprietario o utente amministratore per l'area di lavoro di Azure Machine Learning.

   > [!NOTE]
   > I dati vengono trasferiti tra le istanze di Customer Insights e i servizi Web o le pipeline di Azure selezionati nel flusso di lavoro. Quando trasferisci i dati a un servizio di Azure, assicurati che il servizio sia configurato per elaborare i dati nel modo e nel percorso necessari per soddisfare tutti i requisiti legali o normativi relativi a tali dati per la tua organizzazione.

## <a name="add-a-new-workflow"></a>Aggiungere un nuovo flusso di lavoro

1. Vai a **Intelligenza** > **Modelli personalizzati** e seleziona **Nuovo flusso di lavoro**.

1. Assegna al tuo modello personalizzato un nome riconoscibile nel campo **Nome**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot del riquadro Nuovo flusso di lavoro.](media/new-workflowv2.png "Screenshot del riquadro Nuovo flusso di lavoro")

1. Seleziona l'organizzazione che contiene il servizio Web in **Tenant che contiene il servizio Web**.

1. Se l'abbonamento di Azure Machine Learning si trova in un tenant diverso da Customer Insights, seleziona **Accedi** con le tue credenziali per l'organizzazione selezionata.

1. Seleziona le **Aree di lavoro** associate al tuo servizio web. Sono elencate due sezioni, una per Azure Machine Learning v1 (Machine Learning Studio (versione classica)) e Azure Machine Learning v2 (Azure Machine Learning). Se non sei sicuro qual è l'area di lavoro appropriata per il servizio web Machine Learning Studio (versione classica), seleziona **Qualsiasi**.

1. Scegli il servizio Web Machine Learning Studio (versione classica) o la pipeline Azure Machine Learning nell'elenco a discesa **Servizio Web che contiene il modello**. Quindi seleziona **Avanti**.
   - Leggi gli articoli sulla [pubblicazione di un servizio web in Machine Learning Studio (versione classica)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Leggi gli articoli sulla [pubblicazione di una pipeline in Azure Machine Learning utilizzando la finestra di progettazione](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) o [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). La tua pipeline deve essere pubblicata in un [endpoint di pipeline](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Per ogni **Input servizio Web**, seleziona l'**Entità** corrispondente di Audience Insights e seleziona **Avanti**.
   > [!NOTE]
   > Il flusso di lavoro del modello personalizzato applicherà l'euristica per mappare i campi di input del servizio Web agli attributi dell'entità in base al nome e al tipo di dati del campo. Verrà visualizzato un errore se un campo del servizio Web non può essere mappato a un'entità.

   > [!div class="mx-imgBorder"]
   > ![Configurare un flusso di lavoro.](media/intelligence-screen2-updated.png "Configurare un flusso di lavoro")

1. Nel passaggio **Parametri di output del modello**, imposta le seguenti proprietà:
   - Machine Learning Studio (versione classica)
      1. Immetti il **Nome dell'entità** di output in cui desideri inserire i risultati di output del servizio Web.
   - Azure Machine Learning
      1. Immetti il **Nome dell'entità** di output in cui desideri inserire i risultati di output della pipeline.
      1. Seleziona il **Nome parametro archivio dati di output** della pipeline batch dal menu a discesa.
      1. Seleziona il **Nome parametro percorso di output** della pipeline batch dal menu a discesa.

      > [!div class="mx-imgBorder"]
      > ![Riquadro dei parametri di output del modello.](media/intelligence-screen3-outputparameters.png "Riquadro dei parametri di output del modello")

1. Seleziona l'attributo corrispondente dall'elenco a discesa **ID cliente nei risultati** che identifica i clienti e seleziona **Salva**.

   > [!div class="mx-imgBorder"]
   > ![Riquadro Correla risultati ai dati del cliente.](media/intelligence-screen4-relatetocustomer.png "Riquadro Correla risultati ai dati del cliente")

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

1. Seleziona l'attributo corrispondente dall'elenco a discesa **ID cliente nei risultati** che identifica i clienti e seleziona **Salva**.
   Scegli un attributo nell'output di inferenza con valori simili alla colonna ID cliente dell'entità Cliente. Se non hai una colonna di questo tipo nel tuo set di dati, scegli un attributo che identifichi in modo univoco la riga.

## <a name="run-a-workflow"></a>Eseguire un flusso di lavoro

1. Nella pagina **Modelli personalizzati**, seleziona i puntini di sospensione verticali nella colonna **Azioni** accanto a un flusso di lavoro precedentemente creato.

1. Seleziona **Esegui**.

Il flusso di lavoro viene inoltre eseguito automaticamente con ogni aggiornamento pianificato. Altre informazioni sulla [configurazione degli aggiornamenti pianificati](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Eliminare un flusso di lavoro

1. Nella pagina **Modelli personalizzati**, seleziona i puntini di sospensione verticali nella colonna **Azioni** accanto a un flusso di lavoro precedentemente creato.

1. Seleziona **Elimina** e conferma l'operazione.

Il flusso di lavoro verrà eliminato. L'[entità](entities.md) creata durante la creazione del flusso di lavoro verrà conservata e può essere visualizzata dalla pagina **Entità**.

## <a name="results"></a>Risultati

I risultati di un flusso di lavoro vengono archiviati nell'entità configurata durante la fase del parametro di output del modello. Puoi accedere a questi dati dalla [pagina delle entità](entities.md) o con [l'accesso API](apis.md).

### <a name="api-access"></a>Accesso API

Per la query OData specifica per ottenere dati da un'entità modello personalizzata, utilizza il formato seguente:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Sostituisci `<your instance id>` con l'ID del tuo ambiente Customer Insights, che trovi nella barra degli indirizzi del tuo browser quando accedi a Customer Insights.

1. Sostituisci `<custom model output entity>` con il nome dell'entità fornito durante la fase Parametri di output del modello della configurazione del modello personalizzato.

1. Sostituisci `<guid value>` con l'IDdel cliente per il quale desideri accedere al record. Di solito puoi trovare questo ID nella [pagina dei profili dei clienti](customer-profiles.md) nel campo CustomerID.

## <a name="frequently-asked-questions"></a>Domande frequenti

- Perché non riesco a vedere la mia pipeline durante l'impostazione di un flusso di lavoro del modello personalizzato?    
  Questo problema è spesso causato da un problema di configurazione nella pipeline. Assicurati che il [parametro di input sia configurato](azure-machine-learning-experiments.md#dataset-configuration) e che anche [il datastore e parametri di percorso di output](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) siano configurati.

- Cosa indica l'errore "Impossibile salvare il flusso di lavoro di intelligence"?    
  Gli utenti di solito visualizzano questo messaggio di errore se non dispongono dei privilegi di accesso proprietario o utente amministratore nell'area di lavoro. L'utente necessita di un livello più elevato di autorizzazioni per consentire a Customer Insights di elaborare il flusso di lavoro come un servizio anziché utilizzare le credenziali dell'utente per le successive esecuzioni del flusso di lavoro.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
