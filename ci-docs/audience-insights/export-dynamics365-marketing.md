---
title: Esportare dati di Customer Insights in Dynamics 365 Marketing
description: Informazioni su come configurare la connessione a Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269059"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="74ddc-103">Connettore per Dynamics 365 Marketing (anteprima)</span><span class="sxs-lookup"><span data-stu-id="74ddc-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="74ddc-104">Utilizza i [segmenti](segments.md) per generare campagne e contattare gruppi specifici di clienti con Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="74ddc-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="74ddc-105">Per ulteriori informazioni, vedere [Utilizzare segmenti da Dynamics 365 Customer Insights con Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="74ddc-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="74ddc-106">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="74ddc-106">Prerequisite</span></span>

- <span data-ttu-id="74ddc-107">I record dei contatti devono essere presenti in Dynamics 365 Marketing prima di poter esportare un segmento da Customer Insights a Marketing.</span><span class="sxs-lookup"><span data-stu-id="74ddc-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="74ddc-108">Ulteriori informazioni su come inserire i contatti in [Dynamics 365 Marketing utilizzando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="74ddc-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="74ddc-109">L'esportazione di segmenti da Audience Insights a Marketing non creerà nuovi record dei contatti nelle istanze di Marketing.</span><span class="sxs-lookup"><span data-stu-id="74ddc-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="74ddc-110">I record dei contatti di Marketing devono essere inseriti in Audience Insights e utilizzati come origine dati.</span><span class="sxs-lookup"><span data-stu-id="74ddc-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="74ddc-111">Devono inoltre essere inclusi nell'entità Cliente unificata per mappare gli ID cliente agli ID contatto prima che i segmenti possano essere esportati.</span><span class="sxs-lookup"><span data-stu-id="74ddc-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="74ddc-112">Configurare il connettore per Marketing</span><span class="sxs-lookup"><span data-stu-id="74ddc-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="74ddc-113">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="74ddc-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="74ddc-114">In **Dynamics 365 Marketing**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="74ddc-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="74ddc-115">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="74ddc-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="74ddc-116">Inserisci l'URL di Marketing della tua organizzazione nel campo **Indirizzo server**.</span><span class="sxs-lookup"><span data-stu-id="74ddc-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="74ddc-117">Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="74ddc-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="74ddc-118">Esegui il mapping di un campo ID cliente all'ID contatto di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="74ddc-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="74ddc-119">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="74ddc-119">Select **Next**.</span></span>

1. <span data-ttu-id="74ddc-120">Scegli uno o più segmenti.</span><span class="sxs-lookup"><span data-stu-id="74ddc-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="74ddc-121">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="74ddc-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="74ddc-122">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="74ddc-122">Export the data</span></span>

<span data-ttu-id="74ddc-123">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="74ddc-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="74ddc-124">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="74ddc-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]