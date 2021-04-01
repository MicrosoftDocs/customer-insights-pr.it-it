---
title: Creare e gestire misure
description: Definisci misure per analizzare e riflettere le prestazioni della tua attività.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654737"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="17f46-103">Definire e gestire misure</span><span class="sxs-lookup"><span data-stu-id="17f46-103">Define and manage measures</span></span>

<span data-ttu-id="17f46-104">Le misure ti aiutano a comprendere meglio i comportamenti dei clienti e le prestazioni aziendali recuperando i valori pertinenti da [profili unificati](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="17f46-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="17f46-105">Ad esempio, un'azienda vuole vedere la *spesa totale per cliente* per comprendere la cronologia degli acquisti del singolo cliente.</span><span class="sxs-lookup"><span data-stu-id="17f46-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="17f46-106">O misurare le *vendite totali dell'azienda* per comprendere i ricavi a livello aggregato dell'intera azienda.</span><span class="sxs-lookup"><span data-stu-id="17f46-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="17f46-107">Le misure vengono create utilizzando il generatore di misure, una piattaforma di query di dati con vari operatori e semplici opzioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="17f46-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="17f46-108">Ti consente di filtrare i dati, raggruppare i risultati, rilevare [percorsi di relazione tra entità](relationships.md) e visualizzare in anteprima l'output.</span><span class="sxs-lookup"><span data-stu-id="17f46-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="17f46-109">Utilizza il generatore di misure per pianificare le attività aziendali eseguendo query sui dati dei clienti ed estrai informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="17f46-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="17f46-110">Ad esempio, creare una misura di *spesa totale per cliente* e *rendimento totale per cliente* aiuta a identificare un gruppo di clienti con una spesa elevata ma un ritorno elevato.</span><span class="sxs-lookup"><span data-stu-id="17f46-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="17f46-111">Puoi [creare un segmento](segments.md) per guidare le migliori azioni successive.</span><span class="sxs-lookup"><span data-stu-id="17f46-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="17f46-112">Creare una misura</span><span class="sxs-lookup"><span data-stu-id="17f46-112">Create a measure</span></span>

<span data-ttu-id="17f46-113">Questa sezione illustra come creare una nuova misura da zero.</span><span class="sxs-lookup"><span data-stu-id="17f46-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="17f46-114">È possibile creare una misura con attributi di dati da entità di dati che hanno una relazione impostata per connettersi con l'entità Cliente.</span><span class="sxs-lookup"><span data-stu-id="17f46-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="17f46-115">In Audience Insights, vai a **Misure**.</span><span class="sxs-lookup"><span data-stu-id="17f46-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="17f46-116">Seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="17f46-116">Select **New**.</span></span>

1. <span data-ttu-id="17f46-117">Seleziona **Modifica nome** e fornisci un **Nome** per la misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="17f46-118">Se la configurazione della nuova misura ha solo due campi, ad esempio CustomerID e un calcolo, l'output verrà aggiunto come una nuova colonna all'entità generata dal sistema denominata Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="17f46-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="17f46-119">E sarai in grado di vedere il valore della misura nel profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="17f46-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="17f46-120">Altre misure genereranno le proprie entità.</span><span class="sxs-lookup"><span data-stu-id="17f46-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="17f46-121">Nell'area di configurazione, scegli la funzione di aggregazione dal menu a discesa **Seleziona funzione**.</span><span class="sxs-lookup"><span data-stu-id="17f46-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="17f46-122">Le funzioni di aggregazione includono:</span><span class="sxs-lookup"><span data-stu-id="17f46-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="17f46-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="17f46-123">**Sum**</span></span>
   - <span data-ttu-id="17f46-124">**Media**</span><span class="sxs-lookup"><span data-stu-id="17f46-124">**Average**</span></span>
   - <span data-ttu-id="17f46-125">**Conteggio**</span><span class="sxs-lookup"><span data-stu-id="17f46-125">**Count**</span></span>
   - <span data-ttu-id="17f46-126">**Numero univoco**</span><span class="sxs-lookup"><span data-stu-id="17f46-126">**Count Unique**</span></span>
   - <span data-ttu-id="17f46-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="17f46-127">**Max**</span></span>
   - <span data-ttu-id="17f46-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="17f46-128">**Min**</span></span>
   - <span data-ttu-id="17f46-129">**Primo** : prende il primo valore del record di dati</span><span class="sxs-lookup"><span data-stu-id="17f46-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="17f46-130">**Ultimo** : prende l'ultimo valore aggiunto al record di dati</span><span class="sxs-lookup"><span data-stu-id="17f46-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori per i calcoli delle misure.":::

1. <span data-ttu-id="17f46-132">Seleziona **Aggiungi attributo** per selezionare i dati necessari per creare questa misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="17f46-133">Seleziona la scheda **Attributi**.</span><span class="sxs-lookup"><span data-stu-id="17f46-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="17f46-134">Entità dati: scegli l'entità che include l'attributo che desideri misurare.</span><span class="sxs-lookup"><span data-stu-id="17f46-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="17f46-135">Attributo dati: scegli l'attributo che desideri utilizzare nella funzione di aggregazione per calcolare la misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="17f46-136">Puoi selezionare un solo attributo alla volta.</span><span class="sxs-lookup"><span data-stu-id="17f46-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="17f46-137">È inoltre possibile selezionare un attributo di dati da una misura esistente selezionando la scheda **Misure**. In alternativa, puoi cercare un nome di entità o di misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="17f46-138">Seleziona **Aggiungi** per aggiungere l'attributo selezionato alla misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleziona un attributo da utilizzare nei calcoli.":::

1. <span data-ttu-id="17f46-140">Per creare misure più complesse, puoi aggiungere più attributi o utilizzare operatori matematici nella funzione di misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Crea una misura complessa con operatori matematici.":::

1. <span data-ttu-id="17f46-142">Per aggiungere filtri, seleziona **Filtro** nell'area di configurazione.</span><span class="sxs-lookup"><span data-stu-id="17f46-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="17f46-143">Nella sezione **Aggiungi attributo** del riquadro **Filtri**, seleziona l'attributo che desideri utilizzare per creare filtri.</span><span class="sxs-lookup"><span data-stu-id="17f46-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="17f46-144">Imposta gli operatori di filtro per definire il filtro per ogni attributo selezionato.</span><span class="sxs-lookup"><span data-stu-id="17f46-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="17f46-145">Seleziona **Applica** per aggiungere i filtri alla misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="17f46-146">Per aggiungere dimensioni, seleziona **Dimensione** nell'area di configurazione.</span><span class="sxs-lookup"><span data-stu-id="17f46-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="17f46-147">Le dimensioni verranno visualizzate come colonne nell'entità di output della misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="17f46-148">Seleziona **Modifica dimensioni** per aggiungere gli attributi di dati in base ai quali raggruppare i valori di misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="17f46-149">Ad esempio, città o sesso.</span><span class="sxs-lookup"><span data-stu-id="17f46-149">For example, city or gender.</span></span> <span data-ttu-id="17f46-150">Per impostazione predefinita, la dimensione *CustomerID* è selezionata per creare *misure a livello di cliente*.</span><span class="sxs-lookup"><span data-stu-id="17f46-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="17f46-151">È possibile rimuovere la dimensione predefinita se si desidera creare *misure a livello di azienda*.</span><span class="sxs-lookup"><span data-stu-id="17f46-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="17f46-152">Seleziona **Fatto** per aggiungere le dimensioni alla misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="17f46-153">Se sono presenti più percorsi tra l'entità di dati mappata e l'entità *Cliente*, è necessario scegliere uno dei [percorsi di relazione tra entità](relationships.md) identificati.</span><span class="sxs-lookup"><span data-stu-id="17f46-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="17f46-154">I risultati delle misure possono variare a seconda del percorso selezionato.</span><span class="sxs-lookup"><span data-stu-id="17f46-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="17f46-155">Seleziona **Preferenze dati** e scegli il percorso dell'entità da utilizzare per identificare la misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="17f46-156">Se esiste un solo percorso per l'entità *Cliente*, questo controllo non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="17f46-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="17f46-157">Seleziona **Fatto** per applicare la selezione.</span><span class="sxs-lookup"><span data-stu-id="17f46-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleziona il percorso dell'entità per la misura.":::

1. <span data-ttu-id="17f46-159">Per aggiungere altri calcoli per la misura, seleziona **Nuovo calcolo**.</span><span class="sxs-lookup"><span data-stu-id="17f46-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="17f46-160">È possibile utilizzare solo entità nello stesso percorso entità per nuovi calcoli.</span><span class="sxs-lookup"><span data-stu-id="17f46-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="17f46-161">Gli altri calcoli verranno visualizzati come nuove colonne nell'entità di output della misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="17f46-162">Seleziona **...** sul calcolo per **duplicare**, **rinominare** o **rimuovere** un calcolo da una misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="17f46-163">Nell'area **Anteprima** vedrai lo schema dei dati dell'entità di output della misura, inclusi filtri e dimensioni.</span><span class="sxs-lookup"><span data-stu-id="17f46-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="17f46-164">L'anteprima reagisce dinamicamente alle modifiche nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="17f46-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="17f46-165">Seleziona **Esegui** per calcolare i risultati per la misura configurata.</span><span class="sxs-lookup"><span data-stu-id="17f46-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="17f46-166">Seleziona **Salva e chiudi** se si desidera mantenere la configurazione corrente ed eseguire la misura in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="17f46-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="17f46-167">Vai a **Misure** per vedere la misura appena creata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="17f46-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="17f46-168">Gestire le misure</span><span class="sxs-lookup"><span data-stu-id="17f46-168">Manage your measures</span></span>

<span data-ttu-id="17f46-169">Dopo aver [creato una misura](#create-a-measure), vedrai un elenco di misure nella pagina **Misure**.</span><span class="sxs-lookup"><span data-stu-id="17f46-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="17f46-170">Troverai informazioni sul tipo di misura, l'autore, la data di creazione e lo stato.</span><span class="sxs-lookup"><span data-stu-id="17f46-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="17f46-171">Quando si seleziona una misura dall'elenco, è possibile visualizzare in anteprima l'output e scaricare un file .CSV.</span><span class="sxs-lookup"><span data-stu-id="17f46-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="17f46-172">Per aggiornare tutte le misure contemporaneamente, seleziona **Aggiorna tutto** senza selezionare una misura specifica.</span><span class="sxs-lookup"><span data-stu-id="17f46-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="17f46-173">![Azioni per gestire singole misure](media/measure-actions.png "Azioni per gestire singole misure")</span><span class="sxs-lookup"><span data-stu-id="17f46-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="17f46-174">Seleziona una misura dall'elenco per le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="17f46-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="17f46-175">Seleziona il nome della misura per visualizzarne i dettagli.</span><span class="sxs-lookup"><span data-stu-id="17f46-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="17f46-176">**Modifica** la configurazione della misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="17f46-177">**Aggiorna** la misura in base ai dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="17f46-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="17f46-178">**Rinomina** la misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-178">**Rename** the measure.</span></span>
- <span data-ttu-id="17f46-179">**Elimina** la misura.</span><span class="sxs-lookup"><span data-stu-id="17f46-179">**Delete** the measure.</span></span>
- <span data-ttu-id="17f46-180">**Attiva** o **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="17f46-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="17f46-181">Le misure inattive non verranno aggiornate durante un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="17f46-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="17f46-182">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="17f46-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="17f46-183">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="17f46-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="17f46-184">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="17f46-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="17f46-185">Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="17f46-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="17f46-186">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="17f46-186">Next step</span></span>

<span data-ttu-id="17f46-187">Puoi utilizzare le misure esistenti per creare [un segmento di clienti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="17f46-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]