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
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741434"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="9bb97-103">Creare un segmento basato su un modello di previsione (anteprima)</span><span class="sxs-lookup"><span data-stu-id="9bb97-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="9bb97-104">I risultati delle previsioni a volte si applicano solo a un sottoinsieme dei tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="9bb97-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="9bb97-105">Aumenta la personalizzazione dei consigli creando segmenti dai risultati dei modelli di previsione.</span><span class="sxs-lookup"><span data-stu-id="9bb97-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="9bb97-106">Ad esempio, potresti dare consigli specifici ai clienti che preferiscono un certo tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="9bb97-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9bb97-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9bb97-107">Prerequisites</span></span>

- <span data-ttu-id="9bb97-108">Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9bb97-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="9bb97-109">Un modello di raccomandazione del prodotto, abbandono delle transazioni, abbandono dell'abbonamento o valore della vita del cliente configurato in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9bb97-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="9bb97-110">Esamina i requisiti per configurare i diversi modelli:</span><span class="sxs-lookup"><span data-stu-id="9bb97-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="9bb97-111">Modello di raccomandazione prodotto</span><span class="sxs-lookup"><span data-stu-id="9bb97-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="9bb97-112">Modello di abbandono dell'abbonamento</span><span class="sxs-lookup"><span data-stu-id="9bb97-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="9bb97-113">Modello di abbandono della transazione</span><span class="sxs-lookup"><span data-stu-id="9bb97-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="9bb97-114">Modello di valore durata cliente</span><span class="sxs-lookup"><span data-stu-id="9bb97-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="9bb97-115">Creare un segmento del cliente in base alle previsioni</span><span class="sxs-lookup"><span data-stu-id="9bb97-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="9bb97-116">Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.</span><span class="sxs-lookup"><span data-stu-id="9bb97-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="9bb97-117">Seleziona i puntini di sospensione verticali accanto al modello che desideri esaminare e seleziona **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="9bb97-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="9bb97-118">Nella pagina dei risultati, seleziona **Crea segmento**.</span><span class="sxs-lookup"><span data-stu-id="9bb97-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="9bb97-119">Per ulteriori informazioni sulla pagina dei risultati, consulta l'articolo sul modello.</span><span class="sxs-lookup"><span data-stu-id="9bb97-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Screenshot della pagina dei risultati della previsione con evidenziazione sull'azione Crea segmento.":::

1. <span data-ttu-id="9bb97-121">Crea un nuovo segmento in base all'entità di output del modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="9bb97-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="9bb97-122">Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9bb97-122">For more information, see [Create and manage segments](segments.md).</span></span>