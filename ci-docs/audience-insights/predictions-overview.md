---
title: Panoramica sugli scenari di previsione supportati
description: Scenari e opzioni di previsione coperti dall'applicazione Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095721"
---
# <a name="predictions-overview"></a><span data-ttu-id="8cb35-103">Panoramica delle previsioni</span><span class="sxs-lookup"><span data-stu-id="8cb35-103">Predictions overview</span></span>

<span data-ttu-id="8cb35-104">Dynamics 365 Customer Insights viene fornito con una varietà di opzioni che sfruttano l'intelligenza artificiale e l'apprendimento automatico per prevedere i dati.</span><span class="sxs-lookup"><span data-stu-id="8cb35-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="8cb35-105">Modelli predefiniti</span><span class="sxs-lookup"><span data-stu-id="8cb35-105">Out-of-box models</span></span>

<span data-ttu-id="8cb35-106">Il modo più semplice per iniziare con la previsione dei dati sono i modelli predefiniti, spesso indicati come modelli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="8cb35-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="8cb35-107">Richiedono solo determinati dati e una struttura per generare rapidamente informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="8cb35-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="8cb35-108">Attualmente sono disponibili i seguenti modelli:</span><span class="sxs-lookup"><span data-stu-id="8cb35-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="8cb35-109">[Valore durata cliente](predict-customer-lifetime-value.md): prevede ricavi potenziali di un cliente durante l'intera interazione con un'azienda.</span><span class="sxs-lookup"><span data-stu-id="8cb35-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="8cb35-110">[Raccomandazione del prodotto](predict-product-recommendation.md): suggerisce set di raccomandazioni predittive sui prodotti in base al comportamento di acquisto e ai clienti con modelli di acquisto simili.</span><span class="sxs-lookup"><span data-stu-id="8cb35-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="8cb35-111">[Abbandono dell'abbonamento](predict-subscription-churn.md): prevede se un cliente è a rischio perché non utilizza più i prodotti o i servizi in abbonamento della società.</span><span class="sxs-lookup"><span data-stu-id="8cb35-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="8cb35-112">[Abbandono transazionale](predict-transactional-churn.md): prevede se un cliente non acquisterà più i tuoi prodotti o servizi in un determinato intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8cb35-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="8cb35-113">Integrazione di Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="8cb35-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="8cb35-114">Se un'organizzazione usa già scenari di apprendimento automatico basati su esperimenti di Azure Machine Learning, la funzionalità dei modelli personalizzati in Customer Insights aiuta a collegare i punti.</span><span class="sxs-lookup"><span data-stu-id="8cb35-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="8cb35-115">Crea flussi di lavoro che ti aiutino a scegliere i dati da cui desideri generare informazioni dettagliate e mappare i risultati ai profili dei tuoi clienti unificati.</span><span class="sxs-lookup"><span data-stu-id="8cb35-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="8cb35-116">Per ulteriori informazioni, vedi [Modelli personalizzati apprendimento automatico](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="8cb35-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="8cb35-117">Previsione AI Builder</span><span class="sxs-lookup"><span data-stu-id="8cb35-117">AI Builder prediction</span></span>

<span data-ttu-id="8cb35-118">A volte, i set di dati sono incompleti e mancano alcuni valori.</span><span class="sxs-lookup"><span data-stu-id="8cb35-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="8cb35-119">Customer Insights può aiutare a prevedere i valori mancanti per l'entità e i segmenti Customer.</span><span class="sxs-lookup"><span data-stu-id="8cb35-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="8cb35-120">Per ulteriori informazioni, vedi [Completa i tuoi dati parziali con le previsioni](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="8cb35-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
