---
title: Rivedere l'unificazione dei dati
description: Rivedi i passaggi di unificazione dei dati, crea profili cliente unificati ed esamina i risultati
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303972"
---
# <a name="review-data-unification"></a>Rivedere l'unificazione dei dati

Esamina il riepilogo delle modifiche, crea il profilo unificato e rivedi i risultati.

## <a name="review-and-create-customer-profiles"></a>Rivedi e crea profili cliente

Quest'ultimo passaggio del processo di unificazione mostra un riepilogo dei passaggi del processo e offre la possibilità di apportare modifiche prima di creare il profilo unificato.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Screenshot di Rivedi e crea profili cliente.":::

1. Seleziona **Modifica** per una qualsiasi delle fasi di unificazione dei dati per rivedere e apportare modifiche.

1. Al termine, seleziona **Crea profili cliente** (o **Crea profili account** per B2B). Durante la creazione del profilo cliente unificato viene visualizzata la pagina **Unifica**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Screenshot della pagina Unifica con i riquadri che mostrano lo stato In coda o In aggiornamento.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

L'algoritmo di unificazione richiede tempo per essere completato e non è possibile modificare la configurazione fino al completamento.

## <a name="view-the-results-of-data-unification"></a>Visualizza i risultati dell'unificazione dei dati

Dopo l'unificazione, la pagina **Dati** > **Unifica** mostra il numero di profili cliente unificati (o profili account per B2B). I risultati di ogni fase del processo di unificazione vengono visualizzati su ogni riquadro. Ad esempio **Campi di origine** mostra il numero di attributi mappati (campi) e **Record duplicati** mostra il numero di record duplicati trovati.

:::image type="content" source="media/m3_unified.png" alt-text="Screenshot della pagina Dati > Unifica dopo l'unificazione dei dati.":::

> [!TIP]
> Il riquadro **Condizioni corrispondenti** viene visualizzato solo se sono state selezionate più entità.

Ti consigliamo di rivedere i risultati, in particolare la qualità delle tue [regole di corrispondenza](data-unification-update.md#manage-match-rules) e di affinarli, se necessario.

Se necessario, [apporta modifiche alle impostazioni di unificazione](data-unification-update.md) ed esegui nuovamente il profilo unificato.

### <a name="verify-output-entities-from-data-unification"></a>Verifica le entità di output dall'unificazione dei dati

Vai a **Dati** > **Entità** per verificare le entità di output.

L'entità profilo cliente unificato è chiamata *Cliente* nella sezione **Profili**. La prima esecuzione di unificazione crea l'entità unificata *Cliente*. Tutte le esecuzioni successive espandono quell'entità.

Le entità di deduplicazione e conflazione vengono create e visualizzate nella sezione **Sistema**. Un'entità di deduplicazione per ciascuna delle entità di origine viene creata con il nome **Deduplication_DataSource_Entity**. L'entità **ConflationMatchPairs** contiene informazioni sulle corrispondenze tra entità.

Un'entità di output della deduplicazione contiene le seguenti informazioni:
- ID/chiavi
  - Campi chiave primaria e ID alternativo. Il campo ID alternativo è costituito da tutti gli ID alternativi identificati per un record.
  - Il campo Deduplication_GroupId mostra il gruppo o il cluster identificato all'interno di un'entità che raggruppa tutti i record simili in base ai campi di deduplicazione specificati. È utilizzato per scopi di elaborazione del sistema. Se non sono state specificate regole di deduplicazione manuale e si applicano regole di deduplicazione definite dal sistema, potresti non trovare questo campo nell'entità di output della deduplicazione.
  - Deduplication_WinnerId: questo campo contiene l'ID vincitore dei gruppi o cluster identificati. Se Deduplication_WinnerId è uguale al valore della chiave primaria per un record, significa che il record è il record vincitore.
- Campi utilizzati per definire le regole di deduplicazione.
- I campi Regola e Punteggio per indicare quale delle regole di deduplicazione è stata applicata e il punteggio restituito dall'algoritmo di corrispondenza.

## <a name="next-step"></a>Passaggio successivo

- Per B2B, esegui facoltativamente l'[unificazione dei contatti](data-unification-contacts.md).

- Per B2B, configura [impegni](activities.md), [arricchimenti](enrichment-hub.md), [relazioni](relationships.md) o [misure](measures.md) per ottenere maggiori informazioni sui tuoi clienti.

[!INCLUDE[footer-include](includes/footer-banner.md)]
