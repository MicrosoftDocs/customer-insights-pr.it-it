---
title: Inserire dati tramite un connettore Power Query
description: Connettori per origini dati basati su Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305896"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="327db-103">Connettersi a un'origine dati Power Query</span><span class="sxs-lookup"><span data-stu-id="327db-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="327db-104">Power Query offre un'ampia gamma di connettori per inserire i dati.</span><span class="sxs-lookup"><span data-stu-id="327db-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="327db-105">La maggior parte di questi connettori è supportata da Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="327db-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="327db-106">L'aggiunta di origini dati basate sui connettori Power Query generalmente segue i passaggi descritti nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="327db-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="327db-107">Tuttavia, a seconda del connettore utilizzato, sono necessarie informazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="327db-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="327db-108">Per ulteriori informazioni, vedere la documentazione sui singoli connettori in [Riferimento al connettore Power Query](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="327db-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="327db-109">Crea una nuova origine dati</span><span class="sxs-lookup"><span data-stu-id="327db-109">Create a new data source</span></span>

1. <span data-ttu-id="327db-110">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="327db-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="327db-111">Seleziona **Aggiungi origine dati**.</span><span class="sxs-lookup"><span data-stu-id="327db-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="327db-112">Scegli il metodo **Importa dati** e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="327db-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="327db-113">Fornisci un **Nome** per l'origine dati e seleziona **Avanti** per creare l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="327db-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="327db-114">Linee guida per i nomi:</span><span class="sxs-lookup"><span data-stu-id="327db-114">Name guidelines:</span></span> 
   - <span data-ttu-id="327db-115">Deve iniziare con una lettera.</span><span class="sxs-lookup"><span data-stu-id="327db-115">Start with a letter.</span></span>
   - <span data-ttu-id="327db-116">Usa solo lettere e numeri.</span><span class="sxs-lookup"><span data-stu-id="327db-116">Use letters and numbers only.</span></span> <span data-ttu-id="327db-117">Gli spazi e i caratteri speciali non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="327db-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="327db-118">Usa tra 3 e 64 caratteri.</span><span class="sxs-lookup"><span data-stu-id="327db-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="327db-119">Scegli uno dei [connettori disponibili](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="327db-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="327db-120">Per questo esempio, selezioniamo il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="327db-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="327db-121">Immetti i dettagli richiesti in **Impostazioni di connessione** per il connettore selezionato e seleziona **Avanti** per visualizzare un'anteprima dei dati.</span><span class="sxs-lookup"><span data-stu-id="327db-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="327db-122">Seleziona **Trasforma dati**.</span><span class="sxs-lookup"><span data-stu-id="327db-122">Select **Transform data**.</span></span> <span data-ttu-id="327db-123">In questo passaggio, aggiungerai entità alla tua origine dati.</span><span class="sxs-lookup"><span data-stu-id="327db-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="327db-124">Le entità sono set di dati.</span><span class="sxs-lookup"><span data-stu-id="327db-124">Entities are datasets.</span></span> <span data-ttu-id="327db-125">Se disponi di un database che include più set di dati, ogni set di dati è la propria entità.</span><span class="sxs-lookup"><span data-stu-id="327db-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="327db-126">La finestra di dialogo **Power Query - Modifica query** consente di rivedere e perfezionare i dati.</span><span class="sxs-lookup"><span data-stu-id="327db-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="327db-127">Le entità identificate dai sistemi nell'origine dati selezionata vengono visualizzate nel riquadro di sinistra.</span><span class="sxs-lookup"><span data-stu-id="327db-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="327db-128">![Finestra di dialogo Modifica query](media/data-manager-configure-edit-queries.png "Finestra di dialogo Modifica query")</span><span class="sxs-lookup"><span data-stu-id="327db-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="327db-129">Puoi anche trasformare i dati.</span><span class="sxs-lookup"><span data-stu-id="327db-129">You can also transform your data.</span></span> <span data-ttu-id="327db-130">Seleziona un'entità da modificare o trasformare.</span><span class="sxs-lookup"><span data-stu-id="327db-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="327db-131">Utilizza le opzioni nella finestra Power Query per applicare le trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="327db-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="327db-132">Ogni trasformazione viene elencata in **Passaggi applicati**.</span><span class="sxs-lookup"><span data-stu-id="327db-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="327db-133">Power Query fornisce numerose opzioni di trasformazione predefinite.</span><span class="sxs-lookup"><span data-stu-id="327db-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="327db-134">Per altre informazioni, vedi [Trasformazioni di Power Query](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="327db-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="327db-135">Puoi aggiungere altre entità alla tua origine dati selezionando **Estrai dati** nella finestra di dialogo **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="327db-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="327db-136">Queste trasformazioni sono altamente raccomandate:</span><span class="sxs-lookup"><span data-stu-id="327db-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="327db-137">Se stai inserendo dati da un file CSV, la prima riga spesso contiene intestazioni.</span><span class="sxs-lookup"><span data-stu-id="327db-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="327db-138">Vai a **Trasforma tabella** e seleziona **Usa intestazioni come prima riga**.</span><span class="sxs-lookup"><span data-stu-id="327db-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="327db-139">Assicurati che il tipo di dati sia impostato in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="327db-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="327db-140">Seleziona **Salva** nella parte inferiore della finestra di Power Query per salvare le trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="327db-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="327db-141">Dopo aver salvato, troverai la tua origine dati su **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="327db-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="327db-142">Nella pagina **Origini dati** noterai che la nuova origine dati è nello stato **Aggiornamento in corso**.</span><span class="sxs-lookup"><span data-stu-id="327db-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="327db-143">Origini dati Power Query disponibili</span><span class="sxs-lookup"><span data-stu-id="327db-143">Available Power Query data sources</span></span>

<span data-ttu-id="327db-144">Vedi [Riferimento al connettore Power Query](/power-query/connectors/) per un elenco aggiornato dei connettori che è possibile selezionare per importare i dati in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="327db-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="327db-145">Connettori con un segno di spunta nella colonna **Customer Insights (Flussi di dati)** sono disponibili per creare nuove origini dati basate su Power Query.</span><span class="sxs-lookup"><span data-stu-id="327db-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="327db-146">Esamina la documentazione di un connettore specifico per ulteriori informazioni su prerequisiti, limitazioni e altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="327db-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="327db-147">Modifica origini dati Power Query disponibili</span><span class="sxs-lookup"><span data-stu-id="327db-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="327db-148">Potrebbe non essere possibile apportare modifiche alle origini dati attualmente utilizzate in uno dei processi dell'app (*segmentazione*, *corrispondenza* o *unione*, ad esempio).</span><span class="sxs-lookup"><span data-stu-id="327db-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="327db-149">Usando la pagina **Impostazioni**, puoi tener traccia dell'avanzamento di ciascuno dei processi attivi.</span><span class="sxs-lookup"><span data-stu-id="327db-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="327db-150">Al termine di un processo, puoi tornare alla pagina **Origine dei dati** e apportare le tue modifiche.</span><span class="sxs-lookup"><span data-stu-id="327db-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="327db-151">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="327db-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="327db-152">Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri modificare e seleziona **Modifica** dal menu a tendina.</span><span class="sxs-lookup"><span data-stu-id="327db-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="327db-153">![Modifica opzione](media/edit-option-data-sources.png "Modifica opzione")</span><span class="sxs-lookup"><span data-stu-id="327db-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="327db-154">Applica le modifiche e le trasformazioni nella finestra di dialogo **Power Query - Modifica query** come descritto nella sezione [Crea una nuova origine dati](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="327db-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="327db-155">Seleziona **Salva** in Power Query dopo aver completato le modifiche per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="327db-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]