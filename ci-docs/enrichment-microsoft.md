---
title: Arricchire i profili dei clienti con i dati su marchi e interessi di Microsoft
description: Usa i dati proprietari di Microsoft per arricchire i dati dei tuoi clienti con affinità e share of voice.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953770"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Arricchisci i profili dei clienti con affinità e share of voice (anteprima)

Usa i dati proprietari di Microsoft per arricchire i dati dei tuoi clienti con affinità di marchio, affinità di interessi e share of voice (SoV). Queste affinità e SoV si basano sui dati di persone i cui dati demografici sono simili a quelli dei tuoi clienti. Queste informazioni ti aiutano a comprendere e segmentare meglio i tuoi clienti in base alle loro affinità o SoV a marchi e interessi specifici.

## <a name="how-we-determine-affinities-and-sov"></a>Come determiniamo affinità e SoV

Per trovare affinità e SoV per marchi e interessi in vari segmenti demografici (definiti per età, sesso o posizione), vengono usati i dati delle ricerche online di Microsoft. Il volume delle ricerche online di un marchio o un interesse costituisce la base per determinare l'affinità o SoV. Ognuno offre tuttavia una prospettiva diversa per comprendere i clienti.

- L'affinità è un elemento comparativo tra i segmenti demografici. Puoi usare queste informazioni per identificare i segmenti demografici che hanno la massima affinità per un determinato marchio o interesse, rispetto ad altri segmenti.

- Share of voice è un elemento comparativo tra i marchi o gli interessi selezionati. Puoi usare queste informazioni per identificare quale marchio o interesse ha il valore di share of voice più elevato per un determinato segmento demografico, rispetto ad altri marchi o interessi selezionati.

## <a name="affinity-level-and-score"></a>Livello e punteggio di affinità

Per ogni profilo cliente arricchito forniamo due valori correlati: livello di affinità e punteggio di affinità. Questi valori ti aiutano a determinare quanto sia forte l'affinità per il segmento demografico di quel profilo a un marchio o un interesse, rispetto ad altri segmenti demografici.

Il *livello di affinità* si compone di quattro livelli e il *punteggio di affinità* è calcolato su una scala di 100 punti mappata ai livelli di affinità.

|Livello di affinità |Punteggio di affinità  |
|---------|---------|
|Molto alto     | 85-100       |
|Alta     | 70-84        |
|Medio     | 35-69        |
|Bassa     | 1-34        |

A seconda della granularità che desideri per misurare l'affinità, puoi utilizzare il livello di affinità o il punteggio di affinità. Il punteggio di affinità ti offre un controllo più preciso.

## <a name="share-of-voice-sov"></a>Share of voice (SoV)

Calcoliamo il valore di SoV su una scala di 100 punti. Il SoV totale di tutti i marchi o interessi per ogni profilo cliente arricchito arriva fino a 100. A differenza delle affinità, il valore SoV è relativo ai marchi e agli interessi selezionati. Ad esempio, i valori SoV per "Microsoft" possono essere diversi se i marchi selezionati sono ("Microsoft", "GitHub") piuttosto che ("Microsoft", "LinkedIn").

## <a name="supported-countriesregions"></a>Paesi/aree geografiche supportati

Attualmente supportiamo le seguenti opzioni di paese/area geografica: Australia, Canada (inglese), Francia, Germania, Regno Unito o Stati Uniti (inglese).

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

   - Per configurare le affinità di marchio e l'arricchimento SoV, seleziona **Arricchisci i miei dati** nel riquadro **Marchi**.

   - Per configurare le affinità di interessi e l'arricchimento SoV, seleziona **Arricchisci i miei dati** nel riquadro **Interessi**.

   > [!div class="mx-imgBorder"]
   > ![Riquadri Marchi e Interessi.](media/BrandsInterest-tile-Hub.png "Riquadri Marchi e Interessi")

1. Esamina la panoramica e quindi seleziona **Avanti**.

1. Per cambiare il tuo paese o la tua area geografica, seleziona **Modifica** accanto a **Paese/area geografica**. Nel riquadro **Impostazioni paese/area geografica** scegli un [paese/area geografica supportato](#supported-countriesregions) e seleziona **Applica**.

   > [!NOTE]
   > Quando scegli i tuoi marchi, il sistema fornisce suggerimenti in base al paese o all'area geografica selezionati. Quando scegli un settore, otterrai i marchi o gli interessi più pertinenti in base al paese o all'area geografica selezionati.

1. Scegli fino a cinque marchi o interessi utilizzando una o entrambe queste opzioni:

   - **Settore**: seleziona il tuo settore dall'elenco a discesa, quindi scegli tra i migliori marchi o interessi per quel settore.
   - **Scegli il tuo**: inserisci un marchio o un interesse rilevante per la tua organizzazione, quindi scegli tra i suggerimenti corrispondenti. Se non viene elencato un marchio o interesse che stai cercando, inviaci un feedback utilizzando il collegamento **Suggerisci**.

1. Seleziona **Avanti** e rivedi le tue preferenze di arricchimento predefinite e aggiornale secondo necessità.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Screenshot della finestra delle preferenze di arricchimento.":::

1. Selezionare **Avanti**.

1. Seleziona **Set di dati cliente** e scegli il profilo o il segmento che vuoi arricchire con i dati di Microsoft. L'entità *Cliente* arricchisce tutti i tuoi profili cliente se un segmento arricchisce solo i profili cliente contenuti in quel segmento.

1. Selezionare **Avanti**.

1. Mappa i tuoi campi dall'entità cliente unificata ai dati Microsoft.

   > [!NOTE]
   > Sono richiesti almeno gli attributi Data di nascita o Sesso. Sono richiesti Paese/area geografica e almeno Città (e Provincia) o CAP. Si consiglia di convertire la data di nascita nel tipo DateTime durante l'inserimento dei dati. In alternativa, può essere una stringa in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formato "aaaa-MM-gg" o "aaaa-MM-ggTHH:mm:ss".

1. Seleziona **Avanti** per completare il mapping del campo.

1. Immetti un nome per l'arricchimento. **Nome entità di output** viene selezionato automaticamente.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pagina di revisione e denominazione degli interessi.":::

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

1. Seleziona **Esegui** per avviare il processo di arricchimento o chiudere per tornare alla pagina **Arricchimenti**.

   Arricchendo i profili, arricchiremo tutti i profili dei clienti per i quali otteniamo dati per i marchi e gli interessi selezionati, inclusi i profili che non si trovano nel paese o nell'area geografica selezionata. Ad esempio, se hai selezionato la Germania, arricchiremo i profili situati negli Stati Uniti se abbiamo dati disponibili per i marchi e gli interessi selezionati negli Stati Uniti.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Anteprima dei risultati dopo l'esecuzione del processo di arricchimento.":::

I risultati includono i grafici **Livello di affinità** o **Share of Voice**.

Le entità create dagli arricchimenti sono elencate nel gruppo **Arricchimento** in **Dati** > **Entità**. I dati arricchiti per i marchi vanno nelle entità **BrandAffinityFromMicrosoft** e **BrandShareOfVoiceFromMicrosoft**. I dati per gli interessi sono nelle entità **InterestAffinityFromMicrosoft** e **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Visualizzare i dati di arricchimento nella scheda cliente

Il SoV di marchi e interessi può essere visualizzato anche nelle singole schede cliente. Vai a **Clienti** e seleziona un profilo cliente. Nella scheda cliente sono presenti grafici per il SoV di marchi o interessi in base alle persone nel profilo demografico del cliente.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Scheda cliente con dati arricchiti.":::

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
