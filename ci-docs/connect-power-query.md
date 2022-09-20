---
title: Connessione a un'origine dati Power Query (video)
description: Inserisci i dati tramite un connettore Power Query (video).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6a25e332bafab414c9def4e1e6b461139dd24ea6
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463270"
---
# <a name="connect-to-a-power-query-data-source"></a>Connessione a un'origine dati Power Query

Power Query offre un'ampia serie di connettori per l'inserimento dei dati. La maggior parte di questi connettori è supportata da Dynamics 365 Customer Insights.

L'aggiunta di origini dati basate sui connettori Power Query generalmente segue i passaggi descritti in questa sezione. Tuttavia, a seconda del connettore utilizzato, sono necessarie informazioni diverse. Per saperne di più, vedi la documentazione sui singoli connettori nel [Riferimento del connettore Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crea una nuova origine dati

1. Vai a **Dati** > **Origini dati**.

1. Seleziona **Aggiungi origine dati**.

1. Selezionare **Microsoft Power Query**.

1. Specifica un **Nome** e una **Descrizione** opzionale per l'origine dati e seleziona **Avanti**.

1. Scegli uno dei [connettori disponibili](#available-power-query-data-sources). In questo esempio, selezioniamo il connettore **Testo/CSV**.

1. Immetti i dettagli richiesti in **Impostazioni di connessione** per il connettore selezionato e seleziona **Avanti** per visualizzare un'anteprima dei dati.

1. Seleziona **Trasforma dati**.

1. La finestra di dialogo **Power Query - Modifica query** consente di rivedere e perfezionare i dati. Le entità identificate dai sistemi nell'origine dati selezionata vengono visualizzate nel riquadro di sinistra.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Finestra di dialogo Modifica query":::

1. Puoi anche trasformare i dati. Seleziona un'entità da modificare o trasformare. Usa le opzioni nella finestra Power Query per applicare le trasformazioni. Ogni trasformazione è elencata in **Passaggi applicati**. Power Query fornisce numerose opzioni di [trasformazione predefinite](/power-query/power-query-what-is-power-query#transformations).

   Si consiglia di utilizzare le seguenti trasformazioni:

   - Se stai inserendo dati da un file CSV, la prima riga spesso contiene intestazioni. Vai a **Trasforma**, quindi seleziona **Usa la prima riga come intestazione**.
   - Assicurati che il tipo di dati sia impostato in modo appropriato. Ad esempio, per i campi data, seleziona un tipo di data.

1. Per aggiungere ulteriori entità all'origine dati nella finestra **Modifica query** vai a **Home** e seleziona **Ottieni dati**. Ripeti i passaggi da 5 a 10 finché non avrai aggiunto tutte le entità per questa origine dati. Se disponi di un database che include più set di dati, ogni set di dati è la propria entità.

1. Seleziona **Salva**. Verrà aperta la pagina **Origine dati** che mostra la nuova origine dati con stato **Aggiornamento in corso**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Il caricamento dei dati può richiedere tempo. Al termine dell'aggiornamento, i dati inseriti possono essere esaminati nella pagina [**Entità**](entities.md).

> [!CAUTION]
>
> - Un'origine dati basata su Power Query crea un [flusso di dati in Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Non modificare il nome di un flusso di dati utilizzato in Customer Insights nell'interfaccia di amministrazione di Power Platform. La ridenominazione di un flusso di dati causa problemi con i riferimenti tra l'origine dati di Customer Insights e il flusso di dati di Dataverse.
> - Valutazioni simultanee per origini dati Power Query in Customer Insights hanno gli stessi [limiti di aggiornamento dei Flussi di dati in PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Se un aggiornamento dei dati non riesce perché ha raggiunto il limite di valutazione, ti consigliamo di modificare la pianificazione dell'aggiornamento per ogni flusso di dati per garantire che le origini dati non vengano elaborate contemporaneamente.

### <a name="available-power-query-data-sources"></a>Origini dati di Power Query disponibili

Vedi il [Riferimento del connettore Power Query](/power-query/connectors/) per un elenco di connettori che è possibile utilizzare per importare dati in Customer Insights.

I connettori con un segno di spunta nella colonna **Informazioni dettagliate sui clienti (flussi di dati)** sono disponibili per creare nuove origini dati basate su Power Query. Esamina la documentazione di un connettore specifico per saperne di più sui suoi prerequisiti, sulle [limitazioni della query](/power-query/power-query-online-limits) e altri dettagli.

## <a name="add-data-from-on-premises-data-sources"></a>Aggiungere dati dalle origini dati locale

L'inserimento di dati da origini dati locali è supportata in base ai flussi di dati Microsoft Power Platform (PPDF). Puoi abilitare i flussi di dati in Customer Insights [fornendo l'URL dell'ambiente Microsoft Dataverse](create-environment.md) quando configuri l'ambiente.

Le origini dati che vengono create dopo aver associato un ambiente Dataverse con Customer Insights usano [flussi di dati Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) per impostazione predefinita. I flussi di dati supportano la connettività locale utilizzando il gateway di dati. Puoi rimuovere e ricreare origini dati che esistevano prima dell'associazione dell'ambiente Dataverse [utilizzando i gateway dati locali](/data-integration/gateway/service-gateway-app).

Il gateway dati da un ambiente Power BI o Power Apps esistente sarà visibile e potrai riutilizzarlo in Customer Insights se il gateway dati e l'ambiente Customer Insights si trovano nella stessa regione di Azure. La pagina delle origini dati mostra i collegamenti per andare all'ambiente Microsoft Power Platform in cui è possibile visualizzare e configurare i gateway dati locale.

> [!IMPORTANT]
> Assicurati che i gateway siano aggiornati all'ultima versione. È possibile installare un aggiornamento e riconfigurare un gateway direttamente da un prompt visualizzato sullo schermo del gateway oppure [scaricare l'ultima versione](https://powerapps.microsoft.com/downloads/). Se non si utilizza l'ultima versione del gateway, l'aggiornamento del flusso di dati non viene eseguito e viene visualizzato un messaggio di errore come **La parola chiave non è supportata: proprietà di configurazione. Nome parametro: parola chiave**.
>
> Gli errori con gateway dati locale in Customer Insights sono spesso causati da problemi di configurazione. Per ulteriori informazioni sulla risoluzione dei problemi con i gateway dati, vedi [Risolvere i problemi del gateway dati locale](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Modifica origine dati Power Query

> [!NOTE]
> Potrebbe non essere possibile apportare modifiche alle origini dati attualmente utilizzate in uno dei processi dell'app (ad esempio, segmentazione o unificazione dei dati).
>
> Nella pagina **Impostazioni**, puoi tener traccia dell'avanzamento di ciascuno dei processi attivi. Al termine di un processo, puoi tornare alla pagina **Origine dei dati** e apportare le tue modifiche.

1. Vai a **Dati** > **Origini dati**.

1. Accanto all'origine dati che desideri aggiornare, seleziona **Modifica**.

1. Applica le modifiche e le trasformazioni nella finestra di dialogo **Power Query - Modifica query** come descritto in [Creare una nuova origine dati](#create-a-new-data-source) sezione.

1. Seleziona **Salva** per applicare le modifiche e tornare alla pagina **Origine dati**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
