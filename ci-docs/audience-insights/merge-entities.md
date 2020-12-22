---
title: Unire entità nel processo di unificazione dei dati
description: Unisci entità per creare profili cliente unificati.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406132"
---
# <a name="merge-entities"></a>Gestire entità

La fase di unione è l'ultima fase del processo di unificazione dei dati. Il suo scopo è la riconciliazione di dati in conflitto. Esempi di dati in conflitto potrebbero includere il nome di un cliente che si trova in due dei tuoi set di dati ma si presenta in modo leggermente diverso in ciascuno ("Grant Marshall" rispetto a "Grant Marshal") o un numero di telefono che differisce nel formato (617-803-091X rispetto a 617803091X). L'unione di tali punti di dati in conflitto viene eseguita in base all'attributo per attributo.

Dopo aver completato la [fase di corrispondenza](match-entities.md), avvii la fase di unione selezionando il riquadro **Unione** nella pagina **Unifica**.

## <a name="review-system-recommendations"></a>Rivedere gli elementi consigliati del sistema

Nella pagina **Unione**, scegli ed escludi gli attributi da unire all'interno dell'entità del profilo cliente unificato (il risultato del processo di configurazione). Alcuni attributi vengono automaticamente uniti dal sistema.

### <a name="view-merged-attributes"></a>Visualizzare gli attributi uniti

Per visualizzare gli attributi inclusi in uno degli attributi uniti automaticamente, seleziona l'attributo unito. I due attributi che compongono l'attributo unito sono visualizzati in due nuove righe sotto l'attributo unito.

> [!div class="mx-imgBorder"]
> ![Seleziona l'attributo unito](media/configure-data-merge-profile-attributes.png "Seleziona l'attributo unito")

### <a name="separate-merged-attributes"></a>Attributi uniti separati

Per separare o annullare l'unione di uno qualsiasi degli attributi uniti automaticamente, trova l'attributo nella tabella **Attributi profilo**.

1. Selezionare il pulsante con i puntini di sospensione (...).
  
2. Nell'elenco a discesa, seleziona **Campi separati**.

### <a name="remove-merged-attributes"></a>Rimuovere attributi uniti

Per escludere un attributo dall'entità del profilo cliente finale, cercalo nella tabella **Attributi profilo**.

1. Selezionare il pulsante con i puntini di sospensione (...).
  
2. Nell'elenco a discesa, seleziona **Non unire**.

   L'attributo viene spostato nella sezione **Rimosso dal record del cliente**.

## <a name="manually-add-a-merged-attribute"></a>Aggiungere manualmente un attributo unito

Per aggiungere un attributo unito, vai alla pagina **Unione**.

1. Seleziona **Aggiungi attributo unito**.

2. Fornisci un **Nome** per identificarlo in seguito nella pagina **Unione**.

3. Facoltativamente, fornisci un **nome visualizzato** che verrà visualizzato nell'entità Profilo cliente unificato.

4. Configura **Seleziona gli attributi duplicati** per selezionare gli attributi che vvuoi unire dalle entità corrispondenti. Puoi anche cercare attributi.

5. Impostare **Classificazione per priorità** per assegnare la priorità a un attributo rispetto agli altri. Ad esempio, sel'entità *WebAccountCSV* include i dati più accurati sull'atributo *Nomi completi*, è possibile assegnare priorità a questa entità rispetto a *ContactCSV* selezionando *WebAccountCSV*. Di conseguenza, *WebAccountCSV* passa alla prima priorità, mentre *ContactCSV* passa alla seconda priorità quando si estraggono i valori per l'atributo *Nome completo*.

## <a name="run-your-merge"></a>Eseguire l'unione

Sia che unisci manualmente gli attributi o consenti al sistema di unirli, puoi sempre eseguire l'unione. Seleziona **Esegui** nella pagina **Unione** per avviare il processo.

> [!div class="mx-imgBorder"]
> ![Salvataggio ed esecuzione dell'unione di dati](media/configure-data-merge-save-run.png "Salvataggio ed esecuzione dell'unione di dati")

Per apportare ulteriori modifiche ed eseguire nuovamente il passaggio, puoi annullare un'unione in corso. Seleziona **Aggiornamento in corso ...** e seleziona **Annulla processo** nel riquadro laterale visualizzato.

Dopo che il testo **Aggiornamento in corso ...** cambia in **Completato**, l'unione è stata completata e ha risolto le contraddizioni nei dati in base ai criteri definiti. Gli attributi uniti e non uniti sono inclusi nell'entità profilo unificata. Gli attributi esclusi non sono inclusi nell'entità profilo unificata.

Se non era la prima volta che hai eseguito correttamente un'unione, tutti i processi a valle, inclusi l'arricchimento, la segmentazione e le misure, verranno eseguiti automaticamente. Dopo aver eseguito nuovamente tutti i processi a valle, i profili cliente riflettono le modifiche apportate.

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.

## <a name="next-step"></a>Passaggio successivo

Configura [Impegni](activities.md), [Arricchimento](enrichment-microsoft-graph.md) o [Relazioni](relationships.md) per ulteriori informazioni dettagliate sui clienti.

Se hai già configurato gli impegni, l'arricchimento o le relazioni o se hai definito segmenti, questi verranno elaborati automaticamente per utilizzare i dati cliente più recenti.


