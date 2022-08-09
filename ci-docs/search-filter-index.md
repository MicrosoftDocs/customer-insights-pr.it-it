---
title: Gestire l'indicizzazione di ricerca e filtro per i profili cliente
description: Trova rapidamente informazioni sui profili cliente unificati e filtra per attributi specificati.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187914"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Gestire l'indicizzazione di ricerca e filtro per i profili cliente

Il risultato dell'unificazione dei dati cliente è un'entità *Cliente* che fornisce una visualizzazione unificata della base clienti totale. Per consentire agli utenti di [trovare rapidamente informazioni su un cliente o gruppo di clienti specifico](customer-profiles.md), un amministratore deve configurare le funzionalità **Cerca** o **Filtra** nella pagina **Clienti**.

   :::image type="content" source="media/search-filter.png" alt-text="Filtro ricerca":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definire gli attributi ricercabili e i campi indicizzati

Se è la prima volta che definisci gli attributi ricercabili come amministratore, definisci prima i campi indicizzati. Ti consigliamo di scegliere tutti gli attributi in base ai quali gli utenti possono cercare e filtrare i clienti nella pagina **Clienti**. Puoi specificare solo gli attributi presenti nell'entità *Cliente* creata durante il processo di unificazione dei dati.

1. Vai a **Clienti** e seleziona **Indicizzazione ricerca e filtro**.

1. Seleziona **+ Aggiungi**.

1. Seleziona gli attributi nell'elenco che vuoi aggiungere come campi indicizzati e fai clic su **Applica**.

1. Seleziona **Aggiungi** per aggiungere altri attributi. Per rimuovere un attributo selezionato, seleziona l'attributo e quindi **Elimina**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Pagina Indicizzazione ricerca e filtro":::

1. Seleziona **Esegui** quando sei pronto per applicare le impostazioni di ricerca e filtro. Dopo l'elaborazione delle modifiche, visualizzale nelle [schede cliente della pagina Cliente](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definire le opzioni di filtro per un determinato attributo

Imposta i campi che possono essere utilizzati per filtrare i clienti nella pagina **Clienti**.

1. Vai a **Clienti** e seleziona **Indicizzazione ricerca e filtro**.

1. Seleziona un attributo e **Aggiungi filtro**. Definisci il numero di risultati e l'ordine in cui verranno organizzati. A seconda del tipo di dati dell'attributo, viene visualizzato uno dei riquadri seguenti.

   - Attributi di tipo stringa: specifica il numero di risultati desiderati nel pannello **Filtro stringa** e i criteri di ordine in base ai quali verranno organizzati.

   - Attributi di tipo numerico: specifica gli intervalli inclusi nel pannello **Filtro numero** e i criteri di ordine in base ai quali verranno organizzati.

   - Attributi di tipo data: specifica gli intervalli inclusi nel pannello **Filtro data** e i criteri di ordine in base ai quali verranno organizzati.

1. Seleziona **OK**. Ripeti per tutti gli attributi in base ai quali intendi filtrare.

1. Seleziona **Esegui** quando sei pronto per applicare le impostazioni di ricerca e filtro. Dopo l'elaborazione delle modifiche, visualizzale nelle [schede cliente della pagina Cliente](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Visualizzare i campi cliente indicizzati

La pagina **Indicizzazione ricerca e filtro** visualizza le seguenti informazioni:

- **Nome**: rappresenta il nome dell'attributo così come visualizzato nell'entità *Cliente*.
- **Tipo di dati**: specifica se il tipo di dati è una stringa, un numero o una data.
- **Incluso nella ricerca**: specifica se questo attributo può essere utilizzato per la ricerca dei clienti nella pagina **Clienti** utilizzando il campo **Cerca**.
- **Aggiungi filgtro**: controllo per definire la modalità di utilizzo di questo attributo per il filtro nella pagina **Clienti**.

## <a name="next-steps"></a>Passaggi successivi

Esamina la [pagina dei profili unificati](customer-profiles.md) per cercare profili o utilizzare i campi indicizzati per visualizzare un sottoinsieme di tutti i profili unificati.

[!INCLUDE [footer-include](includes/footer-banner.md)]
