---
title: Arricchire i profili dei clienti con i dati di Microsoft
description: Usa i dati proprietari di Microsoft per arricchire i dati dei tuoi clienti con affinità di marchio e interesse.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3b10fb23cca03ed918aa7fd46478b568d5ebbf1a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555496"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Arricchimento di profili cliente con le affinità relative al marchio e agli interessi (anteprima)

Usa i dati proprietari di Microsoft per arricchire i dati dei tuoi clienti con affinità di marchio e interesse. Queste affinità si basano sui dati di persone con dati demografici simili a quelli dei tuoi clienti. Queste informazioni ti consentono di comprendere e segmentare meglio i tuoi clienti in base alle loro affinità per specifici marchi e interessi.

In Audience Insights, vai a **Dati** > **Arricchimento** per [configurare e visualizzare gli arricchimenti](enrichment-hub.md).

Per configurare l'arricchimento delle affinità del marchio, vai alla scheda **Individua** e seleziona **Arricchisci i miei dati** nel riquadro **Marchi**.

Per configurare l'arricchimento delle affinità degli interessi, vai alla scheda **Individua** e seleziona **Arricchisci i miei dati** nel riquadro **Interessi**.

   > [!div class="mx-imgBorder"]
   > ![Riquadri Marchi e Interessi.](media/BrandsInterest-tile-Hub.png "Riquadri Marchi e Interessi")

## <a name="how-we-determine-affinities"></a>Come determiniamo le affinità

Utilizziamo i dati della ricerca online di Microsoft per trovare affinità per marchi e interessi in vari segmenti demografici (definiti per età, sesso o posizione). Il volume di ricerca online per un marchio o interesse determina quanta affinità un segmento demografico, rispetto ad altri segmenti, ha con quel marchio o interesse.

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

## <a name="supported-countriesregions"></a>Paesi/aree geografiche supportati

Attualmente supportiamo le seguenti opzioni di paese/area geografica: Australia, Canada (inglese), Francia, Germania, Regno Unito o Stati Uniti (inglese).

Per selezionare un paese o un'area geografica, apri **Arricchimento marchi** o **Arricchimento interessi** e seleziona **Cambia** accanto a **Paese/area geografica**. Nel riquadro **Impostazioni paese/area geografica**, scegli un'opzione e seleziona **Applica**.

### <a name="implications-related-to-country-selection"></a>Implicazioni relative alla selezione del paese

- Quando [scegli i tuoi marchi](#define-your-brands-or-interests), il sistema fornisce suggerimenti in base al paese o all'area geografica selezionati.

- Quando [scegli un settore](#define-your-brands-or-interests), otterrai i marchi o gli interessi più pertinenti in base al paese o all'area geografica selezionati.

- [Arricchendo i profili](#refresh-enrichment), arricchiremo tutti i profili dei clienti per i quali otteniamo dati per i marchi e gli interessi selezionati, inclusi i profili che non si trovano nel paese o nell'area geografica selezionata. Ad esempio, se hai selezionato la Germania, arricchiremo i profili situati negli Stati Uniti se abbiamo dati disponibili per i marchi e gli interessi selezionati negli Stati Uniti.

## <a name="configure-enrichment"></a>Configurazione dell'arricchimento

Un'esperienza guidata ti aiuta nella configurazione degli arricchimenti. 

### <a name="define-your-brands-or-interests"></a>Definisci i tuoi marchi o interessi

Scegli fino a cinque marchi o interessi utilizzando una o entrambe queste opzioni:

- **Settore**: seleziona il tuo settore dall'elenco a discesa, quindi scegli tra i migliori marchi o interessi per quel settore.
- **Scegli il tuo**: inserisci un marchio o un interesse rilevante per la tua organizzazione, quindi scegli tra i suggerimenti corrispondenti. Se non viene elencato un marchio o interesse che stai cercando, inviaci un feedback utilizzando il collegamento **Suggerisci**.

### <a name="review-enrichment-preferences"></a>Rivedere le preferenze di arricchimento

Rivedi le tue preferenze di arricchimento predefinite e aggiornale secondo necessità.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Screenshot della finestra delle preferenze di arricchimento.":::

### <a name="select-entity-to-enrich"></a>Selezionare l'entità da arricchire

Seleziona **Entità arricchita** e scegli il set di dati che desideri arricchire con i dati aziendali di Microsoft. Puoi selezionare l'entità Cliente per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.

### <a name="map-your-fields"></a>Esegui il mapping dei campi

Mappa i campi dall'entità cliente unificata per definire il segmento demografico che desideri venga utilizzato per arricchire i tuoi dati cliente. Mappa Paese/area geografica e almeno gli attributi Data di nascita o Sesso. Inoltre, devi eseguire il mapping di almeno una città (e provincia) o un CAP. Seleziona **Modifica** per definire la mappatura dei campi e al termine seleziona **Applica**. Seleziona **Salva** per completare la mappatura dei campi.

Sono supportati i seguenti formati e valori (i valori non fanno distinzione tra maiuscole e minuscole):

- **Data di nascita**: si consiglia di convertire la data di nascita nel tipo DateTime durante l'inserimento dati. In alternativa, può essere una stringa in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formato "aaaa-MM-gg" o "aaaa-MM-ggTHH:mm:ss".
- **Sesso**: Maschio, Femmina, Sconosciuto.
- **Codice postale**: CAP a cinque cifre per gli Stati Uniti, codice postale standard ovunque.
- **Città**: nome della città in inglese.
- **Stato/Provincia**: abbreviazione di due lettere per gli Stati Uniti e il Canada. Abbreviazione di due o tre lettere per l'Australia. Non applicabile per Francia, Germania o Regno Unito.
- **Paese**:

  - US: Stati Uniti d'America, Stati Uniti, USA, US, America
  - CA: Canada, CA
  - GB: Regno Unito, UK, Gran Bretagna, GB, Regno Unito di Gran Bretagna e Irlanda del Nord, Regno Unito di Gran Bretagna
  - AU: Australia, AU, Commonwealth of Australia
  - FR: Francia, FR, Repubblica francese
  - DE: Germania, tedesco, Deutschland, Allemagne, DE, Repubblica Federale di Germania, Repubblica di Germania

## <a name="review-and-name-the-enrichment"></a>Rivedere e dare un nome all'arricchimento

Infine, puoi rivedere le informazioni e fornire un nome per l'arricchimento.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pagina di revisione e denominazione degli interessi.":::

## <a name="refresh-enrichment"></a>Aggiornare l'arricchimento

Esegui l'arricchimento dopo aver configurato marchi, interessi e mappatura dei campi per i dati demografici. Per avviare il processo, seleziona **Esegui** nella pagina di configurazione del marchio o degli interessi. Inoltre, puoi consentire al sistema di eseguire automaticamente l'arricchimento come parte di un aggiornamento pianificato.

A seconda della dimensione dei dati cliente, potrebbero essere necessari alcuni minuti per completare l'esecuzione di un arricchimento.

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Visualizza dettagli** per una delle attività del lavoro, troverai informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Dopo aver eseguito il processo di arricchimento, vai a **I miei arricchimenti** per rivedere il numero totale di clienti arricchiti e una suddivisione di marchi e interessi nei profili cliente arricchiti.

:::image type="content" source="media/my-enrichments.png" alt-text="Anteprima dei risultati dopo l'esecuzione del processo di arricchimento.":::

Rivedi i dati arricchiti selezionando **Visualizza dati arricchiti** nel grafico. I dati arricchiti per i marchi vanno all'entità **BrandAffinityFromMicrosoft**. I dati per gli interessi sono nell'entità **InterestAffinityFromMicrosoft**. Troverai anche queste entità elencate nel gruppo **Arricchimento** in **Dati** > **Entità**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Visualizzare i dati di arricchimento nella scheda cliente

Le affinità per marchi e interessi possono essere visualizzate anche nelle singole schede cliente. Vai a **Clienti** e seleziona un profilo cliente. Nella scheda cliente troverai i grafici per i marchi o gli interessi per i quali le persone nel profilo demografico del cliente hanno affinità.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Scheda cliente con dati arricchiti.":::

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Crea [segmenti](segments.md) e [misure](measures.md) e persino [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
