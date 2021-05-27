---
title: Esportare dati di Customer Insights in Dynamics 365 Sales
description: Scopri come configurare la connessione ed esportare in Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976231"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="a69a7-103">Utilizzare i segmenti in Dynamics 365 Sales (anteprima)</span><span class="sxs-lookup"><span data-stu-id="a69a7-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a69a7-104">Utilizza i tuoi dati del cliente per creare elenchi marketing, effettuare il completamento dei flussi di lavoro e inviare promozioni con Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a69a7-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="a69a7-105">Prerequisiti per la connessione</span><span class="sxs-lookup"><span data-stu-id="a69a7-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="a69a7-106">I record dei contatti devono essere presenti in Dynamics 365 Sales prima di poter esportare un segmento da Customer Insights a Sales.</span><span class="sxs-lookup"><span data-stu-id="a69a7-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="a69a7-107">Ulteriori informazioni su come inserire i contatti in [Dynamics 365 Sales utilizzando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a69a7-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="a69a7-108">L'esportazione di segmenti da Audience Insights a Sales non creerà nuovi record dei contatti nelle istanze di Sales.</span><span class="sxs-lookup"><span data-stu-id="a69a7-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="a69a7-109">I record dei contatti di Sales devono essere inseriti in Audience Insights e utilizzati come origine dati.</span><span class="sxs-lookup"><span data-stu-id="a69a7-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="a69a7-110">Devono inoltre essere inclusi nell'entità Cliente unificata per mappare gli ID cliente agli ID contatto prima che i segmenti possano essere esportati.</span><span class="sxs-lookup"><span data-stu-id="a69a7-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="a69a7-111">Configurare la connessione a Sales</span><span class="sxs-lookup"><span data-stu-id="a69a7-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="a69a7-112">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="a69a7-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a69a7-113">Seleziona **Aggiungi connessione** e scegli **Dynamics 365 Sales** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="a69a7-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="a69a7-114">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="a69a7-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a69a7-115">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="a69a7-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a69a7-116">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="a69a7-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a69a7-117">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="a69a7-117">Choose who can use this connection.</span></span> <span data-ttu-id="a69a7-118">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="a69a7-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a69a7-119">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a69a7-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a69a7-120">Inserisci l'URL di Sales della tua organizzazione nel campo **Indirizzo server**.</span><span class="sxs-lookup"><span data-stu-id="a69a7-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a69a7-121">Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a69a7-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="a69a7-122">Esegui il mapping di un campo ID cliente all'ID contatto di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a69a7-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a69a7-123">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="a69a7-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="a69a7-124">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="a69a7-124">Configure an export</span></span>

<span data-ttu-id="a69a7-125">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="a69a7-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a69a7-126">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a69a7-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a69a7-127">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="a69a7-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a69a7-128">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="a69a7-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a69a7-129">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a69a7-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="a69a7-130">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="a69a7-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a69a7-131">Scegli uno o più segmenti.</span><span class="sxs-lookup"><span data-stu-id="a69a7-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="a69a7-132">Seleziona **Salva**</span><span class="sxs-lookup"><span data-stu-id="a69a7-132">Select **Save**</span></span>

<span data-ttu-id="a69a7-133">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="a69a7-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a69a7-134">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a69a7-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a69a7-135">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a69a7-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
