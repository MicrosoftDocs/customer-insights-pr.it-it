---
title: Connettore Power Automate | Microsoft Docs
description: Crea i flussi in Microsoft Power Automate da Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597930"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="396e6-103">Connettore Power Automate (anteprima)</span><span class="sxs-lookup"><span data-stu-id="396e6-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="396e6-104">Attiva eventi specifici che si verificano automaticamente quando i dati vengono modificati e gestisci flussi più complessi direttamente in [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="396e6-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="396e6-105">Trigger di Power Automate</span><span class="sxs-lookup"><span data-stu-id="396e6-105">Power Automate triggers</span></span>

<span data-ttu-id="396e6-106">Utilizza i trigger per creare flussi cloud e automatizzare attività ripetitive, come notifiche o azioni più avanzate.</span><span class="sxs-lookup"><span data-stu-id="396e6-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="396e6-107">Trigger in caso di errore di aggiornamento dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="396e6-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="396e6-108">Trigger in caso di completamento dell'aggiornamento dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="396e6-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="396e6-109">Trigger in caso di superamento di una soglia su un segmento.</span><span class="sxs-lookup"><span data-stu-id="396e6-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="396e6-110">Il trigger è limitato al superamento della soglia.</span><span class="sxs-lookup"><span data-stu-id="396e6-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="396e6-111">Trigger in caso di superamento di una soglia su una misura aziendale.</span><span class="sxs-lookup"><span data-stu-id="396e6-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="396e6-112">Il trigger è limitato al superamento della soglia.</span><span class="sxs-lookup"><span data-stu-id="396e6-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="396e6-113">Trigger in caso di completamento di un aggiornamento completo (origini dati, segmenti, misure...).</span><span class="sxs-lookup"><span data-stu-id="396e6-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="396e6-114">Trigger in caso di completamento di un aggiornamento del processo di unificazione (mappa, corrispondenza, unione).</span><span class="sxs-lookup"><span data-stu-id="396e6-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="396e6-115">[Configurare i trigger in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="396e6-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="396e6-116">Azioni di Power Automate</span><span class="sxs-lookup"><span data-stu-id="396e6-116">Power Automate actions</span></span>
<span data-ttu-id="396e6-117">Il connettore di Power Automate fornisce altre azioni oltre ai trigger disponibili.</span><span class="sxs-lookup"><span data-stu-id="396e6-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="396e6-118">Per ulteriori informazioni, vedere la [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="396e6-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="396e6-119">Creare un flusso Power Automate</span><span class="sxs-lookup"><span data-stu-id="396e6-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="396e6-120">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="396e6-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="396e6-121">Nel riquadro **Power Automate**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="396e6-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="396e6-122">Si apre il connettore di Customer Insights (anteprima) in Power Automate.</span><span class="sxs-lookup"><span data-stu-id="396e6-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="396e6-123">**Accedi** a  Power Automate.</span><span class="sxs-lookup"><span data-stu-id="396e6-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="396e6-124">Scegli uno dei trigger disponibili e aggiungi più passaggi al tuo nuovo flusso.</span><span class="sxs-lookup"><span data-stu-id="396e6-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="396e6-125">Per ulteriori informazioni, vedere [Creare un flusso cloud in Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="396e6-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="396e6-126">Esempi di come utilizzare i flussi:</span><span class="sxs-lookup"><span data-stu-id="396e6-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="396e6-127">Pubblica un messaggio in un canale Microsoft Teams se un aggiornamento di un'origine dati non riesce.</span><span class="sxs-lookup"><span data-stu-id="396e6-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="396e6-128">Invia un'e-mail ai proprietari dei dati quando viene superata una soglia in un segmento.</span><span class="sxs-lookup"><span data-stu-id="396e6-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]