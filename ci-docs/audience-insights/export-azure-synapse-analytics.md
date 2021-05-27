---
title: Esportare i dati di Customer Insights in Azure Synapse Analytics
description: Scopri come configurare la connessione ed esportare in Azure Synapse Analytics
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977382"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="e36f2-103">Esportare i dati in Azure Synapse Analytics (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e36f2-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="e36f2-104">Azure Synapse è un servizio di analisi che accelera il tempo per ottenere informazioni dettagliate tra data warehouse e sistemi di big data.</span><span class="sxs-lookup"><span data-stu-id="e36f2-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="e36f2-105">Puoi inserire e utilizzare i dati di Customer Insights in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="e36f2-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e36f2-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e36f2-106">Prerequisites</span></span>

<span data-ttu-id="e36f2-107">I seguenti prerequisiti devono essere soddisfatti per configurare la connessione da Customer Insights a Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="e36f2-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="e36f2-108">Assicurati di impostare tutte le **assegnazioni di ruoli** come descritto.</span><span class="sxs-lookup"><span data-stu-id="e36f2-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="e36f2-109">Prerequisiti in Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e36f2-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="e36f2-110">Disponi di un ruolo utente **Amministratore** nell'ambiente di informazioni dettagliate sul gruppo di destinatari.</span><span class="sxs-lookup"><span data-stu-id="e36f2-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="e36f2-111">Scopri di più sull'[impostazione delle autorizzazioni utente nell'ambiente di informazioni dettagliate sul gruppo di destinatari](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="e36f2-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="e36f2-112">In Azure:</span><span class="sxs-lookup"><span data-stu-id="e36f2-112">In Azure:</span></span> 

- <span data-ttu-id="e36f2-113">Una sottoscrizione di Azure attiva.</span><span class="sxs-lookup"><span data-stu-id="e36f2-113">An active Azure subscription.</span></span>

- <span data-ttu-id="e36f2-114">Se si utilizza un nuovo account Azure Data Lake Storage Gen2, *l'entità servizio per le informazioni dettagliate sul gruppo di destinatari* ha bisogno delle autorizzazioni DI **collaboratore ai dati BLOB del servizio di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="e36f2-115">Scopri di più sul [collegamento a un account Azure Data Lake Storage Gen2 con l'entità servizio di Azure per le informazioni dettagliate sul gruppo di destinatari](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e36f2-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="e36f2-116">Il Data Lake Storage Gen2 **deve avere** lo [spazio dei nomi gerarchico](/azure/storage/blobs/data-lake-storage-namespace) abilitato.</span><span class="sxs-lookup"><span data-stu-id="e36f2-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="e36f2-117">Nel gruppo di risorse in cui si trova l'area di lavoro Azure Synapse, *all'entità servizio* e *all'utente per le informazioni dettagliate sul gruppo di destinatari* devono essere assegnate almeno le autorizzazioni di **lettura**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="e36f2-118">Per ulteriori informazioni, vedi [Assegnare ruoli di Azure usando il portale di Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="e36f2-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="e36f2-119">L'*utente* deve avere le autorizzazioni del **collaboratore ai dati BLOB del servizio di archiviazione** per l'account Azure Data Lake Storage Gen2 in cui si trovano i dati e deve essere collegato all'area di lavoro Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="e36f2-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="e36f2-120">Scopri di più sull'[utilizzo del portale di Azure per assegnare un ruolo di Azure per l'accesso ai dati di BLOB e coda](/azure/storage/common/storage-auth-aad-rbac-portal) e sulle [autorizzazioni del collaboratore ai dati BLOB del servizio di archiviazione](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="e36f2-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="e36f2-121">L'*[identità gestita dall'area di lavoro Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* deve avere le autorizzazioni del **collaboratore ai dati BLOB del servizio di archiviazione** per l'account Azure Data Lake Storage Gen2 in cui si trovano i dati e deve essere collegato all'area di lavoro Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="e36f2-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="e36f2-122">Scopri di più sull'[utilizzo del portale di Azure per assegnare un ruolo di Azure per l'accesso ai dati di BLOB e coda](/azure/storage/common/storage-auth-aad-rbac-portal) e sulle [autorizzazioni del collaboratore ai dati BLOB del servizio di archiviazione](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="e36f2-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="e36f2-123">Nell'area di lavoro Azure Synapse, *l'entità servizio per le informazioni dettagliate sul gruppo di destinatari* deve avere il ruolo **amministratore Synapse** assegnato.</span><span class="sxs-lookup"><span data-stu-id="e36f2-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="e36f2-124">Per ulteriori informazioni, vedi [Come impostare il controllo degli accessi per l'area di lavoro Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="e36f2-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="e36f2-125">Configurare la connessione ed esportare in Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="e36f2-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="e36f2-126">Configurare una connessione</span><span class="sxs-lookup"><span data-stu-id="e36f2-126">Configure a connection</span></span>

1. <span data-ttu-id="e36f2-127">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e36f2-128">Seleziona **Aggiungi connessione** e scegli **Azure Synapse Analytics** o seleziona **Imposta** nel riquadro **Azure Synapse Analytics** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="e36f2-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="e36f2-129">Assegna alla tua connessione un nome riconoscibile nel campo Nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="e36f2-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="e36f2-130">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="e36f2-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="e36f2-131">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="e36f2-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e36f2-132">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="e36f2-132">Choose who can use this connection.</span></span> <span data-ttu-id="e36f2-133">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="e36f2-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e36f2-134">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e36f2-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e36f2-135">Seleziona o cerca l'abbonamento in cui desideri utilizzare i dati di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e36f2-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="e36f2-136">Non appena viene selezionato un abbonamento, puoi anche selezionare **Area di lavoro**, **Account di archiviazione**, e **Contenitore**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="e36f2-137">Per salvare la connessione seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="e36f2-138">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="e36f2-138">Configure an export</span></span>

<span data-ttu-id="e36f2-139">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="e36f2-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e36f2-140">Per ulteriori informazioni, vedi [autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e36f2-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e36f2-141">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e36f2-142">Per creare una nuova esportazione seleziona **Aggiungi esportazione**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="e36f2-143">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="e36f2-144">Se non vedi il nome di questa sezione, non sono disponibili [connessioni](connections.md) di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="e36f2-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="e36f2-145">Fornisci un **nome visualizzato** riconoscibile per la tua esportazione e un **Nome del database**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="e36f2-146">Seleziona le entità che desideri esportare in Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="e36f2-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="e36f2-147">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-147">Select **Save**.</span></span>

<span data-ttu-id="e36f2-148">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="e36f2-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e36f2-149">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e36f2-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e36f2-150">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e36f2-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="e36f2-151">Aggiornare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="e36f2-151">Update an export</span></span>

1. <span data-ttu-id="e36f2-152">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="e36f2-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e36f2-153">Seleziona **Modifica** nell'esportazione che vuoi aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e36f2-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="e36f2-154">**Aggiungi** o **Rimuovi** le entità dalla selezione.</span><span class="sxs-lookup"><span data-stu-id="e36f2-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="e36f2-155">Se le entità vengono rimosse dalla selezione, non vengono eliminate dal database di Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="e36f2-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="e36f2-156">Tuttavia, gli aggiornamenti futuri dei dati non aggiorneranno le entità rimosse in quel database.</span><span class="sxs-lookup"><span data-stu-id="e36f2-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="e36f2-157">La **modifica del nome del database** crea un nuovo database Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="e36f2-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="e36f2-158">Il database con il nome configurato in precedenza non riceverà gli aggiornamenti futuri.</span><span class="sxs-lookup"><span data-stu-id="e36f2-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
