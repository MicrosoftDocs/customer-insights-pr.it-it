---
title: Creare un profilo cliente unificato (anteprima)
description: Passa attraverso il processo di unificazione dei dati per creare un unico dataset principale dei contatti.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305027"
---
# <a name="create-a-unified-contact-profile-preview"></a>Creare un profilo cliente unificato (anteprima)

Dopo aver [unificato i conti aziendali](map-entities.md), puoi facoltativamente unificare i contatti per tali account e collegare i contatti unificati agli account unificati. Il processo di unificazione dei contatti mappa i dati dei contatti da più origini dati, rimuove i duplicati, abbina i dati tra entità, imposta la mappatura semantica, crea relazioni tra contatti e account e quindi crea un profilo di contatto unificato.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

I primi passaggi sono identici ai passaggi di unificazione degli account.

## <a name="prerequisites"></a>Prerequisiti

I record di account e contatti devono avere una chiave univoca (denominata chiave esterna) che li collega. Ad esempio, un ID account che esiste nel record di account e un record del contatto che lega l'account e il contatto insieme.

## <a name="preview-limitations"></a>Limiti dell'anteprima

- I contatti senza un collegamento a un account vengono eliminati.
- Se un account viene deduplicato, viene identificato un record vincitore in base alle preferenze di unione. I record ignorati non vengono selezionati e pertanto vengono eliminati. I contatti associati ai record ignorati vengono eliminati.
- Un account può avere più contatti, ma un contatto è collegato a un unico account.
- Gli attributi di contatto mappati nella fase di mappatura semantica sono gli unici attributi che possono essere visualizzati sulla scheda Cliente. Tuttavia, sono disponibili 17 attributi.

## <a name="select-source-fields"></a>Selezionare i campi di origine

1. In **Unifica contatti (anteprima)**, seleziona **Attività iniziali**.

1. [Seleziona le entità e i campi](map-entities.md) per le tue origini dati di contatto, comprese le chiavi primarie e i tipi di attributi.

1. Selezionare **Avanti**.

## <a name="remove-duplicate-records"></a>Rimuovere i record duplicati

1. Opzionalmente, [definisci le regole di deduplicazione](remove-duplicates.md) per le entità selezionate.

1. Selezionare **Avanti**.

## <a name="match-conditions"></a>Condizioni di corrispondenza

1. [Definire l'ordine di corrispondenza e le regole](match-entities.md) per la corrispondenza tra entità.

1. Selezionare **Avanti**.

## <a name="unify-contact-fields"></a>Unificare i campi dei contatti

1. [Combina ed escludi i campi di contatto](merge-entities.md).

1. Selezionare **Avanti**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definisci i campi semantici per i contatti unificati

Questo passaggio nel processo di unificazione associa i campi di contatto unificati ai tipi semantici. In B2B, le schede cliente mostrano gli account. Quando si seleziona la scheda, vengono visualizzati tutti i contatti associati all'account. I campi mappati in questo passaggio sono i campi che verranno visualizzati sulle schede.

1. Seleziona il tipo semantico che esegue il mapping a ciascun campo unificato. Seleziona **Nessuno** se non è disponibile un tipo semantico.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Screenshot della pagina dei campi semantici per definire i tipi semantici." lightbox="media/semantic_mapping.png":::

1. Dopo aver mappato tutti i campi unificati, seleziona **Avanti**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Imposta la relazione tra entità contatti e account

Questo passaggio nel processo di unificazione collega i tuoi dati di contatto ai dati dell'account corrispondente.

1. Per ogni entità, immetti le informazioni seguenti.

   - **Chiave esterna dall'entità contatto**: scegli l'attributo che collega la tua entità di contatto all'account.
   - **A entità account**: scegli l'entità di account associata al contatto.

   :::image type="content" source="media/contact_relationship.png" alt-text="Screenshot della pagina Relazione per collegare le entità di contatto e account.":::

1. Selezionare **Avanti**.

## <a name="review-contact-unification"></a>Rivedere l'unificazione dei contatti

Esamina il riepilogo delle modifiche, crea il profilo unificato e rivedi i risultati.

### <a name="review-and-create-contact-profiles"></a>Rivedi e crea profili contatto

Quest'ultimo passaggio del processo di unificazione mostra un riepilogo dei passaggi del processo e offre la possibilità di apportare modifiche prima di creare il profilo di contatto unificato.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Screenshot di Rivedi e crea profili contatto.":::

1. Seleziona **Modifica** per un qualsiasi passaggio di unificazione dei dati per rivedere e apportare modifiche.

1. Al termine dell'operazione, seleziona **Crea profili di contatto**. Durante la creazione del profilo contatto unificato viene visualizzata la pagina **Unifica**.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Screenshot della pagina Unifica contatti con i riquadri che mostrano lo stato In coda o In aggiornamento.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

L'algoritmo di unificazione richiede tempo per essere completato e non è possibile modificare la configurazione fino al completamento.

### <a name="view-the-results-of-contact-unification"></a>Visualizza i risultati dell'unificazione dei contatti

Al termine dell'unificazione, la pagina **Dati** > **Unifica** mostra il numero di profili dei contatti unificati. I risultati di ogni passaggio del processo di unificazione vengono visualizzati su ogni riquadro. Ad esempio **Campi di origine** mostra il numero di attributi mappati (campi) e **Record duplicati** mostra il numero di record duplicati trovati.

:::image type="content" source="media/unified_contacts.png" alt-text="Screenshot della pagina Dati > Unifica dopo l'unificazione dei contatti.":::

> [!TIP]
> Il riquadro **Condizioni corrispondenti** viene visualizzato solo se sono state selezionate più entità.

Ti consigliamo di rivedere i risultati, in particolare la qualità delle tue [regole di corrispondenza](data-unification-update.md#manage-match-rules) e di affinarli, se necessario.

Se necessario, [apporta modifiche alle impostazioni di unificazione dei contatti](data-unification-update.md) ed esegui nuovamente il profilo unificato.

### <a name="verify-output-entities-from-data-unification"></a>Verifica le entità di output dall'unificazione dei dati

Vai a **Dati** > **Entità** per verificare le entità di output.

L'entità del profilo del contatto unificato, denominata *ContactProfile*, viene visualizzata nella sezione **Entità semantiche**. La prima esecuzione di unificazione crea l'entità unificata *ContactProfile*. Tutte le esecuzioni successive espandono quell'entità.

L'entità *ContactsCustomer* (anteprima) viene creata e visualizzata nella sezione **Profili**. Questa entità contiene i dati di contatto senza i collegamenti agli account. Questa entità viene utilizzata come input nella mappatura semantica e nelle fasi di relazione dell'unificazione dei contatti.

Le entità di deduplicazione e conflazione vengono create e visualizzate nella sezione **Sistema**. Un'entità di deduplicazione per ciascuna delle entità di origine viene creata con il nome **Deduplication_DataSource_Entity**. L'entità **ContactsConflationMatchPairs** contiene informazioni sulle corrispondenze tra entità.

Un'entità di output della deduplicazione contiene le seguenti informazioni:
- ID/chiavi
  - Campi chiave primaria e ID alternativo. Il campo ID alternativo è costituito da tutti gli ID alternativi identificati per un record.
  - Il campo Deduplication_GroupId mostra il gruppo o il cluster identificato all'interno di un'entità che raggruppa tutti i record simili in base ai campi di deduplicazione specificati. È utilizzato per scopi di elaborazione del sistema. Se non sono state specificate regole di deduplicazione manuale e si applicano regole di deduplicazione definite dal sistema, potresti non trovare questo campo nell'entità di output della deduplicazione.
  - Deduplication_WinnerId: questo campo contiene l'ID vincitore dei gruppi o cluster identificati. Se Deduplication_WinnerId è uguale al valore della chiave primaria per un record, significa che il record è il record vincitore.
- Campi utilizzati per definire le regole di deduplicazione.
- I campi Regola e Punteggio per indicare quale delle regole di deduplicazione è stata applicata e il punteggio restituito dall'algoritmo di corrispondenza.

## <a name="next-step"></a>Passaggio successivo

Configura [Impegni](activities.md), [Arricchimento](enrichment-hub.md) o [Relazioni](relationships.md) per ulteriori informazioni dettagliate sui contatti.
