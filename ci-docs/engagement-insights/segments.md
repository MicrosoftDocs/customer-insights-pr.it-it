---
title: Visualizza e crea segmenti
description: Come creare, modificare ed eliminare i segmenti e dove utilizzarli.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: e99c04e6c92d8ca16c2d69957e0f5b7dba0ac757
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225381"
---
# <a name="view-and-create-segments"></a>Visualizza e crea segmenti

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

I segmenti consentono di identificare sottoinsiemi di visitatori in base alle caratteristiche o alle interazioni del sito Web. I segmenti ti consentono di applicare filtri e analizzare quei sottoinsiemi. L'analisi può aiutare a esaminare e rispondere alle tendenze della tua attività. 

:::image type="content" source="media/segments-page.png" alt-text="Screenshot dell'applicazione delle informazioni dettagliate che mostra l'elenco dei segmenti esistenti in un'area di lavoro.":::

## <a name="view-segments"></a>Visualizza segmenti

1. Vai a **Dati** nel riquadro di spostamento sinistro. 

1. Seleziona la scheda **Segmenti** per visualizzare un elenco di tutti i segmenti nell'area di lavoro. 

## <a name="create-a-segment"></a>Crea un segmento

I segmenti sono costituiti da regole e condizioni connesse con operatori logici. Le condizioni applicano filtri a una dimensione selezionata. Ogni segmento può utilizzare fino a cinque dimensioni.

L'esempio seguente mostra un segmento con due condizioni in una regola. Filtra tutti gli eventi del sito Web in cui il browser è Chrome e i sistemi operativi sono iOS o Android.

:::image type="content" source="media/segment-sample.png" alt-text="Segmenti di esempio con due condizioni in una regola per filtrare gli eventi del sito Web.":::

Questa sezione descrive come creare un *segmento vuoto* da zero.

1. Vai a **Dati** > **Segmenti**.

1. Seleziona **Nuovo segmento**.

1. Nella **Libreria delle risorse**, seleziona il (+) accanto all'attributo che vuoi filtrare. Al momento, puoi creare segmenti solo in base alle dimensioni.

   :::image type="content" source="media/create-new-segment.png" alt-text="Creare un nuovo segmento.":::

1. Nella sezione **Regola** , scegliete un operatore e un valore per l'attributo selezionato. Le operazioni seguenti non sono supportate.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Scegli un operatore per il tuo nuovo segmento.":::

   - **è**: richiede una corrispondenza esatta per includere i valori. Usa **uguale a** per un singolo valore o **qualsiasi** per includere più valori.
   - **non è**: richiede una corrispondenza esatta per escludere i valori. Usa **uguale a** per un singolo valore o **qualsiasi** per includere più valori.
   - **inizia con**: una stringa con cui iniziano i valori corrispondenti.
   - **finisce con**: una stringa con cui finiscono i valori corrispondenti.
   - **contiene**: una stringa contenuta in valori corrispondenti.

1. Per aggiungere più condizioni a un gruppo, si possono usare operatori logici. Gli attributi proiettati vengono presi in considerazione quando si utilizzano operatori di gruppo.
   - Operatore **AND**: entrambe le condizioni devono essere soddisfatte come parte del processo di segmentazione. Questa opzione è molto utile quando si definiscono condizioni tra entità diverse.
   - Operatore **OR**: una delle condizioni deve essere soddisfatta come parte del processo di segmentazione. Questa opzione è molto utile quando si definiscono più condizioni per la stessa entità.

1. Seleziona **Salva** e il nome del segmento. 

Il segmento sarà elencato nella pagina **Segmenti** e potrai applicarlo a tutti i report e funnel nell'area di lavoro.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Utilizza un segmento in un report o in un grafico a imbuto

Puoi applicare i segmenti a un report o a un grafico a imbuto per filtrarli in base alle condizioni nel segmento. Tuttavia, non puoi applicare segmenti al report sull'utilizzo in tempo reale.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Un report sulle visualizzazioni di pagina con un elenco a discesa espanso per scegliere quali segmenti applicare.":::

Per applicare un segmento, apri il report o il grafico a imbuto. Seleziona **+ Aggiungi condizione** e scegli **Filtra per segmento**. Scegli il segmento dall'elenco che desideri applicare. Il segmento viene applicato al report. Se un grafico non supporta il segmento, mostra un errore. Per maggiori informazioni, vedi [Creare e gestire i rapporti sui funnel](funnel-reports.md).
 
Puoi applicare *fino a tre segmenti* a un report o a un grafico a imbuto.

## <a name="edit-a-segment"></a>Modificare un segmento

1. Vai a **Dati** > **Segmenti**.
1. Seleziona il segmento nell'elenco per aprirlo. 
1. Modifica o aggiungi valori secondo necessità.
1. Seleziona **Salva** per applicare le modifiche.

## <a name="change-the-name-of-a-segment"></a>Modifica il nome di un segmento

1. Vai a **Dati** > **Segmenti**.
1. Nell'elenco dei segmenti, seleziona **Altro [...]**. 
1. Scegli **Modifica nome** dall'elenco a discesa.
1. Immetti il nuovo nome e seleziona **Rinomina**.

## <a name="delete-a-segment"></a>Elimina un segmento

1. Vai a **Dati** > **Segmenti**.
1. Nell'elenco dei segmenti, seleziona **Altro [...]**. 
1. Scegli **Eimina** dall'elenco a discesa.
1. Seleziona **Elimina** per confermare.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
