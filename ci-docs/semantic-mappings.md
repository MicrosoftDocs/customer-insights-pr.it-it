---
title: Mappature semantiche (anteprima)
description: Panoramica delle mappature semantiche e come usarle.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183636"
---
# <a name="semantic-mappings-preview"></a>Mappature semantiche (anteprima)

Le mappature semantiche ti permettono di mappare i tuoi dati non-attività a schemi predefiniti. Questi schemi consentono a Customer Insights di comprendere meglio gli attributi dei dati. Il mapping semantico e i dati forniti consentono nuove informazioni dettagliate e funzionalità in Customer Insights. Per mappare i dati delle vostre attività agli schemi, rivedete la documentazione delle [attività](activities.md) .

Le **mappature semantiche sono attualmente abilitate per gli ambienti basati su conti commerciali**. *ContactProfile* è l'unico tipo di mapping semantico attualmente disponibile in Customer Insights.

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

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Utilizzare il mapping di un'entità semantica ContactProfile per creare attività a livello di contatto

Dopo aver creato il mapping di un'entità semantica *ContactProfile*, puoi acquisire le attività dei contatti. Ti consente di vedere nella sequenza temporale  delle attività per un account quale contatto era responsabile di ciascuna attività. La maggior parte dei passaggi segue la configurazione tipica del mapping delle attività.

   > [!NOTE]
   > Affinché le attività a livello di contatto funzionino, è necessario disporre di entrambi gli attributi **AccountID** e **ContactID** per ogni record all'interno dei dati dell'attività.

1. [Definisci il mapping di un'entità semantica *ContactProfile*](#define-a-contactprofile-semantic-entity-mapping) ed esegui il mapping semantico.

1. Vai a **Dati** > **Impegni**.

1. Seleziona **Aggiungi attività** per creare una nuova attività.

1. Assegna un nome all'attività, seleziona l'entità dell'attività di origine e seleziona la chiave primaria dell'entità dell'attività.

1. Nel passaggio **Relazioni** crea una relazione indiretta tra i dati di origine dell'attività e gli account, utilizzando i tuoi dati di contatto come entità intermediaria. Per ulteriori informazioni, vedi [percorsi di relazione diretti e indiretti](relationships.md#relationship-paths).
   - Esempio di relazione per un'attività chiamata *Acquisti*:
      - **Dati sull'attività di origine degli acquisti** > **Informazioni di contatto** sull'attributo **ContactID**
      - **Informazioni di contatto** > **Dati dell'account** sull'attributo **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Esempio di configurazione della relazione.":::

1. Dopo aver impostato le relazioni, seleziona **Avanti** e completa la configurazione del mapping delle attività. Per i passaggi dettagliati sulla creazione dell'attività, vedi [definire un'attività](activities.md).

1. Esegui le mappature delle tue attività.

1. Dopo l'esecuzione di un mapping delle attività a livello di contatto, seleziona **Clienti**. Le attività a livello di contatto sono visualizzate nella sequenza temporale dei clienti.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Risultato finale dopo la configurazione delle attività di contatto":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtraggio della sequenza temporale delle attività a livello di contatto

La sequenza temporale delle attività per i tuoi clienti Include i loro ID o nomi, a seconda della configurazione *ContactProfile*, per le attività su cui hanno agito. Filtra le attività in base ai contatti nella sequenza temporale per visualizzare specifici contatti a cui sei interessato. Per visualizzare tutte le attività che non sono assegnate a uno specifico contatto, seleziona **Attività non mappate a un contatto**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Opzioni di filtro disponibili per le attività a livello di contatto.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
