---
title: Creare e configurare una versione di valutazione di Customer Insights
description: Passaggi per ottenere un abbonamento della versione di valutazione per Dynamics 365 Customer Insights e configurarlo.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f80654f03252142ce08241ff3ca3606be4595740
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650481"
---
# <a name="set-up-a-trial-environment"></a>Configurazione di un ambiente della versione di valutazione 

Una versione di valutazione di Dynamics 365 Customer Insights consente di rivedere le funzionalità chiave e saperne di più sulle varie funzionalità. Un abbonamento alla versione di valutazione viene eliminato dopo la scadenza. Gli ambienti delle versioni di valutazione vengono creati dai singoli utenti che diventano amministratori del loro ambiente della versione di valutazione. Possono invitare più utenti alla loro versione di valutazione e configurare le varie funzionalità.

## <a name="create-a-trial-environment"></a>Crea un ambiente di valutazione

Puoi registrarti per una versione di valutazione nella [pagina di iscrizione alla versione di valutazione](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Scegli l'opzione **Iscriviti a una versione di prova gratuita** e seleziona **Iscriviti ora**.

1. Fornisci il tuo indirizzo di posta elettronica aziendale o dell'istituto di istruzione, dicci qualcosa in più su di te e seleziona **Attività iniziali**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Finestra di dialogo per iscriversi a una versione di valutazione":::

1. Esaminare le condizioni e selezionare **Continua** per confermare.

1. Fornisci un **nome** per il tuo nuovo ambiente. 

1. Impostare l'ambiente **Tipo** come **valutazione**.

1. Nel campo **Seleziona una demo di settore**, puoi facoltativamente scegliere un set di dati specifico del settore. Puoi anche [passare a una demo di settore](#use-industry-specific-demo-data-sets-in-audience-insights) successivamente e iniziare con il set di dati predefinito.

1. Scegli l'**area** per il tuo ambiente.

1. Facoltativamente, se sei l'amministratore di un'organizzazione Dynamics 365: seleziona **Impostazioni avanzate** e fornisci l'URL della tua organizzazione per utilizzare le funzionalità di previsione come la previsione dell'abbandono dei clienti. 

1. Seleziona **Crea**. 

La configurazione dell'ambiente richiede alcuni minuti. Dopo il completamento, verrai reindirizzato all'ambiente demo o alla demo di settore che hai scelto nel passaggio precedente. Ora puoi esplorare l'app con dati demo di sola lettura. Per aggiungere i tuoi dati all'ambiente, vedi [Crea dati demo specifici dello scenario nel tuo ambiente](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Screenshot di un ambiente della versione di valutazione appena creato.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Usa set di dati demo specifici del settore nelle informazioni dettagliate sul gruppo di destinatari

La connessione di origini dati reali è uno dei passaggi critici per sfruttare al meglio Customer Insights. Per valutazionere le funzionalità senza interferire con i tuoi dati, puoi facoltativamente utilizzare dati demo specifici del settore. Sono disponibili un paio di set di dati demo per i seguenti settori: 

-   Settore automobilistico
-   Banche
-   Beni di consumo
-   Enti pubblici
-   Sanità
-   Settore ospedaliero
-   Assicurazioni
-   Produzione
-   Servizi professionali
-   Vendita al dettaglio

### <a name="see-industry-specific-demo-data-in-trials"></a>Guarda i dati demo specifici del settore nelle versioni di valutazione

Per una versione di sola lettura di Customer Insights, su misura per un settore o uno scenario specifico, inizia utilizzando l'ambiente demo. 
 
1.  Nelle informazioni dettagliate sul gruppo di destinatari, scegli **Demo** nella selezione dell'ambiente.

2.  In **Home**, scegli un'opzione dal menu a discesa Seleziona una demo di settore.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Scegli un settore per l'ambiente delle versioni di valutazione.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Crea dati dimostrativi specifici dello scenario nel tuo ambiente

Come amministratore, scegli la selezione dell'ambiente nell'intestazione dell'app per creare un nuovo ambiente. Nel nuovo ambiente, puoi configurare le tue origini dati e configurare l'app in base alle tue esigenze. 

1.  In Audience Insights, vai a **Dati** > **Origini dati**.

2.  Per importare le tue origini dati, vai alla [guida all'inserimento dati](data-sources.md).     
   Se preferisci lavorare con dati di esempio che ti consentono di provare l'inserimento dati, puoi inserire i dati dimostrativi del settore nel tuo ambiente. Scegli l'opzione **Importa da hub di dati** e segui i passaggi seguenti.

3.  Seleziona la carta del settore che si adatta al tuo scenario. 

4.  Rivedi e facoltativamente aggiorna il nome suggerito dell'origine dati. 

5.  Seleziona **Avanti** per inserire i dati di esempio. 

Ora puoi utilizzare i dati inseriti per adattare Customer Insights al tuo scenario. Per vedere un ambiente specifico per i dati dimostrativi inseriti, scegli l'opzione **Demo di <Industry>** nella selezione dell'ambiente.

## <a name="limitations-in-trials"></a>Limitazioni delle versioni di valutazione

- Le versioni di valutazione sono attive per 30 giorni per impostazione predefinita. Tuttavia, puoi estenderle dopo il 23° giorno quando accedi alla tua versione di valutazione.
- Non puoi utilizzare il tuo account di Azure Data Lake Storage per archiviare i dati di output in una versione di valutazione. Tuttavia, puoi inserire dati da un account di archiviazione di Data Lake.
- Puoi archiviare fino a 3 GB di dati nell'ambiente Dataverse di cui viene eseguito il provisioning automaticamente quando avvii una versione di valutazione di Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Copia i dati da una versione di valutazione a un abbonamento a pagamento

In genere, ti consigliamo di cominciare con i tuoi dati quando esegui l'aggiornamento alla versione a pagamento di Customer Insights. 

Facoltativamente, puoi copiare i tuoi dati da un ambiente della versione di valutazione se acquisti Customer Insights. Devi essere l'amministratore della versione di valutazione di Customer Insights e l'amministratore globale del tuo tenant Microsoft 365 o l'amministratore di Dynamics 365 nella tua organizzazione per migrare le impostazioni da un ambiente della versione di valutazione a un ambiente a pagamento. 

Dopo aver effettuato l'accesso alla tua istanza a pagamento di Customer Insights per la prima volta, ti viene chiesto di creare un nuovo ambiente. In questo processo, puoi scegliere di copiare la configurazione da un ambiente esistente e migrare la maggior parte delle impostazioni. Se disponi delle autorizzazioni sopra menzionate, l'ambiente della versione di valutazione verrà visualizzato in questo elenco. Per ulteriori informazioni, vedi [Copia la configurazione dell'ambiente](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Passaggi successivi

Consulta i seguenti articoli per iniziare a configurare Customer Insights. 

- [Aggiungi più utenti e assegna i autorizzazioni](permissions.md).
- [Inserisci le tue origini dati](data-sources.md) ed eseguile attraverso il [processo di unificazione dei dati](data-unification.md) per ottenere i [profili dei clienti unificati](customer-profiles.md).
- [Arricchisci i profili dei clienti unificati](enrichment-hub.md) o [esegui modelli predittivi](predictions-overview.md).
- Crea [segmenti](segments.md) per raggruppare i clienti e [misure](measures.md) per rivedere gli indicatori KPI.
- Imposta le [connessioni](connections.md) e le [esportazioni](export-destinations.md) per elaborare sottoinsiemi di dati in altre applicazioni.