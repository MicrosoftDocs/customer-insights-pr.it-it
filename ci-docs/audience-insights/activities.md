---
title: Impegni cliente
description: Definisci le attività dei clienti e visualizzale in una sequenza temporale sui profili dei clienti.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c250efcd54ec126c0726b22a971cdedd89760d6b
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617974"
---
# <a name="customer-activities"></a>Impegni cliente

Combina le attività dei clienti da [varie origini di dati](data-sources.md) in Dynamics 365 Customer Insights per creare una sequenza temporale che elenchi le attività in ordine cronologico. Includi la sequenza temporale nelle app Dynamics 365 con la soluzione [Componente aggiuntivo Scheda cliente](customer-card-add-in.md) o in un dashboard Power BI.

## <a name="define-an-activity"></a>Definire un impegno

Le tue origini dati possono includere entità con dati transazionali e dati di impegni provenienti da più origini dati. Identifica queste entità e seleziona gli impegni che vuoi visualizzare nella sequenza temporale del cliente. Scegli l'entità che include il tuo impegno o i tuoi impegni di destinazione.

Un'entità deve avere almeno un attributo di tipo **Data** per essere incluso in una sequenza temporale del cliente e non puoi aggiungere entità senza campi **Data**. Il controllo **Aggiungi impegno** è disabilitato se non viene trovata tale entità.

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Dati** > **Impegni**.

1. Seleziona **Aggiungi impegno** per avviare l'esperienza guidata per il processo di configurazione dell'impegno.

1. Nel passaggio **Dati sull'impegno** imposta i valori per i seguenti campi:

   - **Nome impegno**: Seleziona un nome per l'impegno.
   - **Entità**: seleziona un'entità che include dati transazionali o di impegni.
   - **Chiave primaria**: seleziona il campo che identifica in modo univoco un record. Non deve contenere valori duplicati, valori vuoti o valori mancanti.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Imposta i dati dell'impegno con nome, entità e chiave primaria.":::

1. Seleziona **Avanti** per procedere al passaggio successivo.

1. Nel passo **Relazione** , configura i dettagli per collegare i dati della tua attività al suo record di cliente corrispondente. Questo passaggio visualizza la connessione tra le entità.  

   - **Primo**: Campo esterno nell'entità dell'impegno che verrà utilizzato per stabilire una relazione con un'altra entità.
   - **Secondo**: Entità cliente di origine corrispondente con la quale l'entità impegno sarà in relazione. È possibile fare riferimento solo alle entità del cliente di origine utilizzate nel processo di unificazione dei dati.
   - **Terzo**: Se esiste già una relazione tra questa entità impegno e l'entità cliente di origine selezionata, il nome della relazione sarà in modalità di sola lettura. Se non esiste tale relazione, verrà creata una nuova relazione con il nome fornito in questa casella.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definisci la relazione dell'entità.":::

   > [!TIP]
   > In ambienti B2B, è possibile selezionare tra entità di conto e altre entità. Se si seleziona un'entità di conto, il percorso della relazione viene impostato automaticamente. Per altre entità, dovete definire il percorso della relazione su una o più entità intermedie fino a raggiungere un'entità conto.

1. Seleziona **Avanti** per procedere al passaggio successivo. 

1. Nel passaggio **Unificazione impegno**, scegli l'evento dell'impegno e l'ora di inizio dell'impegno. 
   - **Campi obbligatori**
      - **Impegno evento**: Campo che rappresenta l'evento per questo impegno.
      - **Timestamp**: Campo che rappresenta l'ora di inizio dell'impegno.

   - **Campi facoltativi**
      - **Ulteriori dettagli**: Campo con informazioni rilevanti per questo impegno.
      - **Icona**: Icona che rappresenta al meglio questo tipo di impegno.
      - **indirizzo Web**: Campo contenente un URL con informazioni su questo impegno. Ad esempio, il sistema transazionale che genera questo impegno. Questo URL può essere qualsiasi campo di origine dati oppure può essere costruito come un nuovo campo usando una trasformazione Power Query. I dati dell'URL verranno archiviati nell'entità *Impegno unificato* che può essere consumata a valle utilizzando le [API](apis.md).

   - **Mostra in sequenza temporale**
      - Scegli se mostrare questo impegno nella visualizzazione sequenza temporale sui profili dei clienti. Seleziona **Sì** per mostrare l'impegno nella sequenza temporale oppure **No** per nasconderlo.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Specifica i dati dell'impegno del cliente in un'entità Impegno unificato.":::

1. Seleziona **Avanti** per passare al passaggio successivo. Puoi selezionare **Termina e rivedi** per salvare l'impegno ora con il tipo di impegno impostato su **Altro**. 

1. Nel passaggio **Tipo di impegno** scegli il tipo di impegno e, facoltativamente, seleziona se vuoi mappare semanticamente alcuni tipi di impegno da utilizzare in altre aree di Customer Insights. Attualmente, i tipi di impegno *Feedback*, *Loyalty*, *SalesOrder*, *SalesOrderLine* e *Subscription* possono essere mappati semanticamente dopo aver accettato di mappare i campi. Se un tipo di impegno non è pertinente per il nuovo impegno, puoi scegliere *Altro* o *Crea nuovo* per un tipo di impegno personalizzato.

1. Seleziona **Avanti** per passare al passaggio successivo. 

1. Nel passaggio **Rivedi**, verifica le tue selezioni. Torna a uno dei passaggi precedenti e aggiorna le informazioni se necessario.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Rivedi i campi specificati per un impegno.":::
   
1. Seleziona **Salva impegno** per applicare le modifiche e seleziona **Fatto** per tornare a **Dati** > **Impegni**. Qui puoi vedere quali impegni sono impostati per essere mostrati nella sequenza temporale. 

1. Nella pagina **Impegni** seleziona **Esegui** per elaborare l'impegno. 

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.


## <a name="manage-existing-activities"></a>Gestire gli impegni esistenti

In **Dati** > **Impegni**, puoi visualizzare tutti gli impegni salvati e gestirli. Ogni impegno è rappresentato da una riga che include anche i dettagli sull'origine, l'entità e il tipo di impegno.

Le seguenti azioni sono disponibili quando selezioni un impegno. 

- **Modifica**: Apre la configurazione dell'impegno nella fase di revisione. Puoi modificare parte o tutta la configurazione corrente da questo passaggio. Dopo aver modificato la configurazione, seleziona **Salva impegno** e poi seleziona **Esegui** per elaborare le modifiche.

- **Rinomina**: apre una finestra di dialogo in cui puoi inserire un nome diverso per l'attività selezionata. Seleziona **Salva** per applicare le modifiche.

- **Elimina**: Apre una finestra di dialogo per confermare l'eliminazione dell'impegno selezionato. È inoltre possibile eliminare più di un impegno contemporaneamente selezionando gli impegni e quindi l'icona di eliminazione. Per confermare l'eliminazione seleziona **Elimina**.

## <a name="view-activity-timelines-on-customer-profiles"></a>Visualizzare la cronologia delle attività sui profili dei clienti

Dopo aver configurato le attività del cliente, seleziona **Mostra in cronologia attività** nella configurazione delle attività per trovare tutte le attività del tuo cliente sul suo profilo cliente.

Per aprire la linea temporale di un cliente, vai a **Clienti** e scegli il profilo del cliente che vuoi visualizzare.

Se un cliente ha partecipato a un'attività che hai configurato, lo troverai nella sezione **Cronologia delle attività** .

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Visualizzare le attività configurate nei profili dei clienti.":::

Ci sono diversi modi per filtrare le attività nella timeline delle attività:

- Puoi selezionare una o molte delle icone di attività per raffinare i tuoi risultati e includere solo il tipo o i tipi selezionati.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrare le attività per tipo usando le icone.":::

- Puoi selezionare **Filtro** per aprire un pannello di filtri per configurare i tuoi filtri della linea temporale.

   1. È possibile filtrare per *TipoAttività* e *Data*
   1. Seleziona **Applica** per utilizzare i filtri nella timeline dell'attività.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Usa il pannello dei filtri per configurare le condizioni del filtro.":::

Per rimuovere i filtri, seleziona la **x** accanto ad ogni filtro applicato alla linea temporale o seleziona **Cancella filtri**.


> [!NOTE]
> I filtri di attività vengono rimossi quando si lascia un profilo cliente. Dovete applicarli ogni volta che aprite un profilo cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
