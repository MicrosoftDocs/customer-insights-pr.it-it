---
title: Unire entità nel processo di unificazione dei dati
description: Unisci entità per creare profili cliente unificati.
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494324"
---
# <a name="merge-entities"></a>Gestire entità

La fase di unione è l'ultima fase del processo di unificazione dei dati. Il suo scopo è la riconciliazione di dati in conflitto. Esempi di dati in conflitto potrebbero includere il nome di un cliente che si trova in due dei tuoi set di dati ma si presenta in modo leggermente diverso in ciascuno ("Grant Marshall" rispetto a "Grant Marshal") o un numero di telefono che differisce nel formato (617-803-091X rispetto a 617803091X). L'unione di tali punti di dati in conflitto viene eseguita in base all'attributo per attributo.

:::image type="content" source="media/merge-fields-page.png" alt-text="Pagina di unione nel processo di unificazione dei dati che mostra la tabella con i campi uniti che definiscono il profilo del cliente unificato.":::

Dopo aver completato la [fase di corrispondenza](match-entities.md), avvii la fase di unione selezionando il riquadro **Unione** nella pagina **Unifica**.

## <a name="review-system-recommendations"></a>Rivedere gli elementi consigliati del sistema

In **Dati** > **Unifica** > **Unisci**, scegli ed escludi gli attributi da unire all'interno dell'entità del profilo del cliente unificato. Il profilo del cliente unificato è il risultato del processo di unificazione dei dati. Alcuni attributi vengono automaticamente uniti dal sistema.

Per visualizzare gli attributi inclusi in uno degli attributi uniti automaticamente, seleziona quell'attributo unito nella scheda **Campi cliente** della tabella. Gli attributi che compongono l'attributo unito verranno visualizzati in due nuove righe sotto l'attributo unito.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Separare, rinominare, escludere e modificare i campi uniti

È possibile modificare il modo in cui il sistema elabora gli attributi uniti per generare il profilo del cliente unificato. Seleziona **Mostra altro** e scegli cosa vuoi cambiare.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opzioni nel menu a discesa Mostra altro per gestire gli attributi uniti.":::

Per ulteriori informazioni, vedi la sezione riportata di seguito.

## <a name="separate-merged-fields"></a>Separare i campi uniti

Per separare i campi uniti, trova l'attributo nella tabella. I campi separati vengono visualizzati come punti dati individuali nel profilo del cliente unificato. 

1. Seleziona il campo unito.
  
1. Seleziona **Mostra altro** e scegli **Separa campi**.
 
1. Conferma la separazione.

1. Seleziona **Salva** ed **Esegui** per elaborare le modifiche.

## <a name="rename-merged-fields"></a>Rinominare i campi uniti

Modifica il nome visualizzato degli attributi uniti. Non è possibile modificare il nome dell'entità di output.

1. Seleziona il campo unito.
  
1. Seleziona **Mostra altro** e scegli **Rinomina**.

1. Conferma il nome visualizzato modificato. 

1. Seleziona **Salva** ed **Esegui** per elaborare le modifiche.

## <a name="exclude-merged-fields"></a>Escludere i campi uniti

Escludi un attributo dal profilo del cliente unificato. Se il campo viene utilizzato in altri processi, ad esempio in un segmento, rimuovilo da questi processi prima di escluderlo dal profilo del cliente. 

1. Seleziona un campo unito.
  
1. Seleziona **Mostra altro** e scegli **Escludi**.

1. Conferma l'esclusione.

1. Seleziona **Salva** ed **Esegui** per elaborare le modifiche. 

Nella pagina **Unisci** seleziona **Campi esclusi** per vedere l'elenco di tutti i campi esclusi. Questo riquadro consente di aggiungere nuovamente i campi esclusi.

## <a name="edit-a-merged-field"></a>Modificare un campo unito

1.  Seleziona un campo unito.

1.  Seleziona **Mostra altro** e scegli **Modifica**.

1.  Specifica come combinare o unire i campi tramite una delle tre opzioni:
    - **Importanza**: identifica il valore prevalente in base al grado di importanza specificato per i campi partecipanti. È l'opzione di unione predefinita. Seleziona **Sposta su/giù** per impostare la classifica per importanza.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Opzione di importanza nella finestra di dialogo dei campi di unione."::: 
    - **Più recente**: identifica il valore prevalente in base alla maggiore recency. Richiede un campo data o numerico per ogni entità partecipante nell'ambito dei campi di unione per definire la recency.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Opzione di recency nella finestra di dialogo dei campi di unione.":::
    - **Meno recente**: identifica il valore prevalente in base alla minore recency. Richiede un campo data o numerico per ogni entità partecipante nell'ambito dei campi di unione per definire la recency.

1.  Puoi aggiungere ulteriori campi per partecipare al processo di unione.

1.  Puoi rinominare il campo unito.

1. Seleziona **Fatto** per applicare le modifiche.

1. Seleziona **Salva** ed **Esegui** per elaborare le modifiche. 

## <a name="manually-combine-fields"></a>Combinare manualmente i campi

Specifica manualmente un attributo unito. 

1. Nella pagina **Unisci** seleziona **Combina campi**.

1. Specifica i criteri prevalenti dell'unione nell'elenco a discesa **Combina campi per**.

1. Scegli un campo da aggiungere. Seleziona **Aggiungi campi** per combinare altri campi.

1. Fornisci un **Nome** e un **Nome del campo di output**.

1. Seleziona **Fatto** per applicare le modifiche.

1. Seleziona **Salva** ed **Esegui** per elaborare le modifiche. 

## <a name="change-the-order-of-fields"></a>Modificare l'ordine dei campi

Alcune entità contengono più dettagli di altre. Se un'entità include i dati più recenti su un campo, puoi dare la priorità ad altre entità quando unisci i valori.

1. Seleziona il campo unito.
  
1. Seleziona **Mostra altro** e scegli **Modifica**.

1. Nel riquadro **Combina campi** seleziona **Sposta su/giù** per impostare l'ordine o trascinali nella posizione desiderata.

1. Conferma la modifica.

1. Seleziona **Salva** ed **Esegui** per elaborare le modifiche.

## <a name="configure-customer-id-generation"></a>Configura la generazione dell'ID cliente 

Dopo aver configurato i campi di unione, è possibile definire come generare i valori CustomerId, gli identificatori univoci del profilo cliente. Il passaggio di unione nel processo di unificazione dei dati genera l'identificatore univoco del profilo cliente. L'identificatore è il CustomerId nell'entità *Cliente* che risulta dal processo di unificazione dei dati. 

Il CustomerId nell'entità Cliente si basa su un hash del primo valore delle chiavi primarie prevalenti non nulle. Queste chiavi provengono dalle entità utilizzate nella fase di corrispondenza e unione e sono influenzate dall'ordine di corrispondenza. Il CustomerID generato può quindi cambiare quando un valore di chiave primaria cambia nell'entità primaria dell'ordine di corrispondenza. Di conseguenza, il valore della chiave primaria potrebbe non rappresentare sempre lo stesso cliente.

La configurazione di un ID cliente stabile consente di evitare tale comportamento.

**Configura ID cliente univoco**

1. Vai a **Unifica** > **Unisci**.

1. Nella pagina **Unisci** seleziona la scheda **Chiavi**. 

1. Passa il mouse sula riga **CustomerId** e seleziona l'opzione **Configura**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Controllo per personalizzare la generazione dell'ID.":::

1. Seleziona fino a cinque campi che comprenderanno un ID cliente univoco e sono più stabili. I record che non corrispondono alla tua configurazione utilizzano invece un ID configurato dal sistema.  

1. Seleziona **Fatto** ed esegui il processo di unione per applicare le modifiche.

## <a name="run-your-merge"></a>Eseguire l'unione

Sia che unisci manualmente gli attributi o consenti al sistema di unirli, puoi sempre eseguire l'unione. Seleziona **Esegui** nella pagina **Unione** per avviare il processo.

> [!div class="mx-imgBorder"]
> ![Salvataggio ed esecuzione dell'unione di dati.](media/configure-data-merge-save-run.png "Salvataggio ed esecuzione dell'unione di dati")

Scegli **Esegui solo unione** se desideri solo vedere l'output riflesso nell'entità cliente unificata. I processi a valle verranno aggiornati come [definito nella pianificazione dell'aggiornamento](system.md#schedule-tab).

Scegli **Esegui processi di unione e downstream** per aggiornare il sistema con le modifiche. Tutti i processi, inclusi arricchimento, segmenti e misure verranno rieseguiti automaticamente. Dopo che tutti i processi a valle sono stati completati, i profili dei clienti riflettono le modifiche apportate.

Per apportare ulteriori modifiche e rieseguire il passaggio, è possibile annullare un'unione in corso. Seleziona **Aggiornamento in corso ...** e seleziona **Annulla processo** nel riquadro laterale visualizzato.

> [!TIP]
> Dopo aver eseguito il processo di unione, seleziona lo stato del processo per aprire il riquadro **Dettagli attività**. Fornisce una panoramica del tempo di elaborazione, della data dell'ultima elaborazione e di tutti gli errori e gli avvisi associati all'attività. Seleziona **Vedi dettagli** per vedere quali entità hanno partecipato al processo corrispondente, se la risoluzione del conflitto è riuscita e se gli aggiornamenti sono stati pubblicati correttamente.  
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Percorso di drill-down per ottenere i dettagli dell'elaborazione dal collegamento sullo stato dell'attività.":::

## <a name="next-step"></a>Passaggio successivo

Configura [Impegni](activities.md), [Arricchimento](enrichment-hub.md) o [Relazioni](relationships.md) per ulteriori informazioni dettagliate sui clienti.

Se hai già configurato attività, arricchimenti o segmenti, verranno elaborati automaticamente per utilizzare i dati dei clienti più recenti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
