---
title: Impegni cliente
description: Definisci gli impegni cliente e visualizzali nella sequenza temporale del cliente.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304931"
---
# <a name="customer-activities"></a>Impegni cliente

Combina le attività dei clienti da [varie origini di dati](data-sources.md) in Dynamics 365 Customer Insights per creare una sequenza temporale che elenchi le attività in ordine cronologico. Includi la sequenza temporale nelle app Dynamics 365 con la soluzione [Componente aggiuntivo Scheda cliente](customer-card-add-in.md) o in un dashboard Power BI.

## <a name="define-an-activity"></a>Definire un impegno

Le tue origini dati possono includere entità con dati transazionali e dati di impegni provenienti da più origini dati. Identifica queste entità e seleziona gli impegni che vuoi visualizzare nella sequenza temporale del cliente. Scegli l'entità che include il tuo impegno o i tuoi impegni di destinazione.

> [!NOTE]
> Un'entità deve avere almeno un attributo di tipo **Data** per essere incluso in una sequenza temporale del cliente e non puoi aggiungere entità senza campi **Data**. Il controllo **Aggiungi impegno** è disabilitato se non viene trovata tale entità.

1. In Audience Insights, vai a **Dati** > **Impegni**.

1. Seleziona **Aggiungi impegno** per avviare l'esperienza guidata per il processo di configurazione dell'impegno.

1. Nel passaggio **Dati sull'impegno** imposta i valori per i seguenti campi:

   - **Nome impegno**: Seleziona un nome per l'impegno.
   - **Entità**: seleziona un'entità che include dati transazionali o di impegni.
   - **Chiave primaria**: seleziona il campo che identifica in modo univoco un record. Non deve contenere valori duplicati, valori vuoti o valori mancanti.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Imposta i dati dell'impegno con nome, entità e chiave primaria.":::

1. Seleziona **Avanti** per procedere al passaggio successivo.

1. Nel passaggio **Relazione**, configura i dettagli per connettere i dati dell'impegno al cliente corrispondente. Questo passaggio visualizza la connessione tra le entità.  

   - **Primo**: Campo esterno nell'entità dell'impegno che verrà utilizzato per stabilire una relazione con un'altra entità.
   - **Secondo**: Entità cliente di origine corrispondente con la quale l'entità impegno sarà in relazione. È possibile fare riferimento solo alle entità del cliente di origine utilizzate nel processo di unificazione dei dati.
   - **Terzo**: Se esiste già una relazione tra questa entità impegno e l'entità cliente di origine selezionata, il nome della relazione sarà in modalità di sola lettura. Se non esiste tale relazione, verrà creata una nuova relazione con il nome fornito in questa casella.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definisci la relazione dell'entità.":::

1. Seleziona **Avanti** per procedere al passaggio successivo. 

1. Nel passaggio **Unificazione impegno**, scegli l'evento dell'impegno e l'ora di inizio dell'impegno. 
   - **Campi obbligatori**
      - **Impegno evento**: Campo che rappresenta l'evento per questo impegno.
      - **Timestamp**: Campo che rappresenta l'ora di inizio dell'impegno.

   - **Campi facoltativi**
      - **Ulteriori dettagli**: Campo con informazioni rilevanti per questo impegno.
      - **Icona**: Icona che rappresenta al meglio questo tipo di impegno.
      - **indirizzo Web**: Campo contenente un URL con informazioni su questo impegno. Ad esempio, il sistema transazionale che genera questo impegno. Questo URL può essere qualsiasi campo di origine dati oppure può essere costruito come un nuovo campo usando una trasformazione Power Query. I dati dell'URL verranno archiviati nell'entità *Impegno unificato* che può essere consumata a valle utilizzando le [API](apis.md).
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Specifica i dati dell'impegno del cliente in un'entità Impegno unificato.":::

1. Seleziona **Avanti** per passare al passaggio successivo. Puoi selezionare **Termina e rivedi** per salvare l'impegno ora con il tipo di impegno impostato su **Altro**. 

1. Nel passaggio **Tipo di impegno** scegli il tipo di impegno e, facoltativamente, seleziona se vuoi mappare semanticamente alcuni tipi di impegno da utilizzare in altre aree di Customer Insights. Attualmente, i tipi di attività *Sottoscrizione* e *SalesOrderLine* possono essere mappati semanticamente dopo aver accettato di mappare i campi. Se un tipo di impegno non è pertinente per il nuovo impegno, puoi scegliere *Altro* o *Crea nuovo* per un tipo di impegno personalizzato.

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]
