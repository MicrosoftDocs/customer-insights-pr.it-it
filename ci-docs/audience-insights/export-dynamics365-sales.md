---
title: Esportare dati di Customer Insights in Dynamics 365 Sales
description: Informazioni su come configurare la connessione a Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598114"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="874c2-103">Connettore per Dynamics 365 Sales (anteprima)</span><span class="sxs-lookup"><span data-stu-id="874c2-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="874c2-104">Utilizza i tuoi dati del cliente per creare elenchi marketing, effettuare il completamento dei flussi di lavoro e inviare promozioni con Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="874c2-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="874c2-105">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="874c2-105">Prerequisite</span></span>

1. <span data-ttu-id="874c2-106">I record dei contatti devono essere presenti in Dynamics 365 Sales prima di poter esportare un segmento da Customer Insights a Sales.</span><span class="sxs-lookup"><span data-stu-id="874c2-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="874c2-107">Ulteriori informazioni su come inserire i contatti in [Dynamics 365 Sales utilizzando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="874c2-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="874c2-108">L'esportazione di segmenti da Audience Insights a Sales non creerà nuovi record dei contatti nelle istanze di Sales.</span><span class="sxs-lookup"><span data-stu-id="874c2-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="874c2-109">I record dei contatti di Sales devono essere inseriti in Audience Insights e utilizzati come origine dati.</span><span class="sxs-lookup"><span data-stu-id="874c2-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="874c2-110">Devono inoltre essere inclusi nell'entità Cliente unificata per mappare gli ID cliente agli ID contatto prima che i segmenti possano essere esportati.</span><span class="sxs-lookup"><span data-stu-id="874c2-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="874c2-111">Configurare il connettore per Sales</span><span class="sxs-lookup"><span data-stu-id="874c2-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="874c2-112">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="874c2-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="874c2-113">In **Dynamics 365 Sales**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="874c2-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="874c2-114">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="874c2-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="874c2-115">Inserisci l'URL di Sales della tua organizzazione nel campo **Indirizzo server**.</span><span class="sxs-lookup"><span data-stu-id="874c2-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="874c2-116">Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="874c2-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="874c2-117">Esegui il mapping di un campo ID cliente all'ID contatto di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="874c2-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="874c2-118">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="874c2-118">Select **Next**.</span></span>

1. <span data-ttu-id="874c2-119">Scegli uno o più segmenti.</span><span class="sxs-lookup"><span data-stu-id="874c2-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="874c2-120">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="874c2-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="874c2-121">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="874c2-121">Export the data</span></span>

<span data-ttu-id="874c2-122">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="874c2-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="874c2-123">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="874c2-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]