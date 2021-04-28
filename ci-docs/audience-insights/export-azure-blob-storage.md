---
title: Esportare dati di Customer Insights in un archivio BLOB di Azure
description: Scopri come configurare la connessione ed esportare nell'archivio BLOB.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760194"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="c354e-103">Esportare l'elenco dei segmenti e altri dati in Archiviazione BLOB di Azure (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c354e-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="c354e-104">Archivia i dati di Customer Insights in un archivio BLOB o utilizzali per trasferire i dati ad altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c354e-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="c354e-105">Configurare la connessione all'archivio BLOB</span><span class="sxs-lookup"><span data-stu-id="c354e-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="c354e-106">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="c354e-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c354e-107">Seleziona **Aggiungi connessione** e scegli **Archiviazione BLOB di Azure** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="c354e-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="c354e-108">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="c354e-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c354e-109">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="c354e-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c354e-110">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="c354e-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c354e-111">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="c354e-111">Choose who can use this connection.</span></span> <span data-ttu-id="c354e-112">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="c354e-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c354e-113">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c354e-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c354e-114">Immetti il **Nome utente**, la **Chiave account**, e il **Contenitore** per il tuo account di archiviazione BLOB.</span><span class="sxs-lookup"><span data-stu-id="c354e-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="c354e-115">Per altre informazioni su come trovare il nome dell'account di archiviazione BLOB e sulla chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c354e-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="c354e-116">Per informazioni su come creare un contenitore, vedi [Creare un contenitore](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="c354e-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c354e-117">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="c354e-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="c354e-118">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="c354e-118">Configure an export</span></span>

<span data-ttu-id="c354e-119">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="c354e-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c354e-120">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c354e-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c354e-121">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="c354e-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c354e-122">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="c354e-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c354e-123">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="c354e-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="c354e-124">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="c354e-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c354e-125">Seleziona la casella accanto a ciascuna delle entità che desideri esportare in questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="c354e-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="c354e-126">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c354e-126">Select **Save**.</span></span>

<span data-ttu-id="c354e-127">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="c354e-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c354e-128">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c354e-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="c354e-129">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c354e-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="c354e-130">I dati esportati vengono archiviati nel contenitore di archiviazione BLOB configurato.</span><span class="sxs-lookup"><span data-stu-id="c354e-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="c354e-131">I seguenti percorsi di cartelle vengono creati automaticamente nel contenitore:</span><span class="sxs-lookup"><span data-stu-id="c354e-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="c354e-132">Per entità di origine ed entità generate dal sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="c354e-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="c354e-133">Esempio: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="c354e-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="c354e-134">Il model.json per le entità esportate sarà a livello di %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="c354e-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="c354e-135">Esempio: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="c354e-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
