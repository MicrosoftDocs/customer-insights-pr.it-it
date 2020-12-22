---
title: Esportare dati di Customer Insights in Dynamics 365 Marketing
description: Informazioni su come configurare la connessione a Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643778"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="6076d-103">Connettore per Dynamics 365 Marketing (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6076d-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6076d-104">Utilizza i [segmenti](segments.md) per generare campagne e contattare gruppi specifici di clienti con Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="6076d-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="6076d-105">Per ulteriori informazioni, vedere [Utilizzare segmenti da Dynamics 365 Customer Insights con Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="6076d-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="6076d-106">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="6076d-106">Prerequisite</span></span>

<span data-ttu-id="6076d-107">Record del contatto [di Dynamics 365 Marketing inseriti utilizzando Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="6076d-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="6076d-108">Configurare il connettore per Marketing</span><span class="sxs-lookup"><span data-stu-id="6076d-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="6076d-109">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="6076d-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6076d-110">In **Dynamics 365 Marketing**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="6076d-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="6076d-111">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="6076d-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6076d-112">Inserisci l'URL di Marketing della tua organizzazione nel campo **Indirizzo server**.</span><span class="sxs-lookup"><span data-stu-id="6076d-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="6076d-113">Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="6076d-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="6076d-114">Esegui il mapping di un campo ID cliente all'ID contatto di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6076d-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="6076d-115">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6076d-115">Select **Next**.</span></span>

1. <span data-ttu-id="6076d-116">Scegli uno o più segmenti.</span><span class="sxs-lookup"><span data-stu-id="6076d-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="6076d-117">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6076d-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6076d-118">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="6076d-118">Export the data</span></span>

<span data-ttu-id="6076d-119">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6076d-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6076d-120">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6076d-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
