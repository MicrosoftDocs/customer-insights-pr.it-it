---
title: Informazioni sui report personalizzati
description: Scopri come creare e personalizzare report.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582882"
---
# <a name="create-and-edit-custom-reports"></a>Creare e modificare report personalizzati

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Oltre ai rapporti out-of-box (OOB), puoi costruire un rapporto personalizzato con visualizzazioni di grafici e tabelle per aiutarti a capire il comportamento degli utenti. Questo articolo spiega come creare un report con i dati necessari utilizzando visualizzazioni di tabelle e grafici. Per informazioni sui rapporti OOB, vedi [Visualizza rapporti](view-reports.md).

## <a name="create-a-custom-report"></a>Creare un report personalizzato

1. Vai ad **Analizza** > **Personalizzato** per accedere all'elenco dei report personalizzati.

1. Seleziona **Nuovo report** per iniziare a creare un report personalizzato.

   :::image type="content" source="media/new-custom-report.png" alt-text="Nuovi report personalizzati.":::

1. Seleziona il tipo di report che desideri compilare:

    - Seleziona **Aggiungi elemento grafico** nella barra dei comandi per creare una visualizzazione tabella predefinita.
    - In alternativa, seleziona una visualizzazione colonna, barra, riga, area, torta, anello o tabella dal riquadro **Editor di report**.

1. Nella sezione **Dati** del pannello **Editor di visualizzazione** , scegli una delle opzioni disponibili (per esempio, le visualizzazioni di pagina) dal menu a tendina **Metriche** . Puoi anche aggiungere **Dimensioni** (per esempio, paese) da mostrare nella visualizzazione. Per ulteriori informazioni, vedere [Visualizzare e creare metriche](metrics.md) e [Visualizzare e creare dimensioni](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Scegli una metrica per il tuo rapporto.":::

1. Selezionate la sezione **Design** del pannello **Editor visualizzazione** per aggiungere il **testo del titolo** e per attivare e disattivare il **titolo** .  Puoi anche cambiare il tipo di visualizzazione selezionando un altro grafico, come quello a **torta**.

1. Per cambiare la dimensione e la posizione di una visualizzazione:
   - Seleziona la visualizzazione e trascina uno degli angoli o dei bordi per regolarne le dimensioni.
   - Seleziona la visualizzazione e spostala in una nuova posizione. Puoi anche utilizzare i tasti freccia per modificare la posizione.
1. Per aggiungere un'altra visualizzazione, seleziona **Aggiungi elemento grafico** nella barra dei comandi.
1. Dopo aver aggiunto le visualizzazioni desiderate per il report, seleziona **Salva** nella barra dei comandi.

1. Specifica un nome per il report personalizzato e seleziona **Salva** per crearlo.
 
## <a name="filter-a-custom-report"></a>Filtrare un rapporto personalizzato

È possibile selezionare il lasso di tempo o l'intervallo di date in un report personalizzato per concentrarsi su un valore o un periodo di tempo.

Per selezionare un lasso di tempo, nell'angolo in alto a destra della vista del rapporto, seleziona un valore dall'elenco a discesa del rapporto. Potete anche scegliere un **intervallo di date* fisse.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtra per intervallo di tempo o di data.":::

Per la maggior parte dei rapporti, seleziona **+ Aggiungi condizione**, per scegliere una dimensione o un segmento per filtrare il rapporto. Per maggiori informazioni, vedi [Visualizzare e creare segmenti](segments.md).

## <a name="edit-a-custom-report"></a>Modificare un report personalizzato

1. Vai ad **Analizza** > **Personalizzato** per accedere all'elenco dei report personalizzati.

1. Nell'elenco dei report personalizzati, seleziona **Altro [...]** 

1. Scegliere **Modifica nome** per cambiare il nome del rapporto.

1. Seleziona il nome del rapporto e usa le opzioni **+ Aggiungi elemento visivo** e **Modifica** per aggiungere, rimuovere, riposizionare o ridimensionare le visualizzazioni.

1. Per cambiare le proprietà di una visualizzazione, selezionare la visualizzazione, selezionare **...** e poi **Modifica visualizzazione**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Modifica delle proprietà del grafico per report personalizzati.":::

1. Una volta completata la modifica del report, seleziona **Salva** per salvare le modifiche. 

## <a name="delete-a-custom-report"></a>Eliminare un report personalizzato

1. Vai ad **Analizza** > **Personalizzato** per accedere all'elenco dei report personalizzati.

1. Nell'elenco dei report personalizzati, seleziona **...**

1. Scegli **Elimina** per rimuovere il report.

1. Conferma l'eliminazione per rimuovere il report in modo permanente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
