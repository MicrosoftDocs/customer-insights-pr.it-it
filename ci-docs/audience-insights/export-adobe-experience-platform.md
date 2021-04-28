---
title: Esportare i dati di Customer Insights in Adobe Experience Platform
description: Scopri come utilizzare i segmenti di informazioni dettagliate gruppo di destinatari in Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760106"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="517e9-103">Utilizzare i segmenti di Customer Insights in Adobe Experience Platform (anteprima)</span><span class="sxs-lookup"><span data-stu-id="517e9-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="517e9-104">Come utente di informazioni dettagliate gruppo di destinatari per Dynamics 365 Customer Insights, potresti aver creato segmenti per rendere più efficienti le tue campagne di marketing rivolgendoti a un gruppo di destinatari pertinente.</span><span class="sxs-lookup"><span data-stu-id="517e9-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="517e9-105">Per utilizzare un segmento dalle informazioni dettagliate gruppo di destinatari in Adobe Experience Platform e nelle applicazioni come Adobe Campaign Standard, devi seguire alcuni passaggi descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="517e9-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagramma di processo dei passaggi descritti in questo articolo.":::

## <a name="prerequisites"></a><span data-ttu-id="517e9-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="517e9-107">Prerequisites</span></span>

-   <span data-ttu-id="517e9-108">Licenza Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="517e9-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="517e9-109">Licenza di Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="517e9-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="517e9-110">Licenza Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="517e9-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="517e9-111">Account di archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="517e9-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="517e9-112">Informazioni generali campagna</span><span class="sxs-lookup"><span data-stu-id="517e9-112">Campaign Overview</span></span>

<span data-ttu-id="517e9-113">Per comprendere meglio come utilizzare i segmenti delle informazioni dettagliate gruppo di destinatari in Adobe Experience Platform, diamo un'occhiata a una campagna di esempio fittizia.</span><span class="sxs-lookup"><span data-stu-id="517e9-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="517e9-114">Supponiamo che la tua azienda offra un servizio mensile su abbonamento ai tuoi clienti negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="517e9-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="517e9-115">Desideri identificare i clienti i cui abbonamenti devono essere rinnovati nei prossimi otto giorni e che non hanno ancora rinnovato l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="517e9-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="517e9-116">Per mantenere questi clienti, desideri inviare loro un'offerta promozionale tramite e-mail, utilizzando Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="517e9-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="517e9-117">In questo esempio, vogliamo eseguire la campagna e-mail promozionale una volta.</span><span class="sxs-lookup"><span data-stu-id="517e9-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="517e9-118">Questo articolo non copre il caso d'uso di eseguire la campagna più di una volta.</span><span class="sxs-lookup"><span data-stu-id="517e9-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="517e9-119">Identificare il gruppo di destinatari di destinazione</span><span class="sxs-lookup"><span data-stu-id="517e9-119">Identify your target audience</span></span>

<span data-ttu-id="517e9-120">Nel nostro scenario, supponiamo che gli indirizzi e-mail dei clienti siano disponibili nelle informazioni dettagliate gruppo di destinatari e che le loro preferenze promozionali siano state analizzate per identificare i membri del segmento.</span><span class="sxs-lookup"><span data-stu-id="517e9-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="517e9-121">Il [segmento che hai definito nelle informazioni dettagliate gruppo di destinatari](segments.md) è chiamato **ChurnProneCustomers** e prevedi di inviare a questi clienti la promozione tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="517e9-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot della pagina dei segmenti con il segmento ChurnProneCustomers creato.":::

<span data-ttu-id="517e9-123">L'e-mail di offerta che desideri inviare conterrà nome, cognome e la data di fine dell'abbonamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="517e9-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="517e9-124">Informa i clienti dello sconto che riceveranno se rinnovano l'abbonamento prima che termini.</span><span class="sxs-lookup"><span data-stu-id="517e9-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="517e9-125">Esportare il gruppo di destinatari di destinazione</span><span class="sxs-lookup"><span data-stu-id="517e9-125">Export your target audience</span></span>

<span data-ttu-id="517e9-126">Una volta identificato il nostro gruppo di destinatari di destinazione, possiamo configurare l'esportazione dalle informazioni dettagliate gruppo di destinatari a un account di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="517e9-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="517e9-127">Configurare una connessione</span><span class="sxs-lookup"><span data-stu-id="517e9-127">Configure a connection</span></span>

1. <span data-ttu-id="517e9-128">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="517e9-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="517e9-129">Seleziona **Aggiungi connessione** e scegli **Archiviazione BLOB di Azure** oppure seleziona **Imposta** nel riquadro **Archiviazione BLOB di Azure**:</span><span class="sxs-lookup"><span data-stu-id="517e9-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Riquadro di configurazione per Archiviazione BLOB di Azure."::: <span data-ttu-id="517e9-131">per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="517e9-131">to configure the connection.</span></span>

1. <span data-ttu-id="517e9-132">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="517e9-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="517e9-133">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="517e9-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="517e9-134">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="517e9-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="517e9-135">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="517e9-135">Choose who can use this connection.</span></span> <span data-ttu-id="517e9-136">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="517e9-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="517e9-137">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="517e9-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="517e9-138">Immetti **Nome utente**, **Chiave account**, e **Contenitore** per l'account di archiviazione BLOB in cui vuoi esportare il segmento.</span><span class="sxs-lookup"><span data-stu-id="517e9-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot della configurazione dell'account di archiviazione. "::: 
   
    - <span data-ttu-id="517e9-140">Per altre informazioni su come trovare il nome dell'account di archiviazione BLOB e sulla chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="517e9-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="517e9-141">Per informazioni su come creare un contenitore, vedi [Creare un contenitore](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="517e9-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="517e9-142">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="517e9-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="517e9-143">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="517e9-143">Configure an export</span></span>

<span data-ttu-id="517e9-144">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="517e9-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="517e9-145">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="517e9-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="517e9-146">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="517e9-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="517e9-147">Per creare una nuova esportazione seleziona **Aggiungi esportazione**.</span><span class="sxs-lookup"><span data-stu-id="517e9-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="517e9-148">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="517e9-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="517e9-149">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="517e9-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="517e9-150">Scegli il segmento che vuoi esportare.</span><span class="sxs-lookup"><span data-stu-id="517e9-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="517e9-151">In questo esempio, è **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="517e9-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot dell'interfaccia utente per la selezione del segmento con il segmento ChurnProneCustomers selezionato.":::

1. <span data-ttu-id="517e9-153">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="517e9-153">Select **Save**.</span></span>

<span data-ttu-id="517e9-154">Dopo aver salvato la destinazione di esportazione, la trovi in **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="517e9-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="517e9-155">Ora puoi [esportare il segmento su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="517e9-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="517e9-156">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md).</span><span class="sxs-lookup"><span data-stu-id="517e9-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="517e9-157">Assicurati che il numero di record nel segmento esportato rientri nel limite consentito dalla licenza di Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="517e9-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="517e9-158">I dati esportati vengono archiviati nel contenitore dell'archivio BLOB di Azure configurato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="517e9-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="517e9-159">Il seguente percorso della cartella viene creato automaticamente nel tuo contenitore:</span><span class="sxs-lookup"><span data-stu-id="517e9-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="517e9-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="517e9-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="517e9-161">Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="517e9-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="517e9-162">Il *model.json* per le entità esportate risiederà a livello di *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="517e9-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="517e9-163">Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="517e9-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="517e9-164">Definire Experience Data Model (XDM) in Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="517e9-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="517e9-165">Prima che i dati esportati dalle informazioni dettagliate gruppo di destinatari possano essere utilizzati all'interno di Adobe Experience Platform, dobbiamo definire lo schema Experience Data Model e [configurare i dati per il profilo del cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="517e9-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="517e9-166">Scopri [cos'è XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e apprendi le [basi della composizione dello schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="517e9-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="517e9-167">Importare i dati in Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="517e9-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="517e9-168">Ora che tutto è a posto, dobbiamo importare i dati destinatari preparati dalle informazioni dettagliate gruppo di destinatari in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="517e9-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="517e9-169">Primo, [crea una connessione di origine dell'archiviazione BLOB di Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="517e9-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="517e9-170">Dopo aver definito la connessione di origine, [configura un flusso di dati](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) per una connessione batch di archiviazione cloud per importare l'output del segmento dalle informazioni dettagliate gruppo di destinatari in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="517e9-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="517e9-171">Crea un gruppo di destinatari in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="517e9-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="517e9-172">Per inviare il messaggio e-mail per questa campagna, utilizzeremo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="517e9-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="517e9-173">Dopo aver importato i dati in Adobe Experience Platform, è necessario [creare un gruppo di destinatari](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard utilizzando i dati di Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="517e9-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="517e9-174">Scopri come [utilizzare il generatore di segmenti](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard per definire un gruppo di destinatari basato sui dati di Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="517e9-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="517e9-175">Creare e inviare l'e-mail utilizzando Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="517e9-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="517e9-176">Crea il contenuto dell'e-mail e poi [esegui il test e invia](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) la tua e-mail.</span><span class="sxs-lookup"><span data-stu-id="517e9-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail di esempio con offerta di rinnovo di Adobe Campaign Standard.":::
