---
title: Modelli di Machine Learning personalizzati | Microsoft Docs
description: Utilizzare modelli personalizzati da Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668908"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="2cd7e-103">Modelli di Machine Learning personalizzati</span><span class="sxs-lookup"><span data-stu-id="2cd7e-103">Custom machine learning models</span></span>

<span data-ttu-id="2cd7e-104">**Intelligenza** > **Modelli personalizzati** consente di gestire flussi di lavoro basati sui modelli di Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="2cd7e-105">I flussi di lavoro ti consentono di scegliere i dati mediante i quali generare informazioni dettagliate e di mappare i risultati ai dati cliente unificati.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="2cd7e-106">Per ulteriori informazioni sulla creazione di modelli di Machine Learning personalizzati, vedi [Utilizzare i modelli basati su Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="2cd7e-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="2cd7e-107">IA responsabile</span><span class="sxs-lookup"><span data-stu-id="2cd7e-107">Responsible AI</span></span>

<span data-ttu-id="2cd7e-108">Le previsioni offrono funzionalità per creare migliori esperienze cliente nonché migliorare le capacità aziendali e i flussi di ricavi.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="2cd7e-109">Ti consigliamo vivamente di equilibrare il valore della previsione rispetto all'impatto che ha e alle tendenze che possono essere introdotte in modo etico.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="2cd7e-110">Ulteriori informazioni su come Microsoft [assicura una IA responsabile](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="2cd7e-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="2cd7e-111">Puoi anche ottenere informazioni su [tecniche e processi per un machine learning responsabile](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifico per Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2cd7e-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2cd7e-112">Prerequisites</span></span>

- <span data-ttu-id="2cd7e-113">Attualmente, questa funzionalità supporta i servizi Web pubblicati tramite [Machine Learning Studio (versione classica)](https://studio.azureml.net) e le [pipeline batch di Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="2cd7e-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="2cd7e-114">Devi disporre di un account di archiviazione di Azure Data Lake Gen2 associato all'istanza di Azure Studio per usare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="2cd7e-115">Per altre informazioni, vedi [Creare un account di archiviazione di Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="2cd7e-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="2cd7e-116">Aggiungere un nuovo flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2cd7e-116">Add a new workflow</span></span>

1. <span data-ttu-id="2cd7e-117">Vai a **Intelligenza** > **Modelli personalizzati** e seleziona **Nuovo flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="2cd7e-118">Assegna al tuo modello personalizzato un nome riconoscibile nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2cd7e-119">![Screenshot del riquadro Nuovo flusso di lavoro](media/new-workflowv2.png "Screenshot del riquadro Nuovo flusso di lavoro")</span><span class="sxs-lookup"><span data-stu-id="2cd7e-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="2cd7e-120">Seleziona l'organizzazione che contiene il servizio Web in **Tenant che contiene il servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="2cd7e-121">Se l'abbonamento di Azure Machine Learning si trova in un tenant diverso da Customer Insights, seleziona **Accedi** con le tue credenziali per l'organizzazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="2cd7e-122">Seleziona le **Aree di lavoro** associate al tuo servizio web.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="2cd7e-123">Sono elencate due sezioni, una per Azure Machine Learning v1 (Machine Learning Studio (versione classica)) e Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="2cd7e-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="2cd7e-124">Se non sei sicuro qual è l'area di lavoro appropriata per il servizio web Machine Learning Studio (versione classica), seleziona **Qualsiasi**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="2cd7e-125">Scegli il servizio Web Machine Learning Studio (versione classica) o la pipeline Azure Machine Learning nell'elenco a discesa **Servizio Web che contiene il modello**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="2cd7e-126">Quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="2cd7e-127">Leggi gli articoli sulla [pubblicazione di un servizio web in Machine Learning Studio (versione classica)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="2cd7e-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="2cd7e-128">Leggi gli articoli sulla [pubblicazione di una pipeline in Azure Machine Learning utilizzando la finestra di progettazione](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) o [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="2cd7e-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="2cd7e-129">La tua pipeline deve essere pubblicata in un [endpoint di pipeline](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="2cd7e-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="2cd7e-130">Per ogni **Input servizio Web**, seleziona l'**Entità** corrispondente di Audience Insights e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2cd7e-131">![Configurare un flusso di lavoro](media/intelligence-screen2-updated.png "Configurare un flusso di lavoro")</span><span class="sxs-lookup"><span data-stu-id="2cd7e-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="2cd7e-132">Nel passaggio **Parametri di output del modello**, imposta le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="2cd7e-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="2cd7e-133">Machine Learning Studio (versione classica)</span><span class="sxs-lookup"><span data-stu-id="2cd7e-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="2cd7e-134">Immetti il **Nome dell'entità** di output in cui desideri inserire i risultati di output del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="2cd7e-135">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="2cd7e-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="2cd7e-136">Immetti il **Nome dell'entità** di output in cui desideri inserire i risultati di output della pipeline.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="2cd7e-137">Seleziona il **Nome parametro archivio dati di output** della pipeline batch dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="2cd7e-138">Seleziona il **Nome parametro percorso di output** della pipeline batch dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="2cd7e-139">![Riquadro dei parametri di output del modello](media/intelligence-screen3-outputparameters.png "Riquadro dei parametri di output del modello")</span><span class="sxs-lookup"><span data-stu-id="2cd7e-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="2cd7e-140">Seleziona l'attributo corrispondente nell'elenco a discesa **ID cliente nei risultati** che identifica i clienti e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2cd7e-141">![Riquadro Correla risultati ai dati del cliente](media/intelligence-screen4-relatetocustomer.png "Riquadro Correla risultati ai dati del cliente")</span><span class="sxs-lookup"><span data-stu-id="2cd7e-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="2cd7e-142">Vedrai la schermata **Flusso di lavoro salvato** con dettagli sul flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="2cd7e-143">Se hai configurato un flusso di lavoro per una pipeline di Azure Machine Learning, Audience Insights assocerà l'area di lavoro che contiene la pipeline.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="2cd7e-144">Audience insights otterrà un ruolo **Collaboratore** nell'area di lavoro di Azure.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="2cd7e-145">Seleziona **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-145">Select **Done**.</span></span>

1. <span data-ttu-id="2cd7e-146">Ora puoi eseguire il flusso di lavoro nella pagina **Modelli personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="2cd7e-147">Modificare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2cd7e-147">Edit a workflow</span></span>

1. <span data-ttu-id="2cd7e-148">Nella pagina **Modelli personalizzati**, seleziona i puntini di sospensione verticali nella colonna **Azioni** accanto a un flusso di lavoro precedentemente creato e seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="2cd7e-149">Puoi aggiornare il nome riconoscibile del flusso di lavoro nel campo **Nome visualizzato**, ma non puoi modificare il servizio Web o la pipeline configurato.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="2cd7e-150">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-150">Select **Next**.</span></span>

1. <span data-ttu-id="2cd7e-151">Per ogni **Input servizio Web**, puoi aggiornare l'**Entità** corrispondente di Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="2cd7e-152">Quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="2cd7e-153">Nel passaggio **Parametri di output del modello**, imposta le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="2cd7e-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="2cd7e-154">Machine Learning Studio (versione classica)</span><span class="sxs-lookup"><span data-stu-id="2cd7e-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="2cd7e-155">Immetti il **Nome dell'entità** di output in cui desideri inserire i risultati di output del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="2cd7e-156">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="2cd7e-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="2cd7e-157">Immetti il **Nome dell'entità** di output in cui desideri inserire i risultati di output della pipeline.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="2cd7e-158">Seleziona **Nome parametro archivio dati di output** per la pipeline di test.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="2cd7e-159">Seleziona il **Nome parametro percorso di output** per la pipeline di test.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="2cd7e-160">Seleziona l'attributo corrispondente nell'elenco a discesa **ID cliente nei risultati** che identifica i clienti e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="2cd7e-161">Devi scegliere un attributo nell'output di inferenza con valori simili alla colonna ID cliente dell'entità Cliente.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="2cd7e-162">Se non hai una colonna di questo tipo nel tuo set di dati, scegli un attributo che identifichi in modo univoco la riga.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="2cd7e-163">Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2cd7e-163">Run a workflow</span></span>

1. <span data-ttu-id="2cd7e-164">Nella pagina **Modelli personalizzati**, seleziona i puntini di sospensione verticali nella colonna **Azioni** accanto a un flusso di lavoro precedentemente creato.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="2cd7e-165">Seleziona **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-165">Select **Run**.</span></span>

<span data-ttu-id="2cd7e-166">Il flusso di lavoro viene inoltre eseguito automaticamente con ogni aggiornamento pianificato.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="2cd7e-167">Altre informazioni sulla [configurazione degli aggiornamenti pianificati](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2cd7e-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="2cd7e-168">Eliminare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2cd7e-168">Delete a workflow</span></span>

1. <span data-ttu-id="2cd7e-169">Nella pagina **Modelli personalizzati**, seleziona i puntini di sospensione verticali nella colonna **Azioni** accanto a un flusso di lavoro precedentemente creato.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="2cd7e-170">Seleziona **Elimina** e conferma l'operazione.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="2cd7e-171">Il flusso di lavoro verrà eliminato.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-171">Your workflow will be deleted.</span></span> <span data-ttu-id="2cd7e-172">L'[entità](entities.md) creata durante la creazione del flusso di lavoro verrà conservata e può essere visualizzata dalla pagina **Entità**.</span><span class="sxs-lookup"><span data-stu-id="2cd7e-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
