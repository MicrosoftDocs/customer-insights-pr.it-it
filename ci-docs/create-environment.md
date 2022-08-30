---
title: Crea un nuovo ambiente
description: Passaggi per creare ambienti in Dynamics 365 Customer Insights.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304249"
---
# <a name="create-a-new-environment"></a>Crea un nuovo ambiente

Dopo [aver acquistato una licenza in abbonamento per Dynamics 365 Customer Insights](paid-license.md), l'amministratore globale del tenant Microsoft 365 riceve un'e-mail che lo invita a creare l'ambiente. Vai a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) per iniziare. In questo scenario, inizia con [Passaggio 1: fornire informazioni di base](#step-1-provide-basic-information).

Dopo aver creato il primo ambiente, l'amministratore globale del tenant Microsoft 365 può [aggiungere utenti dall'organizzazione come amministratori](permissions.md). Questi amministratori possono gestire utenti e ambienti. Se la tua organizzazione acquista più di una licenza per Customer Insights, [contatta il team di supporto](https://go.microsoft.com/fwlink/?linkid=2079641) per aumentare il numero di ambienti disponibili. Per ulteriori informazioni sulla capacità e sulla capacità aggiuntiva, consulta la [Guida alle licenze di Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Una volta che hai la possibilità di creare ambienti aggiuntivi, vai ad [Avviare il processo di creazione dell'ambiente ](#start-the-environment-creation-process).

> [!TIP]
> Se vuoi provare il servizio, vedi [Configurare un ambiente di prova](trial-signup.md).

## <a name="prerequisites"></a>Prerequisiti

[Autorizzazioni di amministratore](permissions.md) in Customer Insights

## <a name="start-the-environment-creation-process"></a>Avviare il processo di creazione dell'ambiente

1. Apri il selettore ambiente e seleziona **+ Nuovo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleziona il selezionatore di ambienti.":::

1. Segui l'esperienza guidata descritta nelle sezioni seguenti per fornire tutte le informazioni necessarie per un nuovo ambiente.

## <a name="step-1-provide-basic-information"></a>Passaggio 1: fornire informazioni di base

1. Scegli se vuoi creare un ambiente da zero o copiare i dati da un altro ambiente. La [copia di dati da un altro ambiente](#copy-the-environment-configuration) richiede passaggi aggiuntivi.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Finestra di dialogo per creare un nuovo ambiente Customer Insights.":::

1. Fornisci i seguenti dettagli:

   - **Nome**: il nome per questo ambiente. Questo campo è già compilato se hai copiato da un ambiente esistente, ma è possibile modificarlo.
   - **Scegli la tua attività**: i destinatari primari per il nuovo ambiente: singoli consumatori (B2C) o [account aziendali](work-with-business-accounts.md) (B2B). Se la tua organizzazione fa affari principalmente con individui, come un rivenditore o una caffetteria, scegli i singoli consumatori. Se il gruppo di destinatari principale è costituito da altre società, come una casa automobilistica o una società di carta, scegli gli account aziendali.
   - **Tipo**: Tipo di ambiente: produzione o sandbox. Gli ambienti sandbox non consentono l'aggiornamento pianificato dei dati e sono destinati alla pre-implementazione e al test. Gli ambienti sandbox usano lo stesso pubblico primario dell'ambiente di produzione attualmente selezionato.
   - **Area geografica**: l'area geografica in cui il servizio viene distribuito e ospitato. Per [usare il tuo account Azure Data Lake Storage](own-data-lake-storage.md) o [connetterti a un'organizzazione Microsoft Dataverse esistente](customer-insights-dataverse.md), l'ambiente Customer Insights deve trovarsi nella stessa area geografica.

1. Selezionare **Avanti**.

## <a name="step-2-configure-data-storage"></a>Passo 2: Configurare l'archiviazione dei dati

1. Scegli dove memorizzare i dati Customer Insights:

   - **Archiviazione di Customer Insights**: l'archiviazione dei dati viene gestita automaticamente. È l'opzione predefinita e, a meno che non vi siano requisiti specifici per archiviare i dati nel tuo account di archiviazione, ti consigliamo di utilizzare questa opzione.
   - **Azure Data Lake Storage**: specifica il tuo account Azure Data Lake Storage per archiviare i dati in modo da avere il pieno controllo su dove vengono archiviati i dati. Segui i passaggi in [Usa il tuo account Azure Data Lake Storage](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Scegli l'opzione preferita per memorizzare i tuoi dati.":::

1. Selezionare **Avanti**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Passo 3: Collegarsi a Microsoft Dataverse

Se disponi di un ambiente Dataverse, connettiti a Customer Insights. Condividi i dati con Dataverse per utilizzarli con applicazioni aziendali basate su Dataverse, come Dynamics 365 Marketing o applicazioni basate su modello in Power Apps.

1. Segui i passaggi in [Lavora con i dati di Customer Insights in Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="condivisione dei dati con Microsoft Dataverse abilitata automaticamente per nuovi ambienti.":::

1. Selezionare **Avanti**.

## <a name="step-4-finalize-the-settings"></a>Passo 4: Finalizzare le impostazioni

Verifica le impostazioni specificate. Quando tutto sembra completo, seleziona **Crea** per impostare l'ambiente.

Per modificare alcune impostazioni in un secondo momento, vedi [Gestisci ambienti](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Lavora con il tuo nuovo ambiente

Vedi gli articoli seguenti per iniziare a configurare Customer Insights:

- [Aggiungi più utenti e assegna i autorizzazioni](permissions.md).
- [Inserisci le tue origini dati](data-sources.md) ed eseguile attraverso il [processo di unificazione dei dati](data-unification.md) per ottenere i [profili dei clienti unificati](customer-profiles.md).
- [Arricchisci i profili dei clienti unificati](enrichment-hub.md) o [esegui modelli predittivi](predictions-overview.md).
- [Creare segmenti](segments.md) per raggruppare clienti e [misure](measures.md) per esaminare gli indicatori KPI.
- Impostate[connessioni](connections.md) ed [esportazioni](export-destinations.md) per elaborare sottoinsiemi dei vostri dati in altre applicazioni.

## <a name="copy-the-environment-configuration"></a>Copia la configurazione dell'ambiente

In qualità di amministratore, se hai scelto di copiare la configurazione da un ambiente esistente, seleziona dall'elenco tutti gli ambienti disponibili nella tua organizzazione.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Screenshot delle opzioni di impostazione nelle impostazioni dell'ambiente.":::

Le impostazioni di configurazione seguenti vengono copiate:

- Origini dati importate tramite Power Query
- Configurazione dell'unificazione dei dati
- Segments
- Misure
- Relazioni
- Attività
- Indicizzazione di ricerca e filtro
- Esportazioni
- Aggiorna pianificazione
- Arricchimenti
- Modelli di previsione
- Assegnazioni di ruolo

### <a name="set-up-a-copied-environment"></a>Impostazione di un ambiente copiato

Quando copi la configurazione di un ambiente, viene visualizzato un messaggio di conferma quando l'ambiente copiato è stato creato. Esegui i seguenti passaggi per confermare le credenziali.

1. Seleziona **Vai a origini dati** per visualizzare l'elenco delle origini dati. Tutte le origini dati mostrano uno stato **Credenziali obbligatorie**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Elenco delle origini dati che sono state copiate e richiedono l'autenticazione.":::

1. Modifica le origini dati e inserisci le credenziali per aggiornarle. Le origini dati dalla cartella Common Data Model e Dataverse devono essere create manualmente con lo stesso nome dell'ambiente di origine.

1. Dopo aver aggiornato le origini dati, vai a **Dati** > **Unifica**. Qui troverai le impostazioni dall'ambiente di origine. Modificale in base alle necessità o seleziona **Unifica** > **Unifica profili cliente e dipendenze** per avviare il processo di unificazione dei dati e crea l'entità cliente unificata.

   > [!TIP]
   > Per account e contatti, seleziona **Unifica account** > **Unifica profili e dipendenze**.

1. Quando l'unificazione dei dati è completa, vai a **Misura** e **Segmenti** per aggiornarli.

1. Vai ad **Amministratore** > **Connessioni** per autenticare nuovamente le connessioni nel nuovo ambiente.

1. Vai a **Dati** > **Arricchimento** e **Dati** > **Esportazioni** per riattivarle.

[!INCLUDE [footer-include](includes/footer-banner.md)]
