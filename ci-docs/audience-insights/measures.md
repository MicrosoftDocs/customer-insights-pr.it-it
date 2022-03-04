---
title: Comprendere e gestire le misure
description: Scopri come le misure aiutano ad analizzare e riflettere le prestazioni della tua attività.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359783"
---
# <a name="measures-overview"></a>Panoramica delle misure

Le misure ti aiutano a comprendere meglio i comportamenti dei clienti e le prestazioni aziendali. Tengono in considerazione i valori rilevanti dei [profili unificati](data-unification.md). Ad esempio, un'azienda vuole vedere la *spesa totale per cliente* per comprendere la cronologia degli acquisti di un singolo cliente oppure misurare le *vendite totali dell'azienda* per comprendere le entrate a livello aggregato nell'intera attività.  

Le misure vengono create [utilizzando il generatore di misure](measure-builder.md), una piattaforma di query di dati con vari operatori e semplici opzioni di mapping. Ti consente di filtrare i dati, raggruppare i risultati, rilevare [percorsi di relazione tra entità](relationships.md) e visualizzare in anteprima l'output. Puoi [utilizzare modelli predefiniti](measure-templates.md) per configurare in modo efficiente le misure di uso comune.

Utilizza il generatore di misure per pianificare le attività aziendali eseguendo query sui dati dei clienti ed estrai informazioni dettagliate. Ad esempio, creare una misura di *spesa totale per cliente* e *rendimento totale per cliente* aiuta a identificare un gruppo di clienti con una spesa elevata ma un ritorno elevato. Puoi [creare un segmento](segments.md) sulla base di queste misure per guidare le prossime azioni migliori. 

## <a name="manage-your-measures"></a>Gestire le misure

Puoi trovare l'elenco delle misure nella pagina **Misure**.

Troverai informazioni sul tipo di misura, l'autore, la data di creazione e lo stato. Quando selezioni una misura dall'elenco, puoi visualizzare in anteprima l'output e scaricare un file CSV.

Per aggiornare tutte le misure contemporaneamente, seleziona **Aggiorna tutto** senza selezionare una misura specifica.

:::image type="content" source="media/measure-actions.png" alt-text="Azioni per gestire singole misure.":::

Seleziona una misura dall'elenco per le seguenti opzioni:

- Seleziona il nome della misura per visualizzarne i dettagli.
- **Modifica** la configurazione della misura.
- **Aggiorna** la misura in base ai dati più recenti.
- **Rinomina** la misura.
- **Elimina** la misura.
- **Attiva** o **Disattiva**. Le misure inattive non verranno aggiornate durante un [aggiornamento pianificato](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Passaggio successivo

Puoi utilizzare le misure esistenti per creare [un segmento di clientela](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
