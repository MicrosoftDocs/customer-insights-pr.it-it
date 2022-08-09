---
title: Attività dei clienti
description: Definisci le attività dei clienti e visualizzale in una sequenza temporale sui profili dei clienti.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188144"
---
# <a name="customer-activities"></a>Attività dei clienti

Le attività dei clienti sono azioni o eventi eseguiti dai clienti. Ad esempio, transazioni, durata della chiamata di assistenza, recensioni sul sito Web, acquisti o resi. Queste attività sono contenute in una o più origini dati. Con Customers Insights, consolida le attività dei tuoi clienti a partire da queste [origini dati](data-sources.md) e associale ai profili cliente. Queste attività sono visualizzate cronologicamente in una sequenza temporale nel profilo cliente. Includi la sequenza temporale nelle app Dynamics 365 con la soluzione [Componente aggiuntivo Scheda cliente](customer-card-add-in.md) soluzione.

## <a name="define-an-activity"></a>Definire un'attività

Un'entità deve avere almeno un attributo di tipo **Data** per essere incluso in una sequenza temporale del cliente. Il controllo **Aggiungi impegno** è disabilitato se non viene trovata tale entità.

1. Vai a **Dati** > **Impegni**.

1. Seleziona **Aggiungi attività** per iniziare l'esperienza guidata.

1. Nel passaggio **Dati attività** immetti le informazioni seguenti:

   - **Nome attività**: il nome dell'attività.
   - **Entità attività**: l'entità che include dati transazionali o dati sull'attività.
   - **Chiave primaria**: campo che identifica in modo univoco un record. Non deve contenere valori duplicati, valori vuoti o valori mancanti.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Imposta i dati dell'impegno con nome, entità e chiave primaria.":::

1. Selezionare **Avanti**.

1. Nel passaggio **Relazione**, seleziona **Aggiungi relazione** per connettere i dati dell'attività al relativo record cliente corrispondente. Questo passaggio visualizza la connessione tra le entità.  

   - **Chiave esterna da entità**: campo nell'entità attività che verrà utilizzato per stabilire una relazione con un'altra entità.
   - **A nome entità**: entità cliente di origine corrispondente con la quale l'entità attività sarà in relazione. È possibile fare riferimento solo alle entità del cliente di origine utilizzate nel processo di unificazione dei dati.
   - **Nome relazione**: il nome che identifica la relazione tra le entità. Se esiste già una relazione tra questa entità attività e l'entità cliente di origine selezionata, il nome della relazione sarà di sola lettura.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definisci la relazione dell'entità.":::

   > [!TIP]
   > Negli ambienti B2B, è possibile scegliere tra entità account e altre entità. Se si seleziona un'entità di conto, il percorso della relazione viene impostato automaticamente. Per altre entità, dovete definire il percorso della relazione su una o più entità intermedie fino a raggiungere un'entità conto.

1. Seleziona **Applica** per creare la relazione.

1. Selezionare **Avanti**.

1. Nel passaggio **Unificazione impegno**, scegli l'evento dell'impegno e l'ora di inizio dell'impegno.
   - **Campi obbligatori**
      - **Impegno evento**: Campo che rappresenta l'evento per questo impegno.
      - **Timestamp**: Campo che rappresenta l'ora di inizio dell'impegno.

   - **Campi facoltativi**
      - **Ulteriori dettagli**: Campo con informazioni rilevanti per questo impegno.
      - **Icona**: Icona che rappresenta al meglio questo tipo di impegno.
      - **indirizzo Web**: Campo contenente un URL con informazioni su questo impegno. Ad esempio, il sistema transazionale che genera questo impegno. Questo URL può essere qualsiasi campo dell'origine dati, oppure può essere creato come un nuovo campo usando una trasformazione Power Query. I dati dell'URL verranno archiviati nell'entità *Impegno unificato* che può essere consumata a valle utilizzando le [API](apis.md).

   - **Mostra in sequenza temporale**
      - Scegli se mostrare questo impegno nella visualizzazione sequenza temporale sui profili dei clienti. Seleziona **Sì** per mostrare l'impegno nella sequenza temporale oppure **No** per nasconderlo.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Specifica i dati dell'impegno del cliente in un'entità Impegno unificato.":::

1. Seleziona **Avanti** per scegliere il tipo di attività o seleziona **Finisci e rivedi** per salvare l'attività con il tipo di attività impostato su **Altro**.

1. Nel passaggio **Tipo di impegno** scegli il tipo di impegno e, facoltativamente, seleziona se vuoi mappare semanticamente alcuni tipi di impegno da utilizzare in altre aree di Customer Insights. Attualmente, i tipi di impegno *Feedback*, *Fedeltà*, *SalesOrder*, *SalesOrderLine* e *Abbonamento* supportano la semantica dopo aver accettato di mappare i campi. Se un tipo di impegno non è pertinente per il nuovo impegno, puoi scegliere *Altro* o *Crea nuovo* per un tipo di impegno personalizzato.

1. Selezionare **Avanti**.

1. Nel passaggio **Rivedi**, verifica le tue selezioni. Torna a uno dei passaggi precedenti e aggiorna le informazioni se necessario.

1. Seleziona **Salva impegno** per applicare le modifiche e seleziona **Fatto** per tornare a **Dati** > **Impegni**. Viene visualizzata l'attività creata.

1. Dopo aver creato tutte le attività, seleziona **Esegui** per elaborarle.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Gestire gli impegni esistenti

Vai a **Dati** > **Attività** per visualizzare le attività salvate, la relativa entità di origine, il tipo di attività e se sono incluse nella sequenza temporale del cliente. Puoi ordinare l'elenco delle attività in base a qualsiasi colonna o utilizzare la casella di ricerca per trovare l'attività che desideri gestire.

Seleziona un'attività per visualizzare le azioni disponibili.

- **Modifica** l'attività per cambiarne la configurazione. La configurazione viene visualizzata nel passaggio Esamina. Dopo aver modificato la configurazione, seleziona **Salva impegno** e poi seleziona **Esegui** per elaborare le modifiche.
- **Rinomina** l'attività. Seleziona **Salva** per applicare le modifiche.
- **Elimina** l'attività. Per eliminare più attività contemporaneamente, seleziona le attività e quindi **Elimina**. Conferma l'eliminazione.

## <a name="view-activity-timelines-on-customer-profiles"></a>Visualizzare la cronologia delle attività sui profili dei clienti

1. Se hai selezionato **Mostra in sequenza temporale attività** nella configurazione delle attività, vai a **Clienti** e seleziona un profilo cliente per visualizzare le attività del cliente nella sezione **Sequenza temporale attività**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Visualizzare le attività configurate nei profili dei clienti.":::

1. Per filtrare le attività nella sequenza temporale delle attività:

   - Seleziona una o più delle icone di attività per affinare i risultati e includere solo il tipo o i tipi selezionati.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrare le attività per tipo usando le icone.":::

   - Seleziona **Filtro** per aprire un pannello di filtri e configurare i filtri della sequenza temporale. Filtra per *ActivityType* e/o *Data*. Seleziona **Applica**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Usa il pannello dei filtri per configurare le condizioni del filtro.":::

1. Per rimuovere i filtri, seleziona **Cancella filtri** o seleziona **Filtro** e deseleziona la casella di controllo del filtro.

> [!NOTE]
> I filtri di attività vengono rimossi quando si lascia un profilo cliente. Devi applicarli ogni volta che apri un profilo cliente.

[!INCLUDE [footer-include](includes/footer-banner.md)]
