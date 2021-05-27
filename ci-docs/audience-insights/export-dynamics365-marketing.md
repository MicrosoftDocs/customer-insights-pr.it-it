---
title: Esportare dati di Customer Insights in Dynamics 365 Marketing
description: Scopri come configurare la connessione ed esportare in Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976805"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="79fb7-103">Utilizzare i segmenti in Dynamics 365 Marketing (anteprima)</span><span class="sxs-lookup"><span data-stu-id="79fb7-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="79fb7-104">Utilizza i [segmenti](segments.md) per generare campagne e contattare gruppi specifici di clienti con Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="79fb7-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="79fb7-105">Per ulteriori informazioni, vedere [Utilizzare segmenti da Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="79fb7-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="79fb7-106">Prerequisiti per la connessione</span><span class="sxs-lookup"><span data-stu-id="79fb7-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="79fb7-107">I record dei contatti devono essere presenti in Dynamics 365 Marketing prima di poter esportare un segmento da Customer Insights a Marketing.</span><span class="sxs-lookup"><span data-stu-id="79fb7-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="79fb7-108">Ulteriori informazioni su come inserire i contatti in [Dynamics 365 Marketing utilizzando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="79fb7-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="79fb7-109">L'esportazione di segmenti da Audience Insights a Marketing non creerà nuovi record dei contatti nelle istanze di Marketing.</span><span class="sxs-lookup"><span data-stu-id="79fb7-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="79fb7-110">I record dei contatti di Marketing devono essere inseriti in Audience Insights e utilizzati come origine dati.</span><span class="sxs-lookup"><span data-stu-id="79fb7-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="79fb7-111">Devono inoltre essere inclusi nell'entità Cliente unificata per mappare gli ID cliente agli ID contatto prima che i segmenti possano essere esportati.</span><span class="sxs-lookup"><span data-stu-id="79fb7-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="79fb7-112">Configurare la connessione a Marketing</span><span class="sxs-lookup"><span data-stu-id="79fb7-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="79fb7-113">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="79fb7-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="79fb7-114">Seleziona **Aggiungi connessione** e scegli **Dynamics 365 Marketing** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="79fb7-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="79fb7-115">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="79fb7-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="79fb7-116">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="79fb7-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="79fb7-117">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="79fb7-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="79fb7-118">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="79fb7-118">Choose who can use this connection.</span></span> <span data-ttu-id="79fb7-119">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="79fb7-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="79fb7-120">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="79fb7-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="79fb7-121">Inserisci l'URL di Marketing della tua organizzazione nel campo **Indirizzo server**.</span><span class="sxs-lookup"><span data-stu-id="79fb7-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="79fb7-122">Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="79fb7-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="79fb7-123">Esegui il mapping di un campo ID cliente all'ID contatto di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="79fb7-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="79fb7-124">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="79fb7-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="79fb7-125">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="79fb7-125">Configure an export</span></span>

<span data-ttu-id="79fb7-126">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="79fb7-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="79fb7-127">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="79fb7-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="79fb7-128">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="79fb7-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="79fb7-129">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="79fb7-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="79fb7-130">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="79fb7-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="79fb7-131">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="79fb7-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="79fb7-132">Scegli uno o più segmenti.</span><span class="sxs-lookup"><span data-stu-id="79fb7-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="79fb7-133">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79fb7-133">Select **Save**.</span></span>

<span data-ttu-id="79fb7-134">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="79fb7-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="79fb7-135">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="79fb7-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="79fb7-136">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="79fb7-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
