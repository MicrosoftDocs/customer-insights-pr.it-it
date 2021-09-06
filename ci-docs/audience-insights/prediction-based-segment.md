---
title: Segmenti in base all'output delle previsioni
description: Crea segmenti in base all'entità di output di un modello di previsione.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036424"
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

1. Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.

1. Seleziona i puntini di sospensione verticali accanto al modello che desideri esaminare e seleziona **Visualizza**.

1. Nella pagina dei risultati, seleziona **Crea segmento**. Per ulteriori informazioni sulla pagina dei risultati, consulta l'articolo sul modello.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Screenshot della pagina dei risultati della previsione con evidenziazione sull'azione Crea segmento.":::

1. Crea un nuovo segmento in base all'entità di output del modello selezionato. Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).