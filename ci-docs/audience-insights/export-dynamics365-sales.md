---
title: Esportare dati di Customer Insights in Dynamics 365 Sales
description: Informazioni su come configurare la connessione a Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269013"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="634e2-103">Connettore per Dynamics 365 Sales (anteprima)</span><span class="sxs-lookup"><span data-stu-id="634e2-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="634e2-104">Utilizza i tuoi dati del cliente per creare elenchi marketing, effettuare il completamento dei flussi di lavoro e inviare promozioni con Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="634e2-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="634e2-105">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="634e2-105">Prerequisite</span></span>

1. <span data-ttu-id="634e2-106">I record dei contatti devono essere presenti in Dynamics 365 Sales prima di poter esportare un segmento da Customer Insights a Sales.</span><span class="sxs-lookup"><span data-stu-id="634e2-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="634e2-107">Ulteriori informazioni su come inserire i contatti in [Dynamics 365 Sales utilizzando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="634e2-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="634e2-108">L'esportazione di segmenti da Audience Insights a Sales non creerà nuovi record dei contatti nelle istanze di Sales.</span><span class="sxs-lookup"><span data-stu-id="634e2-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="634e2-109">I record dei contatti di Sales devono essere inseriti in Audience Insights e utilizzati come origine dati.</span><span class="sxs-lookup"><span data-stu-id="634e2-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="634e2-110">Devono inoltre essere inclusi nell'entità Cliente unificata per mappare gli ID cliente agli ID contatto prima che i segmenti possano essere esportati.</span><span class="sxs-lookup"><span data-stu-id="634e2-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="634e2-111">Configurare il connettore per Sales</span><span class="sxs-lookup"><span data-stu-id="634e2-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="634e2-112">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="634e2-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="634e2-113">In **Dynamics 365 Sales**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="634e2-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="634e2-114">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="634e2-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="634e2-115">Inserisci l'URL di Sales della tua organizzazione nel campo **Indirizzo server**.</span><span class="sxs-lookup"><span data-stu-id="634e2-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="634e2-116">Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="634e2-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="634e2-117">Esegui il mapping di un campo ID cliente all'ID contatto di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="634e2-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="634e2-118">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="634e2-118">Select **Next**.</span></span>

1. <span data-ttu-id="634e2-119">Scegli uno o più segmenti.</span><span class="sxs-lookup"><span data-stu-id="634e2-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="634e2-120">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="634e2-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="634e2-121">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="634e2-121">Export the data</span></span>

<span data-ttu-id="634e2-122">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="634e2-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="634e2-123">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="634e2-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]