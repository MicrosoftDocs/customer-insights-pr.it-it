---
title: Mappature semantiche (anteprima)
description: Panoramica delle mappature semantiche e come usarle.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303881"
---
# <a name="semantic-mappings-preview"></a>Mappature semantiche (anteprima)

> [!NOTE]
> La pagina **Mappature semantiche** è disponibile solo per gli ambienti aziendali (B2B) in cui i profili di contatto sono già stati creati utilizzando questa pagina. Puoi continuare a creare e gestire i singoli profili di contatto utilizzando la pagina **Mappature semantiche**. Oppure, [unifica i tuoi dati di contatto](data-unification-contacts.md) per rimuovere i duplicati, identificare corrispondenze tra entità e creare un profilo di contatto unificato. Puoi quindi usare un profilo di contatto unificato per creare attività a livello di contatto.

Le mappature semantiche ti permettono di mappare i tuoi dati non-attività a schemi predefiniti. Questi schemi aiutano Customer Insights a comprendere meglio gli attributi dei dati. La mappatura semantica e i dati forniti consentono nuove informazioni dettagliate e funzionalità in Customer Insights. Per mappare i dati delle vostre attività agli schemi, rivedete la documentazione delle [attività](activities.md) .

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definire il mapping di un'entità semantica ContactProfile

1. Vai a **Dati** > **Mappature semantiche (anteprima)**.

1. Seleziona **Aggiungi mapping semantico** per iniziare l'esperienza guidata.

1. Nel passo **Dati entità** , impostate i valori per i seguenti campi:

   - **Nome mapping di entità semantica**: il nome del mapping dell'entità semantica.
   - **Entità di origine**: l'entità che include i dati di contatto.
   - **Chiave primaria**: il campo che identifica in modo univoco un record di contatto. Non deve contenere valori duplicati, valori vuoti o valori mancanti.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Impostare il mapping dell'entità semantica con nome, entità di origine e chiave primaria.":::

1. Selezionare **Avanti**.

1. Nel passo **Relazioni** , configura i dettagli per collegare i tuoi dati di contatto ai dati dell'account corrispondente. Questo passaggio visualizza la connessione tra le entità.  

   Ci sono due tipi di percorsi di relazione che possono essere implementati: **Relazioni dirette** e **relazioni indirette**. Per maggiori informazioni, vai a [percorsi di relazioni dirette e indirette](relationships.md#relationship-paths).

   1. Seleziona **Aggiungi relazione** per configurare la relazione.
   1. Scegli l'attributo della tua entità di origine che collega la tua entità di contatto ad un'altra entità.
   1. Scegli l'entità a cui collegare la tua entità di contatto. Scegli un'entità nella sezione **Entità account** o **Entità intermedia**. Se selezioni un'entità intermedia, definisci una seconda relazione per eseguire la connessione all'entità account di destinazione.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Selezionare un'entità conto o un'entità intermedia.":::

   1. Fornire un **nome di relazione**. Se una relazione tra le tue entità esiste già, il nome della relazione è di sola lettura. Se non esiste alcuna relazione, verrà creata una nuova relazione con il nome fornito.
   1. Seleziona **Applica** per finire la configurazione della relazione.

   > [!NOTE]
   > È possibile configurare più relazioni tra l'entità contatto e altre entità di conto con entità intermedie.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualizzazione di varie relazioni che collegano le entità di contatto alle entità di conto.":::

1. Selezionare **Avanti**.

1. Nel passo **Imposta il tipo semantico** , scegli un **tipo semantico**. Attualmente, c'è un **tipo semantico** chiamato *ContactProfile*.

1. Mappa il tuo ID contatto al tipo semantico *ContactProfile* **ID contatto**. Eventualmente, mappa altri campi come Nome, Cognome, Sesso o Indirizzo email.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mappate i vostri attributi di dati di contatto ai campi obbligatori e opzionali forniti.":::

1. Selezionare **Avanti**.

1. Nel passaggio **Rivedi**, esamina la configurazione del mapping semantico. Per apportare modifiche, seleziona **Modifica** per la sezione corrispondente.

1. Seleziona **Salva**.

1. Seleziona **Esegui** per elaborare il mapping semantico. Oppure seleziona **Chiudi** per salvare il mapping semantico senza elaborarlo. Per eseguirlo successivamente, seleziona il mapping semantico e seleziona **Aggiorna**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Gestire le mappature semantiche esistenti

Vai a **Dati** > **Mapping semantici (anteprima)** per visualizzare i mapping semantici salvati, l'entità di origine, il tipo semantico, il tipo di mapping e lo stato.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opzioni per gestire le mappature semantiche.":::

Seleziona il mapping semantico per visualizzare le azioni disponibili.
- **Modifica** la configurazione corrente. Seleziona **Salva** ed **Esegui** per elaborare le modifiche.
- **Aggiorna** il mapping semantico per includere i dati più recenti. L'aggiornamento di un dato mapping semantico aggiornerà tutti i mapping semantici dello stesso tipo.
- **Rinomina** il mapping semantico. Seleziona **Salva**.
- **Elimina** il mapping semantico. Per eliminare più di un mapping semantico alla volta, seleziona i mapping semantici e l'icona di eliminazione. Per confermare l'eliminazione seleziona **Elimina**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
