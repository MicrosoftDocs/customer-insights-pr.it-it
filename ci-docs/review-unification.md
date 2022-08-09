---
title: Rivedere l'unificazione dei dati
description: Rivedi i passaggi di unificazione dei dati, crea profili cliente unificati ed esamina i risultati
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139589"
---
# <a name="review-data-unification"></a>Rivedere l'unificazione dei dati

Quest'ultimo passaggio del processo di unificazione mostra un riepilogo dei passaggi del processo e offre la possibilità di apportare modifiche prima di creare il profilo unificato.

:::image type="content" source="media/m3_review.png" alt-text="Screenshot di Rivedi e crea profili cliente.":::

## <a name="review-the-data-unification-steps"></a>Esamina i passaggi di unificazione dei dati

1. Seleziona **Modifica** per una qualsiasi delle fasi di unificazione dei dati per rivedere e apportare modifiche.

1. Al termine dell'operazione, seleziona **Crea profili cliente**. Durante la creazione del profilo cliente unificato viene visualizzata la pagina **Unifica**. Tutti i riquadri tranne **Campi di origine** mostrano lo stato **In coda** o **In aggiornamento**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Screenshot della pagina Unifica con i riquadri che mostrano lo stato In coda o In aggiornamento.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

L'algoritmo di unificazione richiede tempo per essere completato e non è possibile modificare la configurazione fino al completamento. Al termine del processo di unificazione, l'entità del profilo cliente unificato denominata *Cliente* viene elencata nella pagina **Entità** nella sezione **Profili**. La prima esecuzione di unificazione crea l'entità unificata *Cliente*. Tutte le esecuzioni successive espandono quell'entità.

## <a name="review-the-results-of-data-unification"></a>Esamina i risultati dell'unificazione dei dati

Dopo l'unificazione, la pagina **Dati** > **Unifica** mostra il numero di profili cliente unificati. I risultati di ogni fase del processo di unificazione vengono visualizzati su ogni riquadro. Ad esempio **Campi di origine** mostra il numero di attributi mappati (campi) e **Record duplicati** mostra il numero di record duplicati trovati.

:::image type="content" source="media/m3_unified.png" alt-text="Screenshot della pagina Dati > Unifica dopo l'unificazione dei dati.":::

> [!TIP]
> Il riquadro **Condizioni corrispondenti** viene visualizzato solo se sono state selezionate più entità.

Ti consigliamo di rivedere i risultati, in particolare la qualità delle tue [regole di corrispondenza](data-unification-update.md#manage-match-rules) e di affinarli, se necessario.

Se necessario, [apporta modifiche alle impostazioni di unificazione](data-unification-update.md) ed esegui nuovamente il profilo unificato.

## <a name="next-step"></a>Passaggio successivo

Configura [impegni](activities.md), [arricchimenti](enrichment-hub.md), [relazioni](relationships.md) o [misure](measures.md) per ottenere maggiori informazioni sui tuoi clienti.

[!INCLUDE[footer-include](includes/footer-banner.md)]
