---
title: Visualizzare profili cliente
description: Ottieni una visualizzazione combinata dei dati cliente unificati.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 1e9e59d7ae6c16ed8b33f2ea482563c3520ab885
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947051"
---
# <a name="customer-profiles"></a>Profili cliente

La pagina **Clienti** mostra una vista combinata dei tuoi profili cliente unificati. I profili dei clienti sono disponibili una volta [creata l'entità Customer unificata](data-unification.md). La pagina permette di cercare i clienti e di definire l'indice per questa ricerca.

I clienti possono essere individui oppure organizzazioni. Ogni profilo di cliente è rappresentato da una piastrella. Usa i controlli di paginazione per ottenere più record. La scheda visualizza i campi dell'entità *Cliente* come definiti nell' **indice di ricerca e filtro**. L'ordine dei campi all'interno di ciascuna scheda viene selezionato dal sistema.

Seleziona un riquadro per vedere i dati per il cliente selezionato in una pagina dedicata chiamata [Pagina dei dettagli del cliente](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"]
> ![Pagina dei clienti che mostra le piastrelle dei risultati](media/customers-page-result-tiles-B2C.png "Pagina dei clienti che mostra le piastrelle dei risultati")

> [!NOTE]
> Se non riesci a vedere le tessere quando selezioni **Clienti** nella navigazione, il tuo amministratore ha bisogno di [definire almeno un attributo ricercabile](search-filter-index.md) nell' **indice di Ricerca & filtro**.

## <a name="search-for-customers"></a>Ricerca di clienti

Cerca i clienti inserendo un nome o un altro attributo nella casella di ricerca. La ricerca funziona solo all'interno dell'entità *Cliente* creata durante il processo di unificazione dei dati.

Come amministratore, puoi configurare gli attributi ricercabili mediante la pagina **Indicizzazione ricerca e filtro**. Per maggiori informazioni, vai a [Gestire la ricerca e il filtro dell'indice](search-filter-index.md).

## <a name="filter-customers"></a>Applicazione di filtri ai clienti

Puoi filtrare i clienti per i campi dell'entità *Cliente* . Simile alla ricerca, l'amministratore dovrà prima definire i campi come filtrabili utilizzando la pagina **Indicizzazione ricerca e filtro**.

1. Seleziona **Mostra filtri** nella pagina **Clienti** .

1. Seleziona le caselle di controllo accanto agli attributi in base a cui vuoi filtrare i clienti.

1. Rimuovi i filtri selezionando **Cancella filtri** nella pagina **Clienti**.

## <a name="customer-details-page"></a>Pagina Dettagli cliente

Seleziona uno dei riquadri del cliente per aprire la **pagina Dettagli cliente**. Questa visualizzazione contiene informazioni unificate per il cliente selezionato. I dettagli del cliente includono il seguente contenuto:

**Mattonella del profilo del cliente**: Questo riquadro mostra i diversi valori dell'entità *Customer* unificata. Fatta eccezione per il campo dell'indirizzo, un campo non verrà visualizzato qualora non contenga alcun valore per il profilo cliente selezionato. La piastrella è strutturata in sezioni:

- La prima sezione mostra un insieme predefinito di campi seguito da tutti i campi che fanno parte dell'indice di ricerca e filtro. Tutti i campi relativi all'indirizzo sono combinati in un'unica riga, che viene mostrata anche se il profilo non contiene informazioni sull'indirizzo.
- **Contatti per questo cliente**: Negli ambienti per i conti commerciali, vedrai tutti i contatti correlati per questo cliente come seconda sezione. Ogni contatto è mostrato con i suoi campi. I campi vuoti sono nascosti.
- **Campi aggiuntivi**: Mostra i restanti campi del cliente selezionato, eccetto gli ID.
- **ID**: Elenca tutti gli ID sotto il nome dell'entità corrispondente. I campi sono identificati come ID dalla loro semantica, che li categorizza come tali.

**Cronologia delle attività**: Mostra i dati se hai configurato delle attività. La vista timeline contiene attività ordinate cronologicamente del cliente selezionato, a partire dall'attività più recente. Per maggiori informazioni, andate su [Attività del cliente](activities.md).

**Approfondimenti**:

- **Misure**: Mostra se hai configurato una o più misure di attributi del cliente. Includono KPI calcolati relativi ai clienti a livello di singolo cliente. Per maggiori informazioni, vai a [Definire e gestire le misure](measures.md).

- **Potenziali interessi, potenziali marche**: Mostra se hai configurato un arricchimento di affinità di marca o di interesse. Rappresenta i potenziali interessi e affinità per i marchi basati su altri clienti il cui profilo è simile a quello del cliente selezionato. Per maggiori informazioni, vai a [Arricchire i profili dei clienti con le affinità di marca e di interesse](enrichment-microsoft.md).

Per tornare alla pagina di ricerca dei clienti, seleziona **Torna ai clienti**.

## <a name="next-steps"></a>Passaggi successivi

Aggiungete[altre fonti di dati](data-sources.md), [arricchite i profili unificati](enrichment-hub.md)o [create segmenti](segments.md) per lavorare con i profili cliente unificati in altre applicazioni.

[!INCLUDE [footer-include](includes/footer-banner.md)]
