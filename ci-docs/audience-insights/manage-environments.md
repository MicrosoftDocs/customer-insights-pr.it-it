---
title: Creare e gestire ambienti
description: Scopri come iscriverti al servizio e come gestire gli ambienti.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270117"
---
# <a name="manage-environments"></a><span data-ttu-id="4fe4c-103">Gestisci ambienti</span><span class="sxs-lookup"><span data-stu-id="4fe4c-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4fe4c-104">In questo viene descritto come creare una nuova organizzazione e come eseguire il provisioning di un ambiente.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="4fe4c-105">Iscriversi e creare un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4fe4c-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="4fe4c-106">Vai al sito Web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="4fe4c-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="4fe4c-107">Seleziona **Inizia subito**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="4fe4c-108">Scegli il tuo scenario di iscrizione preferito e seleziona il collegamento corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="4fe4c-109">Accetta le condizioni e seleziona **Continua** per iniziare a creare l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="4fe4c-110">Dopo aver creato l'ambiente, verrai reindirizzato a [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="4fe4c-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="4fe4c-111">Utilizza l'ambiente demo per esplorare l'app o crea un nuovo ambiente seguendo i passaggi nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="4fe4c-112">Dopo aver specificato le impostazioni dell'ambiente, seleziona **Crea**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="4fe4c-113">Dopo la corretta creazione dell'ambiente, sarai connesso.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="4fe4c-114">Creazione di un ambiente in un'organizzazione esistente</span><span class="sxs-lookup"><span data-stu-id="4fe4c-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="4fe4c-115">Ci sono due modi per creare un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="4fe4c-116">Puo specifica una configurazione interamente nuova oppure copiare alcune impostazioni di configurazione da un ambiente esistente.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="4fe4c-117">Per creare un ambiente:</span><span class="sxs-lookup"><span data-stu-id="4fe4c-117">To create an environment:</span></span>

1. <span data-ttu-id="4fe4c-118">Seleziona il selettore **Ambiente** nell'intestazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="4fe4c-119">Seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4fe4c-120">![Impostazioni ambiente](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="4fe4c-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="4fe4c-121">Nella finestra di dialogo **Crea nuovo ambiente** seleziona **Nuovo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="4fe4c-122">Per [copiare i dati dall'ambiente corrente](#additional-considerations-for-copy-configuration-preview), seleziona **Copia dall'ambiente esistente**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="4fe4c-123">Vedrai un elenco di tutti gli ambienti disponibili nella tua organizzazione da cui puoi copiare i dati.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="4fe4c-124">Fornisci i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="4fe4c-124">Provide the following details:</span></span>
   - <span data-ttu-id="4fe4c-125">**Nome**: il nome dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="4fe4c-126">Questo campo è già compilato se hai copiato da un ambiente esistente, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="4fe4c-127">**Area geografica**: l'area geografica in cui il servizio viene distribuito e ospitato.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="4fe4c-128">**Tipo**: scegli se vuoi creare un ambiente di produzione o sandbox.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="4fe4c-129">È possibile facoltativamente selezionare **Impostazioni avanzate**:</span><span class="sxs-lookup"><span data-stu-id="4fe4c-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="4fe4c-130">**Salva tutti i dati in**: specifica dove vuoi archiviare i dati di output generati da Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="4fe4c-131">Avrai a disposizione due opzioni: **Archiviazione di Customer Insights** (un Azure Data Lake gestito dal team Customer Insights) e **Azure Data Lake Storage Gen2** (il tuo Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="4fe4c-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="4fe4c-132">Per impostazione predefinita, l'opzione di archiviazione di Customer Insights è selezionata.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4fe4c-133">Salvando i dati in Azure Data Lake Storage, accetti che i dati vengano trasferiti e archiviati nella posizione geografica appropriata per tale account di archiviazione di Azure, che può essere diversa da quella in cui sono archiviati i dati in Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="4fe4c-134">Altre informazioni nel Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="4fe4c-135">Attualmente, le entità inserite vengono sempre archiviate nel data lake gestito di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="4fe4c-136">Supportiamo solo gli account di archiviazione di Azure Data Lake Gen2 che si trovano nella stessa area di Azure selezionata durante la creazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="4fe4c-137">Sono supportati solo gli account di archiviazione abilitati per Azure Data Lake Gen2 Hierarchical Name Space (HNS).</span><span class="sxs-lookup"><span data-stu-id="4fe4c-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="4fe4c-138">Per l'opzione Azure Data Lake Storage Gen2, puoi scegliere tra l'utilizzo di un'opzione basata su risorse e un'opzione basata su sottoscrizione per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="4fe4c-139">Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="4fe4c-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="4fe4c-140">Il nome del **Contenitore** non può essere modificato e sarà "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="4fe4c-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="4fe4c-141">Se vuoi usare [previsioni](predictions.md) o configurare la condivisione dei dati con applicazioni e soluzioni basate su Microsoft Dataverse, fornisci l'URL dell'ambiente Microsoft Dataverse in **Configura la condivisione dei dati con Microsoft Dataverse e abilita funzionalità aggiuntive**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="4fe4c-142">Seleziona **Abilita la condivisione dei dati** per condividere i dati di output di Customer Insights con un Data Lake gestito di Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="4fe4c-143">Condivisione dei dati con un Data Lake gestito di Microsoft Dataverse non è attualmente supportata quando salvi tutti i dati nel tuo Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="4fe4c-144">[Previsione di valori mancanti in un'entità](predictions.md) non è attualmente supportata quando abiliti la condivisione dei dati con Data Lake gestito di Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="4fe4c-145">![Opzioni di configurazione per abilitare la condivisione dei dati con Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="4fe4c-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="4fe4c-146">Quando esegui processi, come l'inserimento dati o la creazione di segmenti, le cartelle corrispondenti verranno create nell'account di archiviazione specificato sopra.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="4fe4c-147">I file di dati e i file model.json verranno creati e aggiunti alle rispettive sottocartelle in base al processo eseguito.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="4fe4c-148">Se crei più ambienti di Customer Insights e scegli di salvare le entità di output da quegli ambienti nell'account di archiviazione, verranno create cartelle separate per ogni ambiente con ci_<environmentid> nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="4fe4c-149">Considerazioni aggiuntive per la configurazione della copia (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4fe4c-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="4fe4c-150">Le impostazioni di configurazione seguenti vengono copiate:</span><span class="sxs-lookup"><span data-stu-id="4fe4c-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="4fe4c-151">Configurazioni delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="4fe4c-151">Feature configurations</span></span>
- <span data-ttu-id="4fe4c-152">Origini dati inserite/importate</span><span class="sxs-lookup"><span data-stu-id="4fe4c-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="4fe4c-153">Configurazione di unificazione dei dati (mapping, corrispondenza, unione)</span><span class="sxs-lookup"><span data-stu-id="4fe4c-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="4fe4c-154">Segmenti</span><span class="sxs-lookup"><span data-stu-id="4fe4c-154">Segments</span></span>
- <span data-ttu-id="4fe4c-155">Misure</span><span class="sxs-lookup"><span data-stu-id="4fe4c-155">Measures</span></span>
- <span data-ttu-id="4fe4c-156">Relazioni</span><span class="sxs-lookup"><span data-stu-id="4fe4c-156">Relationships</span></span>
- <span data-ttu-id="4fe4c-157">Impegni</span><span class="sxs-lookup"><span data-stu-id="4fe4c-157">Activities</span></span>
- <span data-ttu-id="4fe4c-158">Indice di ricerca e filtro</span><span class="sxs-lookup"><span data-stu-id="4fe4c-158">Search & filter Index</span></span>
- <span data-ttu-id="4fe4c-159">Destinazioni di esportazione</span><span class="sxs-lookup"><span data-stu-id="4fe4c-159">Export destinations</span></span>
- <span data-ttu-id="4fe4c-160">Aggiornamento pianificato</span><span class="sxs-lookup"><span data-stu-id="4fe4c-160">Scheduled refresh</span></span>
- <span data-ttu-id="4fe4c-161">Arricchimenti</span><span class="sxs-lookup"><span data-stu-id="4fe4c-161">Enrichments</span></span>
- <span data-ttu-id="4fe4c-162">Gestione modelli</span><span class="sxs-lookup"><span data-stu-id="4fe4c-162">Model management</span></span>
- <span data-ttu-id="4fe4c-163">Assegnazioni di ruolo</span><span class="sxs-lookup"><span data-stu-id="4fe4c-163">Role assignments</span></span>

<span data-ttu-id="4fe4c-164">Le impostazioni di configurazione seguenti *non* vengono copiate:</span><span class="sxs-lookup"><span data-stu-id="4fe4c-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="4fe4c-165">Profili cliente.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-165">Customer profiles.</span></span>
- <span data-ttu-id="4fe4c-166">Credenziali origine dati.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-166">Data source credentials.</span></span> <span data-ttu-id="4fe4c-167">Dovrai fornire le credenziali per ogni origine dati e aggiornare manualmente le origini dati.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="4fe4c-168">Origini dati dalla cartella Common Data Model e data lake gestito Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="4fe4c-169">Dovrai creare tali origini dati manualmente con lo stesso nome dell'ambiente di origine.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="4fe4c-170">Quando copi un ambiente, vedrai un messaggio di conferma che il nuovo ambiente è stato creato.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="4fe4c-171">Seleziona **Vai a origini dati** per visualizzare l'elenco delle origini dati.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="4fe4c-172">Tutte le origini dati mostreranno uno stato **Credenziali obbligatorie**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="4fe4c-173">Modifica le origini dati e inserisci le credenziali per aggiornarle.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4fe4c-174">![Origini dati copiate](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="4fe4c-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="4fe4c-175">Dopo aver aggiornato le origini dati, vai a **Dati** > **Unifica**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="4fe4c-176">Qui troverai le impostazioni dall'ambiente di origine.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="4fe4c-177">Modificale in base alle necessità o seleziona **Esegui** per avviare il processo di unificazione dei dati e creare l'entità cliente unificata.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="4fe4c-178">Quando l'unificazione dei dati è completa, vai a **Misure** e **Segmenti** per aggiornarli.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="4fe4c-179">Modificare un ambiente esistente</span><span class="sxs-lookup"><span data-stu-id="4fe4c-179">Edit an existing environment</span></span>

<span data-ttu-id="4fe4c-180">Puoi modificare alcuni dei dettagli degli ambienti esistenti.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="4fe4c-181">Seleziona il selettore **Ambiente** nell'intestazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="4fe4c-182">Seleziona l'icona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="4fe4c-183">Nella casella **Modifica ambiente** puoi aggiornare il **Nome visualizzato** dell'ambiente, ma non puoi modificare **Area** o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="4fe4c-184">Se un ambiente è configurato per l'archiviazione dei dati in Azure Data Lake Storage Gen2, puoi aggiornare la **Chiave dell' account**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="4fe4c-185">Tuttavia, non puoi modificare il **Nome account** o il nome del **Contenitore**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="4fe4c-186">Facoltativamente, puoi eseguire l'aggiornamento da una connessione basata sulla chiave dell'account a una connessione basata su risorse o sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="4fe4c-187">Dopo l'aggiornamento, non puoi ripristinare la chiave dell'account.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="4fe4c-188">Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="4fe4c-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="4fe4c-189">Non puoi modificare le informazioni sul **Contenitore** durante l'aggiornamento della connessione.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="4fe4c-190">Reimpostare un ambiente esistente</span><span class="sxs-lookup"><span data-stu-id="4fe4c-190">Reset an existing environment</span></span>

<span data-ttu-id="4fe4c-191">Come amministratore, puoi reimpostare un ambiente su uno stato vuoto se desideri eliminare tutte le configurazioni e rimuovere i dati inseriti.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="4fe4c-192">Seleziona il selettore **Ambiente** nell'intestazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="4fe4c-193">Seleziona l'ambiente che desideri reimpostare e seleziona i puntini di sospensione **...**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="4fe4c-194">Scegli l'opzione **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="4fe4c-195">Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="4fe4c-196">Eliminare un ambiente esistente (disponibile solo per gli amministratori)</span><span class="sxs-lookup"><span data-stu-id="4fe4c-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="4fe4c-197">In qualità di amministratore, puoi eliminare un ambiente che amministri.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="4fe4c-198">Seleziona il selettore **Ambiente** nell'intestazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="4fe4c-199">Seleziona l'ambiente che desideri reimpostare e seleziona i puntini di sospensione **...**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="4fe4c-200">Scegli l'opzione **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="4fe4c-201">Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="4fe4c-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]