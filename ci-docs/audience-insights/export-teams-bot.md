---
title: Bot per Microsoft Teams
description: Cerca i profili cliente unificati in Microsoft Teams con l'aiuto di un bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267957"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="5833a-103">Bot di Teams per Dynamics 365 Customer Insights (anteprima)</span><span class="sxs-lookup"><span data-stu-id="5833a-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="5833a-104">Connettiti con Microsoft Teams per consentire a un bot di cercare profili cliente unificati nei canali di Teams.</span><span class="sxs-lookup"><span data-stu-id="5833a-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5833a-105">![Bot di Teams che mostra un record del cliente](media/teams-bot.png "Bot di Teams che mostra un record del cliente")</span><span class="sxs-lookup"><span data-stu-id="5833a-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5833a-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5833a-106">Prerequisites</span></span>

<span data-ttu-id="5833a-107">Per impostare e configurare il bot, devono essere soddisfatti i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="5833a-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5833a-108">Deve esserci almeno un'[origine dati aggiunta](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="5833a-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="5833a-109">Il [processo di unificazione](data-unification.md) è stato completato.</span><span class="sxs-lookup"><span data-stu-id="5833a-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="5833a-110">I campi vengono aggiunti all'[indice di ricerca e dei filtri](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="5833a-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="5833a-111">Customer Insights e Teams sono nella stessa organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5833a-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="5833a-112">Configurare il bot</span><span class="sxs-lookup"><span data-stu-id="5833a-112">Configure the bot</span></span>

1. <span data-ttu-id="5833a-113">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="5833a-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="5833a-114">Nel riquadro Microsoft Teams, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="5833a-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="5833a-115">Vieni reindirizzato all'area **App** in Teams.</span><span class="sxs-lookup"><span data-stu-id="5833a-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="5833a-116">Puoi anche aprire Teams e selezionare **App** nell'angolo in basso a sinistra o [scaricarla da AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) direttamente.</span><span class="sxs-lookup"><span data-stu-id="5833a-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="5833a-117">Cerca **Customer Insights** e seleziona l'app.</span><span class="sxs-lookup"><span data-stu-id="5833a-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="5833a-118">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5833a-118">Select **Add**.</span></span>
1. <span data-ttu-id="5833a-119">Dopo aver effettuato l'accesso a Customer Insights in Teams, viene visualizzato un messaggio di benvenuto e potrai iniziare.</span><span class="sxs-lookup"><span data-stu-id="5833a-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="5833a-120">Operazioni eseguibili con il bot</span><span class="sxs-lookup"><span data-stu-id="5833a-120">Things you can do with the bot</span></span>

<span data-ttu-id="5833a-121">Il bot offre funzionalità di ricerca per profili cliente unificati.</span><span class="sxs-lookup"><span data-stu-id="5833a-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="5833a-122">Immetti **cerca** seguito da un nome, un indirizzo e-mail o qualsiasi altro campo nel profilo cliente unificato che viene aggiunto all'indice di ricerca e filtro.</span><span class="sxs-lookup"><span data-stu-id="5833a-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="5833a-123">Otterrai una scheda con un massimo di 15 campi dal profilo cliente risultante.</span><span class="sxs-lookup"><span data-stu-id="5833a-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="5833a-124">Più corrispondenze restituiscono un elenco di risultati in cui è possibile selezionare un profilo.</span><span class="sxs-lookup"><span data-stu-id="5833a-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="5833a-125">Puoi aggiungere il termine di ricerca tra virgolette doppie per cercare una corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="5833a-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="5833a-126">Se la tua organizzazione gestisce più ambienti Customer Insights nella stessa organizzazione, puoi immettere **switchinstance** per scegliere l'ambiente a cui connettere il bot.</span><span class="sxs-lookup"><span data-stu-id="5833a-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="5833a-127">Immetti **Aiuto** per visualizzare un elenco di comandi disponibili per il bot.</span><span class="sxs-lookup"><span data-stu-id="5833a-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]