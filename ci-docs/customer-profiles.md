---
title: Visualizzare profili cliente
description: Visualizzare i dati unificati dei clienti, anche tramite ricerca e filtro
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
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188098"
---
# <a name="view-customer-profiles"></a>Visualizzare profili cliente

I profili cliente sono disponibili dopo che hai [creato l'entità *Cliente* unificata](data-unification.md). La vista combinata dei tuoi profili cliente unificati è visualizzata nella pagina **Clienti**. I clienti possono essere individui oppure organizzazioni.

Vai alla pagina **Clienti** per visualizzare i tuoi clienti e i relativi profili. Ogni profilo di cliente è rappresentato da una piastrella. Usa i controlli di paginazione per ottenere più record. La scheda visualizza i campi dell'entità *Cliente* come definiti nell'**indicizzazione di ricerca e filtro**. L'ordine dei campi all'interno di ciascuna scheda viene selezionato dal sistema.

> [!NOTE]
> Se non riesci a vedere i riquadri quando selezioni **Clienti**, il tuo amministratore deve [definire almeno un attributo ricercabile](search-filter-index.md) nell'**indicizzazione di ricerca & filtro**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Pagina dei clienti che mostra i riquadri dei risultati.":::

Seleziona una qualsiasi delle seguenti azioni:
- [Visualizzare i dettagli dei clienti](#view-customer-details)
- [Gestire l'indicizzazione di ricerca e filtro](search-filter-index.md) (solo amministratori)
- [Filtrare i clienti](#filter-customers)
- **Espandere le schede** o **comprimere le schede** per espandere o comprimere le informazioni visualizzate nel riquadro del cliente
- **Ordinare in base** a un particolare attributo
- [Cercare clienti](#search-for-customers)

  > [!NOTE]
  > Per utilizzare la ricerca e il filtro, un amministratore deve configurare gli attributi ricercabili e definire i campi filtrabili utilizzando l'indicizzazione di ricerca e filtro.

## <a name="search-for-customers"></a>Cercare clienti

Cerca i clienti inserendo un nome o un altro attributo in **Ricerca clienti**. Gli attributi ricercabili sono definiti dall'amministratore e provengono dall'entità *Cliente* unificata.

> [!NOTE]
> **Stringa** è l'unico tipo di dati incluso nella ricerca. Usalo nel campo **Ricerca clienti** della pagina Clienti per cercare i clienti.

## <a name="filter-customers"></a>Filtrare i clienti

Filtra i clienti in base ai campi dell'entità *Cliente*. I campi filtrabili sono definiti dall'amministratore.

1. Seleziona **Mostra filtri** nella pagina **Clienti**. Viene visualizzato il riquadro dei filtri.

1. Seleziona le caselle di controllo accanto agli attributi in base a cui vuoi filtrare i clienti.

1. Rimuovi tutti i filtri selezionando **Cancella filtri** o deseleziona una casella di controllo accanto a un attributo selezionato.

1. Seleziona **Nascondi filtri** per chiudere il riquadro dei filtri.

1. Per salvare i risultati dei filtri come [segmento](segments.md), seleziona **Salva filtri come segmento**.
   1. Immetti un nome per il segmento.
   1. Seleziona **Salva** per salvare il segmento.
   1. Scegli **Attiva** per eseguire il segmento ora o **In seguito** per eseguirlo successivamente.

## <a name="view-customer-details"></a>Visualizzare i dettagli dei clienti

Nella pagina **Clienti**, seleziona un riquadro per visualizzare i dettagli del cliente selezionato.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Pagina dei dettagli del cliente.":::

I dettagli del cliente includono:

Il **riquadro del profilo cliente** mostra i differenti valori dell'entità *Customer* unificata. Fatta eccezione per il campo dell'indirizzo, un campo non verrà visualizzato qualora non contenga alcun valore per il profilo cliente selezionato. La piastrella è strutturata in sezioni:

- La prima sezione mostra un insieme predefinito di campi seguito da tutti i campi che fanno parte dell'indicizzazione di ricerca e filtro. Tutti i campi relativi all'indirizzo sono combinati in un'unica riga, che viene mostrata anche se il profilo non contiene informazioni sull'indirizzo.
- I **contatti di questo cliente** sono visualizzati in ambienti per account aziendali. Ogni contatto è mostrato con i suoi campi. I campi vuoti sono nascosti.
- **Campi aggiuntivi** mostra i restanti campi del cliente selezionato, eccetto gli ID.
- **ID** elenca tutti gli ID sotto il nome dell'entità corrispondente. I campi sono identificati come ID in base alla relativa semantica.

**Sequenza temporale attività** mostra i dati se hai configurato le [attività](activities.md). La vista timeline contiene attività ordinate cronologicamente del cliente selezionato, a partire dall'attività più recente.

**Approfondimenti**:

- **Misure** mostra se hai configurato una o più [misure di attributi del cliente](measures.md). Includono KPI calcolati relativi ai clienti a livello di singolo cliente.

- **Potenziali interessi, marchi potenziali** mostra se hai configurato un [arricchimento di affinità di marca o di interesse](enrichment-microsoft.md). Rappresenta i potenziali interessi e affinità per i marchi basati su altri clienti il cui profilo è simile a quello del cliente selezionato.

Seleziona **Torna a Clienti** per tornare alla pagina **Clienti**.

## <a name="next-steps"></a>Passaggi successivi

Aggiungete[altre fonti di dati](data-sources.md), [arricchite i profili unificati](enrichment-hub.md)o [create segmenti](segments.md) per lavorare con i profili cliente unificati in altre applicazioni.

[!INCLUDE [footer-include](includes/footer-banner.md)]
