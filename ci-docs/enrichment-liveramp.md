---
title: Arricchisci i profili dei clienti con i dati di identità di LiveRamp (anteprima)
description: Arricchisci i profili dei clienti con i dati LiveRamp.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237817"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Arricchisci i profili dei clienti con i dati di identità di LiveRamp (anteprima)

LiveRamp fornisce la risoluzione deterministica dell'identità offline e il consolidamento dei dati dei clienti. Puoi mappare gli identificatori personali nei dati dei clienti sul grafico dell'identità AbiliTec e ricevere ID AbiliTec. Puoi quindi utilizzare questi ID per una migliore unificazione dei dati dei clienti.

## <a name="supported-countriesregions"></a>Paesi/aree geografiche supportati

Attualmente supportiamo l'arricchimento dei profili dei clienti con i dati LiveRamp solo negli Stati Uniti.

## <a name="prerequisites"></a>Prerequisiti

- Un abbonamento di LiveRamp attivo. Per ottenere un abbonamento, contatta il team del tuo account LiveRamp o all'indirizzo [dynamics@liveramp.com](mailto:dynamics@liveramp.com) per maggiori informazioni.

- Un abbonamento AbiliTec attivo con ID client e segreto per accedere all'API. Per ulteriori informazioni, vedi [Hub per sviluppatori API AbiliTec](https://developers.liveramp.com/abilitec-api/).

- Una [connessione](connections.md) LiveRamp [configurata](#configure-the-connection-for-liveramp) da un amministratore.

## <a name="configure-the-connection-for-liveramp"></a>Configurare la connessione per LiveRamp

Devi essere un [amministratore](permissions.md#admin) in Customer Insights e avere un ID client LiveRamp attivo e un segreto.

1. Seleziona **Aggiungi connessione** durante la configurazione di un arricchimento o vai ad **Amministratore** > **Connessioni** e seleziona **Impostazione** nel riquadro LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Riquadro di configurazione per impostare la connessione al servizio LiveRamp AbiliTec. ":::

1. Immetti un nome per la connessione e un ID client LiveRamp valido e un segreto.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione e quindi seleziona **Salva**.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** sul riquadro **Identità** di LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Riquadro identità nella pagina della panoramica dell'arricchimento. ":::

1. Esamina la panoramica e quindi seleziona **Avanti**.

1. Seleziona la connessione. Contatta un amministratore se non è disponibile alcuna connessione.

1. Selezionare **Avanti**.

1. Seleziona **Set di dati cliente** e scegli il profilo o il segmento che vuoi arricchire con i dati di identità di LiveRamp. L'entità *Cliente* arricchisce tutti i tuoi profili cliente se un segmento arricchisce solo i profili cliente contenuti in quel segmento.

1. Definisci il tipo di campi per i tuoi profili unificati da usare per i dati di identità corrispondenti di LiveRamp. Almeno uno dei campi **Nome e indirizzo**, **E-mail** o **Telefono** è obbligatorio. Per una maggiore accuratezza di corrispondenza, aggiungi altri campi. Selezionare **Avanti**.

1. Mappa i tuoi campi ai dati di identificazione di LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opzioni di mapping dei dati per l'arricchimento di LiveRamp.":::

1. Seleziona **Avanti** per completare il mapping del campo.

1. Specifica un **Nome** per l'arricchimento e il **Nome entità di output**.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

1. Seleziona **Esegui** per avviare il processo di arricchimento o chiudere per tornare alla pagina **Arricchimenti**.

## <a name="view-enrichment-results"></a>Visualizzare i risultati dell'arricchimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Il campo **Numero di clienti arricchiti per campo** fornisce un'analisi dettagliata della copertura di ciascun campo arricchito.

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Usa gli ID AbiliTec per consolidare i profili dei clienti in una vista basata sulla persona.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
