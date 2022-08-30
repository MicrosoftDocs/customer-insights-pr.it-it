---
title: Aggiornare le impostazioni di unificazione per cliente, account o contatti
description: Aggiornare le regole duplicate, le regole di corrispondenza o i campi unificati nelle impostazioni di unificazione dei clienti o degli account.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304340"
---
# <a name="update-unification-settings"></a>Aggiornare le impostazioni di unificazione

Per rivedere o modificare le impostazioni di unificazione una volta creato un profilo unificato, esegui queste operazioni.

1. Vai a **Dati** > **Unifica**.

   Per i clienti individuali (B2C), la pagina **Unifica** mostra il numero di profili cliente unificati e i riquadri per ciascuno dei passaggi di unificazione.

   :::image type="content" source="media/m3_unified.png" alt-text="Screenshot della pagina Dati > Unifica dopo l'unificazione dei dati." lightbox="media/m3_unified.png":::

   Per gli account aziendali (B2B), la pagina **Unifica** mostra il numero di profili account unificati e i riquadri per ciascuno dei passaggi di unificazione dell'account. Se i contatti sono stati unificati, viene visualizzato il numero di profili e riquadri di contatti unificati per ciascuno dei passaggi di unificazione dei contatti. Scegli il riquadro appropriato in **Unifica account** o **Unifica contatti (anteprima)** a seconda di cosa vuoi aggiornare.

   :::image type="content" source="media/b2b_unified.png" alt-text="Screenshot della pagina Unifica dati dopo l'unificazione dei dati dei contatti e degli account." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Il riquadro **Condizioni corrispondenti** viene visualizzato solo se sono state selezionate più entità.

1. Scegli gli elementi da aggiornare:
   - [Campi di origine](#edit-source-fields) per aggiungere entità o attributi o modificare i tipi di attributi.
   - [Record duplicati](#manage-deduplication-rules) per gestire le regole di deduplicazione o unire le preferenze.
   - [Condizioni corrispondenti](#manage-match-rules) per aggiornare le regole di corrispondenza tra due o più entità.
   - [Campi cliente unificati](#manage-unified-fields) per combinare o escludere campi. Puoi anche raggruppare i profili correlati in cluster.
   - [Campi semantici](#manage-semantic-fields-for-unified-contacts) per gestire i tipi semantici per i campi di contatto unificati.
   - [Relazioni](#manage-contact-and-account-relationships) per gestire la relazione tra contatti e account.

1. Dopo aver apportato le modifiche, scegli l'opzione successiva:

   - [Esegui solo condizioni corrispondenti](#run-matching-conditions) per valutare rapidamente la qualità delle condizioni corrispondenti (regole di deduplicazione e di corrispondenza) senza aggiornare il profilo unificato. L'opzione **Esegui solo condizioni corrispondenti** non viene visualizzata per una singola entità.
   - [Unificare i profili](#run-updates-to-the-unified-profile) per eseguire condizioni corrispondenti e aggiornare l'entità dei profili unificati senza influire sulle dipendenze (come arricchimenti, segmenti o misure). I processi dipendenti non vengono eseguiti, ma verranno aggiornati come [definito nel programma di aggiornamento](schedule-refresh.md).
   - [Unifica profili cliente e dipendenze](#run-updates-to-the-unified-profile) per eseguire condizioni corrispondenti, aggiornare l'entità dei profili unificati e aggiornare tutte le dipendenze (come arricchimenti, segmenti o misure). Tutti i processi vengono rieseguiti automaticamente. In B2B, l'unificazione viene eseguita sia sull'account che sulle entità di contatto che aggiornano i profili unificati.

## <a name="edit-source-fields"></a>Modifica i campi di origine

Non puoi rimuovere un attributo né un'entità se sono già stati unificati.

1. Seleziona **Modifica** nel riquadro **Campi di origine**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Screenshot della pagina Campi di origine che mostra il numero di chiavi primarie e di campi mappati e non mappati":::

   Viene visualizzato il numero di campi mappati e non mappati.

1. Per aggiungere altri attributi o entità, seleziona **Seleziona entità e campi**.

1. Facoltativamente, puoi modificare la chiave primaria per un'entità, i tipi di attributo e attivare/disattivare **Mapping intelligente**. Per altre informazioni, vedi [Seleziona campi di origine](map-entities.md).

1. Seleziona **Avanti** per apportare modifiche alle regole di deduplicazione oppure seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-unification-settings).

## <a name="manage-deduplication-rules"></a>Gestire le regole di deduplicazione

1. Seleziona **Modifica** nel riquadro **Record duplicati**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Screenshot della pagina Record duplicati che mostra il numero di record duplicati" lightbox="media/m3_duplicates_edit.png":::

   Il numero di record duplicati trovati viene visualizzato in **Duplicati**. La colonna **Record deduplicati** mostra quali entità avevano record duplicati e la percentuale di record duplicati.

1. Per utilizzare un'entità arricchita, seleziona **Utilizza entità arricchite**. Per altre informazioni, vedi [Arricchimento per le origini dati](data-sources-enrichment.md).

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

   1. Seleziona **Fatto**.

1. Seleziona **Avanti** per apportare modifiche alle regole di corrispondenza oppure seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-unification-settings).

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

1. Seleziona **Avanti** per apportare modifiche ai campi unificati oppure seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-unification-settings).

## <a name="manage-unified-fields"></a>Gestire campi unificati

1. Seleziona **Modifica** nel riquadro **Campi clienti unificati**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Screenshot dei campi cliente unificati":::

1. Esamina i campi combinati ed esclusi e apporta le modifiche necessarie. Aggiungi o modifica la chiave CustomerID o raggruppa i profili in cluster. Per altre informazioni, vedi [Unifica campi cliente](merge-entities.md).

1. Per clienti o account, seleziona **Avanti** per rivedere e [aggiornare il profilo unificato e le dipendenze](#run-updates-to-the-unified-profile). Oppure seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-unification-settings) per apportare ulteriori modifiche.

   Per i contatti, seleziona **Avanti** per gestire i campi semantici. Oppure seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-unification-settings) per apportare ulteriori modifiche.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Gestisci i campi semantici per i contatti unificati

1. Seleziona **Modifica** nel riquadro **Campi semantici**.

1. Per modificare il tipo semantico per un campo unificato, seleziona un nuovo tipo. Per ulteriori informazioni, vedi [Definisci i campi semantici per i contatti unificati](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Seleziona **Avanti** per gestire la relazione tra contatti e account oppure seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-unification-settings) per apportare ulteriori modifiche.

## <a name="manage-contact-and-account-relationships"></a>Gestisci relazioni tra account e contatti

1. Seleziona **Modifica** nel riquadro **Relazioni**.

1. Per modificare il contatto e la relazione di account, modifica una delle seguenti informazioni:

   - **Chiave esterna dall'entità contatto**: scegli l'attributo che collega la tua entità di contatto all'account.
   - **A entità account**: scegli l'entità di account associata al contatto.

1. Seleziona **Avanti** per rivedere le impostazioni di unificazione e [aggiornare il profilo unificato e le dipendenze](#run-updates-to-the-unified-profile) o seleziona **Salva e chiudi** e torna ad [Aggiornare le impostazioni di unificazione](#update-unification-settings) per apportare più modifiche.

## <a name="run-matching-conditions"></a>Esegui le condizioni corrispondenti

Esegui solo condizioni corrispondenti esegue solo le regole di deduplicazione e di corrispondenza e aggiorna le entità *Deduplication_** e *ConflationMatchPair*.

1. Nella pagina **Dati** > **Unifica** seleziona **Esegui solo condizioni corrispondenti**.

   I riquadri **Record duplicati** e **Condizioni corrispondenti** mostrano lo stato **In coda** o **Aggiornamento**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Al termine del processo di abbinamento, seleziona **Modifica** nel riquadro **Condizioni corrispondenti**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Screenshot ritagliato delle metriche chiave nella pagina Corrispondenza con numeri e dettagli.":::

1. Per apportare modifiche, vedi [Gestisci le regole di deduplicazione](#manage-deduplication-rules) o [Gestire le regole di corrispondenza](#manage-match-rules).

1. Esegui di nuovo il processo di corrispondenza o [esegui gli aggiornamenti al profilo](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Esegui gli aggiornamenti al profilo unificato

- Per eseguire condizioni corrispondenti e aggiornare l'entità dei profili unificati *senza* influire sulle dipendenze (come schede cliente, arricchimenti, segmenti o misure), seleziona **Unifica profili cliente**. Per gli account, seleziona **Unifica account** > **Unifica profili**. Per i contatti, seleziona **Unifica contatti (anteprima)** > **Unifica profili**. I processi dipendenti non vengono eseguiti, ma verranno aggiornati come [definito nel programma di aggiornamento](schedule-refresh.md).
- Per eseguire condizioni corrispondenti, aggiornare il profilo unificato ed eseguire le dipendenze, seleziona **Unifica profili cliente e dipendenze**. Tutti i processi vengono rieseguiti automaticamente. Per account e contatti, seleziona **Unifica account** > **Unifica profili e dipendenze**. Le condizioni corrispondenti vengono eseguite sia per gli account che per i contatti che aggiornano i profili unificati e tutte le altre dipendenze.

Tutti i riquadri tranne **Campi di origine** mostrano **In coda** o **In aggiornamento**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

I risultati di un'esecuzione riuscita vengono visualizzati nella pagina **Unifica** che mostra il numero di profili unificati.
