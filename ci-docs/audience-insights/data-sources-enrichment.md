---
title: Arricchimento per le origini dati
description: Arricchisci le origini dati prima di passare al processo di unificazione dei dati.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376584"
---
# <a name="enrichment-for-data-sources-preview"></a>Arricchimento per le origini dati (anteprima)

Usa i dati provenienti da origini come Microsoft e altri partner per arricchire i dati dei tuoi clienti prima dell'unificazione dei dati. Gli arricchimenti per le origini dati aiutano a produrre una maggiore completezza e qualità dei dati che possono aiutare a ottenere risultati migliori una volta unificati. Ad esempio, l'utilizzo di un formato normalizzato e standardizzato per gli indirizzi aumenta la qualità dei risultati della corrispondenza. Per un elenco degli arricchimenti supportati, vedi [opzioni di arricchimento supportate per le origine dati](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Arricchire un'origine dati

Devi disporre delle autorizzazioni collaboratore o amministratore per creare o modificare gli arricchimenti. Per ulteriori informazioni, vedi [Autorizzazioni](permissions.md).  

1. Vai a **Dati** > **Unifica**. Seleziona l'entità che desideri arricchire e seleziona un attributo come chiave primaria per l'entità. Per ulteriori informazioni, vedi [Selezionare la chiave primaria](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Vai a **Dati** > **Origini dati**.
 
1. Seleziona i puntini verticali accanto all'origine dati che vuoi arricchire e seleziona **Arricchisci**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Pagina Arricchimento delle origini dati,":::

   La scheda **Individua** mostra le [opzioni di arricchimento supportate per le origini dati](#supported-data-source-enrichments).

1. Seleziona **Arricchisci i miei dati** per configurare un arricchimento dell'origine dati. Il nome dell'entità di output viene popolato automaticamente.

## <a name="supported-data-source-enrichments"></a>Arricchimenti supportati per le origini dati

I seguenti arricchimenti sono attualmente disponibili per le origini dati. Esamina i passaggi dettagliati per l'arricchimento per apprendere come configurarlo.

- [Indirizzi ottimizzati](enrichment-enhanced-addresses.md)
- [Dati aziendali ottimizzati](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Gestire gli arricchimenti per le origini dati esistenti

Vai alla scheda **I miei arricchimenti** per vedere tutti gli arricchimenti configurati.

Seleziona l'arricchimento per vedere le opzioni disponibili. È inoltre possibile selezionare i puntini di sospensione (...) di un elemento dell'elenco per visualizzare le opzioni. Se hai configurato diversi arricchimenti, puoi utilizzare la casella di ricerca per trovarli rapidamente.

Puoi visualizzare, modificare, eseguire o eliminare un arricchimento dell'origine dati. Per altre informazioni, consulta [Gestire gli arricchimenti esistenti](enrichment-hub.md).