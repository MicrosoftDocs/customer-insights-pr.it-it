---
title: Connettore Power Automate | Microsoft Docs
description: Crea flussi in Microsoft Power Automate da Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406092"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="822de-103">Connettore Power Automate (anteprima)</span><span class="sxs-lookup"><span data-stu-id="822de-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="822de-104">Attiva eventi specifici che si verificano automaticamente quando i dati vengono modificati e gestisci flussi più complessi direttamente in [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="822de-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="822de-105">Trigger di Power Automate</span><span class="sxs-lookup"><span data-stu-id="822de-105">Power Automate triggers</span></span>

<span data-ttu-id="822de-106">Puoi utilizzare una varietà di trigger che consentono di creare flussi per automatizzare attività ripetitive, come notifiche o azioni più avanzate.</span><span class="sxs-lookup"><span data-stu-id="822de-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="822de-107">Trigger in caso di errore di aggiornamento dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="822de-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="822de-108">Trigger in caso di completamento dell'aggiornamento dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="822de-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="822de-109">Trigger in caso di superamento di una soglia su un segmento.</span><span class="sxs-lookup"><span data-stu-id="822de-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="822de-110">Il trigger è limitato al superamento della soglia.</span><span class="sxs-lookup"><span data-stu-id="822de-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="822de-111">Trigger in caso di superamento di una soglia su una misura aziendale.</span><span class="sxs-lookup"><span data-stu-id="822de-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="822de-112">Il trigger è limitato al superamento della soglia.</span><span class="sxs-lookup"><span data-stu-id="822de-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="822de-113">Trigger in caso di completamento di un aggiornamento completo (origini dati, segmenti, misure...).</span><span class="sxs-lookup"><span data-stu-id="822de-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="822de-114">Trigger in caso di completamento di un aggiornamento del processo di unificazione (mappa, corrispondenza, unione).</span><span class="sxs-lookup"><span data-stu-id="822de-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="822de-115">[Configurare i trigger in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="822de-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="822de-116">Azioni di Power Automate</span><span class="sxs-lookup"><span data-stu-id="822de-116">Power Automate actions</span></span>
<span data-ttu-id="822de-117">Il connettore di Power Automate fornisce altre azioni oltre ai trigger disponibili.</span><span class="sxs-lookup"><span data-stu-id="822de-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="822de-118">Per ulteriori informazioni, vedere la [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="822de-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="822de-119">Creare un flusso Power Automate in Audience Insights</span><span class="sxs-lookup"><span data-stu-id="822de-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="822de-120">In Audience Insights, vai a **Amministratore** > **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="822de-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="822de-121">Nella pagina **Sistema** seleziona la scheda **Stato**.</span><span class="sxs-lookup"><span data-stu-id="822de-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="822de-122">Nella sezione **Origini dati**, seleziona **Flussi** e seleziona **Crea un flusso** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="822de-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="822de-123">![Connettore Power Automate che mostra l'azione Crea un flusso](media/power-automate-connector-create-flow.png "Connettore Power Automate che mostra l'azione Crea un flusso")</span><span class="sxs-lookup"><span data-stu-id="822de-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="822de-124">In Power Automate, seleziona uno dei trigger disponibili per creare il flusso preferito.</span><span class="sxs-lookup"><span data-stu-id="822de-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="822de-125">Se stai creando il tuo primo flusso, devi prima autenticarti con il connettore Power Automate.</span><span class="sxs-lookup"><span data-stu-id="822de-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
