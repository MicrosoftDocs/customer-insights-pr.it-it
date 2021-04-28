---
title: Esportare i dati di Customer Insights in Adobe Campaign Standard
description: Scopri come utilizzare i segmenti di informazioni dettagliate gruppo di destinatari in Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760286"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="1019a-103">Utilizzare i segmenti di Customer Insights in Adobe Campaign Standard (anteprima)</span><span class="sxs-lookup"><span data-stu-id="1019a-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="1019a-104">Come utente di informazioni dettagliate gruppo di destinatari per Dynamics 365 Customer Insights, potresti aver creato segmenti per rendere più efficienti le tue campagne di marketing rivolgendoti a un gruppo di destinatari pertinente.</span><span class="sxs-lookup"><span data-stu-id="1019a-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="1019a-105">Per utilizzare un segmento dalle informazioni dettagliate gruppo di destinatari in Adobe Experience Platform e nelle applicazioni come Adobe Campaign Standard, devi seguire alcuni passaggi descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1019a-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagramma di processo dei passaggi descritti in questo articolo.":::

## <a name="prerequisites"></a><span data-ttu-id="1019a-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1019a-107">Prerequisites</span></span>

-   <span data-ttu-id="1019a-108">Licenza Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1019a-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="1019a-109">Licenza Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1019a-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="1019a-110">Account di archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="1019a-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="1019a-111">Informazioni generali campagna</span><span class="sxs-lookup"><span data-stu-id="1019a-111">Campaign Overview</span></span>

<span data-ttu-id="1019a-112">Per comprendere meglio come utilizzare i segmenti delle informazioni dettagliate gruppo di destinatari in Adobe Experience Platform, diamo un'occhiata a una campagna di esempio fittizia.</span><span class="sxs-lookup"><span data-stu-id="1019a-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="1019a-113">Supponiamo che la tua azienda offra un servizio mensile su abbonamento ai tuoi clienti negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="1019a-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="1019a-114">Desideri identificare i clienti i cui abbonamenti devono essere rinnovati nei prossimi otto giorni e che non hanno ancora rinnovato l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1019a-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="1019a-115">Per mantenere questi clienti, desideri inviare loro un'offerta promozionale tramite e-mail, utilizzando Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1019a-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="1019a-116">In questo esempio, vogliamo eseguire la campagna e-mail promozionale una volta.</span><span class="sxs-lookup"><span data-stu-id="1019a-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="1019a-117">Questo articolo non copre il caso d'uso di eseguire la campagna più di una volta.</span><span class="sxs-lookup"><span data-stu-id="1019a-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="1019a-118">Tuttavia, le informazioni dettagliate gruppo di destinatari e Adobe Campaign Standard possono essere configurati per funzionare anche in uno scenario di campagna ricorrente.</span><span class="sxs-lookup"><span data-stu-id="1019a-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="1019a-119">Identificare il gruppo di destinatari di destinazione</span><span class="sxs-lookup"><span data-stu-id="1019a-119">Identify your target audience</span></span>

<span data-ttu-id="1019a-120">Nel nostro scenario, supponiamo che gli indirizzi e-mail dei clienti siano disponibili nelle informazioni dettagliate gruppo di destinatari e che le loro preferenze promozionali siano state analizzate per identificare i membri del segmento.</span><span class="sxs-lookup"><span data-stu-id="1019a-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="1019a-121">Il [segmento che hai definito nelle informazioni dettagliate gruppo di destinatari](segments.md) è chiamato **ChurnProneCustomers** e prevedi di inviare a questi clienti la promozione tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1019a-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot della pagina dei segmenti con il segmento ChurnProneCustomers creato.":::

<span data-ttu-id="1019a-123">L'e-mail di offerta che desideri inviare conterrà nome, cognome e la data di fine dell'abbonamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="1019a-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="1019a-124">Informa i clienti dello sconto che riceveranno se rinnovano l'abbonamento prima che termini.</span><span class="sxs-lookup"><span data-stu-id="1019a-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="1019a-125">Esportare il gruppo di destinatari di destinazione</span><span class="sxs-lookup"><span data-stu-id="1019a-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="1019a-126">Configurare una connessione</span><span class="sxs-lookup"><span data-stu-id="1019a-126">Configure a connection</span></span>

<span data-ttu-id="1019a-127">Una volta identificato il nostro gruppo di destinatari di destinazione, possiamo configurare l'esportazione dalle informazioni dettagliate gruppo di destinatari a un account di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="1019a-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="1019a-128">In informazioni dettagliate sul gruppo di destinatari, vai a **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="1019a-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1019a-129">Seleziona **Aggiungi connessione** e scegli **Adobe Campaign** per configurare la connessione o seleziona **Imposta** nel riquadro **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="1019a-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Riquadro di configurazione per Adobe Campaign Standard.":::

1. <span data-ttu-id="1019a-131">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="1019a-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1019a-132">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="1019a-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1019a-133">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="1019a-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1019a-134">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="1019a-134">Choose who can use this connection.</span></span> <span data-ttu-id="1019a-135">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="1019a-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1019a-136">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1019a-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1019a-137">Immetti **Nome utente**, **Chiave account**, e **Contenitore** dell'account di archiviazione BLOB di Azure in cui vuoi esportare il segmento.</span><span class="sxs-lookup"><span data-stu-id="1019a-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot della configurazione dell'account di archiviazione. "::: 

   - <span data-ttu-id="1019a-139">Per altre informazioni su come trovare il nome dell'account dell'archivio BLOB di Azure e la chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1019a-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="1019a-140">Per informazioni su come creare un contenitore, vedi [Creare un contenitore](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="1019a-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1019a-141">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="1019a-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="1019a-142">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="1019a-142">Configure an export</span></span>

<span data-ttu-id="1019a-143">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="1019a-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1019a-144">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1019a-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1019a-145">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="1019a-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1019a-146">Per creare una nuova esportazione seleziona **Aggiungi esportazione**.</span><span class="sxs-lookup"><span data-stu-id="1019a-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="1019a-147">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="1019a-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="1019a-148">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="1019a-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1019a-149">Scegli il segmento che vuoi esportare.</span><span class="sxs-lookup"><span data-stu-id="1019a-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="1019a-150">In questo esempio, è **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1019a-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot dell'interfaccia utente per la selezione del segmento con il segmento ChurnProneCustomers selezionato.":::

1. <span data-ttu-id="1019a-152">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1019a-152">Select **Next**.</span></span>

1. <span data-ttu-id="1019a-153">Ora mappiamo i campi di **origine** dal segmento delle informazioni dettagliate gruppo di destinatari ai nomi dei campi di **destinazione** nello schema del profilo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1019a-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mappatura dei campi per il connettore Adobe Campaign Standard.":::

   <span data-ttu-id="1019a-155">Se desideri aggiungere più attributi, seleziona **Aggiungi attributo**.</span><span class="sxs-lookup"><span data-stu-id="1019a-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="1019a-156">Il nome di destinazione può essere diverso dal nome del campo di origine in modo che tu possa comunque mappare l'output del segmento dalle informazioni dettagliate gruppo di destinatari ad Adobe Campaign Standard se i campi non hanno lo stesso nome nei due sistemi.</span><span class="sxs-lookup"><span data-stu-id="1019a-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1019a-157">L'indirizzo e-mail viene utilizzato come campo di identità, ma puoi utilizzare qualsiasi altro identificatore dal tuo profilo cliente delle informazioni dettagliate gruppo di destinatari per mappare i dati in Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1019a-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="1019a-158">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1019a-158">Select **Save**.</span></span>

<span data-ttu-id="1019a-159">Dopo aver salvato la destinazione di esportazione, la trovi in **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="1019a-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="1019a-160">Ora puoi [esportare il segmento su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1019a-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1019a-161">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md).</span><span class="sxs-lookup"><span data-stu-id="1019a-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1019a-162">Assicurati che il numero di record nel segmento esportato rientri nel limite consentito dalla licenza di Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1019a-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="1019a-163">I dati esportati vengono archiviati nel contenitore dell'archivio BLOB di Azure configurato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1019a-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="1019a-164">Il seguente percorso della cartella viene creato automaticamente nel tuo contenitore:</span><span class="sxs-lookup"><span data-stu-id="1019a-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="1019a-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="1019a-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="1019a-166">Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="1019a-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="1019a-167">Configurare Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1019a-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="1019a-168">Quando un segmento dalle informazioni dettagliate gruppo di destinatari viene esportato, contiene le colonne selezionate durante la definizione della destinazione di esportazione nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="1019a-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="1019a-169">Questi dati possono essere utilizzati per [creare profili in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="1019a-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="1019a-170">Per utilizzare il segmento in Adobe Campaign Standard, è necessario estendere lo schema del profilo in Adobe Campaign Standard per includere due campi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1019a-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="1019a-171">Scopri come [estendere la risorsa profilo](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) con nuovi campi in Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1019a-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="1019a-172">Nel nostro esempio, questi campi sono *Nome segmento e Data del segmento (facoltativa).*</span><span class="sxs-lookup"><span data-stu-id="1019a-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="1019a-173">Utilizzeremo questi campi per identificare i profili in Adobe Campaign Standard che vogliamo scegliere come destinazione per questa campagna.</span><span class="sxs-lookup"><span data-stu-id="1019a-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="1019a-174">Se non ci sono altri record in Adobe Campaign Standard, oltre a quello che stai per importare, puoi saltare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="1019a-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="1019a-175">Importare i dati in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1019a-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="1019a-176">Ora che tutto è a posto, dobbiamo importare i dati destinatari preparati dalle informazioni dettagliate gruppo di destinatari in Adobe Campaign Standard per creare i profili.</span><span class="sxs-lookup"><span data-stu-id="1019a-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="1019a-177">Scopri [come importare i profili in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) utilizzando un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1019a-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="1019a-178">Il flusso di lavoro di importazione nell'immagine seguente è stato configurato per essere eseguito ogni 8 ore e cerca segmenti delle informazioni dettagliate gruppo di destinatari esportati (file .csv nell'archiviazione BLOB di Azure).</span><span class="sxs-lookup"><span data-stu-id="1019a-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="1019a-179">Il flusso di lavoro estrae il contenuto del file .csv in un ordine di colonna specificato.</span><span class="sxs-lookup"><span data-stu-id="1019a-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="1019a-180">Questo flusso di lavoro è stato creato per eseguire la gestione degli errori di base e garantire che ogni record abbia un indirizzo e-mail prima di essere implementato nei dati in Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1019a-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="1019a-181">Il flusso di lavoro estrae anche il nome del segmento dal nome file prima di eseguire l'upsert nei dati del profilo ACS.</span><span class="sxs-lookup"><span data-stu-id="1019a-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Screenshot di un flusso di lavoro di importazione nell'interfaccia utente di Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="1019a-183">Recuperare il gruppo di destinatari in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1019a-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="1019a-184">Una volta importati i dati in Adobe Campaign Standard, [puoi creare un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e una [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) per i clienti in base ai campi *Nome segmento* e *Data segmento* per selezionare i profili che sono stati identificati per la nostra campagna di esempio.</span><span class="sxs-lookup"><span data-stu-id="1019a-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="1019a-185">Creare e inviare l'e-mail utilizzando Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1019a-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="1019a-186">Crea il contenuto dell'e-mail e poi [esegui il test e invia](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) la tua e-mail.</span><span class="sxs-lookup"><span data-stu-id="1019a-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail di esempio con offerta di rinnovo di Adobe Campaign Standard.":::
