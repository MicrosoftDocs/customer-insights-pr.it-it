---
title: Creare segmenti semplici con segmenti rapidi
description: Crea segmenti semplici di clienti per raggrupparli in base a vari attributi.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171136"
---
# <a name="create-simple-segments-with-quick-segments"></a>Creare segmenti semplici con segmenti rapidi

I segmenti rapidi consentono di creare rapidamente segmenti semplici con un singolo operatore per ottenere informazioni più rapide. I segmenti rapidi sono supportati solo in ambienti per **clienti individuali**.

## <a name="create-a-new-segment-with-quick-segments"></a>Creare un nuovo segmento con segmenti rapidi

1. Vai a **Segmenti**.

1. Seleziona **Nuovo** > **Crea da**.
   - Seleziona l'opzione **Profili** per creare un segmento basato sull'*entità cliente unificata*.
   - Seleziona l'opzione **Misure** per costruire un segmento intorno alle misure che hai creato in precedenza.
   - Seleziona l'opzione **Intelligenza** per creare un segmento attorno a una delle entità di output generate utilizzando le funzionalità **Previsioni** o **Modelli personalizzati**.

1. Nella finestra di dialogo **Nuovo segmento rapido**, seleziona un attributo dal menu a discesa **Campo**. In base alla selezione, il sistema fornisce valori differenti.
   - Per i campi di categoria, vengono visualizzati i primi 10 conteggi dei clienti. Scegli un **valore** e seleziona **Revisione**.
   - Per un attributo numerico, il sistema mostra quale valore dell'attributo rientra nel percentile di ciascun cliente. Scegli un **operatore** e un **valore**, quindi seleziona **Revisione**.

1. Il sistema fornisce una **dimensione stimata del segmento**. Genera il segmento che hai definito oppure scegli un campo differente.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nome e stima per un segmento rapido.":::

1. Fornisci un **nome** per il segmento e il **nome entità di output**. Facoltativamente, aggiungi [tag](work-with-tags-columns.md#manage-tags).

1. Seleziona **Salva** per creare il segmento. Viene visualizzata la pagina **Segmenti**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Passaggi successivi

[Esporta un segmento](export-destinations.md) ed esplora l'[integrazione della scheda cliente](customer-card-add-in.md) per utilizzare i segmenti in altre applicazioni.

[!INCLUDE [footer-include](includes/footer-banner.md)]
