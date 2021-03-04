---
title: Limitazioni e inserimento dati in tempo reale
description: Informazioni generali sulle funzionalità in tempo reale di Audience Insights.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270285"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="f121c-103">Inserimento dati in tempo reale (anteprima)</span><span class="sxs-lookup"><span data-stu-id="f121c-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="f121c-104">La funzionalità quasi in tempo reale consente di visualizzare, in pochi secondi, le interazioni più recenti che i tuoi clienti hanno effettuato con i tuoi prodotti o servizi.</span><span class="sxs-lookup"><span data-stu-id="f121c-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="f121c-105">Gli [aggiornamenti pianificati](system.md#schedule-tab) includono un gran numero di record e diverse operazioni complesse.</span><span class="sxs-lookup"><span data-stu-id="f121c-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="f121c-106">Innanzitutto, i dati vengono estratti dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f121c-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="f121c-107">Successivamente, i dati vengono unificati e quindi arricchiti con ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="f121c-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="f121c-108">Ogni esecuzione di questo processo può richiedere da minuti a ore.</span><span class="sxs-lookup"><span data-stu-id="f121c-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="f121c-109">La funzionalità in tempo reale fornisce dei dati immediatamente per il consumo, fino a quando il successivo aggiornamento pianificato non estrae questi dati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f121c-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="f121c-110">Gli aggiornamenti in tempo reale hanno un tempo di scadenza dopo il quale non sovrascrivono più il valore dall'origine dati:</span><span class="sxs-lookup"><span data-stu-id="f121c-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="f121c-111">Gli aggiornamenti del profilo verranno conservati per 4 ore</span><span class="sxs-lookup"><span data-stu-id="f121c-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="f121c-112">Gli impegni verranno conservati per 30 giorni</span><span class="sxs-lookup"><span data-stu-id="f121c-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="f121c-113">Questi valori sono parametri di chiamata API che puoi modificare.</span><span class="sxs-lookup"><span data-stu-id="f121c-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="f121c-114">Mirano a garantire che i dati di origine rimangano l'origine reale.</span><span class="sxs-lookup"><span data-stu-id="f121c-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="f121c-115">Se desideri includere più a lungo aggiornamenti in tempo reale, devi aggiungerli a un'origine dati di modo che vengano estratti durante l'aggiornamento pianificato successivo.</span><span class="sxs-lookup"><span data-stu-id="f121c-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="f121c-116">Aggiornamento in tempo reale dei campi del profilo cliente unificato</span><span class="sxs-lookup"><span data-stu-id="f121c-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="f121c-117">I profili aggiornati verranno visualizzati nella visualizzazione della scheda cliente o in qualsiasi altra visualizzazione nel giro di pochi secondi.</span><span class="sxs-lookup"><span data-stu-id="f121c-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="f121c-118">Poiché le operazioni in tempo reale avvengono dopo che è avvenuta l'unificazione dei dati, si applicano solo ai profili cliente unificati.</span><span class="sxs-lookup"><span data-stu-id="f121c-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="f121c-119">Di conseguenza, le modifiche al profilo in tempo reale non aggiorneranno misure, appartenenza al segmento o arricchimenti.</span><span class="sxs-lookup"><span data-stu-id="f121c-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="f121c-120">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="f121c-120">Limitations</span></span>

- <span data-ttu-id="f121c-121">I profili cliente possono essere aggiornati, ma non creati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="f121c-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="f121c-122">L'esportazione di aggiornamenti in tempo reale su sistemi esterni, ad esempio Power BI, non è possibile al momento.</span><span class="sxs-lookup"><span data-stu-id="f121c-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="f121c-123">Creazione di impegni in tempo reale</span><span class="sxs-lookup"><span data-stu-id="f121c-123">Real-time creation of activities</span></span>

<span data-ttu-id="f121c-124">L'API in tempo reale ti consente di pubblicare un nuovo impegno dal sistema di origine (un singolo record di origine) in un profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="f121c-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="f121c-125">Il nuovo impegno sarà disponibile come impegno unificato nella sequenza temporale del profilo cliente unificato entro pochi secondi.</span><span class="sxs-lookup"><span data-stu-id="f121c-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="f121c-126">Puoi visualizzare la sequenza temporale nella visualizzazione della scheda cliente o in qualsiasi altra integrazione della sequenza temporale configurata.</span><span class="sxs-lookup"><span data-stu-id="f121c-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f121c-127">Gli impegni sono immutabili.</span><span class="sxs-lookup"><span data-stu-id="f121c-127">Activities are immutable.</span></span> <span data-ttu-id="f121c-128">Non cambiano una volta creati.</span><span class="sxs-lookup"><span data-stu-id="f121c-128">They don't change once created.</span></span>
> - <span data-ttu-id="f121c-129">Attualmente, i segmenti e le misure non verranno aggiornati in base al nuovo impegno.</span><span class="sxs-lookup"><span data-stu-id="f121c-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="f121c-130">Gli impegni aggiunti solo tramite l'API in tempo reale non fanno parte delle esportazioni e non verranno visualizzati in PowerBI.</span><span class="sxs-lookup"><span data-stu-id="f121c-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="f121c-131">Esistono due modi per connettersi all'API in tempo reale:</span><span class="sxs-lookup"><span data-stu-id="f121c-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="f121c-132">[indirettamente](#connect-via-the-dynamics-365-customer-insights-connector), tramite il [connettore Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="f121c-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="f121c-133">[direttamente](#connect-directly-to-the-real-time-api), con il codice</span><span class="sxs-lookup"><span data-stu-id="f121c-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="f121c-134">I seguenti prerequisiti si applicano a entrambi:</span><span class="sxs-lookup"><span data-stu-id="f121c-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="f121c-135">Un ambiente di Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f121c-135">A Customer Insights environment</span></span>
- <span data-ttu-id="f121c-136">Profili cliente unificati</span><span class="sxs-lookup"><span data-stu-id="f121c-136">Unified customer profiles</span></span>
- <span data-ttu-id="f121c-137">Impegni configurati ed eseguiti</span><span class="sxs-lookup"><span data-stu-id="f121c-137">Activities configured and run</span></span>
- <span data-ttu-id="f121c-138">Autorizzazioni come contributore o amministratore per autenticare il tuo account</span><span class="sxs-lookup"><span data-stu-id="f121c-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="f121c-139">Connettersi tramite il connettore Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f121c-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="f121c-140">L'API in tempo reale può inserire dati da un connettore Power Platform dedicato, il [connettore di Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), senza la necessità di scrivere e distribuire alcun codice.</span><span class="sxs-lookup"><span data-stu-id="f121c-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="f121c-141">Il connettore può eseguire le stesse azioni in tempo reale dell'API.</span><span class="sxs-lookup"><span data-stu-id="f121c-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="f121c-142">È necessaria una licenza valida per i connettori premium.</span><span class="sxs-lookup"><span data-stu-id="f121c-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="f121c-143">Per altre informazioni, vedi [Domande frequenti sulle licenze di Power Apps e Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="f121c-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="f121c-144">Power Platform [Power Apps e/o Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="f121c-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="f121c-145">[App per la logica](https://docs.microsoft.com/azure/connectors/apis-list) di Azure</span><span class="sxs-lookup"><span data-stu-id="f121c-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="f121c-146">Per dettagli sulla creazione di flussi, vedi la [documentazione di Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="f121c-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="f121c-147">Connettersi direttamente all'API in tempo reale</span><span class="sxs-lookup"><span data-stu-id="f121c-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="f121c-148">Puoi utilizzare le funzionalità in tempo reale creando una pipeline e connettendoti direttamente all'API in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="f121c-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="f121c-149">Puoi pubblicare un impegno nel formato del tuo sistema di origine o nel formato UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="f121c-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="f121c-150">Ottieni il formato effettuando una chiamata API a /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="f121c-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="f121c-151">I dettagli di questa API, inclusi parametri e risposte, sono disponibili nella sezione **EntityData** del [Riferimento API di Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="f121c-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="f121c-152">Per ulteriori informazioni, vedi [Utilizzare le API di Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="f121c-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="f121c-153">Comprendi il tuo utilizzo in tempo reale con i dati di telemetria</span><span class="sxs-lookup"><span data-stu-id="f121c-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="f121c-154">Ottieni una panoramica del volume di richieste all'API in tempo reale e informazioni sui problemi che il sistema può incontrare.</span><span class="sxs-lookup"><span data-stu-id="f121c-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="f121c-155">Puoi [accedere alla telemetria in tempo reale](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="f121c-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]