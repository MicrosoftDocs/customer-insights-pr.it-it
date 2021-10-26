---
title: Visualizza e crea metriche
description: Come creare, modificare ed eliminare le metriche.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 79600a14bc7e98dfd066270f19c353fd007e1341
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623727"
---
# <a name="view-and-create-metrics"></a>Visualizza e crea metriche

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Le metriche aiutano a capire il comportamento dei tuoi visitatori. Aggregano le proprietà degli eventi e misurano le statistiche e le prestazioni delle tue proprietà Web.  

Supponiamo che tu stia eseguendo una promozione di marketing sul tuo sito Web. Puoi utilizzare le metriche per tenere traccia del numero di visitatori o utenti unici che hanno visitato il tuo sito Web durante la promozione. L'analisi delle metriche ti aiuta a capire meglio i destinatari del tuo sito Web. La combinazione delle metriche con [dimensioni](dimensions.md) su un [report personalizzato](custom-reports.md) ti consente di analizzare il comportamento per comprendere i tuoi utenti. Ad esempio, puoi separare i visitatori in categorie nuove e ricorrenti per identificare le differenze di interessi e intenzioni tra i gruppi.

## <a name="view-metrics"></a>Visualizza metriche

Gli approfondimenti sul coinvolgimento includono aggregazioni comunemente utilizzate delle proprietà degli eventi come metriche di sistema: 

- Visitatori
- Visite
- Visualizzazioni di pagina
- Clic

Queste metriche di sistema si basano sulle proprietà degli eventi esistenti negli eventi di base.

1. Vai a **Dati** nel riquadro di spostamento sinistro. 
1. Seleziona la scheda **Metriche** per visualizzare un elenco di tutte le metriche nell'area di lavoro. 
   > [!NOTE]
   > Le metriche generate dal sistema sono di sola lettura. Non puoi modificarli o cancellarli. Puoi solo creare e modificare metriche personalizzate.

## <a name="create-a-metric"></a>Crea una metrica

Gli amministratori dell'ambiente e dell'area di lavoro possono creare metriche. Le proprietà dell'evento devono essere inviate all'area di lavoro prima di creare una metrica. È possibile creare metriche in base alle proprietà degli eventi inviate dagli eventi di base o utilizzare l'SDK Web per [inviare proprietà evento personalizzate](advanced-SDK-implementation.md).

1. Vai a **Dati** > **Metriche**.
1. Seleziona **New metric** per aprire la finestra di dialogo **Resource Library** e **New untitled metric** .

   :::image type="content" source="media/new-metric.png" alt-text="Aggiungi una metrica a un evento.":::

1. Nella finestra di dialogo **New untitled metric** , seleziona l'elenco a discesa **Format** e scegli il tipo di dati **Integer** o **Double** . Integer è un numero intero. Per Double, potete scegliere una e tre cifre decimali.

   :::image type="content" source="media/create-new-metric.png" alt-text="Creare una nuova metrica.":::
   
5. Nel riquadro **Resource Library** , trova la proprietà dell'evento su cui basare la metrica.
6. Seleziona il **segno più (+)** accanto alla proprietà per utilizzarla nella formula. Puoi creare solo una formula basata su una proprietà. 
7. Scegli una delle funzioni aggregate seguenti. 

   - Somma: il totale aritmetico di tutti i valori 
   - Media: la media di tutti i valori
   - Conteggio: il numero totale di valori
   - Valori distinti: il numero totale di valori distinti

   Dopo aver definito la metrica, viene visualizzata un'anteprima dell'attività della metrica per l'ultima ora.

1. Seleziona **Salva**. 
1. Immetti un nome per la metrica e seleziona **Salva**.

Può richiedere fino a un minuto prima di poter utilizzare la metrica per [creare report personalizzati](custom-reports.md).

## <a name="edit-a-metric"></a>Modificare una metrica

Puoi solo modificare le metriche personalizzate.

1. Vai a **Dati** > **Metriche**.
1. Seleziona la metrica nell'elenco.
1. Cambia la definizione della metrica
1. Seleziona **Salva**.

## <a name="change-the-name-of-a-metric"></a>Modifica il nome di una metrica

Si può solo cambiare il nome delle metriche personalizzate.

1. Vai a **Dati** > **Metriche**.
1. Seleziona **Altro [...]** per una metrica e scegli **Modifica nome**.
1. Modifica il nome. 
1. Selezionare **Rinomina**.

## <a name="delete-a-metric"></a>Elimina una metrica

Si possono cancellare solo le metriche personalizzate.

1. Vai a **Dati** > **Metriche**.
1. Seleziona **Altro [...]** per una metrica e scegli **Elimina**.

   :::image type="content" source="media/delete-metric.png" alt-text="Elimina una metrica per un evento.":::

1. Per confermare l'eliminazione seleziona **Elimina**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
