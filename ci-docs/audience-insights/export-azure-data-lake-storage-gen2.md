---
title: Esportare dati di Customer Insights in Azure Data Lake Storage Gen2
description: Scopri come configurare la connessione a Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477184"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="27271-103">Connettore per Azure Data Lake Storage Gen2 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="27271-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="27271-104">Archivia i dati di Customer Insights in Azure Data Lake Storage Gen2 o utilizzali per trasferire i dati ad altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="27271-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="27271-105">Configurare il connettore per Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="27271-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="27271-106">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="27271-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="27271-107">In **Azure Data Lake Storage Gen2**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="27271-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="27271-108">Assegna alla tua destinazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="27271-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="27271-109">Immetti **Nome account**, **Chiave account**, e **Contenitore** per il Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="27271-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="27271-110">Per scoprire come creare un account di archiviazione da usare con Azure Data Lake Storage Gen2, vedi [Creare un account di archiviazione](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="27271-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="27271-111">Per altre informazioni su come trovare il nome dell'account Azure Data Lake Gen2 e la chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="27271-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="27271-112">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27271-112">Select **Next**.</span></span>

1. <span data-ttu-id="27271-113">Seleziona la casella accanto a ciascuna delle entità che desideri esportare in questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="27271-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="27271-114">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27271-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="27271-115">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="27271-115">Export the data</span></span>

<span data-ttu-id="27271-116">Puoi [esportare dati su richiesta](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="27271-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="27271-117">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="27271-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
