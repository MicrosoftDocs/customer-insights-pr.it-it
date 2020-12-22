---
title: Creare e gestire ambienti
description: Scopri come iscriverti al servizio e come gestire gli ambienti.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644138"
---
# <a name="manage-environments"></a><span data-ttu-id="c50c1-103">Gestisci ambienti</span><span class="sxs-lookup"><span data-stu-id="c50c1-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c50c1-104">In questo viene descritto come creare una nuova organizzazione e come eseguire il provisioning di un ambiente.</span><span class="sxs-lookup"><span data-stu-id="c50c1-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="c50c1-105">Iscriversi e creare un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c50c1-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="c50c1-106">Vai al sito Web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="c50c1-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="c50c1-107">Seleziona **Inizia subito**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="c50c1-108">Scegli il tuo scenario di iscrizione preferito e seleziona il collegamento corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c50c1-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="c50c1-109">Accetta le condizioni e seleziona **Continua** per iniziare a creare l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c50c1-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="c50c1-110">Dopo aver creato l'ambiente, verrai reindirizzato a [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="c50c1-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="c50c1-111">Utilizza l'ambiente demo per esplorare l'app o crea un nuovo ambiente seguendo i passaggi nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="c50c1-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="c50c1-112">Dopo aver specificato le impostazioni dell'ambiente, seleziona **Crea**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="c50c1-113">Dopo la corretta creazione dell'ambiente, sarai connesso.</span><span class="sxs-lookup"><span data-stu-id="c50c1-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="c50c1-114">Creazione di un ambiente in un'organizzazione esistente</span><span class="sxs-lookup"><span data-stu-id="c50c1-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="c50c1-115">Ci sono due modi per creare un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="c50c1-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="c50c1-116">Puo specifica una configurazione interamente nuova oppure copiare alcune impostazioni di configurazione da un ambiente esistente.</span><span class="sxs-lookup"><span data-stu-id="c50c1-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="c50c1-117">Per creare un ambiente:</span><span class="sxs-lookup"><span data-stu-id="c50c1-117">To create an environment:</span></span>

1. <span data-ttu-id="c50c1-118">Seleziona il simbolo **Impostazioni** nell'intestazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="c50c1-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="c50c1-119">Seleziona **Nuovo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c50c1-120">![Impostazioni ambiente](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="c50c1-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="c50c1-121">Nella finestra di dialogo **Crea nuovo ambiente** seleziona **Nuovo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="c50c1-122">Per [copiare i dati dall'ambiente corrente](#additional-considerations-for-copy-configuration-preview), seleziona **Copia dall'ambiente esistente**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="c50c1-123">Vedrai un elenco di tutti gli ambienti disponibili nella tua organizzazione da cui puoi copiare i dati.</span><span class="sxs-lookup"><span data-stu-id="c50c1-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="c50c1-124">Fornisci i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="c50c1-124">Provide the following details:</span></span>
   - <span data-ttu-id="c50c1-125">**Nome**: il nome dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c50c1-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="c50c1-126">Questo campo è già compilato se hai copiato da un ambiente esistente, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="c50c1-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="c50c1-127">**Area geografica**: l'area geografica in cui il servizio viene distribuito e ospitato.</span><span class="sxs-lookup"><span data-stu-id="c50c1-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="c50c1-128">**Tipo**: scegli se vuoi creare un ambiente di produzione o sandbox.</span><span class="sxs-lookup"><span data-stu-id="c50c1-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="c50c1-129">È possibile facoltativamente selezionare **Impostazioni avanzate**:</span><span class="sxs-lookup"><span data-stu-id="c50c1-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="c50c1-130">**Salva tutti i dati in**: specifica dove vuoi archiviare i dati di output generati da Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c50c1-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="c50c1-131">Avrai a disposizione due opzioni: **Archiviazione di Customer Insights** (un Azure Data Lake gestito dal team Customer Insights) e **Azure Data Lake Storage Gen2** (il tuo Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="c50c1-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="c50c1-132">Per impostazione predefinita, l'opzione di archiviazione di Customer Insights è selezionata.</span><span class="sxs-lookup"><span data-stu-id="c50c1-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c50c1-133">Salvando i dati in Azure Data Lake Storage, accetti che i dati vengano trasferiti e archiviati nella posizione geografica appropriata per tale account di archiviazione di Azure, che può essere diversa da quella in cui sono archiviati i dati in Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c50c1-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="c50c1-134">Altre informazioni nel Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="c50c1-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="c50c1-135">Attualmente, le entità inserite vengono sempre archiviate nel data lake gestito di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c50c1-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="c50c1-136">Supportiamo solo gli account di archiviazione di Azure Data Lake Gen2 che si trovano nella stessa area di Azure selezionata durante la creazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c50c1-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="c50c1-137">Sono supportati solo gli account di archiviazione abilitati per Azure Data Lake Gen2 Hierarchical Name Space (HNS).</span><span class="sxs-lookup"><span data-stu-id="c50c1-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="c50c1-138">Per l'opzione Azure Data Lake Storage Gen2, puoi scegliere tra l'utilizzo di un'opzione basata su risorse e un'opzione basata su sottoscrizione per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c50c1-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="c50c1-139">Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c50c1-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="c50c1-140">Il nome del **Contenitore** non può essere modificato e sarà "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="c50c1-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="c50c1-141">Se vuoi usare [previsioni](predictions.md), immetti l'URL dell'istanza Common Data Service nl campo istanza **Indirizzo server** sotto **Usa previsioni**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="c50c1-142">Quando esegui processi, come l'inserimento dati o la creazione di segmenti, le cartelle corrispondenti verranno create nell'account di archiviazione specificato sopra.</span><span class="sxs-lookup"><span data-stu-id="c50c1-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="c50c1-143">I file di dati e i file model.json verranno creati e aggiunti alle rispettive sottocartelle in base al processo eseguito.</span><span class="sxs-lookup"><span data-stu-id="c50c1-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="c50c1-144">Se crei più ambienti di Customer Insights e scegli di salvare le entità di output da quegli ambienti nell'account di archiviazione, verranno create cartelle separate per ogni ambiente con ci_<environmentid> nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="c50c1-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="c50c1-145">Considerazioni aggiuntive per la configurazione della copia (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c50c1-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="c50c1-146">Le impostazioni di configurazione seguenti vengono copiate:</span><span class="sxs-lookup"><span data-stu-id="c50c1-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="c50c1-147">Configurazioni delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="c50c1-147">Feature configurations</span></span>
- <span data-ttu-id="c50c1-148">Origini dati importate/inserite</span><span class="sxs-lookup"><span data-stu-id="c50c1-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="c50c1-149">Configurazione di unificazione dei dati (mapping, corrispondenza, unione)</span><span class="sxs-lookup"><span data-stu-id="c50c1-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="c50c1-150">Segmenti</span><span class="sxs-lookup"><span data-stu-id="c50c1-150">Segments</span></span>
- <span data-ttu-id="c50c1-151">Misure</span><span class="sxs-lookup"><span data-stu-id="c50c1-151">Measures</span></span>
- <span data-ttu-id="c50c1-152">Relazioni</span><span class="sxs-lookup"><span data-stu-id="c50c1-152">Relationships</span></span>
- <span data-ttu-id="c50c1-153">Impegni</span><span class="sxs-lookup"><span data-stu-id="c50c1-153">Activities</span></span>
- <span data-ttu-id="c50c1-154">Indice di ricerca e filtro</span><span class="sxs-lookup"><span data-stu-id="c50c1-154">Search & filter Index</span></span>
- <span data-ttu-id="c50c1-155">Destinazioni di esportazione</span><span class="sxs-lookup"><span data-stu-id="c50c1-155">Export destinations</span></span>
- <span data-ttu-id="c50c1-156">Aggiornamento pianificato</span><span class="sxs-lookup"><span data-stu-id="c50c1-156">Scheduled refresh</span></span>
- <span data-ttu-id="c50c1-157">Arricchimenti</span><span class="sxs-lookup"><span data-stu-id="c50c1-157">Enrichments</span></span>
- <span data-ttu-id="c50c1-158">Gestione modelli</span><span class="sxs-lookup"><span data-stu-id="c50c1-158">Model management</span></span>
- <span data-ttu-id="c50c1-159">Assegnazioni di ruolo</span><span class="sxs-lookup"><span data-stu-id="c50c1-159">Role assignments</span></span>

<span data-ttu-id="c50c1-160">Le impostazioni di configurazione seguenti *non* vengono copiate:</span><span class="sxs-lookup"><span data-stu-id="c50c1-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="c50c1-161">Profili cliente.</span><span class="sxs-lookup"><span data-stu-id="c50c1-161">Customer profiles.</span></span>
- <span data-ttu-id="c50c1-162">Credenziali origine dati.</span><span class="sxs-lookup"><span data-stu-id="c50c1-162">Data source credentials.</span></span> <span data-ttu-id="c50c1-163">Dovrai fornire le credenziali per ogni origine dati e aggiornare manualmente le origini dati.</span><span class="sxs-lookup"><span data-stu-id="c50c1-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="c50c1-164">Origini dati dalla cartella Common Data Model e data lake gestito Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c50c1-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="c50c1-165">Dovrai creare tali origini dati manualmente con lo stesso nome dell'ambiente di origine.</span><span class="sxs-lookup"><span data-stu-id="c50c1-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="c50c1-166">Quando copi un ambiente, vedrai un messaggio di conferma che il nuovo ambiente è stato creato.</span><span class="sxs-lookup"><span data-stu-id="c50c1-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="c50c1-167">Seleziona **Vai a origini dati** per visualizzare l'elenco delle origini dati.</span><span class="sxs-lookup"><span data-stu-id="c50c1-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="c50c1-168">Tutte le origini dati mostreranno uno stato **Credenziali obbligatorie**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="c50c1-169">Modifica le origini dati e inserisci le credenziali per aggiornarle.</span><span class="sxs-lookup"><span data-stu-id="c50c1-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c50c1-170">![Origini dati copiate](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="c50c1-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="c50c1-171">Dopo aver aggiornato le origini dati, vai a **Dati** > **Unifica**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="c50c1-172">Qui troverai le impostazioni dall'ambiente di origine.</span><span class="sxs-lookup"><span data-stu-id="c50c1-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="c50c1-173">Modificale in base alle necessità o seleziona **Esegui** per avviare il processo di unificazione dei dati e creare l'entità cliente unificata.</span><span class="sxs-lookup"><span data-stu-id="c50c1-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="c50c1-174">Quando l'unificazione dei dati è completa, vai a **Misure** e **Segmenti** per aggiornarli.</span><span class="sxs-lookup"><span data-stu-id="c50c1-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="c50c1-175">Modificare un ambiente esistente</span><span class="sxs-lookup"><span data-stu-id="c50c1-175">Edit an existing environment</span></span>

<span data-ttu-id="c50c1-176">Puoi modificare alcuni dei dettagli degli ambienti esistenti.</span><span class="sxs-lookup"><span data-stu-id="c50c1-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="c50c1-177">Vai ad **Amministratore** > **Sistema** > **Informazioni**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="c50c1-178">Seleziona **Modifica**</span><span class="sxs-lookup"><span data-stu-id="c50c1-178">Select **Edit**.</span></span>

3. <span data-ttu-id="c50c1-179">Puoi aggiornare il **Nome visualizzato** dell'ambiente, ma non puoi modificare i valori di **Area geografica** o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="c50c1-180">Se un ambiente è configurato per l'archiviazione dei dati in Azure Data Lake Storage Gen2, puoi aggiornare la **Chiave dell' account**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="c50c1-181">Tuttavia, non puoi modificare il **Nome account** o il nome del **Contenitore**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="c50c1-182">Facoltativamente, puoi eseguire l'aggiornamento da una connessione basata sulla chiave dell'account a una connessione basata su risorse o sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="c50c1-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="c50c1-183">Dopo l'aggiornamento, non puoi ripristinare la chiave dell'account.</span><span class="sxs-lookup"><span data-stu-id="c50c1-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="c50c1-184">Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c50c1-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="c50c1-185">Non puoi modificare le informazioni sul **Contenitore** durante l'aggiornamento della connessione.</span><span class="sxs-lookup"><span data-stu-id="c50c1-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="c50c1-186">Reimpostare un ambiente esistente</span><span class="sxs-lookup"><span data-stu-id="c50c1-186">Reset an existing environment</span></span>

<span data-ttu-id="c50c1-187">Puoi reimpostare un ambiente su uno stato vuoto se desideri eliminare tutte le configurazioni e rimuovere i dati inseriti.</span><span class="sxs-lookup"><span data-stu-id="c50c1-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="c50c1-188">Vai ad **Amministratore** > **Sistema** > **Informazioni**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="c50c1-189">Seleziona **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="c50c1-190">Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="c50c1-191">Eliminare un ambiente esistente</span><span class="sxs-lookup"><span data-stu-id="c50c1-191">Delete an existing environment</span></span>

1. <span data-ttu-id="c50c1-192">Vai ad **Amministratore** > **Sistema** > **Informazioni**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="c50c1-193">Seleziona **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="c50c1-193">Select **Delete**.</span></span>

1. <span data-ttu-id="c50c1-194">Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="c50c1-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
