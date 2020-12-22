---
title: Inserire dati tramite un connettore Power Query
description: Connettori per origini dati basati su Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406116"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="95565-103">Connettersi a un'origine dati Power Query</span><span class="sxs-lookup"><span data-stu-id="95565-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="95565-104">Power Query offre un'ampia gamma di connettori per inserire i dati.</span><span class="sxs-lookup"><span data-stu-id="95565-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="95565-105">La maggior parte di questi connettori è supportata da Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="95565-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="95565-106">L'aggiunta di origini dati basate sui connettori Power Query generalmente segue i passaggi descritti nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="95565-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="95565-107">Tuttavia, a seconda del connettore utilizzato, sono necessarie informazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="95565-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="95565-108">Per ulteriori informazioni, vedere la documentazione sui singoli connettori in [Riferimento al connettore Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="95565-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="95565-109">Crea una nuova origine dati</span><span class="sxs-lookup"><span data-stu-id="95565-109">Create a new data source</span></span>

1. <span data-ttu-id="95565-110">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="95565-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="95565-111">Seleziona **Aggiungi origine dati**.</span><span class="sxs-lookup"><span data-stu-id="95565-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="95565-112">Scegli il metodo **Importa dati** e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95565-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="95565-113">Fornisci un **Nome** per l'origine dati e seleziona **Avanti** per creare l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="95565-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="95565-114">Scegli uno dei [connettori disponibili](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="95565-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="95565-115">Per questo esempio, selezioniamo il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="95565-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="95565-116">Immetti i dettagli richiesti in **Impostazioni di connessione** per il connettore selezionato e seleziona **Avanti** per visualizzare un'anteprima dei dati.</span><span class="sxs-lookup"><span data-stu-id="95565-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="95565-117">Seleziona **Trasforma dati**.</span><span class="sxs-lookup"><span data-stu-id="95565-117">Select **Transform data**.</span></span> <span data-ttu-id="95565-118">In questo passaggio, aggiungerai entità alla tua origine dati.</span><span class="sxs-lookup"><span data-stu-id="95565-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="95565-119">Le entità sono set di dati.</span><span class="sxs-lookup"><span data-stu-id="95565-119">Entities are datasets.</span></span> <span data-ttu-id="95565-120">Se disponi di un database che include più set di dati, ogni set di dati è la propria entità.</span><span class="sxs-lookup"><span data-stu-id="95565-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="95565-121">La finestra di dialogo **Power Query - Modifica query** consente di rivedere e perfezionare i dati.</span><span class="sxs-lookup"><span data-stu-id="95565-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="95565-122">Le entità identificate dai sistemi nell'origine dati selezionata vengono visualizzate nel riquadro di sinistra.</span><span class="sxs-lookup"><span data-stu-id="95565-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="95565-123">![Finestra di dialogo Modifica query](media/data-manager-configure-edit-queries.png "Finestra di dialogo Modifica query")</span><span class="sxs-lookup"><span data-stu-id="95565-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="95565-124">Puoi anche trasformare i dati.</span><span class="sxs-lookup"><span data-stu-id="95565-124">You can also transform your data.</span></span> <span data-ttu-id="95565-125">Seleziona un'entità da modificare o trasformare.</span><span class="sxs-lookup"><span data-stu-id="95565-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="95565-126">Utilizza le opzioni nella finestra Power Query per applicare le trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="95565-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="95565-127">Ogni trasformazione viene elencata in **Passaggi applicati**.</span><span class="sxs-lookup"><span data-stu-id="95565-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="95565-128">Power Query fornisce numerose opzioni di trasformazione predefinite.</span><span class="sxs-lookup"><span data-stu-id="95565-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="95565-129">Per altre informazioni, vedi [Trasformazioni di Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="95565-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="95565-130">Puoi aggiungere altre entità alla tua origine dati selezionando **Estrai dati** nella finestra di dialogo **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="95565-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="95565-131">Queste trasformazioni sono altamente raccomandate:</span><span class="sxs-lookup"><span data-stu-id="95565-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="95565-132">Se stai inserendo dati da un file CSV, la prima riga spesso contiene intestazioni.</span><span class="sxs-lookup"><span data-stu-id="95565-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="95565-133">Vai a **Trasforma tabella** e seleziona **Usa intestazioni come prima riga**.</span><span class="sxs-lookup"><span data-stu-id="95565-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="95565-134">Assicurati che il tipo di dati sia impostato in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="95565-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="95565-135">Seleziona **Salva** nella parte inferiore della finestra di Power Query per salvare le trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="95565-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="95565-136">Dopo aver salvato, troverai la tua origine dati su **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="95565-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="95565-137">Nella pagina **Origini dati** noterai che la nuova origine dati è nello stato **Aggiornamento in corso**.</span><span class="sxs-lookup"><span data-stu-id="95565-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="95565-138">Origini dati Power Query disponibili</span><span class="sxs-lookup"><span data-stu-id="95565-138">Available Power Query data sources</span></span>

<span data-ttu-id="95565-139">Vedi [Riferimento al connettore Power Query](https://docs.microsoft.com/power-query/connectors/) per un elenco aggiornato dei connettori che è possibile selezionare per importare i dati in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="95565-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="95565-140">Connettori con un segno di spunta nella colonna **Customer Insights (Flussi di dati)** sono disponibili per creare nuove origini dati basate su Power Query.</span><span class="sxs-lookup"><span data-stu-id="95565-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="95565-141">Esamina la documentazione di un connettore specifico per ulteriori informazioni su prerequisiti, limitazioni e altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="95565-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="95565-142">Modifica origini dati Power Query disponibili</span><span class="sxs-lookup"><span data-stu-id="95565-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="95565-143">Potrebbe non essere possibile apportare modifiche alle origini dati attualmente utilizzate in uno dei processi dell'app (*segmentazione*, *corrispondenza* o *unione*, ad esempio).</span><span class="sxs-lookup"><span data-stu-id="95565-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="95565-144">Usando la pagina **Impostazioni**, puoi tener traccia dell'avanzamento di ciascuno dei processi attivi.</span><span class="sxs-lookup"><span data-stu-id="95565-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="95565-145">Al termine di un processo, puoi tornare alla pagina **Origine dei dati** e apportare le tue modifiche.</span><span class="sxs-lookup"><span data-stu-id="95565-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="95565-146">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="95565-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="95565-147">Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri modificare e seleziona **Modifica** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="95565-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="95565-148">![Modifica opzione](media/edit-option-data-sources.png "Modifica opzione")</span><span class="sxs-lookup"><span data-stu-id="95565-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="95565-149">Applica le modifiche e le trasformazioni nella finestra di dialogo **Power Query - Modifica query** come descritto nella sezione [Crea una nuova origine dati](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="95565-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="95565-150">Seleziona **Salva** in Power Query dopo aver completato le modifiche per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="95565-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
