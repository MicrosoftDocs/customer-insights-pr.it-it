---
title: Arricchimento dei dati di identità LiveRamp
description: Arricchisci i profili dei clienti con i dati LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373024"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Arricchisci i profili dei clienti con i dati di identità di LiveRamp (Anteprima) 

LiveRamp fornisce la risoluzione deterministica dell'identità offline e il consolidamento dei dati dei clienti. Puoi mappare gli identificatori personali nei dati dei clienti sul grafico dell'identità AbiliTec e ricevere ID AbiliTec. Puoi quindi utilizzare questi ID per una migliore unificazione dei dati dei clienti. 

## <a name="prerequisites"></a>Prerequisiti 

Per configurare l'arricchimento, devono essere rispettati i seguenti requisiti: 

- Un abbonamento di LiveRamp attivo. Per ottenere un abbonamento, contatta il team del tuo account LiveRamp o all'indirizzo [dynamics@liveramp.com](mailto:dynamics@liveramp.com) per maggiori informazioni.   

- Un abbonamento AbiliTec attivo con ID client e segreto per accedere all'API. Per ulteriori informazioni, vedi [Hub per sviluppatori API AbiliTec](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Paesi/aree geografiche supportati 

Attualmente supportiamo l'arricchimento dei profili dei clienti con i dati LiveRamp solo negli Stati Uniti. 

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento 

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**. 

1. Seleziona **Arricchisci i miei dati** sul riquadro **Identità**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Riquadro identità nella pagina della panoramica dell'arricchimento. ":::

1. Seleziona una [connessione](connections.md) dall'elenco a discesa. Contatta un amministratore se non è disponibile alcuna connessione. Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione**. Scegli **LiveRamp** dall'elenco a discesa. 

1. Seleziona **Avanti** e scegli il **Set di dati cliente** che vuoi arricchire con i dati di identità di LiveRamp. Puoi selezionare l'entità *Cliente* per arricchire tutti i tuoi profili cliente o selezionare un'entità *segmento* per arricchire solo i profili cliente contenuti in quel segmento. 

1. Seleziona **Avanti** e definisci quale tipo di campi dei tuoi profili unificati devono essere utilizzati per cercare i dati di identità corrispondenti di LiveRamp. Almeno uno dei campi **Nome e indirizzo**, **Telefono**, o **E-mail** è obbligatorio. 

   > [!TIP]
   > Maggiore è il numero di identificatori chiave e campi mappati, maggiore è la probabilità di ottenere corrispondenze migliori 

1. Mappa i campi dall'entità *Cliente* unificata che verrà utilizzata per la corrispondenza con il grafico ID AbiliTec di LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opzioni di mapping dei dati per l'arricchimento di LiveRamp.":::

1. Seleziona **Avanti** per completare il mapping del campo. 

1. Fornisci un **nome** per l'arricchimento e l' **entità di output**. 

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte. 

## <a name="configure-the-connection-for-liveramp"></a>Configurare la connessione per LiveRamp 

Devi essere un amministratore per [configurare le connessioni](connections.md). Seleziona **Aggiungi connessione** durante la configurazione dell'arricchimento o vai ad **Amministratore** > **Connessioni** e seleziona **Impostazione** nel riquadro **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Riquadro di configurazione per impostare la connessione al servizio LiveRamp AbiliTec. ":::

1. Per **nome visualizzato**, immetti il nome della connessione. 

1. Fornisci un ID client LiveRamp valido e un segreto. 

1. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**. 

1. Seleziona **Verifica** per convalidare la configurazione. 

1. Seleziona **Salva** per completare la connessione. 

## <a name="enrichment-results"></a>Risultati dell'arricchimento 

Per avviare il processo di arricchimento, seleziona Esegui dalla barra dei comandi. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un  [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipende dalle dimensioni dei dati del cliente. 

Al termine del processo di arricchimento, puoi rivedere i dati dei profili dei clienti appena arricchiti in  **I miei arricchimenti**. Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti. 

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando  **Visualizza dati arricchiti**. 

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Usa gli ID AbiliTec per consolidare i profili dei clienti in una vista basata sulla persona. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati 

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a LiveRamp, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati su tua istruzione, ma sei tenuto a garantire che LiveRamp soddisfi qualsiasi obbligo di privacy o sicurezza che potresti avere. Per ulteriori informazioni leggi l'[informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
