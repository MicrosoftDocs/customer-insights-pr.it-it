---
title: Come creare un nuovo ambiente
description: Passaggi per creare ambienti in Dynamics 365 Customer Insights.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 62969527ceed906ff06fb9be90b972496323ce0a
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052750"
---
# <a name="how-to-create-a-new-environment"></a>Come creare un nuovo ambiente

Dopo [aver acquistato una licenza in abbonamento per Dynamics 365 Customer Insights](paid-license.md), l'amministratore globale del tenant Microsoft 365 riceve un'e-mail che lo invita a creare l'ambiente. Vai a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) per iniziare. In questo scenario, puoi andare direttamente al [Passaggio 1: fornire informazioni di base](#step-1-provide-basic-information).

Dopo aver creato il primo ambiente, l'amministratore globale del tenant Microsoft 365 può [aggiungere utenti dall'organizzazione come amministratori](permissions.md). Andando avanti, questi amministratori possono gestire utenti e ambienti. Se la tua organizzazione acquista più di una licenza per Customer Insights, [contatta il team di supporto](https://go.microsoft.com/fwlink/?linkid=2079641) per aumentare il numero di ambienti disponibili. Per ulteriori informazioni sulla capacità e sulla capacità aggiuntiva, consulta la [Guida alle licenze di Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Se vuoi provare il servizio, vedi [Configurare un ambiente di prova](trial-signup.md).

## <a name="prerequisites"></a>Prerequisiti

Hai bisogno delle [autorizzazioni di amministratore](permissions.md) in Customer Insights per creare o gestire ambienti.

## <a name="start-the-environment-creation-process"></a>Avviare il processo di creazione dell'ambiente

1. Apri il selettore ambiente e seleziona **+ Nuovo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleziona il selezionatore di ambienti.":::

1. Segui l'esperienza guidata descritta nelle sezioni seguenti per fornire tutte le informazioni necessarie per un nuovo ambiente. Se hai configurato un ambiente in precedenza, puoi anche fare una [copia della configurazione](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Passaggio 1: fornire informazioni di base

Nel passo **Informazioni di base** , scegli se vuoi creare un ambiente da zero o [copiare i dati da un altro ambiente](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Finestra di dialogo per creare un nuovo ambiente Customer Insights.":::

Fornisci i seguenti dettagli:

- **Nome**: il nome dell'ambiente. Questo campo è già compilato se hai copiato da un ambiente esistente, ma è possibile modificarlo.
- **Scegli la tua attività**: scegli il gruppo di destinatari principale per il nuovo ambiente. Puoi scegliere consumatori singoli (B2C) oppure [account aziendali](work-with-business-accounts.md) (B2B). Se la tua organizzazione fa affari principalmente con individui, come un rivenditore o una caffetteria, scegli i singoli consumatori. Nel caso in cui il tuo gruppo di destinatari principale sia costituito da altre società, come una casa automobilistica o una società di carta, scegli gli account aziendali.
- **Tipo**: scegli se vuoi creare un ambiente di produzione o sandbox. Gli ambienti sandbox non consentono l'aggiornamento pianificato dei dati e sono destinati alla pre-implementazione e al test. Gli ambienti sandbox usano lo stesso pubblico primario dell'ambiente di produzione attualmente selezionato.
- **Area geografica**: l'area geografica in cui il servizio viene distribuito e ospitato. Per [usare il tuo account Azure Data Lake Storage](own-data-lake-storage.md) o [connetterti a un'organizzazione Microsoft Dataverse esistente](customer-insights-dataverse.md), l'ambiente Customer Insights deve trovarsi nella stessa area geografica.

## <a name="step-2-configure-data-storage"></a>Passo 2: Configurare l'archiviazione dei dati

Nel passaggio **Archivio dati** scegli dove archiviare i dati di Customer Insights.

È possibile scegliere fra due opzioni:

- **Archiviazione di Customer Insights**: l'archiviazione dei dati viene gestita dal team di Customer Insights. È l'opzione predefinita e, a meno che non vi siano requisiti specifici per archiviare i dati nel tuo account di archiviazione, ti consigliamo di utilizzare questa opzione.
- **Azure Data Lake Storage**: Specifica il tuo account Azure Data Lake Storage per archiviare i dati in modo da avere il pieno controllo su dove vengono archiviati i dati. Per altre informazioni, vedi [Usare l'account Azure Data Lake Storage](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Scegli l'opzione preferita per memorizzare i tuoi dati.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Passo 3: Collegarsi a Microsoft Dataverse

Il passo **Microsoft Dataverse** permette di collegare Customer Insights con il vostro ambiente Dataverse. Condividi i dati con Dataverse per utilizzarli con applicazioni aziendali basate su Dataverse, come Dynamics 365 Marketing o applicazioni basate su modello in Power Apps.


Lascia vuoto questo campo se non hai un tuo ambiente Dataverse e te ne creeremo uno.

Per altre informazioni, consulta [Utilizzare i dati di Customer Insights in Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="condivisione dei dati con Microsoft Dataverse abilitata automaticamente per nuovi ambienti.":::

### <a name="step-4-finalize-the-settings"></a>Passo 4: Finalizzare le impostazioni

Nel passaggio **Revisione** esamina tutte le impostazioni specificate. Quando tutto sembra completo, seleziona **Crea** per impostare l'ambiente.

È possibile modificare alcune impostazioni in un secondo momento. Per ulteriori informazioni, vedere [Gestire ambienti](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Lavora con il tuo nuovo ambiente

Vedi gli articoli seguenti per iniziare a configurare Customer Insights:

- [Aggiungi più utenti e assegna i autorizzazioni](permissions.md).
- [Inserisci le tue origini dati](data-sources.md) ed eseguile attraverso il [processo di unificazione dei dati](data-unification.md) per ottenere i [profili dei clienti unificati](customer-profiles.md).
- [Arricchisci i profili dei clienti unificati](enrichment-hub.md) o [esegui modelli predittivi](predictions-overview.md).
- [Creare segmenti](segments.md) per raggruppare clienti e [misure](measures.md) per esaminare gli indicatori KPI.
- Impostate[connessioni](connections.md) ed [esportazioni](export-destinations.md) per elaborare sottoinsiemi dei vostri dati in altre applicazioni.

## <a name="copy-the-environment-configuration"></a>Copia la configurazione dell'ambiente

In qualità di amministratore, puoi scegliere di copiare la configurazione da un ambiente esistente quando ne crei uno nuovo.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Screenshot delle opzioni di impostazione nelle impostazioni dell'ambiente.":::

Vedrai un elenco di tutti gli ambienti disponibili nella tua organizzazione da cui puoi copiare i dati.

Le impostazioni di configurazione seguenti vengono copiate:

- Origini dati importate tramite Power Query
- Configurazione dell'unificazione dei dati
- Segments
- Misure
- Relazioni
- Attività
- Indicizzazione ricerca e filtro
- Esportazioni
- Aggiorna pianificazione
- Arricchimenti
- Modelli di previsione
- Assegnazioni di ruolo

## <a name="set-up-a-copied-environment"></a>Impostazione di un ambiente copiato

Quando copi la configurazione dell'ambiente, devi eseguire alcuni passaggi aggiuntivi per confermare le credenziali:

- Profili cliente. Innanzitutto, autentica e importa le tue origini dati ed esegui l'unificazione dei dati per ricreare i profili dei clienti.
- Credenziali origine dati. Devi fornire le credenziali per ogni origine dati per autenticare e aggiornare manualmente le origini dati.
- Origini dati dalla cartella Common Data Model e da Dataverse. È necessario creare manualmente tali origini dati con lo stesso nome dell'ambiente di origine.
- Segreti di connessione utilizzati per le esportazioni e gli arricchimenti. Devi riautenticare le connessioni e poi riattivare gli arricchimenti e le esportazioni.

Verrà visualizzato un messaggio di conferma quando l'ambiente copiato è stato creato. Seleziona **Vai a origini dati** per visualizzare l'elenco delle origini dati.

Tutte le origini dati mostreranno uno stato **Credenziali obbligatorie**. Modifica le origini dati e inserisci le credenziali per aggiornarle.

:::image type="content" source="media/data-sources-copied.png" alt-text="Elenco delle origini dati che sono state copiate e richiedono l'autenticazione.":::

Dopo aver aggiornato le origini dati, vai a **Dati** > **Unifica**. Qui troverai le impostazioni dall'ambiente di origine. Modificale in base alle necessità o seleziona **Esegui** per avviare il processo di unificazione dei dati e creare l'entità cliente unificata.

Quando l'unificazione dei dati è completa, vai a **Misure** e **Segmenti** per aggiornarli.

Prima di riattivare esportazioni e arricchimenti, vai a **Amministratore** > **Connessioni** per riautenticare le connessioni nel nuovo ambiente.

[!INCLUDE [footer-include](includes/footer-banner.md)]
