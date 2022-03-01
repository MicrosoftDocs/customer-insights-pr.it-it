---
title: Mappature semantiche (Anteprima)
description: Panoramica delle mappature semantiche e come usarle.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622940"
---
# <a name="semantic-mappings"></a>Mappature semantiche

Le mappature semantiche ti permettono di mappare i tuoi dati non-attività a schemi predefiniti. Questi schemi aiutano il pubblico a capire meglio gli attributi dei vostri dati. La mappatura semantica e i dati forniti permettono nuove intuizioni e caratteristiche negli insight del pubblico. Per mappare i dati delle vostre attività agli schemi, rivedete la documentazione delle [attività](activities.md) .

Le **mappature semantiche sono attualmente abilitate per gli ambienti basati su conti commerciali**. *ProfiloContatto* è l'unico tipo di mappatura semantica attualmente disponibile in approfondimenti sul pubblico.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definire una mappatura semantica dell'entità ContactProfile

1. In approfondimenti sul pubblico, vai a **Data** > **Semantic mappings (anteprima)**.

1. Seleziona **Aggiungi la mappatura semantica** per iniziare l'esperienza guidata.

1. Nel passo **Dati entità** , impostate i valori per i seguenti campi:

   - **Nome di mappatura dell'entità semantica**: Fornisci un nome per la tua mappatura semantica delle entità.
   - **Entità di origine**: Seleziona un'entità che include i dati di contatto.
   - **Chiave primaria**: Seleziona il campo che identifica univocamente un record di contatto. Non deve contenere valori duplicati, valori vuoti o valori mancanti.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Impostare la mappatura semantica delle entità con nome, entità di origine e chiave primaria.":::

1. Selezionare **Avanti** per continuare.

1. Nel passo **Relazioni** , configura i dettagli per collegare i tuoi dati di contatto ai dati dell'account corrispondente. Questo passaggio visualizza la connessione tra le entità.  

   Ci sono due tipi di percorsi di relazione che possono essere implementati: **Relazioni dirette** e **relazioni indirette**. Per maggiori informazioni, vai a [percorsi di relazioni dirette e indirette](relationships.md#relationship-paths).

   1. Selezionare **Aggiungi relazione** per configurare la relazione.
   1. Scegli l'attributo della tua entità di origine che collega la tua entità di contatto ad un'altra entità.
   1. Scegli l'entità a cui collegare la tua entità di contatto. Puoi scegliere un'entità dalla sezione **Entità del conto** o dall' **entità intermedia** . Se si seleziona un'entità intermedia, è necessario definire una seconda relazione per connettersi all'entità di destinazione del conto.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Selezionare un'entità conto o un'entità intermedia.":::

   1. Fornire un **nome di relazione**. Se una relazione tra le tue entità esiste già, il nome della relazione è di sola lettura. Se non esiste alcuna relazione, verrà creata una nuova relazione con il nome fornito.
   1. Seleziona **Applica** per finire la configurazione della relazione.

   > [!NOTE]
   > È possibile configurare più relazioni tra l'entità contatto e altre entità di conto con entità intermedie.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualizzazione di varie relazioni che collegano le entità di contatto alle entità di conto.":::

1. Seleziona **Avanti** quando hai finito con la configurazione della relazione.

1. Nel passo **Imposta il tipo semantico** , scegli un **tipo semantico**. Attualmente, c'è un **tipo semantico** chiamato *ContactProfile*.

1. Mappa i tuoi dati al **tipo semantico**  *ContactProfile* per i campi mostrati.
   - Campo obbligatorio: ID contatto
   - Campi opzionali: Nome, cognome, data di nascita, sesso, email principale e telefono principale

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mappate i vostri attributi di dati di contatto ai campi obbligatori e opzionali forniti.":::

1. Selezionare **Avanti** per continuare.

1. Nella fase di **revisione** , dai un'occhiata alla configurazione della mappatura semantica. Seleziona **Modifica** per la sezione corrispondente per apportare modifiche.

1. Seleziona **Save** per salvare la tua nuova **mappatura semantica**.

1. Dopo aver salvato, puoi selezionare **Run** process the semantic mapping o puoi selezionare **Close** per salvare la tua mappatura semantica senza elaborarla.

1. Per eseguire una mappatura semantica in un momento successivo, seleziona la mappatura semantica e seleziona **Refresh**.

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.

## <a name="manage-existing-semantic-mappings"></a>Gestire le mappature semantiche esistenti

Su **Data** > **Mappature semantiche (anteprima)**, puoi visualizzare tutte le tue mappature semantiche salvate e gestirle. Ogni mappatura semantica è rappresentata da una riga separata. Troverai i dettagli sull'entità sorgente, il tipo semantico, il tipo di mappatura e il suo stato.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opzioni per gestire le mappature semantiche.":::

- **Modifica**: Apre la configurazione dell'impostazione della mappatura semantica nel passo di revisione. È possibile cambiare la configurazione corrente. Seleziona **Salva** ed **Esegui** per elaborare le modifiche.

- **Rinfrescare**: Aggiorna la mappatura semantica selezionata con i dati più aggiornati delle entità che fanno parte della sua configurazione. Il refresh di una data mappatura semantica aggiornerà tutte le mappature semantiche dello stesso tipo.

- **Rinominare**: Apre una finestra di dialogo dove è possibile inserire un nome diverso per la mappatura semantica selezionata. Seleziona **Salva** per applicare le modifiche.

- **Cancellare**: Apre una finestra di dialogo per confermare l'eliminazione della mappatura semantica selezionata. Puoi anche cancellare più di una mappatura semantica alla volta selezionando le mappature semantiche e l'icona di cancellazione. Per confermare l'eliminazione seleziona **Elimina**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
