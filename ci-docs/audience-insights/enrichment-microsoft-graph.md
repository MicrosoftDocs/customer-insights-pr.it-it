---
title: Arricchimento di profili cliente con Microsoft Graph
description: Utilizza i dati proprietari di Microsoft Graph per arricchire i tuoi dati cliente con le affinità relative al marchio e agli interessi.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406104"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Arricchimento di profili cliente con le affinità relative al marchio e agli interessi (anteprima)

Utilizza i dati proprietari di Microsoft Graph per arricchire i tuoi dati cliente con le affinità relative al marchio e agli interessi. Queste affinità sono determinate in base ai dati di persone con dati demografici simili ai tuoi clienti. Queste informazioni ti consentono di comprendere e segmentare meglio i tuoi clienti in base alle loro affinità per specifici marchi e interessi.

In Audience Insights, vai a **Dati** > **Arricchimento** per [configurare e visualizzare gli arricchimenti](enrichment-hub.md).

Per configurare l'arricchimento delle affinità del marchio, vai alla scheda **Individua** e seleziona **Arricchisci i miei dati** nel riquadro **Marchi**.

Per configurare l'arricchimento delle affinità degli interessi, vai alla scheda **Individua** e seleziona **Arricchisci i miei dati** nel riquadro **Interessi**.

   > [!div class="mx-imgBorder"]
   > ![Riquadri Marchi e interessi](media/BrandsInterest-tile-Hub.png "Riquadri Marchi e interessi")

## <a name="about-microsoft-graph"></a>Informazioni su Microsoft Graph

I dati di ricerca online di Microsoft Graph vengono utilizzati per trovare affinità per marchi e interessi in vari segmenti demografici (definiti per età, sesso o posizione). Il volume di ricerca online per un marchio o interesse determina quanta affinità un segmento demografico, rispetto ad altri segmenti, ha con quel marchio o interesse.

[Altre informazioni su Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Punteggio di affinità e fiducia nell'affinità

Il **punteggio di affinità** viene calcolato su una scala di 100 punti, con 100 che rappresenta il segmento con la più alta affinità per un marchio o un interesse.

L'**attendibilità di affinità** viene inoltre calcolata su una scala di 100 punti. Indica il livello di attendibilità del sistema in base al quale un segmento ha un'affinità con il marchio o l'interesse. Il livello di fiducia si basa sulla dimensione del segmento e sulla granularità del segmento. La dimensione del segmento è determinata dalla quantità di dati che abbiamo per un determinato segmento. La granularità del segmento è determinata da quanti attributi (età, sesso, posizione) sono disponibili in un profilo.

I punteggi non vengono normalizzati per il tuo set di dati. Di conseguenza, potresti non vedere tutti i possibili valori del punteggio di affinità per il set di dati. Ad esempio, potrebbe non esserci un profilo cliente arricchito con punteggio di affinità 100 nei dati. Ciò è possibile se non esistono clienti nel segmento demografico a cui è stato assegnato 100 per un determinato marchio o interesse.

> [!TIP]
> Quando si [creano segmenti ](segments.md) utilizzando punteggi di affinità, esamina la distribuzione dei punteggi di affinità per il tuo set di dati prima di decidere le soglie di punteggio appropriate. Ad esempio, un punteggio di affinità pari a 10 può essere considerato significativo in un set di dati il cui punteggio di affinità più elevato è soltanto 25 per un determinato marchio o interesse.

## <a name="supported-countriesregions"></a>Paesi/aree geografiche supportati

Attualmente supportiamo le seguenti opzioni di paese/area geografica: Australia, Canada (inglese), Francia, Germania, Regno Unito o Stati Uniti (inglese).

Per selezionare un paese, apri **Arricchimento marchi** o **Arricchimento interessi** e seleziona **Cambia** accanto a **Paese**. Nel riquadro **Impostazioni paese/area geografica**, scegli un'opzione e seleziona **Applica**.

### <a name="implications-related-to-country-selection"></a>Implicazioni relative alla selezione del paese

- Durante la [scelta dei marchi](#define-your-brands-or-interests), forniremo suggerimenti in base al paese/area geografica selezionato.

- Quando [scegli un settore](#define-your-brands-or-interests), identificheremo i marchi o gli interessi più rilevanti in base al paese o alla regione selezionata.

- Durante il [mapping dei campi](#map-your-fields), se il campo Paese non è mappato, utilizzeremo i dati di Microsoft Graph dal paese/area geografica selezionato per arricchire i profili cliente. Useremo questa selezione anche per arricchire i profili cliente che non dispongono di dati relativi a paesi/aree geografiche.

- Durante l'[arricchimento dei profili](#refresh-enrichment), arricchiremo tutti i profili cliente per i quali disponiamo di dati Microsoft Graph per i marchi e gli interessi selezionati, inclusi i profili che non si trovano nel paese/area geografica selezionato. Ad esempio, se hai selezionato la Germania, arricchiremo i profili situati negli Stati Uniti se disponiamo dei dati di Microsoft Graph per i marchi e gli interessi selezionati negli Stati Uniti.

## <a name="configure-enrichment"></a>Configurare l'arricchimento

La configurazione di arricchimento di marchi o interessi prevede due passaggi:

### <a name="define-your-brands-or-interests"></a>Definisci i tuoi marchi o interessi

Selezionare una delle opzioni seguenti:

- **Settore**: il sistema identifica i principali marchi o interessi rilevanti per il tuo settore e arricchisce i dati cliente con essi.
- **Scegli il tuo**: seleziona fino a cinque voci dall'elenco di marchi o interessi più rilevanti per la tua organizzazione.

Per aggiungere un marchio o un interesse, immettilo nell'area di input per ottenere suggerimenti in base ai termini corrispondenti. Se non viene elencato un marchio o interesse che stai cercando, inviaci un feedback utilizzando il collegamento **Suggerisci**.

### <a name="map-your-fields"></a>Esegui il mapping dei campi

Mappa i campi dall'entità cliente unificata ad almeno due attributi per definire il segmento demografico che desideri venga utilizzato per arricchire i tuoi dati cliente. Seleziona **Modifica** per definire la mappatura dei campi e al termine seleziona **Applica**. Seleziona **Salva** per completare la mappatura dei campi.

Sono supportati i seguenti formati e valori, i valori non fanno distinzione tra maiuscole e minuscole:

- **Data di nascita**: si consiglia di convertire la data di nascita nel tipo DateTime durante l'inserimento dati. In alternativa, può essere una stringa nel formato "aaaa-MM-gg" o "aaaa-MM-ggTHH:mm:ssZ" [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).
- **Sesso**: Maschio, Femmina, Sconosciuto
- **Codice postale**: codici postali a cinque cifre per gli Stati Uniti, codice postale standard per gli altri paesi
- **Città**: nome della città in inglese
- **Stato/Provincia**: abbreviazione di due lettere per gli Stati Uniti e il Canada. Abbreviazione di due o tre lettere per l'Australia. Non applicabile per Francia, Germania o Regno Unito.
- **Paese**:

  - US: Stati Uniti d'America, Stati Uniti, USA, US, America
  - CA: Canada, CA
  - GB: Regno Unito, UK, Gran Bretagna, GB, Regno Unito di Gran Bretagna e Irlanda del Nord, Regno Unito di Gran Bretagna
  - AU: Australia, AU, Commonwealth di Australia
  - FR: Francia, FR, Repubblica francese
  - DE: Germania, tedesco, Deutschland, Allemagne, DE, Repubblica Federale di Germania, Repubblica di Germania

## <a name="refresh-enrichment"></a>Aggiornare l'arricchimento

Esegui l'arricchimento dopo aver configurato marchi, interessi e mappatura dei campi per i dati demografici. Per avviare il processo, seleziona **Esegui** nella pagina di configurazione del marchio o degli interessi. Inoltre, puoi consentire al sistema di eseguire automaticamente l'arricchimento come parte di un aggiornamento pianificato.
A seconda della dimensione dei dati cliente, potrebbero essere necessari alcuni minuti per completare l'esecuzione di un arricchimento.

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Dopo aver eseguito il processo di arricchimento, vai a **I miei arricchimenti** per rivedere il numero totale di clienti arricchiti e una suddivisione di marchi e interessi nei profili cliente arricchiti.

:::image type="content" source="media/my-enrichments.png" alt-text="Anteprima dei risultati dopo l'esecuzione del processo di arricchimento":::

Rivedi i dati arricchiti selezionando **Visualizza dati arricchiti** nel grafico. I dati arricchiti per i marchi vanno all'entità **BrandAffinityFromMicrosoft**. I dati per gli interessi sono nell'entità **InterestAffinityFromMicrosoft**. Troverai anche queste entità elencate nel gruppo **Arricchimento** in **Dati** > **Entità**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Visualizzare i dati di arricchimento nella scheda cliente

Le affinità per marchi e interessi possono essere visualizzate anche nelle singole schede cliente. Vai a **Clienti** e seleziona un profilo cliente. Nella scheda cliente troverai i grafici per i marchi o gli interessi per i quali le persone nel profilo demografico del cliente hanno affinità.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Scheda cliente con dati arricchiti":::

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.
