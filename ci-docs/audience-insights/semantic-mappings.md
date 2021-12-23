---
title: Mappature semantiche (Anteprima)
description: Panoramica delle mappature semantiche e come usarle.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881835"
---
# <a name="semantic-mappings-preview"></a>Mappature semantiche (Anteprima)

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Gestire le mappature semantiche esistenti

Su **Data** > **Mappature semantiche (anteprima)**, puoi visualizzare tutte le tue mappature semantiche salvate e gestirle. Ogni mappatura semantica è rappresentata da una riga separata. Troverai i dettagli sull'entità sorgente, il tipo semantico, il tipo di mappatura e il suo stato.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opzioni per gestire le mappature semantiche.":::

- **Modifica**: Apre la configurazione dell'impostazione della mappatura semantica nel passo di revisione. È possibile cambiare la configurazione corrente. Seleziona **Salva** ed **Esegui** per elaborare le modifiche.

- **Rinfrescare**: Aggiorna la mappatura semantica selezionata con i dati più aggiornati delle entità che fanno parte della sua configurazione. Il refresh di una data mappatura semantica aggiornerà tutte le mappature semantiche dello stesso tipo.

- **Rinominare**: Apre una finestra di dialogo dove è possibile inserire un nome diverso per la mappatura semantica selezionata. Seleziona **Salva** per applicare le modifiche.

- **Cancellare**: Apre una finestra di dialogo per confermare l'eliminazione della mappatura semantica selezionata. Puoi anche cancellare più di una mappatura semantica alla volta selezionando le mappature semantiche e l'icona di cancellazione. Per confermare l'eliminazione seleziona **Elimina**.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Utilizzare una mappatura di entità semantiche ContactProfile per creare attività a livello di contatto

Dopo aver creato una mappatura delle entità semantiche *ContactProfile*, è possibile acquisire le attività dei contatti. Ti consente di vedere nella cronologia delle attività per un account quale contatto era responsabile di ciascuna attività. La maggior parte dei passaggi segue la configurazione tipica della mappatura delle attività.

   > [!NOTE]
   > Affinché le attività a livello di contatto funzionino, è necessario disporre di entrambi gli attributi **AccountID** e **ContactID** per ogni record all'interno dei dati dell'attività.

1. [Definire una mappatura semantica dell'entità *ContactProfile*.](#define-a-contactprofile-semantic-entity-mapping) ed eseguire la mappatura semantica.

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Dati** > **Impegni**.

1. Seleziona **Aggiungi attività** per creare una nuova attività.

1. Assegna un nome all'attività, seleziona l'entità dell'attività di origine e seleziona la chiave primaria dell'entità dell'attività.

1. Nel passaggio **Relazioni** crea una relazione indiretta tra i dati di origine dell'attività e gli account, utilizzando i tuoi dati di contatto come entità intermediaria. Per ulteriori informazioni, vedi [percorsi di relazione diretti e indiretti](relationships.md#relationship-paths).
   - Esempio di relazione per un'attività chiamata *Acquisti*:
      - **Dati sull'attività di origine degli acquisti** > **Informazioni di contatto** sull'attributo **ContactID**
      - **Informazioni di contatto** > **Dati dell'account** sull'attributo **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Esempio di configurazione della relazione.":::

1. Dopo aver impostato le relazioni, seleziona **Avanti** e completa la configurazione della mappatura delle attività. Per i passaggi dettagliati sulla creazione dell'attività, vedi [definire un'attività](activities.md).

1. Esegui le mappature delle tue attività.

1. Le tue attività a livello di contatto saranno ora visibili sulla cronologia dei tuoi clienti.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Risultato finale dopo la configurazione delle attività di contatto":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtraggio della sequenza temporale delle attività a livello di contatto

Dopo aver configurato una mappatura delle attività a livello di contatto e averla eseguita, la cronologia delle attività per i tuoi clienti verrà aggiornata. Include i loro ID o nomi, a seconda della tua configurazione *ContactProfile*, per le attività su cui hanno agito. Puoi filtrare le attività in base ai contatti nella sequenza temporale per visualizzare i contatti specifici a cui sei interessato. Inoltre, puoi vedere tutte le attività che non sono assegnate a un contatto specifico selezionando **Attività non mappate a un contatto**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opzioni di filtro disponibili per le attività a livello di contatto.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
