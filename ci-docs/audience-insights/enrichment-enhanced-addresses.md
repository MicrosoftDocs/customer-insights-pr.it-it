---
title: Arricchimento migliorato dell'indirizzo
description: Arricchisci e normalizza le informazioni sugli indirizzi dei profili dei clienti con i modelli Microsoft.
ms.date: 07/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 65db6ce05f4d6f7f7b08ada172fec057027dd310
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692258"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Arricchimento dei profili dei clienti con indirizzi avanzati

Gli indirizzi nei tuoi dati possono essere non strutturati, incompleti o errati. Usa i modelli di Microsoft per normalizzare e arricchire i tuoi indirizzi nel [formato Common Data Model](/common-data-model/schema/core/applicationcommon/address) per una migliore precisione e informazioni dettagliate.

## <a name="how-we-enhance-addresses"></a>Come migliorare gli indirizzi

Il nostro modello passa attraverso un processo in due fasi per migliorare un indirizzo. Innanzitutto, analizza l'indirizzo per identificare i suoi componenti e li inserisce in un formato strutturato. Quindi, utilizziamo l'intelligenza artificiale per correggere, completare e standardizzare i valori nell'indirizzo.

### <a name="example"></a>Esempio

Le informazioni sull'indirizzo potrebbero essere in un formato non standard e contenere errori di ortografia. Il modello può risolvere questi problemi e creare indirizzi coerenti nei profili dei clienti unificati.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Limiti

Gli indirizzi avanzati funzionano solo con i valori già presenti nei dati degli indirizzi inseriti. Il modello non: 

1. Verifica se l'indirizzo è un indirizzo valido.
2. Verifica se uno qualsiasi dei valori, come codici postali o nomi di strade, è valido.
3. Cambia i valori che non riconosce.

Il modello utilizza tecniche basate sull'apprendimento automatico per migliorare gli indirizzi. Sebbene applichiamo una soglia di confidenza elevata per quando il modello modifica un valore di input, come con qualsiasi modello basato sull'apprendimento automatico, l'accuratezza del 100% non è garantita.

## <a name="supported-countries-or-regions"></a>Paesi o aree geografiche supportati

Attualmente supportiamo indirizzi di arricchimento in questi paesi o aree geografiche: 

- Australia
- Canada
- Francia
- Germania
- Italia
- Giappone
- Regno Unito
- Stati Uniti

Gli indirizzi devono contenere un valore di paese/area geografica. Non elaboriamo gli indirizzi per paesi o aree geografiche non supportati e gli indirizzi per cui non è fornito alcun paese o area geografica.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento**.

1. Seleziona **Arricchisci i miei dati** nel riquadro **Indirizzi avanzati**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Screenshot del riquadro Indirizzi avanzati.":::

1. Seleziona il **set di dati del cliente** e scegli l'entità contenente gli indirizzi che vuoi arricchire. Puoi selezionare l'entità *Cliente* per arricchire gli indirizzi in tutti i profili dei clienti o selezionare un'entità segmento per arricchire gli indirizzi solo nei profili dei clienti contenuti in quel segmento.

1. Seleziona il formato degli indirizzi nel set di dati. Scegli **Indirizzo ad attributo singolo** se gli indirizzi nei tuoi dati utilizzano un unico campo. Scegli **Indirizzo a più attributi** se gli indirizzi nei tuoi dati utilizzano più di un campo dati.

   > [!NOTE]
   > Il valore di paese/area geografica è obbligatorio sia negli indirizzi con attributo singolo che con più attributi. Gli indirizzi che non contengono valori di paese/area geografica validi o supportati non verranno arricchiti.

1.  Mappa i campi dell'indirizzo dalla tua entità cliente unificato.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Pagina di mappatura dei campi degli indirizzi migliorata.":::

1. Seleziona **Avanti** per completare il mapping del campo.

1. Fornisci un nome per l'arricchimento e l'entità di output.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipende dalle dimensioni dei dati del cliente.

Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**. Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Crea [segmenti](segments.md) e [misure](measures.md) e persino [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
