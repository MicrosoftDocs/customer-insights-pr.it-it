---
title: Esportare dati di Customer Insights in Azure Data Lake Storage Gen2
description: Scopri come configurare la connessione a Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760056"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="bfeda-103">Configurare la connessione ad Azure Data Lake Storage Gen2 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="bfeda-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="bfeda-104">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="bfeda-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bfeda-105">Seleziona **Aggiungi connessione** e scegli **Azure Data Lake Gen 2** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="bfeda-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="bfeda-106">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="bfeda-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bfeda-107">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="bfeda-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bfeda-108">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="bfeda-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bfeda-109">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="bfeda-109">Choose who can use this connection.</span></span> <span data-ttu-id="bfeda-110">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="bfeda-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bfeda-111">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bfeda-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bfeda-112">Immetti **Nome account**, **Chiave account**, e **Contenitore** per il Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="bfeda-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="bfeda-113">Per scoprire come creare un account di archiviazione da usare con Azure Data Lake Storage Gen2, vedi [Creare un account di archiviazione](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="bfeda-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="bfeda-114">Per altre informazioni sul nome dell'account di archiviazione di Azure Data Lake Gen2 e sulla chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="bfeda-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="bfeda-115">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="bfeda-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="bfeda-116">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="bfeda-116">Configure an export</span></span>

<span data-ttu-id="bfeda-117">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="bfeda-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bfeda-118">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bfeda-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bfeda-119">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="bfeda-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bfeda-120">Per creare una nuova esportazione seleziona **Aggiungi esportazione**.</span><span class="sxs-lookup"><span data-stu-id="bfeda-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="bfeda-121">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="bfeda-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="bfeda-122">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="bfeda-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bfeda-123">Seleziona la casella accanto a ciascuna delle entità che desideri esportare in questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="bfeda-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="bfeda-124">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bfeda-124">Select **Save**.</span></span>

<span data-ttu-id="bfeda-125">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="bfeda-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bfeda-126">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bfeda-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bfeda-127">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bfeda-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="bfeda-128">I dati esportati vengono archiviati nel contenitore di archiviazione di Azure Data Lake Gen 2 configurato.</span><span class="sxs-lookup"><span data-stu-id="bfeda-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
