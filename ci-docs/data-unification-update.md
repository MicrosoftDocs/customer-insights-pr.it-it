---
title: Aggiornare le impostazioni di unificazione
description: Aggiornare le regole duplicate, le regole di corrispondenza o i campi unificati nelle impostazioni di unificazione.
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: be399da9b98d8803d7d1a90f44a40e0d638a8d47
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755595"
---
# <a name="update-the-unification-settings"></a>Aggiornare le impostazioni di unificazione

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Per rivedere o modificare le impostazioni di unificazione una volta creato un profilo unificato, esegui queste operazioni.

1. Vai a **Dati** > **Unifica**.

   :::image type="content" source="media/m3_unified.png" alt-text="Screenshot della pagina Dati > Unifica dopo l'unificazione dei dati.":::

   > [!TIP]
   > Il riquadro **Condizioni corrispondenti** viene visualizzato solo se sono state selezionate più entità.

1. Scegli gli elementi da aggiornare:
   - [Campi di origine](#edit-source-fields) per aggiungere entità o attributi o modificare i tipi di attributi.
   - [Record duplicati](#manage-deduplication-rules) per gestire le regole di deduplicazione o unire le preferenze.
   - [Condizioni corrispondenti](#manage-match-rules) per aggiornare le regole di corrispondenza tra due o più entità.
   - [Campi cliente unificati](#manage-unified-fields) per combinare o escludere campi. Puoi anche raggruppare i profili correlati in cluster.

1. Dopo aver apportato le modifiche, scegli l'opzione successiva:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Screenshot della pagina Unifica dati con le opzioni Unifica evidenziate.":::

   - Per aggiornare il profilo cliente unificato (con o senza dipendenze), vedi [Eseguire gli aggiornamenti al profilo del cliente](#run-updates-to-the-unified-customer-profile).
   - Per valutare la qualità delle condizioni di corrispondenza senza aggiornare il profilo unificato, vedi [Esegui condizioni corrispondenti](#run-matching-conditions). L'opzione **Esegui solo condizioni corrispondenti** non viene visualizzata per una singola entità.

## <a name="edit-source-fields"></a>Modifica i campi di origine

Non puoi rimuovere un attributo né un'entità se sono già stati unificati.

1. Seleziona **Modifica** nel riquadro **Campi di origine**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Screenshot della pagina Campi di origine che mostra il numero di chiavi primarie e di campi mappati e non mappati":::

   Viene visualizzato il numero di campi mappati e non mappati.

1. Scegli **Seleziona entità e campi** per aggiungere altri attributi o entità. Usa la funzionalità di ricerca o scorri per trovare e selezionare gli attributi e le entità che ti interessano. Seleziona **Applica**.

1. Facoltativamente, puoi modificare la chiave primaria per un'entità, i tipi di attributo e attivare/disattivare **Mappatura intelligente**. Per ulteriori informazioni, vedi [Seleziona la chiave primaria e il tipo semantico per gli attributi](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Seleziona **Avanti** per apportare modifiche alle regole di deduplicazione oppure seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Gestire le regole di deduplicazione

1. Seleziona **Modifica** nel riquadro **Record duplicati**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Screenshot della pagina Record duplicati che mostra il numero di record duplicati" lightbox="media/m3_duplicates_edit.png":::

   Il numero di record duplicati trovati viene visualizzato in **Duplicati**. La colonna **Record deduplicati** mostra quali entità avevano record duplicati e la percentuale di record duplicati.

1. Se hai aggiunto un'entità arricchita, seleziona **Utilizza entità arricchite**. Per altre informazioni, vedi [Arricchimento per le origini dati](data-sources-enrichment.md).

1. Per gestire le regole di deduplicazione, scegli una delle seguenti opzioni:
   - **Crea una nuova regola**: seleziona **Aggiungi regola** sotto l'entità appropriata. Per ulteriori informazioni, vedi [Definire le regole di deduplicazione](remove-duplicates.md#define-deduplication-rules).
   - **Modifica condizioni regola**: seleziona la regola, quindi **Modifica**. Modifica i campi, aggiungi o rimuovi condizioni oppure aggiungi o rimuovi eccezioni.
   - **Anteprima**: seleziona la regola, quindi **Anteprima** per visualizzare i risultati dell'ultima esecuzione per questa regola.
   - **Disattiva una regola**: seleziona la regola e poi scegli **Disattiva** per mantenere una regola di deduplicazione escludendola dal processo di abbinamento.
   - **Duplica una regola**: seleziona la regola e quindi **Duplica** per creare una regola simile con modifiche.
   - **Elimina una regola**: seleziona la regola e quindi **Elimina**.

1. Per modificare le preferenze di unione, seleziona l'entità. È possibile modificare le preferenze solo se viene creata una regola.
   1. Seleziona **Modifica preferenze di unione** e modifica l'opzione **Record da mantenere**.
   1. Per modificare le preferenze di unione sui singoli attributi di un'entità, seleziona **Avanzate** e apporta le modifiche necessarie.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Screenshot delle preferenze di unione avanzate che mostrano l'indirizzo e-mail più recente e l'indirizzo più completo":::

   1. Seleziona **Fatto**.

1. Seleziona **Avanti** per apportare modifiche alle regole di corrispondenza oppure seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Gestire le regole di corrispondenza

Puoi riconfigurare e ottimizzare la maggior parte dei parametri di corrispondenza. Non puoi aggiungere né eleminare entità. Le regole di corrispondenza non si applicano a una singola entità.

1. Seleziona **Modifica** nel riquadro **Condizioni corrispondenti**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Screenshot della pagina delle regole e delle condizioni di corrispondenza con le statistiche." lightbox="media/m3_match_edit.png":::

   La pagina mostra l'ordine di corrispondenza, le regole definite e le seguenti statistiche:
   - **Record di origine univoci** mostra il numero di record di origine individuali che sono stati elaborati nell'ultima esecuzione della corrispondenza.
   - **Record corrispondenti e non corrispondenti** evidenzia quanti record univoci rimangono dopo l'elaborazione delle regole di corrispondenza.
   - **Solo record corrispondenti** mostra il numero di corrispondenze in tutte le coppie di corrispondenza.

1. Per visualizzare i risultati di tutte le regole e i relativi punteggi, seleziona **Visualizza ultima esecuzione**. Vengono visualizzati i risultati, inclusi gli ID contatto alternativi. Puoi scaricare i risultati.

1. Per visualizzare i risultati e i punteggi di una determinata regola, seleziona la regola e quindi **Anteprima**. Vengono visualizzati i risultati. Puoi scaricare i risultati.

1. Per visualizzare i risultati di una determinata condizione su una regola, seleziona la regola e quindi **Modifica**. Nel riquadro Modifica, seleziona **Anteprima** sotto la condizione. Puoi scaricare i risultati.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Rappresentazione grafica di record non corrispondenti e corrispondenti inclusi in un elenco dei dati.":::

1. Se hai aggiunto un'entità arricchita, seleziona **Utilizza entità arricchite**. Per altre informazioni, vedi [Arricchimento per le origini dati](data-sources-enrichment.md).

1. Per gestire le regole, scegli una delle seguenti opzioni:
   - **Crea una nuova regola**: seleziona **Aggiungi regola** sotto l'entità appropriata. Per ulteriori informazioni, vedi [Definire le regole per le coppie di corrispondenza](match-entities.md#define-rules-for-match-pairs).
   - **Modificare l'ordine delle regole** se hai definito più regole: trascina le regole nell'ordine desiderato. Per altre informazioni, vedi [Specifica dell'ordine di corrispondenza](match-entities.md#specify-the-match-order).
   - **Modifica condizioni regola**: seleziona la regola, quindi **Modifica**. Modifica i campi, aggiungi o rimuovi condizioni oppure aggiungi o rimuovi eccezioni.
   - **Disattiva una regola**: seleziona la regola e poi scegli **Disattiva** per mantenere una regola di corrispondenza escludendola dal processo di abbinamento.
   - **Duplica una regola**: seleziona la regola e quindi **Duplica** per creare una regola simile con modifiche.
   - **Elimina una regola**: seleziona la regola e quindi **Elimina**.

1. Seleziona **Avanti** per apportare modifiche ai campi unificati oppure seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Gestire campi unificati

1. Seleziona **Modifica** nel riquadro **Campi clienti unificati**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Screenshot dei campi cliente unificati":::

1. Esamina i campi combinati ed esclusi e apporta le modifiche necessarie. Aggiungi o modifica la chiave CustomerID o raggruppa i profili in cluster. Per altre informazioni, vedi [Unifica campi cliente](merge-entities.md).

1. Seleziona **Avanti** per rivedere le impostazioni di unificazione e [aggiornare il profilo unificato e le dipendenze](#run-updates-to-the-unified-customer-profile) o seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-the-unification-settings) per apportare più modifiche.

## <a name="run-matching-conditions"></a>Esegui le condizioni corrispondenti

1. Nella pagina **Dati** > **Unifica** seleziona **Esegui solo condizioni corrispondenti**.

   I riquadri **Record duplicati** e **Condizioni corrispondenti** mostrano **In coda** o **Aggiornamento**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

1. Al termine del processo di abbinamento, seleziona **Modifica** nel riquadro **Condizioni corrispondenti**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Screenshot ritagliato delle metriche chiave nella pagina Corrispondenza con numeri e dettagli.":::

1. Per apportare modifiche, vedi [Gestisci le regole di deduplicazione](#manage-deduplication-rules) o [Gestire le regole di corrispondenza](#manage-match-rules).

1. Esegui di nuovo il processo di corrispondenza o [esegui gli aggiornamenti al profilo del cliente](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Esegui gli aggiornamenti al profilo cliente unificato

1. Nella pagina **Dati** > **Unifica** seleziona:

   - **Unifica profili cliente**: aggiorna l'entità del profilo cliente unificato senza influire sulle dipendenze (come arricchimenti, segmenti o misure). I processi dipendenti non vengono eseguiti, ma verranno aggiornati come [definito nel programma di aggiornamento](system.md#schedule-tab).

   - **Unifica profili cliente e dipendenze**: aggiorna il profilo unificato e tutte le dipendenze. Tutti i processi vengono rieseguiti automaticamente. Dopo che tutti i processi a valle sono stati completati, il profilo del cliente riflette i dati aggiornati.

   I riquadri **Record duplicati**, **Condizioni corrispondenti** e **Campi clienti unificati** mostrano **In coda** o **Aggiornamento**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]
