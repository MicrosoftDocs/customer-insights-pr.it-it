---
title: Creare ambienti in Customer Insights
description: Passi per creare ambienti con un abbonamento con licenza per Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0efda9d2997bcfd069b6d2445b69d159d7d3e59b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646619"
---
# <a name="create-an-environment-in-customer-insights"></a>Creare un ambiente in Customer Insights

Questo articolo spiega come creare un nuovo ambiente dopo che la tua organizzazione ha acquistato un abbonamento Dynamics 365 Customer Insights. 

Le organizzazioni possono creare più ambienti per ogni licenza di Customer Insights. Se la tua organizzazione acquista più di una licenza, [contatta il nostro team di supporto](https://go.microsoft.com/fwlink/?linkid=2079641) per aumentare il numero di ambienti disponibili. Per ulteriori informazioni sulla capacità e sulla capacità aggiuntiva, consulta la [Guida alle licenze di Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Se vuoi provare il servizio, vedi [Configurare un ambiente di prova](trial-signup.md).

## <a name="create-a-new-environment"></a>Crea un nuovo ambiente

Dopo aver acquistato una licenza in abbonamento per Customer Insights, l'amministratore globale del tenant Microsoft 365 riceve un'e-mail che lo invita a creare l'ambiente. Vai a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) per iniziare. 

Un'esperienza guidata ti aiuta attraverso i passi per raccogliere tutte le informazioni necessarie per un nuovo ambiente. Hai bisogno delle [autorizzazioni di amministratore](permissions.md) in Customer Insights per creare o gestire ambienti.

1. Apri il selettore ambiente e seleziona **+ Nuovo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleziona il selezionatore di ambienti.":::

1. Segui l'esperienza guidata delineata nelle sezioni seguenti.

### <a name="step-1-provide-environment-information"></a>Passo 1: Fornire informazioni sull'ambiente

Nel passo **Informazioni di base** , scegli se vuoi creare un ambiente da zero o [copiare i dati da un altro ambiente](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Finestra di dialogo per creare un nuovo ambiente Customer Insights.":::

Fornisci i seguenti dettagli:
   - **Nome**: il nome dell'ambiente. Questo campo è già compilato se hai copiato da un ambiente esistente, ma è possibile modificarlo.
   - **Scegli la tua attività**: scegli il gruppo di destinatari principale per il nuovo ambiente. Puoi scegliere consumatori singoli (B2C) oppure [account aziendali](work-with-business-accounts.md) (B2B).
   - **Tipo**: scegli se vuoi creare un ambiente di produzione o sandbox. Gli ambienti sandbox non consentono l'aggiornamento pianificato dei dati e sono destinati alla pre-implementazione e al test. Gli ambienti sandbox usano lo stesso pubblico primario dell'ambiente di produzione attualmente selezionato.
   - **Area geografica**: l'area geografica in cui il servizio viene distribuito e ospitato.

### <a name="step-2-configure-data-storage"></a>Passo 2: Configurare l'archiviazione dei dati

Nel passaggio **Archivio dati** scegli dove archiviare i dati di Customer Insights.

Avrai due opzioni: **Archiviazione di Customer Insights** (un Azure Data Lake gestito dal team Customer Insights) e **Azure Data Lake Storage** (il tuo Azure Data Lake Storage). Per impostazione predefinita, l'opzione di archiviazione di Customer Insights è selezionata.

:::image type="content" source="media/data-storage-environment.png" alt-text="Scegli Azure Data Lake Storage per memorizzare i tuoi dati.":::

Salvando i dati su Azure Data Lake Storage, l'utente accetta che i dati vengano trasferiti e conservati nella posizione geografica appropriata per quell'account di archiviazione Azure. Questa posizione può essere diversa da quella in cui i dati sono memorizzati in Dynamics 365 Customer Insights. Per saperne di più, visita il [Microsoft Trust Center](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights attualmente supporta quanto segue:
> - Entità ingerite da Power BI flussi di dati che sono memorizzati in un Data Lake gestito da Microsoft Dataverse.  
> - Azure Data Lake Storage dalla stessa regione di Azure che hai selezionato quando hai creato l'ambiente.
> - Gli account Azure Data Lake Storage che sono Gen2 e hanno lo *spazio dei nomi gerarchico* abilitato. Gli account di archiviazione Azure Data Lake Gen1 non sono supportati.

Per l'opzione Azure Data Lake Storage puoi scegliere tra un'opzione basata sulle risorse e un'opzione basata su sottoscrizione per l'autenticazione. Per ulteriori informazioni, vedi [Connessione a un account Azure Data Lake Storage tramite un'entità servizio di Azure](connect-service-principal.md). Un contenitore denominato `customerinsights` deve esistere nell'account di archiviazione.

Quando i processi di sistema come l'ingestione dei dati è completa, il sistema crea le cartelle corrispondenti nell'account di archiviazione che hai specificato. I file di dati e i file *model.json* sono creati e aggiunti alle cartelle in base al nome del processo.

Se si creano più ambienti di Customer Insights e si sceglie di salvare le entità di output da questi ambienti nel proprio account di archiviazione, Customer Insights crea cartelle separate per ogni ambiente con `ci_environmentID` nel contenitore.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Passo 3: Collegarsi a Microsoft Dataverse
   
Il passo **Microsoft Dataverse** permette di collegare Customer Insights con il vostro ambiente Dataverse.

Fornisci l'ambiente Microsoft Dataverse per condividere dati (profili e informazioni dettagliate) con applicazioni aziendali basate su Dataverse, come Dynamics 365 Marketing o applicazioni basate su modello in Power Apps. Lascia vuoto questo campo se non hai un tuo ambiente Dataverse e te ne forniremo uno.

La connessione al tuo ambiente Dataverse ti consente anche di [inserire i dati dalle origini dati locali utilizzando flussi di dati e gateway Power Platform](data-sources.md#add-data-from-on-premises-data-sources). Puoi anche usare i [modelli di previsione predefiniti](predictions-overview.md?tabs=b2c#out-of-box-models) collegando un ambiente Dataverse.

> [!IMPORTANT]
> 1. Customer Insights e Dataverse devono trovarsi nella stessa regione per consentire la condivisione dei dati.
> 1. Devi avere un ruolo globale amministratore nell'ambiente Dataverse. Verifica che questo [ambiente Dataverse sia associato](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinati gruppi di sicurezza e assicurati di essere aggiunto a tali gruppi.
> 1. Nessun ambiente Customer Insights esistente è già associato a questo ambiente Dataverse. Scopri come [rimuovere una connessione esistente in un ambiente Dataverse](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="condivisione dei dati con Microsoft Dataverse abilitata automaticamente per nuove istanze.":::

Per ulteriori informazioni sull'abilitazione della condivisione dei dati con Microsoft Dataverse dall'istanza di Azure Data Lake Storage personalizzata, vedi [Connettersi a Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights non supporta i seguenti scenari di condivisione dei dati:
- Se abiliti la condivisione dei dati con Dataverse, non sarai in grado di [creare valori previsti o mancanti in un'entità](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Passo 4: Finalizzare le impostazioni

Nella fase di **revisione**, esamina tutte le impostazioni specificate. Quando tutto sembra completo, seleziona **Crea** per impostare l'ambiente. 

Potete anche cambiare la maggior parte delle impostazioni in seguito. Per ulteriori informazioni, vedere [Gestire ambienti](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Lavora con il tuo nuovo ambiente

Vedi gli articoli seguenti per iniziare a configurare Customer Insights: 

- [Aggiungi più utenti e assegna i autorizzazioni](permissions.md).
- [Inserisci le tue origini dati](data-sources.md) ed eseguile attraverso il [processo di unificazione dei dati](data-unification.md) per ottenere i [profili dei clienti unificati](customer-profiles.md).
- [Arricchisci i profili dei clienti unificati](enrichment-hub.md) o [esegui modelli predittivi](predictions-overview.md).
- [Creare segmenti](segments.md) per raggruppare clienti e [misure](measures.md) per esaminare gli indicatori KPI.
- Impostate[connessioni](connections.md) ed [esportazioni](export-destinations.md) per elaborare sottoinsiemi dei vostri dati in altre applicazioni.
