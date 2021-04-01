---
title: Connettere i dati di Common Data Model a un account Azure Data Lake
description: Utilizza i dati di Common Data Model con Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596550"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="05c7b-103">Connettere a una cartella Common Data Model usando un account Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="05c7b-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="05c7b-104">Questo articolo fornisce informazioni su come inserire dati di una cartella Common Data Model utilizzando l'account Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="05c7b-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="05c7b-105">Considerazioni importanti</span><span class="sxs-lookup"><span data-stu-id="05c7b-105">Important considerations</span></span>

- <span data-ttu-id="05c7b-106">I dati in Azure Data Lake devono seguire lo standard Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="05c7b-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="05c7b-107">Altri formati non sono supportati al momento.</span><span class="sxs-lookup"><span data-stu-id="05c7b-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="05c7b-108">L'inserimento dati supporta esclusivamente gli account di archiviazione di Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="05c7b-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="05c7b-109">Non puoi usare account di archiviazione di Azure Data Lake Gen1 per inserire i dati.</span><span class="sxs-lookup"><span data-stu-id="05c7b-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="05c7b-110">Per eseguire l'autenticazione con un'entità servizio di Azure, assicurati che sia configurata nel tenant.</span><span class="sxs-lookup"><span data-stu-id="05c7b-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="05c7b-111">Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="05c7b-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="05c7b-112">L'Azure Data Lake da cui intendi eseguire la connessione e inserire i dati deve trovarsi nella stessa area di Azure dell'ambiente Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="05c7b-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="05c7b-113">Le connessioni a una cartella di Common Data Model da un data lake in un'area diversa di Azure non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="05c7b-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="05c7b-114">Per conoscere l'area di Azure dell'ambiente, seleziona **Amministratore** > **Sistema** > **Informazioni** in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="05c7b-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="05c7b-115">I dati memorizzati nei servizi online possono essere archiviati in una posizione diversa da quella in cui i dati vengono elaborati o archiviati in Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="05c7b-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="05c7b-116">Importando o connettendoti a dati archiviati nei servizi online, accetti che i dati possano essere trasferiti e archiviati con Dynamics 365 Customer Insights. [Altre informazioni sono disponibili nel Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="05c7b-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="05c7b-117">Connetti a cartella di Common Data Model</span><span class="sxs-lookup"><span data-stu-id="05c7b-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="05c7b-118">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="05c7b-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="05c7b-119">Seleziona **Aggiungi origine dati**.</span><span class="sxs-lookup"><span data-stu-id="05c7b-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="05c7b-120">Seleziona **Connetti a cartella di Common Data Model**, immetti un **Nome** per l'origine dati e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="05c7b-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="05c7b-121">Linee guida per i nomi:</span><span class="sxs-lookup"><span data-stu-id="05c7b-121">Name guidelines:</span></span> 
   - <span data-ttu-id="05c7b-122">Deve iniziare con una lettera.</span><span class="sxs-lookup"><span data-stu-id="05c7b-122">Start with a letter.</span></span>
   - <span data-ttu-id="05c7b-123">Usa solo lettere e numeri.</span><span class="sxs-lookup"><span data-stu-id="05c7b-123">Use letters and numbers only.</span></span> <span data-ttu-id="05c7b-124">Gli spazi e i caratteri speciali non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="05c7b-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="05c7b-125">Usa tra 3 e 64 caratteri.</span><span class="sxs-lookup"><span data-stu-id="05c7b-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="05c7b-126">Puoi scegliere tra l'utilizzo di un'opzione basata su risorse e un'opzione basata su sottoscrizione per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="05c7b-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="05c7b-127">Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="05c7b-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="05c7b-128">Immetti le informazioni relative al **Contenitore** e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="05c7b-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="05c7b-129">![Finestra di dialogo di immissione dei dettagli della nuova connessione per Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="05c7b-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="05c7b-130">È necessario uno dei seguenti ruoli per il contenitore o l'account di archiviazione di cui sopra per essere in grado di connettersi e creare un'origine dati:</span><span class="sxs-lookup"><span data-stu-id="05c7b-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="05c7b-131">Lettore dati BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="05c7b-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="05c7b-132">Proprietario dati BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="05c7b-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="05c7b-133">Collaboratore dati BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="05c7b-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="05c7b-134">Nella finestra di dialogo **Seleziona una cartella di Common Data Model** , seleziona il file model.json o manifest.json da cui importare i dati e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="05c7b-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="05c7b-135">Qualsiasi file model.json o manifest.json associato a un'altra origine dati nell'ambiente non verrà visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="05c7b-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="05c7b-136">Otterrai un elenco di entità disponibili nel file model.json o manifest.json selezionato.</span><span class="sxs-lookup"><span data-stu-id="05c7b-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="05c7b-137">Puoi rivedere e selezionare dall'elenco di entità disponibili e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="05c7b-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="05c7b-138">Tutte le entità selezionate verranno inserite dalla nuova origine dati.</span><span class="sxs-lookup"><span data-stu-id="05c7b-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="05c7b-139">![Finestra di dialogo che mostra un elenco di entità da un file model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="05c7b-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="05c7b-140">Specifica le entità di dati per cui vuoi abilitare il profiling dei dati e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="05c7b-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="05c7b-141">Il profiling dei dati consente l'analisi e altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="05c7b-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="05c7b-142">Puoi selezionare l'intera entità, che seleziona tutti gli attributi dall'entità, o selezionare alcuni attributi di tua scelta.</span><span class="sxs-lookup"><span data-stu-id="05c7b-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="05c7b-143">Per impostazione predefinita, nessuna entità è abilitata per il profiling dei dati.</span><span class="sxs-lookup"><span data-stu-id="05c7b-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="05c7b-144">![Finestra di dialogo che mostra un profiling dei dati](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="05c7b-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="05c7b-145">Dopo aver salvato le selezioni, viene visualizzata la pagina **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="05c7b-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="05c7b-146">Ora la connessione alla cartella Common Data Model viene visualizzata come origine dati.</span><span class="sxs-lookup"><span data-stu-id="05c7b-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="05c7b-147">Un file model.json o manifest.json può essere associato solo a un'origine dati nello stesso ambiente.</span><span class="sxs-lookup"><span data-stu-id="05c7b-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="05c7b-148">Tuttavia, lo stesso file model.json o manifest.json può essere utilizzato per origini dati in più ambienti.</span><span class="sxs-lookup"><span data-stu-id="05c7b-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="05c7b-149">Modificare un'origine dati della cartella Common Data Model</span><span class="sxs-lookup"><span data-stu-id="05c7b-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="05c7b-150">Puoi aggiornare la chiave di accesso per l'account di archiviazione contenente la cartella di Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="05c7b-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="05c7b-151">Puoi anche modificare il file model.json o manifest.json.</span><span class="sxs-lookup"><span data-stu-id="05c7b-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="05c7b-152">Per connetterti a un contenitore diverso dal tuo account di archiviazione o modificare il nome dell'account, [crea una nuova connessione all'origine dati](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="05c7b-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="05c7b-153">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="05c7b-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="05c7b-154">Accanto all'origine dati che vuoi aggiornare, seleziona i puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="05c7b-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="05c7b-155">Seleziona l'opzione **Modifica** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="05c7b-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="05c7b-156">Facoltativamente, aggiorna il valore di **Chiave di accesso** e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="05c7b-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Finestra di dialogo per modificare e aggiornare una chiave di accesso per un'origine dati esistente](media/edit-access-key.png)

5. <span data-ttu-id="05c7b-158">Facoltativamente, puoi eseguire l'aggiornamento da una connessione con chiave dell'account a una connessione basata su risorse o sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="05c7b-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="05c7b-159">Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="05c7b-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="05c7b-160">Non puoi modificare le informazioni sul **Contenitore** durante l'aggiornamento della connessione.</span><span class="sxs-lookup"><span data-stu-id="05c7b-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Finestra di dialogo per immettere i dettagli di connessione per Azure Data Lake a un account di archiviazione esistente](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="05c7b-162">È necessario uno dei seguenti ruoli per il contenitore o l'account di archiviazione di cui sopra per essere in grado di connettersi e creare un'origine dati:</span><span class="sxs-lookup"><span data-stu-id="05c7b-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="05c7b-163">Lettore dati BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="05c7b-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="05c7b-164">Proprietario dati BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="05c7b-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="05c7b-165">Collaboratore dati BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="05c7b-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="05c7b-166">Facoltativamente, scegli un file model.json o manifest.json diverso con un set di entità diverso dal contenitore.</span><span class="sxs-lookup"><span data-stu-id="05c7b-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="05c7b-167">Facoltativamente, puoi selezionare entità aggiuntive da inserire.</span><span class="sxs-lookup"><span data-stu-id="05c7b-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="05c7b-168">Puoi anche rimuovere qualsiasi entità già selezionata se non ci sono dipendenze.</span><span class="sxs-lookup"><span data-stu-id="05c7b-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="05c7b-169">Se sono presenti dipendenze dal file model.json o manifest.json esistente e dal set di entità, verrà visualizzato un messaggio di errore e non sarà possibile selezionare un file model.json o manifest.json diverso.</span><span class="sxs-lookup"><span data-stu-id="05c7b-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="05c7b-170">Rimuovi queste dipendenze prima di cambiare il file model.json o manifest.json o crea un nuovo origine dati con il file model.json o manifest.json che vuoi utilizzare per evitare di rimuovere le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="05c7b-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="05c7b-171">Facoltativamente, puoi selezionare attributi o entità aggiuntivi per abilitare il profilng dei dati o disabilitare quelli già selezionati.</span><span class="sxs-lookup"><span data-stu-id="05c7b-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]