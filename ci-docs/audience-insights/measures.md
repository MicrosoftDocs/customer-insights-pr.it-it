---
title: Creare e gestire misure
description: Definisci misure per analizzare e riflettere le prestazioni della tua attività.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304801"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="f1820-103">Definire e gestire misure</span><span class="sxs-lookup"><span data-stu-id="f1820-103">Define and manage measures</span></span>

<span data-ttu-id="f1820-104">Le misure ti aiutano a comprendere meglio i comportamenti dei clienti e le prestazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="f1820-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="f1820-105">Tengono in considerazione i valori rilevanti dei [profili unificati](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="f1820-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="f1820-106">Ad esempio, un'azienda vuole vedere la *spesa totale per cliente* per comprendere la cronologia degli acquisti di un singolo cliente oppure misurare le *vendite totali dell'azienda* per comprendere le entrate a livello aggregato nell'intera attività.</span><span class="sxs-lookup"><span data-stu-id="f1820-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="f1820-107">Le misure vengono create utilizzando il generatore di misure, una piattaforma di query di dati con vari operatori e semplici opzioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="f1820-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="f1820-108">Ti consente di filtrare i dati, raggruppare i risultati, rilevare [percorsi di relazione tra entità](relationships.md) e visualizzare in anteprima l'output.</span><span class="sxs-lookup"><span data-stu-id="f1820-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="f1820-109">Utilizza il generatore di misure per pianificare le attività aziendali eseguendo query sui dati dei clienti ed estrai informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="f1820-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="f1820-110">Ad esempio, creare una misura di *spesa totale per cliente* e *rendimento totale per cliente* aiuta a identificare un gruppo di clienti con una spesa elevata ma un ritorno elevato.</span><span class="sxs-lookup"><span data-stu-id="f1820-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="f1820-111">Puoi [creare un segmento](segments.md) per guidare le migliori azioni successive.</span><span class="sxs-lookup"><span data-stu-id="f1820-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="f1820-112">Creare la misura da zero</span><span class="sxs-lookup"><span data-stu-id="f1820-112">Build your own measure from scratch</span></span>

<span data-ttu-id="f1820-113">Questa sezione illustra come creare una nuova misura da zero.</span><span class="sxs-lookup"><span data-stu-id="f1820-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="f1820-114">È possibile creare una misura con attributi di dati da entità di dati che hanno una relazione impostata per connettersi con l'entità Cliente.</span><span class="sxs-lookup"><span data-stu-id="f1820-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="f1820-115">In Audience Insights, vai a **Misure**.</span><span class="sxs-lookup"><span data-stu-id="f1820-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="f1820-116">Seleziona **Nuovo** e scegli **Crea un valore personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="f1820-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="f1820-117">Seleziona **Modifica nome** e fornisci un **Nome** per la misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="f1820-118">Se la configurazione della nuova misura ha solo due campi, ad esempio CustomerID e un calcolo, l'output verrà aggiunto come una nuova colonna all'entità generata dal sistema denominata Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="f1820-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="f1820-119">E sarai in grado di vedere il valore della misura nel profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="f1820-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="f1820-120">Altre misure genereranno le proprie entità.</span><span class="sxs-lookup"><span data-stu-id="f1820-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="f1820-121">Nell'area di configurazione scegli la funzione di aggregazione dal menu a discesa **Seleziona funzione**.</span><span class="sxs-lookup"><span data-stu-id="f1820-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="f1820-122">Le funzioni di aggregazione includono:</span><span class="sxs-lookup"><span data-stu-id="f1820-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="f1820-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="f1820-123">**Sum**</span></span>
   - <span data-ttu-id="f1820-124">**Media**</span><span class="sxs-lookup"><span data-stu-id="f1820-124">**Average**</span></span>
   - <span data-ttu-id="f1820-125">**Conteggio**</span><span class="sxs-lookup"><span data-stu-id="f1820-125">**Count**</span></span>
   - <span data-ttu-id="f1820-126">**Numero univoco**</span><span class="sxs-lookup"><span data-stu-id="f1820-126">**Count Unique**</span></span>
   - <span data-ttu-id="f1820-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="f1820-127">**Max**</span></span>
   - <span data-ttu-id="f1820-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="f1820-128">**Min**</span></span>
   - <span data-ttu-id="f1820-129">**Primo**: prende il primo valore del record di dati</span><span class="sxs-lookup"><span data-stu-id="f1820-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="f1820-130">**Ultimo**: prende l'ultimo valore aggiunto al record di dati</span><span class="sxs-lookup"><span data-stu-id="f1820-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori per i calcoli delle misure.":::

1. <span data-ttu-id="f1820-132">Seleziona **Aggiungi attributo** per selezionare i dati necessari per creare questa misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="f1820-133">Seleziona la scheda **Attributi**.</span><span class="sxs-lookup"><span data-stu-id="f1820-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="f1820-134">Entità dati: scegli l'entità che include l'attributo che desideri misurare.</span><span class="sxs-lookup"><span data-stu-id="f1820-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="f1820-135">Attributo dati: scegli l'attributo che desideri utilizzare nella funzione di aggregazione per calcolare la misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="f1820-136">Puoi selezionare un solo attributo alla volta.</span><span class="sxs-lookup"><span data-stu-id="f1820-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="f1820-137">È inoltre possibile selezionare un attributo di dati da una misura esistente selezionando la scheda **Misure**. In alternativa, puoi cercare un nome di entità o di misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="f1820-138">Seleziona **Aggiungi** per aggiungere l'attributo selezionato alla misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleziona un attributo da utilizzare nei calcoli.":::

1. <span data-ttu-id="f1820-140">Per creare misure più complesse, puoi aggiungere più attributi o utilizzare operatori matematici nella funzione di misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Crea una misura complessa con operatori matematici.":::

1. <span data-ttu-id="f1820-142">Per aggiungere filtri, seleziona **Filtro** nell'area di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1820-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="f1820-143">Nella sezione **Aggiungi attributo** del riquadro **Filtri** seleziona l'attributo che desideri utilizzare per creare filtri.</span><span class="sxs-lookup"><span data-stu-id="f1820-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="f1820-144">Imposta gli operatori di filtro per definire il filtro per ogni attributo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f1820-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="f1820-145">Seleziona **Applica** per aggiungere i filtri alla misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="f1820-146">Per aggiungere dimensioni, seleziona **Dimensione** nell'area di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1820-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="f1820-147">Le dimensioni verranno visualizzate come colonne nell'entità di output della misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="f1820-148">Seleziona **Modifica dimensioni** per aggiungere gli attributi di dati in base ai quali raggruppare i valori di misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="f1820-149">Ad esempio, città o sesso.</span><span class="sxs-lookup"><span data-stu-id="f1820-149">For example, city or gender.</span></span> <span data-ttu-id="f1820-150">Per impostazione predefinita, la dimensione *CustomerID* è selezionata per creare *misure a livello di cliente*.</span><span class="sxs-lookup"><span data-stu-id="f1820-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="f1820-151">È possibile rimuovere la dimensione predefinita se si desidera creare *misure a livello di azienda*.</span><span class="sxs-lookup"><span data-stu-id="f1820-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="f1820-152">Seleziona **Fatto** per aggiungere le dimensioni alla misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="f1820-153">Se sono presenti valori nei dati che devi sostituire con un numero intero, ad esempio se devi sostituire *Null* con *0*, seleziona **Regole**.</span><span class="sxs-lookup"><span data-stu-id="f1820-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="f1820-154">Configura la regola e assicurati di scegliere solo numeri interi come sostituti.</span><span class="sxs-lookup"><span data-stu-id="f1820-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="f1820-155">Se sono presenti più percorsi tra l'entità di dati mappata e l'entità *Cliente*, è necessario scegliere uno dei [percorsi di relazione tra entità](relationships.md) identificati.</span><span class="sxs-lookup"><span data-stu-id="f1820-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="f1820-156">I risultati delle misure possono variare a seconda del percorso selezionato.</span><span class="sxs-lookup"><span data-stu-id="f1820-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="f1820-157">Seleziona **Preferenze dati** e scegli il percorso dell'entità da utilizzare per identificare la misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="f1820-158">Se esiste un solo percorso per l'entità *Cliente*, questo controllo non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="f1820-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="f1820-159">Seleziona **Fatto** per applicare la selezione.</span><span class="sxs-lookup"><span data-stu-id="f1820-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleziona il percorso dell'entità per la misura.":::

1. <span data-ttu-id="f1820-161">Per aggiungere altri calcoli per la misura, seleziona **Nuovo calcolo**.</span><span class="sxs-lookup"><span data-stu-id="f1820-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="f1820-162">È possibile utilizzare solo entità nello stesso percorso entità per nuovi calcoli.</span><span class="sxs-lookup"><span data-stu-id="f1820-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="f1820-163">Gli altri calcoli verranno visualizzati come nuove colonne nell'entità di output della misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="f1820-164">Seleziona **...** sul calcolo per **duplicare**, **rinominare** o **rimuovere** un calcolo da una misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="f1820-165">Nell'area **Anteprima** vedrai lo schema dei dati dell'entità di output della misura, inclusi filtri e dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f1820-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="f1820-166">L'anteprima reagisce dinamicamente alle modifiche nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1820-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="f1820-167">Seleziona **Esegui** per calcolare i risultati per la misura configurata.</span><span class="sxs-lookup"><span data-stu-id="f1820-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="f1820-168">Seleziona **Salva e chiudi** se si desidera mantenere la configurazione corrente ed eseguire la misura in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f1820-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="f1820-169">Vai a **Misure** per vedere la misura appena creata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f1820-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="f1820-170">Usare un modello per costruire una misura</span><span class="sxs-lookup"><span data-stu-id="f1820-170">Use a template to build a measure</span></span>

<span data-ttu-id="f1820-171">È possibile utilizzare modelli predefiniti di misure di uso comune per crearli.</span><span class="sxs-lookup"><span data-stu-id="f1820-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="f1820-172">Descrizioni dettagliate dei modelli e un'esperienza guidata ti aiutano a creare misure efficienti.</span><span class="sxs-lookup"><span data-stu-id="f1820-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="f1820-173">I modelli si basano sui dati mappati dall'entità *Impegno unificato*.</span><span class="sxs-lookup"><span data-stu-id="f1820-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="f1820-174">Quindi assicurati di aver configurato [impegni del cliente](activities.md) prima di creare una misura da un modello.</span><span class="sxs-lookup"><span data-stu-id="f1820-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="f1820-175">Modelli di misura disponibili:</span><span class="sxs-lookup"><span data-stu-id="f1820-175">Available measure templates:</span></span> 
- <span data-ttu-id="f1820-176">Valore medio transazione</span><span class="sxs-lookup"><span data-stu-id="f1820-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="f1820-177">Valore transazione totale</span><span class="sxs-lookup"><span data-stu-id="f1820-177">Total transaction value</span></span>
- <span data-ttu-id="f1820-178">Ricavi medi giornalieri</span><span class="sxs-lookup"><span data-stu-id="f1820-178">Average daily revenue</span></span>
- <span data-ttu-id="f1820-179">Ricavi medi annuali</span><span class="sxs-lookup"><span data-stu-id="f1820-179">Average yearly revenue</span></span>
- <span data-ttu-id="f1820-180">Numero di transazioni</span><span class="sxs-lookup"><span data-stu-id="f1820-180">Transaction count</span></span>
- <span data-ttu-id="f1820-181">Punti programma fedeltà ottenuti</span><span class="sxs-lookup"><span data-stu-id="f1820-181">Loyalty points earned</span></span>
- <span data-ttu-id="f1820-182">Punti programma fedeltà riscattati</span><span class="sxs-lookup"><span data-stu-id="f1820-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="f1820-183">Saldo punti programma fedeltà</span><span class="sxs-lookup"><span data-stu-id="f1820-183">Loyalty points balance</span></span>
- <span data-ttu-id="f1820-184">Durata del cliente attivo</span><span class="sxs-lookup"><span data-stu-id="f1820-184">Active customer lifespan</span></span>
- <span data-ttu-id="f1820-185">Durata iscrizione al programma fedeltà</span><span class="sxs-lookup"><span data-stu-id="f1820-185">Loyalty membership duration</span></span>
- <span data-ttu-id="f1820-186">Tempo dall'ultimo acquisto</span><span class="sxs-lookup"><span data-stu-id="f1820-186">Time since last purchase</span></span>

<span data-ttu-id="f1820-187">La procedura seguente descrive i passaggi per creare una nuova misura utilizzando un modello.</span><span class="sxs-lookup"><span data-stu-id="f1820-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="f1820-188">In Audience Insights, vai a **Misure**.</span><span class="sxs-lookup"><span data-stu-id="f1820-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="f1820-189">Seleziona **Nuovo** e seleziona **Scegli un modello**.</span><span class="sxs-lookup"><span data-stu-id="f1820-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Screenshot del menu a discesa durante la creazione di una nuova misura con evidenziazione sul modello.":::

1. <span data-ttu-id="f1820-191">Trova il modello che si adatta alle tue esigenze e seleziona **Scegli modello**.</span><span class="sxs-lookup"><span data-stu-id="f1820-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="f1820-192">Rivedi i dati richiesti e seleziona **Attività iniziali** se disponi di tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="f1820-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="f1820-193">Nel riquadro **Modifica nome** imposta il nome per la misura e l'entità di output.</span><span class="sxs-lookup"><span data-stu-id="f1820-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="f1820-194">Seleziona **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="f1820-194">Select **Done**.</span></span>

1. <span data-ttu-id="f1820-195">Nella sezione **Imposta periodo di tempo** definisci l'intervallo di tempo dei dati da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f1820-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="f1820-196">Scegli se vuoi che la nuova misura copra l'intero set di dati selezionando **Sempre** o se vuoi che la misura si concentri su un **Periodo di tempo specifico**.</span><span class="sxs-lookup"><span data-stu-id="f1820-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot che mostra la sezione del periodo di tempo durante la configurazione di una misura da un modello.":::

1. <span data-ttu-id="f1820-198">Nella sezione successiva, seleziona **Aggiungi dati** per scegliere gli impegni e mappare i dati corrispondenti dalla entità *Impegno unificato*.</span><span class="sxs-lookup"><span data-stu-id="f1820-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="f1820-199">Passaggio 1 di 2: sotto **Tipo di impegno**, scegli il tipo di entità che desideri utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f1820-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="f1820-200">Per **Impegni**, seleziona le entità che desideri mappare.</span><span class="sxs-lookup"><span data-stu-id="f1820-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="f1820-201">Passaggio 2 di 2: scegli l'attributo dall'entità *Impegno unificato* per il componente richiesto dalla formula.</span><span class="sxs-lookup"><span data-stu-id="f1820-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="f1820-202">Ad esempio, per valore medio della transazione, è l'attributo che rappresenta il valore della transazione.</span><span class="sxs-lookup"><span data-stu-id="f1820-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="f1820-203">Per **Timestamp impegno**, scegli l'attributo dall'entità Impegno unificato che rappresenta la data e l'ora dell'impegno.</span><span class="sxs-lookup"><span data-stu-id="f1820-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="f1820-204">Una volta completata la mappatura dei dati, puoi vedere lo stato come **Completato** e il nome degli impegni e degli attributi mappati.</span><span class="sxs-lookup"><span data-stu-id="f1820-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Screenshot di una configurazione del modello di misura completata.":::

1. <span data-ttu-id="f1820-206">Ora puoi selezionare **Esegui** per calcolare i risultati della misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="f1820-207">Per perfezionarlo in un secondo momento, seleziona **Salva bozza**.</span><span class="sxs-lookup"><span data-stu-id="f1820-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="f1820-208">Gestire le misure</span><span class="sxs-lookup"><span data-stu-id="f1820-208">Manage your measures</span></span>

<span data-ttu-id="f1820-209">Puoi trovare l'elenco delle misure nella pagina **Misure**.</span><span class="sxs-lookup"><span data-stu-id="f1820-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="f1820-210">Troverai informazioni sul tipo di misura, l'autore, la data di creazione e lo stato.</span><span class="sxs-lookup"><span data-stu-id="f1820-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="f1820-211">Quando selezioni una misura dall'elenco, puoi visualizzare in anteprima l'output e scaricare un file CSV.</span><span class="sxs-lookup"><span data-stu-id="f1820-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="f1820-212">Per aggiornare tutte le misure contemporaneamente, seleziona **Aggiorna tutto** senza selezionare una misura specifica.</span><span class="sxs-lookup"><span data-stu-id="f1820-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f1820-213">![Azioni per gestire singole misure.](media/measure-actions.png "Azioni per gestire singole misure.")</span><span class="sxs-lookup"><span data-stu-id="f1820-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="f1820-214">Seleziona una misura dall'elenco per le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="f1820-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="f1820-215">Seleziona il nome della misura per visualizzarne i dettagli.</span><span class="sxs-lookup"><span data-stu-id="f1820-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="f1820-216">**Modifica** la configurazione della misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="f1820-217">**Aggiorna** la misura in base ai dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="f1820-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="f1820-218">**Rinomina** la misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-218">**Rename** the measure.</span></span>
- <span data-ttu-id="f1820-219">**Elimina** la misura.</span><span class="sxs-lookup"><span data-stu-id="f1820-219">**Delete** the measure.</span></span>
- <span data-ttu-id="f1820-220">**Attiva** o **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="f1820-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="f1820-221">Le misure inattive non verranno aggiornate durante un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f1820-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="f1820-222">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="f1820-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f1820-223">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f1820-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f1820-224">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="f1820-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f1820-225">Dopo aver selezionato **Visualizza dettagli** per una delle attività del lavoro, troverai informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="f1820-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="f1820-226">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f1820-226">Next step</span></span>

<span data-ttu-id="f1820-227">Puoi utilizzare le misure esistenti per creare [un segmento di clientela](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f1820-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
