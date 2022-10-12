---
title: Modelli di Machine Learning personalizzati | Microsoft Docs
description: Utilizzare modelli personalizzati da Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609751"
---
# <a name="custom-machine-learning-models"></a>Modelli di Machine Learning personalizzati

> [!NOTE]
> Il supporto per Machine Learning Studio (classico) terminerà il 31 agosto 2024. Ti consigliamo di passare ad [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) entro quella data.
>
> A partire dal 1° dicembre 2021, non sarai in grado di creare nuove risorse di Machine Learning Studio (classico). Fino al 31 agosto 2024, puoi continuare a utilizzare le risorse Machine Learning Studio (classic) esistenti. Per maggiori informazioni, vedi [Migrazione ad Azure Machine Learning](/azure/machine-learning/migrate-overview).

I modelli personalizzati consentono di gestire i flussi di lavoro basati sui modelli Azure Machine Learning. I flussi di lavoro ti consentono di scegliere i dati mediante i quali generare informazioni dettagliate e di mappare i risultati ai dati cliente unificati. Per ulteriori informazioni sulla creazione di modelli di Machine Learning personalizzati, vedi [Utilizzare i modelli basati su Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Prerequisiti

- Servizi Web pubblicati tramite [Pipeline batch di Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).
- La pipeline deve essere pubblicata in un [endpoint di pipeline](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Un [account di archiviazione di Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) associato all'istanza di Azure Studio.
- Per le aree di lavoro di Azure Machine Learning con pipeline, le autorizzazioni di accesso proprietario o utente amministratore per l'area di lavoro di Azure Machine Learning.

  > [!NOTE]
  > I dati vengono trasferiti tra le istanze di Customer Insights e i servizi Web o le pipeline di Azure selezionati nel flusso di lavoro. Quando trasferisci i dati a un servizio di Azure, assicurati che il servizio sia configurato per elaborare i dati nel modo e nel percorso necessari per soddisfare tutti i requisiti legali o normativi relativi a tali dati per la tua organizzazione.

## <a name="add-a-new-workflow"></a>Aggiungere un nuovo flusso di lavoro

1. Vai a **Intelligence** > **Modelli personalizzati** e seleziona **Nuovo flusso di lavoro**.

1. Fornire un **Nome** riconoscibile.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Screenshot del riquadro Nuovo flusso di lavoro.":::

1. Seleziona l'organizzazione che contiene il servizio Web in **Tenant che contiene il servizio Web**.

1. Se l'abbonamento di Azure Machine Learning si trova in un tenant diverso da Customer Insights, seleziona **Accedi** con le tue credenziali per l'organizzazione selezionata.

1. Seleziona le **Aree di lavoro** associate al tuo servizio web.

1. Scegli la pipeline Azure Machine Learning nel menu a discesa **Servizio Web che contiene il tuo modello**. Quindi seleziona **Avanti**.
   Leggi gli articoli sulla [pubblicazione di una pipeline in Azure Machine Learning utilizzando la finestra di progettazione](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) o [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Per ciascun valore in **Input servizio Web**, seleziona l'**Entità** corrispondente da Customer Insights. Quindi seleziona **Avanti**.
   > [!NOTE]
   > Il flusso di lavoro del modello personalizzato applicherà l'euristica per mappare i campi di input del servizio Web agli attributi dell'entità in base al nome e al tipo di dati del campo. Verrà visualizzato un errore se un campo del servizio Web non può essere mappato a un'entità.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Configurare un flusso di lavoro.":::

1. Per **Parametri del modello di output**, imposta le seguenti proprietà:
   - **Nome entità** per i risultati di output della pipeline
   - **Nome parametro archivio dati di output** della pipeline batch
   - **Nome parametro percorso di output** della pipeline batch

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Riquadro dei parametri di output del modello.":::

1. Seleziona l'attributo corrispondente da **ID cliente nei risultati** che identifica i clienti e seleziona **Salva**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Riquadro Correla risultati ai dati del cliente.":::

   Viene visualizzata la schermata **Flusso di lavoro salvato** con dettagli sul flusso di lavoro. Se hai configurato un flusso di lavoro per una pipeline di Azure Machine Learning, Customer Insights si collega all'area di lavoro che contiene la pipeline. Customer Insights riceverà un ruolo **Collaboratore** nell'area di lavoro di Azure.

1. Seleziona **Fatto**. Viene visualizzata la pagina **Modelli personalizzati**.

1. Seleziona i puntini di sospensione verticali (&vellip;) per il flusso di lavoro, quindi scegli **Esegui**. Il flusso di lavoro viene inoltre eseguito automaticamente con ogni [aggiornamento pianificato](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Gestire un flusso di lavoro esistente

Vai a **Intelligence** > **Modelli personalizzati** per visualizzare i flussi di lavoro creati.

Seleziona un flusso di lavoro per visualizzare le azioni disponibili.

- **Modificare** un flusso di lavoro
- **Eseguire** un flusso di lavoro
- [**Eliminare**](#delete-a-workflow) un flusso di lavoro

### <a name="edit-a-workflow"></a>Modificare un flusso di lavoro

1. Vai a **Intelligence** > **Modelli personalizzati**.

1. Accanto al flusso di lavoro che desideri aggiornare, seleziona i puntini di sospensione verticali (&vellip;) e seleziona **Modifica**.

1. Modifica il **Nome visualizzato** se necessario e seleziona **Avanti**.

1. Per ciascun valore in **Input servizio Web**, aggiorna l'**Entità** corrispondente da Customer Insights, se necessario. Quindi seleziona **Avanti**.

1. Per **Parametri del modello di output**, modifica quanto segue:
   - **Nome entità** per i risultati di output della pipeline
   - **Nome parametro archivio dati di output** della pipeline batch
   - **Nome parametro percorso di output** della pipeline batch

1. Modifica l'attributo corrispondente dall'elenco a discesa **ID cliente nei risultati** per identificare i clienti. Scegli un attributo nell'output di inferenza con valori simili alla colonna ID cliente dell'entità Cliente. Se non hai una colonna di questo tipo nel tuo set di dati, scegli un attributo che identifichi in modo univoco la riga.

1. Seleziona **Salva**

### <a name="delete-a-workflow"></a>Eliminare un flusso di lavoro

1. Vai a **Intelligence** > **Modelli personalizzati**.

1. Accanto al flusso di lavoro che desideri eliminare, seleziona i puntini di sospensione verticali (&vellip;) e seleziona **Elimina**.

1. Conferma l'eliminazione.

Il flusso di lavoro verrà eliminato. L'[entità](entities.md) creata durante la creazione del flusso di lavoro verrà conservata e può essere visualizzata dalla pagina **Dati** > **Entità**.

## <a name="view-the-results"></a>Visualizzare i risultati

I risultati di un flusso di lavoro vengono archiviati nel nome dell'entità definita per **Parametri di output del modello**. Accedi a questi dati dalla [pagina **Dati** > **Entità**](entities.md) o mediante l'[accesso API](apis.md).

### <a name="api-access"></a>Accesso API

Per la query OData specifica per ottenere dati da un'entità modello personalizzata, utilizza il formato seguente:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Sostituisci `<your instance id>` con l'ID del tuo ambiente Customer Insights, visualizzato nella barra degli indirizzi del tuo browser quando accedi a Customer Insights.

1. Sostituisci `<custom model output entity>` con il nome dell'entità specificato per **Parametri di output del modello**.

1. Sostituisci `<guid value>` con l'IDdel cliente al quale desideri accedere. L'ID viene visualizzato nella [pagina dei profili dei clientni](customer-profiles.md) nel campo CustomerID.

## <a name="frequently-asked-questions"></a>Domande frequenti

- Perché non riesco a vedere la mia pipeline durante l'impostazione di un flusso di lavoro del modello personalizzato?
  Questo problema è spesso causato da un problema di configurazione nella pipeline. Assicurati che il [parametro di input sia configurato](azure-machine-learning-experiments.md#dataset-configuration) e che anche [il datastore e parametri di percorso di output](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) siano configurati.

- Cosa indica l'errore "Impossibile salvare il flusso di lavoro di intelligence"? 
  Gli utenti di solito visualizzano questo messaggio di errore se non dispongono dei privilegi di accesso proprietario o utente amministratore nell'area di lavoro. L'utente necessita di un livello più elevato di autorizzazioni per consentire a Customer Insights di elaborare il flusso di lavoro come un servizio anziché utilizzare le credenziali dell'utente per le successive esecuzioni del flusso di lavoro.

- È supportato un collegamento privato/endpoint privato per il flusso di lavoro del mio modello personalizzato?
  Customer Insights attualmente non supporta l'endpoint privato per i modelli personalizzati predefiniti, ma è disponibile una soluzione manuale. Contatta il supporto per conoscere i dettagli.

## <a name="responsible-ai"></a>IA responsabile

Le previsioni offrono funzionalità per creare migliori esperienze cliente nonché migliorare le capacità aziendali e i flussi di ricavi. Ti consigliamo vivamente di equilibrare il valore della previsione rispetto all'impatto che ha e alle tendenze che possono essere introdotte in modo etico. Ulteriori informazioni su come Microsoft [assicura una IA responsabile](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Puoi anche ottenere informazioni su [tecniche e processi per un machine learning responsabile](/azure/machine-learning/concept-responsible-ml) specifico per Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
