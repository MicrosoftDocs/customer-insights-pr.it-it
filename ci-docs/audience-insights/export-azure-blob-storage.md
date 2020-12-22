---
title: Esportare dati di Customer Insights in un archivio BLOB di Azure
description: Istruzioni su come configurare la connessione all'archivio BLOB di Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667144"
---
# <a name="connector-for-azure-blob-storage-preview"></a><span data-ttu-id="26b50-103">Connettore per l'archivio BLOB di Azure (anteprima)</span><span class="sxs-lookup"><span data-stu-id="26b50-103">Connector for Azure Blob storage (preview)</span></span>

<span data-ttu-id="26b50-104">Archivia dati di Customer Insights in un archivio BLOB di Azure o utilizzali per trasferire i tuoi dati in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="26b50-104">Store your Customer Insights data in an Azure Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-blob-storage"></a><span data-ttu-id="26b50-105">Configurare il connettore per l'archivio BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="26b50-105">Configure the connector for Azure Blob storage</span></span>

1. <span data-ttu-id="26b50-106">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="26b50-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="26b50-107">In **Archivio BLOB di Azure**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="26b50-107">Under **Azure Blob Storage**, select **Set up**.</span></span>

1. <span data-ttu-id="26b50-108">Immetti un valore per **Nome utente**, **Chiave account** e **Contenitore** per l'account dell'archivio BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="26b50-108">Enter **Account name**, **Account key**, and **Container** for your Azure Blob storage account.</span></span>
    - <span data-ttu-id="26b50-109">Per altre informazioni su come trovare il nome dell'account dell'archivio BLOB di Azure e la chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="26b50-109">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="26b50-110">Per informazioni su come creare un contenitore, vedi [Creare un contenitore](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="26b50-110">To learn how to create a container, see [Create a container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="26b50-111">Assegna alla tua destinazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="26b50-111">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="26b50-112">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="26b50-112">Select **Next**.</span></span>

1. <span data-ttu-id="26b50-113">Seleziona la casella accanto a ciascuna delle entità che desideri esportare in questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="26b50-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="26b50-114">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="26b50-114">Select **Save**.</span></span>

<span data-ttu-id="26b50-115">I dati esportati vengono archiviati nel contenitore dell'archivio BLOB di Azure configurato.</span><span class="sxs-lookup"><span data-stu-id="26b50-115">Exported data is stored in the Azure Blob storage container you configured.</span></span> <span data-ttu-id="26b50-116">I seguenti percorsi di cartelle vengono creati automaticamente nel contenitore:</span><span class="sxs-lookup"><span data-stu-id="26b50-116">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="26b50-117">Per entità di origine ed entità generate dal sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="26b50-117">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="26b50-118">Esempio: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="26b50-118">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="26b50-119">Il file model.json per le entità esportate risiederà al livello %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="26b50-119">The model.json for the exported entities will reside at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="26b50-120">Esempio: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="26b50-120">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

## <a name="export-the-data"></a><span data-ttu-id="26b50-121">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="26b50-121">Export the data</span></span>

<span data-ttu-id="26b50-122">Puoi [esportare dati su richiesta](/export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="26b50-122">You can [export data on demand](/export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="26b50-123">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="26b50-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
