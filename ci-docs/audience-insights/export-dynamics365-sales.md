---
title: Esportare dati di Customer Insights in Dynamics 365 Sales
description: Informazioni su come configurare la connessione a Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643823"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="aabe6-103">Connettore per Dynamics 365 Sales (anteprima)</span><span class="sxs-lookup"><span data-stu-id="aabe6-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="aabe6-104">Utilizza i tuoi dati cliente per creare elenchi marketing, effettuare il completamento dei flussi di lavoro e inviare promozioni con Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="aabe6-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="aabe6-105">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="aabe6-105">Prerequisite</span></span>

<span data-ttu-id="aabe6-106">Record del contatto [di Dynamics 365 Sales inseriti utilizzando Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="aabe6-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="aabe6-107">Configurare il connettore per Sales</span><span class="sxs-lookup"><span data-stu-id="aabe6-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="aabe6-108">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="aabe6-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="aabe6-109">In **Dynamics 365 Sales**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="aabe6-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="aabe6-110">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="aabe6-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="aabe6-111">Inserisci l'URL di Sales della tua organizzazione nel campo **Indirizzo server**.</span><span class="sxs-lookup"><span data-stu-id="aabe6-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="aabe6-112">Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="aabe6-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="aabe6-113">Esegui il mapping di un campo ID cliente all'ID contatto di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="aabe6-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="aabe6-114">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aabe6-114">Select **Next**.</span></span>

1. <span data-ttu-id="aabe6-115">Scegli uno o più segmenti.</span><span class="sxs-lookup"><span data-stu-id="aabe6-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="aabe6-116">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="aabe6-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="aabe6-117">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="aabe6-117">Export the data</span></span>

<span data-ttu-id="aabe6-118">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="aabe6-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="aabe6-119">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aabe6-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
