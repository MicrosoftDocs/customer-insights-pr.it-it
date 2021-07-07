---
title: Unire entità nel processo di unificazione dei dati
description: Unisci entità per creare profili cliente unificati.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305647"
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

1. Seleziona il campo unito.
  
1. Seleziona **Mostra altro** e scegli **Escludi**.

1. Conferma l'esclusione.

1. Seleziona **Salva** ed **Esegui** per elaborare le modifiche. 

Nella pagina **Unisci** seleziona **Campi esclusi** per vedere l'elenco di tutti i campi esclusi. Questo riquadro consente di aggiungere nuovamente i campi esclusi.

## <a name="manually-combine-fields"></a>Combinare manualmente i campi

Specifica manualmente un attributo unito. 

1. Nella pagina **Unisci** seleziona **Combina campi**.

1. Fornisci un **Nome** e un **Nome del campo di output**.

1. Scegli un campo da aggiungere. Seleziona **Aggiungi campi** per combinare altri campi.

1. Conferma l'esclusione.

1. Seleziona **Salva** ed **Esegui** per elaborare le modifiche. 

## <a name="change-the-order-of-fields"></a>Modificare l'ordine dei campi

Alcune entità contengono più dettagli di altre. Se un'entità include i dati più recenti su un campo, puoi dare la priorità ad altre entità quando unisci i valori.

1. Seleziona il campo unito.
  
1. Seleziona **Mostra altro** e scegli **Modifica**.

1. Nel riquadro **Combina campi** seleziona **Sposta su/giù** per impostare l'ordine o trascinali nella posizione desiderata.

1. Conferma la modifica.

1. Seleziona **Salva** ed **Esegui** per elaborare le modifiche.

## <a name="run-your-merge"></a>Eseguire l'unione

Sia che unisci manualmente gli attributi o consenti al sistema di unirli, puoi sempre eseguire l'unione. Seleziona **Esegui** nella pagina **Unione** per avviare il processo.

> [!div class="mx-imgBorder"]
> ![Salvataggio ed esecuzione dell'unione di dati](media/configure-data-merge-save-run.png "Salvataggio ed esecuzione dell'unione di dati")

Scegli **Esegui solo unione** se desideri solo vedere l'output riflesso nell'entità cliente unificata. I processi a valle verranno aggiornati come [definito nella pianificazione dell'aggiornamento](system.md#schedule-tab).

Scegli **Esegui processi di unione e downstream** per aggiornare il sistema con le modifiche. Tutti i processi, inclusi arricchimento, segmenti e misure verranno rieseguiti automaticamente. Dopo che tutti i processi a valle sono stati completati, i profili dei clienti riflettono le modifiche apportate.

Per apportare ulteriori modifiche e rieseguire il passaggio, è possibile annullare un'unione in corso. Seleziona **Aggiornamento in corso ...** e seleziona **Annulla processo** nel riquadro laterale visualizzato.

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.

## <a name="next-step"></a>Passaggio successivo

Configura [Impegni](activities.md), [Arricchimento](enrichment-hub.md) o [Relazioni](relationships.md) per ulteriori informazioni dettagliate sui clienti.

Se hai già configurato attività, arricchimenti o segmenti, verranno elaborati automaticamente per utilizzare i dati dei clienti più recenti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
