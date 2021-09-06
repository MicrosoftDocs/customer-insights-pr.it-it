---
title: Creare e configurare una licenza a pagamento di Customer Insights
description: Passaggi per ottenere un abbonamento licenziato per Dynamics 365 Customer Insights e configurarlo.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034457"
---
# <a name="get-started-with-a-paid-subscription"></a>Attività iniziali con un abbonamento a pagamento

Questo articolo spiega come creare un nuovo ambiente dopo che la tua organizzazione ha acquistato un abbonamento Dynamics 365 Customer Insights. Se desideri acquistare Customer Insights, le nostre opzioni di contatto sono elencate nel [sito Web di Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Se stai cercando di provare il servizio e le funzionalità, vedi [Configura un ambiente della versione di valutazione](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Creazione di un ambiente in un'organizzazione esistente

Dopo aver acquistato un contratto di licenza sottoscrizione per Customer Insights, l'amministratore globale del tenant di Microsoft 365 riceve un'e-mail che lo invita a creare l'ambiente. Vai a [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) per iniziare. 

Customer Insights non è concesso in licenza per utente, quindi non verrà visualizzato nell'area Licenze. Se stai cercando la licenza nell'interfaccia di amministrazione di Microsoft 365, vai a **I tuoi prodotti**. 

> [!NOTE]
> Le organizzazioni possono creare *due* ambienti per ogni licenza Customer Insights. Se la tua organizzazione acquista più di una licenza, [contatta il nostro team di supporto](https://go.microsoft.com/fwlink/?linkid=2079641) per aumentare il numero di ambienti disponibili. Per ulteriori informazioni sulla capacità e sulla capacità aggiuntiva, scarica la [Guida per le licenze di Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Per creare un ambiente:

1. Nella finestra di dialogo **Crea un ambiente** seleziona **Nuovo ambiente**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Finestra di dialogo per creare un nuovo ambiente Customer Insights.":::

   Ti consigliamo di iniziare a configurare un ambiente da zero. Tuttavia, se sei un amministratore o un membro di un ambiente della versione di valutazione, potresti [copiare i dati da un altro ambiente](manage-environments.md#copy-the-environment-configuration), scegliendo **Copia dall'ambiente esistente**. Vedrai un elenco di tutti gli ambienti disponibili nella tua organizzazione da cui puoi copiare i dati.

1. Fornisci i seguenti dettagli:
   - **Nome**: il nome dell'ambiente. Questo campo è già compilato se hai copiato da un ambiente esistente, ma è possibile modificarlo.
   - **Area geografica**: l'area geografica in cui il servizio viene distribuito e ospitato.
   - **Tipo**: scegli se vuoi creare un ambiente di produzione o sandbox. Gli ambienti sandbox non consentono l'aggiornamento pianificato dei dati e sono destinati alla pre-implementazione e al test.
   
1. È possibile facoltativamente selezionare **Impostazioni avanzate**:

   - **Salva tutti i dati in**: specifica dove vuoi archiviare i dati di output generati da Customer Insights. Avrai due opzioni: **Archiviazione di Customer Insights** (un Azure Data Lake gestito dal team Customer Insights) e **Azure Data Lake Storage** (il tuo Azure Data Lake Storage). Per impostazione predefinita, l'opzione di archiviazione di Customer Insights è selezionata.

     > [!NOTE]
     > Salvando i dati in Azure Data Lake Storage, accetti che i dati vengano trasferiti e archiviati nella posizione geografica appropriata per tale account di archiviazione di Azure, che può essere diversa da quella in cui sono archiviati i dati in Dynamics 365 Customer Insights. [Altre informazioni nel Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > Attualmente le entità inserite da flussi di dati Power BI vengono archiviate nel data lake gestito di Microsoft Dataverse. 
     > 
     > Supportiamo solo account Azure Data Lake Storage della stessa area di Azure selezionata durante la creazione dell'ambiente. 
     > 
     > Supportiamo solo account Azure Data Lake Storage con spazio dei nomi gerarchico abilitato.


   - Per l'opzione Azure Data Lake Storage puoi scegliere tra un'opzione basata sulle risorse e un'opzione basata su sottoscrizione per l'autenticazione. Per ulteriori informazioni, vedi [Connettere Informazioni dettagliate sul gruppo di destinatari a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md). Il nome **Contenitore** non può essere cambiato e sarà `customerinsights`.
   
   - Se vuoi usare [modelli predefiniti](predictions-overview.md#out-of-box-models), configura la condivisione dei dati con Microsoft Dataverse o abilita l'inserimento di dati da origini dati locali, fornisci l'URL dell'ambiente Microsoft Dataverse in **Configura la condivisione dei dati con Microsoft Dataverse e abilita le funzionalità aggiuntive**. Seleziona **Abilita la condivisione dei dati** per condividere i dati di output di Customer Insights con un Data Lake gestito di Microsoft Dataverse.

     > [!NOTE]
     > - Condivisione dei dati con un Data Lake gestito di Microsoft Dataverse non è attualmente supportata quando salvi tutti i dati nel tuo Azure Data Lake Storage.
     > - [La previsione di valori mancanti in un'entità](predictions.md) non è attualmente supportata quando abiliti la condivisione dei dati con il data lake gestito di Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Opzioni di configurazione per abilitare la condivisione dei dati con Microsoft Dataverse.":::

   Al termine dei processi del sistema come l'inserimento dei dati, il sistema crea le cartelle corrispondenti nell'account di archiviazione specificato. I file di dati e i file model.json vengono creati e aggiunti alle cartelle in base al nome del processo.

   Se crei più ambienti di Customer Insights e scegli di salvare le entità di output da quegli ambienti nell'account di archiviazione, verranno create cartelle separate per ogni ambiente con ci_<environmentid> nel contenitore.

1. Seleziona **Crea** per configurare l'ambiente. 

## <a name="configure-an-environment"></a>Configurare un ambiente

Consulta i seguenti articoli per iniziare a configurare Customer Insights. 

- [Aggiungi più utenti e assegna i autorizzazioni](permissions.md).
- [Inserisci le tue origini dati](data-sources.md) ed eseguile attraverso il [processo di unificazione dei dati](data-unification.md) per ottenere i [profili dei clienti unificati](customer-profiles.md).
- [Arricchisci i profili dei clienti unificati](enrichment-hub.md) o [esegui modelli predittivi](predictions-overview.md).
- Crea [segmenti](segments.md) per raggruppare i clienti e [misure](measures.md) per rivedere gli indicatori KPI.
- Imposta le [connessioni](connections.md) e le [esportazioni](export-destinations.md) per elaborare sottoinsiemi di dati in altre applicazioni.
