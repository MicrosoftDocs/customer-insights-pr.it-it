---
title: Connettore Power Automate | Microsoft Docs
description: Crea i flussi in Microsoft Power Automate da Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976093"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="ad11c-103">Connettore Power Automate (anteprima)</span><span class="sxs-lookup"><span data-stu-id="ad11c-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="ad11c-104">Attiva eventi specifici che si verificano automaticamente quando i dati vengono modificati e gestisci flussi più complessi direttamente in [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ad11c-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="ad11c-105">Trigger di Power Automate</span><span class="sxs-lookup"><span data-stu-id="ad11c-105">Power Automate triggers</span></span>

<span data-ttu-id="ad11c-106">Utilizza i trigger per creare flussi cloud e automatizzare attività ripetitive, come notifiche o azioni più avanzate.</span><span class="sxs-lookup"><span data-stu-id="ad11c-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="ad11c-107">Trigger in caso di errore di aggiornamento dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ad11c-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="ad11c-108">Trigger in caso di completamento dell'aggiornamento dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ad11c-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="ad11c-109">Trigger in caso di superamento di una soglia su un segmento.</span><span class="sxs-lookup"><span data-stu-id="ad11c-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="ad11c-110">Il trigger è limitato al superamento della soglia.</span><span class="sxs-lookup"><span data-stu-id="ad11c-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="ad11c-111">Trigger in caso di superamento di una soglia su una misura aziendale.</span><span class="sxs-lookup"><span data-stu-id="ad11c-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="ad11c-112">Solo le misure aziendali senza una dimensione sono supportate.</span><span class="sxs-lookup"><span data-stu-id="ad11c-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="ad11c-113">Il trigger è limitato al superamento della soglia.</span><span class="sxs-lookup"><span data-stu-id="ad11c-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="ad11c-114">Trigger in caso di completamento di un aggiornamento completo (origini dati, segmenti, misure...).</span><span class="sxs-lookup"><span data-stu-id="ad11c-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="ad11c-115">Trigger in caso di completamento di un aggiornamento del processo di unificazione (mappa, corrispondenza, unione).</span><span class="sxs-lookup"><span data-stu-id="ad11c-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="ad11c-116">[Configurare i trigger in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="ad11c-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="ad11c-117">Azioni di Power Automate</span><span class="sxs-lookup"><span data-stu-id="ad11c-117">Power Automate actions</span></span>
<span data-ttu-id="ad11c-118">Il connettore di Power Automate fornisce altre azioni oltre ai trigger disponibili.</span><span class="sxs-lookup"><span data-stu-id="ad11c-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="ad11c-119">Per ulteriori informazioni, vedere la [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="ad11c-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="ad11c-120">Creare un flusso Power Automate</span><span class="sxs-lookup"><span data-stu-id="ad11c-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="ad11c-121">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="ad11c-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ad11c-122">Nel riquadro **Power Automate**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="ad11c-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="ad11c-123">Si apre il connettore di Customer Insights (anteprima) in Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ad11c-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="ad11c-124">**Accedi** a  Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ad11c-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="ad11c-125">Scegli uno dei trigger disponibili e aggiungi più passaggi al tuo nuovo flusso.</span><span class="sxs-lookup"><span data-stu-id="ad11c-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="ad11c-126">Per ulteriori informazioni, vedere [Creare un flusso cloud in Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="ad11c-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="ad11c-127">Esempi di come utilizzare i flussi:</span><span class="sxs-lookup"><span data-stu-id="ad11c-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="ad11c-128">Pubblica un messaggio in un canale Microsoft Teams se un aggiornamento di un'origine dati non riesce.</span><span class="sxs-lookup"><span data-stu-id="ad11c-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="ad11c-129">Invia un'e-mail ai proprietari dei dati quando viene superata una soglia in un segmento.</span><span class="sxs-lookup"><span data-stu-id="ad11c-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
