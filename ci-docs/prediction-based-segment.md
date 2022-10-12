---
title: Creare un segmento in base a un modello di previsione
description: Crea segmenti in base all'entità di output di un modello di previsione.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610425"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Creare un segmento basato su un modello di previsione (anteprima)

I risultati delle previsioni a volte si applicano solo a un sottoinsieme dei tuoi clienti. Aumenta la personalizzazione dei consigli creando segmenti dai risultati dei modelli di previsione. Ad esempio, potresti dare consigli specifici ai clienti che preferiscono un certo tipo di servizio.

## <a name="prerequisites"></a>Prerequisiti

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.

- Un modello di raccomandazione del prodotto, abbandono delle transazioni, abbandono dell'abbonamento o valore della vita del cliente configurato in Customer Insights. Esamina i requisiti per configurare i diversi modelli:

  - [Modello di raccomandazione prodotto](predict-product-recommendation.md)
  - [Modello di abbandono dell'abbonamento](predict-subscription-churn.md)
  - [Modello di abbandono della transazione](predict-transactional-churn.md)
  - [Modello di valore durata cliente](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Creare un segmento del cliente in base alle previsioni

1. Vai a **Intelligence** > **Predizioni** e seleziona la scheda **Le mie previsioni**.

1. Seleziona il modello che desideri rivedere e seleziona **Visualizza**.

1. Nella pagina dei risultati, seleziona **Crea segmento**. Per ulteriori informazioni sulla pagina dei risultati, consulta l'articolo sul modello.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Screenshot della pagina dei risultati della previsione con evidenziazione sull'azione Crea segmento.":::

1. Crea un nuovo segmento usando gli attributi dell'entità di output del modello selezionato. Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).

> [!TIP]
> Puoi anche creare un segmento per un modello previsione dalla pagina **Segmenti** selezionando **Nuovo** e scegliendo **Crea da** > **Intelligence**. Per maggiori informazioni, vedi [Creare un nuovo segmento con segmenti rapidi](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
