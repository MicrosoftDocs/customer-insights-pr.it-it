---
title: Unire entità nel processo di unificazione dei dati
description: Unisci entità per creare profili cliente unificati.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896516"
---
# <a name="merge-entities"></a><span data-ttu-id="93fc4-103">Gestire entità</span><span class="sxs-lookup"><span data-stu-id="93fc4-103">Merge entities</span></span>

<span data-ttu-id="93fc4-104">La fase di unione è l'ultima fase del processo di unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="93fc4-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="93fc4-105">Il suo scopo è la riconciliazione di dati in conflitto.</span><span class="sxs-lookup"><span data-stu-id="93fc4-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="93fc4-106">Esempi di dati in conflitto potrebbero includere il nome di un cliente che si trova in due dei tuoi set di dati ma si presenta in modo leggermente diverso in ciascuno ("Grant Marshall" rispetto a "Grant Marshal") o un numero di telefono che differisce nel formato (617-803-091X rispetto a 617803091X).</span><span class="sxs-lookup"><span data-stu-id="93fc4-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="93fc4-107">L'unione di tali punti di dati in conflitto viene eseguita in base all'attributo per attributo.</span><span class="sxs-lookup"><span data-stu-id="93fc4-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="93fc4-108">Dopo aver completato la [fase di corrispondenza](match-entities.md), avvii la fase di unione selezionando il riquadro **Unione** nella pagina **Unifica**.</span><span class="sxs-lookup"><span data-stu-id="93fc4-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="93fc4-109">Rivedere gli elementi consigliati del sistema</span><span class="sxs-lookup"><span data-stu-id="93fc4-109">Review system recommendations</span></span>

<span data-ttu-id="93fc4-110">Nella pagina **Unione**, scegli ed escludi gli attributi da unire all'interno dell'entità del profilo cliente unificato (il risultato del processo di configurazione).</span><span class="sxs-lookup"><span data-stu-id="93fc4-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="93fc4-111">Alcuni attributi vengono automaticamente uniti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="93fc4-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="93fc4-112">Visualizzare gli attributi uniti</span><span class="sxs-lookup"><span data-stu-id="93fc4-112">View merged attributes</span></span>

<span data-ttu-id="93fc4-113">Per visualizzare gli attributi inclusi in uno degli attributi uniti automaticamente, seleziona l'attributo unito.</span><span class="sxs-lookup"><span data-stu-id="93fc4-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="93fc4-114">I due attributi che compongono l'attributo unito sono visualizzati in due nuove righe sotto l'attributo unito.</span><span class="sxs-lookup"><span data-stu-id="93fc4-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="93fc4-115">![Seleziona l'attributo unito](media/configure-data-merge-profile-attributes.png "Seleziona l'attributo unito")</span><span class="sxs-lookup"><span data-stu-id="93fc4-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="93fc4-116">Attributi uniti separati</span><span class="sxs-lookup"><span data-stu-id="93fc4-116">Separate merged attributes</span></span>

<span data-ttu-id="93fc4-117">Per separare o annullare l'unione di uno qualsiasi degli attributi uniti automaticamente, trova l'attributo nella tabella **Attributi profilo**.</span><span class="sxs-lookup"><span data-stu-id="93fc4-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="93fc4-118">Selezionare il pulsante con i puntini di sospensione (...).</span><span class="sxs-lookup"><span data-stu-id="93fc4-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="93fc4-119">Nell'elenco a discesa, seleziona **Campi separati**.</span><span class="sxs-lookup"><span data-stu-id="93fc4-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="93fc4-120">Rimuovere attributi uniti</span><span class="sxs-lookup"><span data-stu-id="93fc4-120">Remove merged attributes</span></span>

<span data-ttu-id="93fc4-121">Per escludere un attributo dall'entità del profilo cliente finale, cercalo nella tabella **Attributi profilo**.</span><span class="sxs-lookup"><span data-stu-id="93fc4-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="93fc4-122">Selezionare il pulsante con i puntini di sospensione (...).</span><span class="sxs-lookup"><span data-stu-id="93fc4-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="93fc4-123">Nell'elenco a discesa, seleziona **Non unire**.</span><span class="sxs-lookup"><span data-stu-id="93fc4-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="93fc4-124">L'attributo viene spostato nella sezione **Rimosso dal record del cliente**.</span><span class="sxs-lookup"><span data-stu-id="93fc4-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="93fc4-125">Aggiungere manualmente un attributo unito</span><span class="sxs-lookup"><span data-stu-id="93fc4-125">Manually add a merged attribute</span></span>

<span data-ttu-id="93fc4-126">Per aggiungere un attributo unito, vai alla pagina **Unione**.</span><span class="sxs-lookup"><span data-stu-id="93fc4-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="93fc4-127">Seleziona **Aggiungi attributo unito**.</span><span class="sxs-lookup"><span data-stu-id="93fc4-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="93fc4-128">Fornisci un **Nome** per identificarlo in seguito nella pagina **Unione**.</span><span class="sxs-lookup"><span data-stu-id="93fc4-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="93fc4-129">Facoltativamente, fornisci un **nome visualizzato** che verrà visualizzato nell'entità Profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="93fc4-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="93fc4-130">Configura **Seleziona gli attributi duplicati** per selezionare gli attributi che vvuoi unire dalle entità corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="93fc4-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="93fc4-131">Puoi anche cercare attributi.</span><span class="sxs-lookup"><span data-stu-id="93fc4-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="93fc4-132">Impostare **Classificazione per priorità** per assegnare la priorità a un attributo rispetto agli altri.</span><span class="sxs-lookup"><span data-stu-id="93fc4-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="93fc4-133">Ad esempio, sel'entità *WebAccountCSV* include i dati più accurati sull'atributo *Nomi completi*, è possibile assegnare priorità a questa entità rispetto a *ContactCSV* selezionando *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="93fc4-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="93fc4-134">Di conseguenza, *WebAccountCSV* passa alla prima priorità, mentre *ContactCSV* passa alla seconda priorità quando si estraggono i valori per l'atributo *Nome completo*.</span><span class="sxs-lookup"><span data-stu-id="93fc4-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="93fc4-135">Eseguire l'unione</span><span class="sxs-lookup"><span data-stu-id="93fc4-135">Run your merge</span></span>

<span data-ttu-id="93fc4-136">Sia che unisci manualmente gli attributi o consenti al sistema di unirli, puoi sempre eseguire l'unione.</span><span class="sxs-lookup"><span data-stu-id="93fc4-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="93fc4-137">Seleziona **Esegui** nella pagina **Unione** per avviare il processo.</span><span class="sxs-lookup"><span data-stu-id="93fc4-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="93fc4-138">![Salvataggio ed esecuzione dell'unione di dati](media/configure-data-merge-save-run.png "Salvataggio ed esecuzione dell'unione di dati")</span><span class="sxs-lookup"><span data-stu-id="93fc4-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="93fc4-139">Per apportare ulteriori modifiche ed eseguire nuovamente il passaggio, puoi annullare un'unione in corso.</span><span class="sxs-lookup"><span data-stu-id="93fc4-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="93fc4-140">Seleziona **Aggiornamento in corso ...** e seleziona **Annulla processo** nel riquadro laterale visualizzato.</span><span class="sxs-lookup"><span data-stu-id="93fc4-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="93fc4-141">Dopo che il testo **Aggiornamento in corso ...** cambia in **Completato**, l'unione è stata completata e ha risolto le contraddizioni nei dati in base ai criteri definiti.</span><span class="sxs-lookup"><span data-stu-id="93fc4-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="93fc4-142">Gli attributi uniti e non uniti sono inclusi nell'entità profilo unificata.</span><span class="sxs-lookup"><span data-stu-id="93fc4-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="93fc4-143">Gli attributi esclusi non sono inclusi nell'entità profilo unificata.</span><span class="sxs-lookup"><span data-stu-id="93fc4-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="93fc4-144">Se non era la prima volta che hai eseguito correttamente un'unione, tutti i processi a valle, inclusi l'arricchimento, la segmentazione e le misure, verranno eseguiti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="93fc4-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="93fc4-145">Dopo aver eseguito nuovamente tutti i processi a valle, i profili cliente riflettono le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="93fc4-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="93fc4-146">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="93fc4-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="93fc4-147">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="93fc4-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="93fc4-148">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="93fc4-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="93fc4-149">Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="93fc4-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="93fc4-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="93fc4-150">Next Step</span></span>

<span data-ttu-id="93fc4-151">Configura [Impegni](activities.md), [Arricchimento](enrichment-hub.md) o [Relazioni](relationships.md) per ulteriori informazioni dettagliate sui clienti.</span><span class="sxs-lookup"><span data-stu-id="93fc4-151">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="93fc4-152">Se hai già configurato gli impegni, l'arricchimento o le relazioni o se hai definito segmenti, questi verranno elaborati automaticamente per utilizzare i dati cliente più recenti.</span><span class="sxs-lookup"><span data-stu-id="93fc4-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]