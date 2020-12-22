---
title: Creare e modificare misure
description: Definisci misure relative al cliente per analizzare e riflettere le prestazioni di determinate aree di business.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406135"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="30108-103">Definire e gestire misure</span><span class="sxs-lookup"><span data-stu-id="30108-103">Define and manage measures</span></span>

<span data-ttu-id="30108-104">Le **misure** rappresentano gli indicatori di prestazione chiave (KPI) che riflettono le prestazioni e lo stato di aree di business specifiche.</span><span class="sxs-lookup"><span data-stu-id="30108-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="30108-105">Audience Insights offre un'esperienza intuitiva per la creazione di diversi tipi di misure, utilizzando un generatore di query che non richiede di codificare o convalidare le misure manualmente.</span><span class="sxs-lookup"><span data-stu-id="30108-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="30108-106">Puoi tener traccia delle misure aziendali nella pagina **Home**, vedere le misure per clienti specifici sulla **Scheda cliente** e utilizzare le misure per definire i segmenti di clienti nella pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="30108-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="30108-107">Creare una misura</span><span class="sxs-lookup"><span data-stu-id="30108-107">Create a measure</span></span>

<span data-ttu-id="30108-108">Questa sezione illustra come creare una misura da zero.</span><span class="sxs-lookup"><span data-stu-id="30108-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="30108-109">Puoi creare misure con dati provenienti da più origini dati connesse tramite l'entità Cliente.</span><span class="sxs-lookup"><span data-stu-id="30108-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="30108-110">Si applicano alcuni [limiti di servizio](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="30108-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="30108-111">In Audience Insights, vai a **Misure**.</span><span class="sxs-lookup"><span data-stu-id="30108-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="30108-112">Seleziona **Nuova misura**.</span><span class="sxs-lookup"><span data-stu-id="30108-112">Select **New measure**.</span></span>

3. <span data-ttu-id="30108-113">Scegli il **tipo** di misura:</span><span class="sxs-lookup"><span data-stu-id="30108-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="30108-114">**Attributo cliente**: un unico campo per cliente che riflette un punteggio, un valore o uno stato per il cliente.</span><span class="sxs-lookup"><span data-stu-id="30108-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="30108-115">Gli attributi del cliente vengono creati come attributi in una nuova entità generata dal sistema chiamata **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="30108-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="30108-116">**Misura del cliente**: informazioni dettagliate sul comportamento del cliente con suddivisione per dimensioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="30108-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="30108-117">Viene generata una nuova entità per ogni misura, potenzialmente con più record per cliente.</span><span class="sxs-lookup"><span data-stu-id="30108-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="30108-118">**Misura aziendale**: tiene traccia delle prestazioni e dello stato dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="30108-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="30108-119">Le misure aziendali possono avere due output diversi: un output numerico che viene visualizzato nella pagina **Home** o una nuova entità che trovi nella pagina **Entità**.</span><span class="sxs-lookup"><span data-stu-id="30108-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="30108-120">Specifica un **Nome** e un **nome visualizzato** facoltativo, quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="30108-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="30108-121">Nella sezione **Entità**, seleziona la prima entità nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="30108-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="30108-122">A questo punto, è necessario decidere se sono necessarie altre entità come parte della definizione della misura.</span><span class="sxs-lookup"><span data-stu-id="30108-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30108-123">![Definizione misura](media/measure-definition.png "Definizione misura")</span><span class="sxs-lookup"><span data-stu-id="30108-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="30108-124">Per aggiungere più entità, seleziona **Aggiungi entità** e seleziona le entità che desideri utilizzare per la misura.</span><span class="sxs-lookup"><span data-stu-id="30108-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="30108-125">Puoi selezionare solo entità che hanno relazioni con l'entità iniziale.</span><span class="sxs-lookup"><span data-stu-id="30108-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="30108-126">Per ulteriori informazioni sulla definizione delle relazioni, vedi [Relazioni](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="30108-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="30108-127">Facoltativamente, puoi configurare le variabili.</span><span class="sxs-lookup"><span data-stu-id="30108-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="30108-128">Nella sezione **Variabili**, seleziona **Nuova variabile**.</span><span class="sxs-lookup"><span data-stu-id="30108-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="30108-129">Le variabili sono calcoli effettuati su ciascuno dei record selezionati.</span><span class="sxs-lookup"><span data-stu-id="30108-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="30108-130">Ad esempio, sommando il punto vendita (POS) e le vendite online per ciascuno dei record dei clienti.</span><span class="sxs-lookup"><span data-stu-id="30108-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="30108-131">Specifica un **nome** per la variabile.</span><span class="sxs-lookup"><span data-stu-id="30108-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="30108-132">Nell'area **Espressione**, scegli un campo con cui iniziare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="30108-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="30108-133">Digita un'espressione nell'area **Espressione** mentre scegli più campi da includere nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="30108-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="30108-134">Attualmente, solo le espressioni aritmetiche sono supportate.</span><span class="sxs-lookup"><span data-stu-id="30108-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="30108-135">Inoltre, il calcolo delle variabili non è supportato per entità provenienti da diversi [percorsi di entità](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="30108-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="30108-136">Seleziona **Fine**.</span><span class="sxs-lookup"><span data-stu-id="30108-136">Select **Done**.</span></span>

11. <span data-ttu-id="30108-137">Nella sezione **Definizione misura**, definirai il modo in cui le entità scelte e le variabili calcolate vengono aggregate in una nuova entità di misura o attributo.</span><span class="sxs-lookup"><span data-stu-id="30108-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="30108-138">Seleziona **Nuova dimensione**.</span><span class="sxs-lookup"><span data-stu-id="30108-138">Select **New dimension**.</span></span> <span data-ttu-id="30108-139">Puoi pensare a una dimensione come a una funzione di *raggruppamento*.</span><span class="sxs-lookup"><span data-stu-id="30108-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="30108-140">L'output dei dati dell'entità o dell'attributo Misura sarà raggruppato per tutte le dimensioni definite.</span><span class="sxs-lookup"><span data-stu-id="30108-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="30108-141">![Scegliere un ciclo aggregato](media/measures-businessreport-measure-definition2.png "Scegliere un ciclo aggregato")</span><span class="sxs-lookup"><span data-stu-id="30108-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="30108-142">Seleziona o inserisci le seguenti informazioni come parte della definizione della tua dimensione:</span><span class="sxs-lookup"><span data-stu-id="30108-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="30108-143">**Entità**: se definisci un'entità Misura, dovrebbe includere almeno un attributo.</span><span class="sxs-lookup"><span data-stu-id="30108-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="30108-144">Se definisci un attributo Misura, includerà solo un attributo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="30108-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="30108-145">Questa selezione riguarda la scelta dell'entità che include quell'attributo.</span><span class="sxs-lookup"><span data-stu-id="30108-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="30108-146">**Campo**: scegli l'attributo specifico da includere nell'entità Misura o nell'attributo.</span><span class="sxs-lookup"><span data-stu-id="30108-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="30108-147">**Bucket**: sceglie se vuoi aggregare i dati su base giornaliera, mensile o annuale.</span><span class="sxs-lookup"><span data-stu-id="30108-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="30108-148">È una selezione obbligatoria solo se hai selezionato un attributo Tipo data.</span><span class="sxs-lookup"><span data-stu-id="30108-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="30108-149">**Come**: definisce il nome del nuovo campo.</span><span class="sxs-lookup"><span data-stu-id="30108-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="30108-150">**Nome visualizzato**: definisce il nome visualizzato del campo.</span><span class="sxs-lookup"><span data-stu-id="30108-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30108-151">La misura aziendale verrà salvata come entità a numero singolo e verrà visualizzata nella pagina **Home** a meno che tu non aggiunga più dimensioni alla tua misura.</span><span class="sxs-lookup"><span data-stu-id="30108-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="30108-152">Dopo aver aggiunto più dimensioni, la misura *non* verrà visualizzata nella pagina **Home**.</span><span class="sxs-lookup"><span data-stu-id="30108-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="30108-153">Facoltativamente, aggiungi funzioni di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="30108-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="30108-154">Qualsiasi aggregazione creata genera un nuovo valore all'interno dell'entità o dell'attributo Misure.</span><span class="sxs-lookup"><span data-stu-id="30108-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="30108-155">Le funzioni di aggregazione supportate sono: **Min**, **Max**, **Media**, **Mediana**, **Somma**, **Numero univoco**, **Primo** (acquisisce il primo record di un valore di dimensione) e **Ultimo** (acquisisce l'ultimo record aggiunto a un valore di dimensione).</span><span class="sxs-lookup"><span data-stu-id="30108-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="30108-156">Seleziona **Salva** per applicare le modifiche alla misura.</span><span class="sxs-lookup"><span data-stu-id="30108-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="30108-157">Gestire le misure</span><span class="sxs-lookup"><span data-stu-id="30108-157">Manage your measures</span></span>

<span data-ttu-id="30108-158">Dopo aver creato almeno una misura, vedrai un elenco di misure nella pagina **Misure**.</span><span class="sxs-lookup"><span data-stu-id="30108-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="30108-159">Troverai informazioni sul tipo di misura, l'autore, la data e l'ora di creazione, la data e l'ora dell'ultima modifica, lo stato (se la misura è attiva, inattiva o non riuscita) e la data e l'ora dell'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="30108-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="30108-160">Quando selezioni una misura dall'elenco, puoi visualizzare un'anteprima del suo output.</span><span class="sxs-lookup"><span data-stu-id="30108-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="30108-161">Per aggiornare tutte le misure contemporaneamente, seleziona **Aggiorna tutto** senza selezionare una misura specifica.</span><span class="sxs-lookup"><span data-stu-id="30108-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="30108-162">![Azioni per gestire singole misure](media/measure-actions.png "Azioni per gestire singole misure")</span><span class="sxs-lookup"><span data-stu-id="30108-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="30108-163">In alternativa, seleziona una misura dall'elenco ed effettua una delle seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="30108-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="30108-164">Seleziona il nome della misura per visualizzarne i dettagli.</span><span class="sxs-lookup"><span data-stu-id="30108-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="30108-165">**Modifica** la configurazione della misura.</span><span class="sxs-lookup"><span data-stu-id="30108-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="30108-166">**Rinomina** la misura.</span><span class="sxs-lookup"><span data-stu-id="30108-166">**Rename** the measure.</span></span>
- <span data-ttu-id="30108-167">**Elimina** la misura.</span><span class="sxs-lookup"><span data-stu-id="30108-167">**Delete** the measure.</span></span>
- <span data-ttu-id="30108-168">Seleziona i puntini di sospensione (...) e quindi **Aggiorna** per avviare il processo di aggiornamento per la misura.</span><span class="sxs-lookup"><span data-stu-id="30108-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="30108-169">Seleziona i puntini di sospensione (...) e quindi **Scarica** per scaricare un file .CSV della misura.</span><span class="sxs-lookup"><span data-stu-id="30108-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="30108-170">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="30108-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="30108-171">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="30108-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="30108-172">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="30108-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="30108-173">Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="30108-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="30108-174">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="30108-174">Next step</span></span>

<span data-ttu-id="30108-175">Puoi utilizzare le misure esistenti per creare il tuo primo segmento di clienti nella pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="30108-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="30108-176">Per ulteriori informazioni, vedi [Segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="30108-176">For more information, see [Segments](segments.md).</span></span>
