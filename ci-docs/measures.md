---
title: Panoramica delle misure
description: Scopri come le misure aiutano ad analizzare e riflettere le prestazioni della tua attività.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245378"
---
# <a name="measures-overview"></a>Panoramica delle misure

Le misure ti aiutano a comprendere meglio i comportamenti dei clienti e le prestazioni aziendali. Tengono in considerazione i valori rilevanti dei [profili unificati](data-unification.md). Ad esempio, un'azienda vuole vedere la *spesa totale per cliente* per comprendere la cronologia degli acquisti di un singolo cliente oppure misurare le *vendite totali dell'azienda* per comprendere le entrate a livello aggregato nell'intera attività.

Crea misure per pianificare le attività aziendali eseguendo query sui dati dei clienti ed estrarre informazioni dettagliate. Ad esempio, crea una misura di *spesa totale per cliente* e *reso totale per cliente* per identificare un gruppo di clienti con una spesa elevata ma un reso elevato. Quindi, [crea un segmento](segments.md) sulla base di queste misure per determinare quali sono le migliori azioni da intraprendere in seguito.

## <a name="create-a-measure"></a>Creare una misura

Scegli come creare una misura in base al gruppo di destinatari di riferimento.

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (B2C)](#tab/b2c)

- Da zero con il generatore di misure: [genera le tue misure](measure-builder.md).
- A partire da misure di uso comune: [usa modelli predefiniti](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Account aziendali (B2B)](#tab/b2b)

Da zero con il generatore di misure: [genera le tue misure](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Gestire misure esistenti

Vai alla pagina **Misure** per visualizzare le misure create, il relativo stato, il tipo di misura e l'ultimo aggiornamento dei dati. Puoi ordinare l'elenco delle misure in base a qualsiasi colonna o utilizzare la casella di ricerca per trovare la misura che vuoi gestire.

Seleziona accanto a una misura per visualizzare le azioni disponibili. Seleziona il nome della misura per visualizzare in anteprima l'output e scaricare un file CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Azioni per gestire singole misure."lightbox="media/measures-actions.png":::

- **Modifica** la misura per modificarne le proprietà.
- **Aggiorna** la misura per includere gli ultimi dati.
- **Rinomina** la misura.
- **Attiva** o **Disattiva** la misura. Le misure non attive non verranno aggiornate durante un [aggiornamento pianificato](schedule-refresh.md) e il relativo **stato** sarà **Ignorato**, a indicare che non è stato nemmeno tentato un aggiornamento.
- Scegli **Tag** per [gestire i tag](work-with-tags-columns.md#manage-tags) per la misura.
- **Elimina** la misura.
- **Colonne** per [personalizzare le colonne](work-with-tags-columns.md#customize-columns) visualizzate.
- **Filtro** per [filtrare in base ai tag](work-with-tags-columns.md#filter-on-tags).
- Scegli **Cerca nome** per eseguire la ricerca in base al nome della misura.

## <a name="refresh-measures"></a>Aggiornare le misure

Le misure possono essere aggiornate in base a una pianificazione automatica o manualmente su richiesta. Per aggiornare manualmente uno o più misure, selezionale e scegli **Aggiorna**. Per [pianificare un aggiornamento automatico](schedule-refresh.md), vai ad **Amministratore** > **Sistema** > **Pianifica**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
