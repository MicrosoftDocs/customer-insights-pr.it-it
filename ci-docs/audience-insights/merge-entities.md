---
title: Unire entità nel processo di unificazione dei dati
description: Unisci entità per creare profili cliente unificati.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085581"
---
# <a name="merge-entities"></a><span data-ttu-id="1ee10-103">Gestire entità</span><span class="sxs-lookup"><span data-stu-id="1ee10-103">Merge entities</span></span>

<span data-ttu-id="1ee10-104">La fase di unione è l'ultima fase del processo di unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="1ee10-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="1ee10-105">Il suo scopo è la riconciliazione di dati in conflitto.</span><span class="sxs-lookup"><span data-stu-id="1ee10-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="1ee10-106">Esempi di dati in conflitto potrebbero includere il nome di un cliente che si trova in due dei tuoi set di dati ma si presenta in modo leggermente diverso in ciascuno ("Grant Marshall" rispetto a "Grant Marshal") o un numero di telefono che differisce nel formato (617-803-091X rispetto a 617803091X).</span><span class="sxs-lookup"><span data-stu-id="1ee10-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="1ee10-107">L'unione di tali punti di dati in conflitto viene eseguita in base all'attributo per attributo.</span><span class="sxs-lookup"><span data-stu-id="1ee10-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Pagina di unione nel processo di unificazione dei dati che mostra la tabella con i campi uniti che definiscono il profilo del cliente unificato.":::

<span data-ttu-id="1ee10-109">Dopo aver completato la [fase di corrispondenza](match-entities.md), avvii la fase di unione selezionando il riquadro **Unione** nella pagina **Unifica**.</span><span class="sxs-lookup"><span data-stu-id="1ee10-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="1ee10-110">Rivedere gli elementi consigliati del sistema</span><span class="sxs-lookup"><span data-stu-id="1ee10-110">Review system recommendations</span></span>

<span data-ttu-id="1ee10-111">In **Dati** > **Unifica** > **Unisci**, scegli ed escludi gli attributi da unire all'interno dell'entità del profilo del cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="1ee10-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="1ee10-112">Il profilo del cliente unificato è il risultato del processo di unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="1ee10-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="1ee10-113">Alcuni attributi vengono automaticamente uniti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="1ee10-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="1ee10-114">Per visualizzare gli attributi inclusi in uno degli attributi uniti automaticamente, seleziona quell'attributo unito nella scheda **Campi cliente** della tabella.</span><span class="sxs-lookup"><span data-stu-id="1ee10-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="1ee10-115">Gli attributi che compongono l'attributo unito verranno visualizzati in due nuove righe sotto l'attributo unito.</span><span class="sxs-lookup"><span data-stu-id="1ee10-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="1ee10-116">Separare, rinominare, escludere e modificare i campi uniti</span><span class="sxs-lookup"><span data-stu-id="1ee10-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="1ee10-117">È possibile modificare il modo in cui il sistema elabora gli attributi uniti per generare il profilo del cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="1ee10-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="1ee10-118">Seleziona **Mostra altro** e scegli cosa vuoi cambiare.</span><span class="sxs-lookup"><span data-stu-id="1ee10-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opzioni nel menu a discesa Mostra altro per gestire gli attributi uniti.":::

<span data-ttu-id="1ee10-120">Per ulteriori informazioni, vedi la sezione riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="1ee10-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="1ee10-121">Separare i campi uniti</span><span class="sxs-lookup"><span data-stu-id="1ee10-121">Separate merged fields</span></span>

<span data-ttu-id="1ee10-122">Per separare i campi uniti, trova l'attributo nella tabella.</span><span class="sxs-lookup"><span data-stu-id="1ee10-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="1ee10-123">I campi separati vengono visualizzati come punti dati individuali nel profilo del cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="1ee10-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="1ee10-124">Seleziona il campo unito.</span><span class="sxs-lookup"><span data-stu-id="1ee10-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="1ee10-125">Seleziona **Mostra altro** e scegli **Separa campi**.</span><span class="sxs-lookup"><span data-stu-id="1ee10-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="1ee10-126">Conferma la separazione.</span><span class="sxs-lookup"><span data-stu-id="1ee10-126">Confirm the separation.</span></span>

1. <span data-ttu-id="1ee10-127">Seleziona **Salva** ed **Esegui** per elaborare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1ee10-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="1ee10-128">Rinominare i campi uniti</span><span class="sxs-lookup"><span data-stu-id="1ee10-128">Rename merged fields</span></span>

<span data-ttu-id="1ee10-129">Modifica il nome visualizzato degli attributi uniti.</span><span class="sxs-lookup"><span data-stu-id="1ee10-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="1ee10-130">Non è possibile modificare il nome dell'entità di output.</span><span class="sxs-lookup"><span data-stu-id="1ee10-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="1ee10-131">Seleziona il campo unito.</span><span class="sxs-lookup"><span data-stu-id="1ee10-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="1ee10-132">Seleziona **Mostra altro** e scegli **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="1ee10-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="1ee10-133">Conferma il nome visualizzato modificato.</span><span class="sxs-lookup"><span data-stu-id="1ee10-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="1ee10-134">Seleziona **Salva** ed **Esegui** per elaborare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1ee10-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="1ee10-135">Escludere i campi uniti</span><span class="sxs-lookup"><span data-stu-id="1ee10-135">Exclude merged fields</span></span>

<span data-ttu-id="1ee10-136">Escludi un attributo dal profilo del cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="1ee10-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="1ee10-137">Se il campo viene utilizzato in altri processi, ad esempio in un segmento, rimuovilo da questi processi prima di escluderlo dal profilo del cliente.</span><span class="sxs-lookup"><span data-stu-id="1ee10-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="1ee10-138">Seleziona il campo unito.</span><span class="sxs-lookup"><span data-stu-id="1ee10-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="1ee10-139">Seleziona **Mostra altro** e scegli **Escludi**.</span><span class="sxs-lookup"><span data-stu-id="1ee10-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="1ee10-140">Conferma l'esclusione.</span><span class="sxs-lookup"><span data-stu-id="1ee10-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="1ee10-141">Seleziona **Salva** ed **Esegui** per elaborare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1ee10-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="1ee10-142">Nella pagina **Unisci** seleziona **Campi esclusi** per vedere l'elenco di tutti i campi esclusi.</span><span class="sxs-lookup"><span data-stu-id="1ee10-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="1ee10-143">Questo riquadro consente di aggiungere nuovamente i campi esclusi.</span><span class="sxs-lookup"><span data-stu-id="1ee10-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="1ee10-144">Combinare manualmente i campi</span><span class="sxs-lookup"><span data-stu-id="1ee10-144">Manually combine fields</span></span>

<span data-ttu-id="1ee10-145">Specifica manualmente un attributo unito.</span><span class="sxs-lookup"><span data-stu-id="1ee10-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="1ee10-146">Nella pagina **Unisci** seleziona **Combina campi**.</span><span class="sxs-lookup"><span data-stu-id="1ee10-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="1ee10-147">Fornisci un **Nome** e un **Nome del campo di output**.</span><span class="sxs-lookup"><span data-stu-id="1ee10-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="1ee10-148">Scegli un campo da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1ee10-148">Choose a field to add.</span></span> <span data-ttu-id="1ee10-149">Seleziona **Aggiungi campi** per combinare altri campi.</span><span class="sxs-lookup"><span data-stu-id="1ee10-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="1ee10-150">Conferma l'esclusione.</span><span class="sxs-lookup"><span data-stu-id="1ee10-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="1ee10-151">Seleziona **Salva** ed **Esegui** per elaborare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1ee10-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="1ee10-152">Modificare l'ordine dei campi</span><span class="sxs-lookup"><span data-stu-id="1ee10-152">Change the order of fields</span></span>

<span data-ttu-id="1ee10-153">Alcune entità contengono più dettagli di altre.</span><span class="sxs-lookup"><span data-stu-id="1ee10-153">Some entities contain more details than others.</span></span> <span data-ttu-id="1ee10-154">Se un'entità include i dati più recenti su un campo, puoi dare la priorità ad altre entità quando unisci i valori.</span><span class="sxs-lookup"><span data-stu-id="1ee10-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="1ee10-155">Seleziona il campo unito.</span><span class="sxs-lookup"><span data-stu-id="1ee10-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="1ee10-156">Seleziona **Mostra altro** e scegli **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1ee10-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="1ee10-157">Nel riquadro **Combina campi** seleziona **Sposta su/giù** per impostare l'ordine o trascinali nella posizione desiderata.</span><span class="sxs-lookup"><span data-stu-id="1ee10-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="1ee10-158">Conferma la modifica.</span><span class="sxs-lookup"><span data-stu-id="1ee10-158">Confirm the change.</span></span>

1. <span data-ttu-id="1ee10-159">Seleziona **Salva** ed **Esegui** per elaborare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1ee10-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="1ee10-160">Eseguire l'unione</span><span class="sxs-lookup"><span data-stu-id="1ee10-160">Run your merge</span></span>

<span data-ttu-id="1ee10-161">Sia che unisci manualmente gli attributi o consenti al sistema di unirli, puoi sempre eseguire l'unione.</span><span class="sxs-lookup"><span data-stu-id="1ee10-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="1ee10-162">Seleziona **Esegui** nella pagina **Unione** per avviare il processo.</span><span class="sxs-lookup"><span data-stu-id="1ee10-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1ee10-163">![Salvataggio ed esecuzione dell'unione di dati](media/configure-data-merge-save-run.png "Salvataggio ed esecuzione dell'unione di dati")</span><span class="sxs-lookup"><span data-stu-id="1ee10-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="1ee10-164">Scegli **Esegui solo unione** se desideri solo vedere l'output riflesso nell'entità cliente unificata.</span><span class="sxs-lookup"><span data-stu-id="1ee10-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="1ee10-165">I processi a valle verranno aggiornati come [definito nella pianificazione dell'aggiornamento](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1ee10-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="1ee10-166">Scegli **Esegui processi di unione e downstream** per aggiornare il sistema con le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1ee10-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="1ee10-167">Tutti i processi, inclusi arricchimento, segmenti e misure verranno rieseguiti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1ee10-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="1ee10-168">Dopo che tutti i processi a valle sono stati completati, i profili dei clienti riflettono le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="1ee10-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="1ee10-169">Per apportare ulteriori modifiche e rieseguire il passaggio, è possibile annullare un'unione in corso.</span><span class="sxs-lookup"><span data-stu-id="1ee10-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="1ee10-170">Seleziona **Aggiornamento in corso ...** e seleziona **Annulla processo** nel riquadro laterale visualizzato.</span><span class="sxs-lookup"><span data-stu-id="1ee10-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="1ee10-171">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="1ee10-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="1ee10-172">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="1ee10-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="1ee10-173">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="1ee10-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="1ee10-174">Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="1ee10-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="1ee10-175">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="1ee10-175">Next Step</span></span>

<span data-ttu-id="1ee10-176">Configura [Impegni](activities.md), [Arricchimento](enrichment-hub.md) o [Relazioni](relationships.md) per ulteriori informazioni dettagliate sui clienti.</span><span class="sxs-lookup"><span data-stu-id="1ee10-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="1ee10-177">Se hai già configurato attività, arricchimenti o segmenti, verranno elaborati automaticamente per utilizzare i dati dei clienti più recenti.</span><span class="sxs-lookup"><span data-stu-id="1ee10-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
