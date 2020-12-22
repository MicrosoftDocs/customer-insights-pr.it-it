---
title: Creare e gestire segmenti
description: Crea segmenti di clienti per raggrupparli in base a vari attributi.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406144"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="bec55-103">Creare e gestire segmenti</span><span class="sxs-lookup"><span data-stu-id="bec55-103">Create and manage segments</span></span>

<span data-ttu-id="bec55-104">I segmenti ti consentono di raggruppare i clienti in base ad attributi demografici, transazionali o comportamentali.</span><span class="sxs-lookup"><span data-stu-id="bec55-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="bec55-105">Puoi utilizzare i segmenti per indirizzare campagne promozionali, attività di vendita e azioni di assistenza clienti per raggiungere i tuoi obiettivi aziendali.</span><span class="sxs-lookup"><span data-stu-id="bec55-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="bec55-106">È possibile definire filtri complessi intorno all'entità Profilo cliente e alle entità correlate.</span><span class="sxs-lookup"><span data-stu-id="bec55-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="bec55-107">Ogni segmento, dopo l'elaborazione, crea una serie di record dei clienti che puoi esportare o su cui puoi intervenire.</span><span class="sxs-lookup"><span data-stu-id="bec55-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="bec55-108">Si applicano alcuni [limiti di servizio](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="bec55-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="bec55-109">Salvo diversa indicazione, tutti i segmenti sono **Segmenti dinamici**, che vengono aggiornati in base a una pianificazione ricorrente.</span><span class="sxs-lookup"><span data-stu-id="bec55-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="bec55-110">Il seguente esempio illustra la funzionalità di segmentazione.</span><span class="sxs-lookup"><span data-stu-id="bec55-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="bec55-111">Abbiamo definito un segmento per i clienti che hanno ordinato almeno $500 di merci negli ultimi 90 giorni *e* che sono stati coinvolti in una chiamata servizio clienti che è stata riassegnata.</span><span class="sxs-lookup"><span data-stu-id="bec55-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bec55-112">![Gruppi multipli](media/segmentation-group1-2.png "Gruppi multipli")</span><span class="sxs-lookup"><span data-stu-id="bec55-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="bec55-113">Creare un nuovo segmento</span><span class="sxs-lookup"><span data-stu-id="bec55-113">Create a new segment</span></span>

<span data-ttu-id="bec55-114">I segmenti sono gestiti nella pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="bec55-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="bec55-115">In Audience Insights, vai alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="bec55-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="bec55-116">Seleziona **Nuovo** > **Segmento vuoto**.</span><span class="sxs-lookup"><span data-stu-id="bec55-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="bec55-117">Nel riquadro **Nuovo segmento**, scegli un tipo di segmento e assegna un **Nome**.</span><span class="sxs-lookup"><span data-stu-id="bec55-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="bec55-118">Facoltativamente, fornisci un nome visualizzato e una descrizione che aiuti a identificare il segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="bec55-119">Seleziona **Avanti** per andare alla pagina **Generatore di segmenti** in cui puoi definire un gruppo.</span><span class="sxs-lookup"><span data-stu-id="bec55-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="bec55-120">Un gruppo è un set di clienti.</span><span class="sxs-lookup"><span data-stu-id="bec55-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="bec55-121">Scegli l'entità che include l'attributo in base al quale vuoi segmentare.</span><span class="sxs-lookup"><span data-stu-id="bec55-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="bec55-122">Scegli l'attributo in base a cui segmentare.</span><span class="sxs-lookup"><span data-stu-id="bec55-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="bec55-123">Questo attributo può avere uno dei quattro tipi di valore: numerico, stringa, data o booleano.</span><span class="sxs-lookup"><span data-stu-id="bec55-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="bec55-124">Scegli un operatore e un valore per l'attributo selezionato.</span><span class="sxs-lookup"><span data-stu-id="bec55-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bec55-125">![Filtro gruppo clienti](media/customer-group-numbers.png "Filtro gruppo clienti")</span><span class="sxs-lookup"><span data-stu-id="bec55-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="bec55-126">Numero</span><span class="sxs-lookup"><span data-stu-id="bec55-126">Number</span></span> |<span data-ttu-id="bec55-127">Definizione</span><span class="sxs-lookup"><span data-stu-id="bec55-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="bec55-128">1</span><span class="sxs-lookup"><span data-stu-id="bec55-128">1</span></span>     |<span data-ttu-id="bec55-129">Entity</span><span class="sxs-lookup"><span data-stu-id="bec55-129">Entity</span></span>          |
   |<span data-ttu-id="bec55-130">2</span><span class="sxs-lookup"><span data-stu-id="bec55-130">2</span></span>     |<span data-ttu-id="bec55-131">Attributo</span><span class="sxs-lookup"><span data-stu-id="bec55-131">Attribute</span></span>          |
   |<span data-ttu-id="bec55-132">3</span><span class="sxs-lookup"><span data-stu-id="bec55-132">3</span></span>    |<span data-ttu-id="bec55-133">Operatore</span><span class="sxs-lookup"><span data-stu-id="bec55-133">Operator</span></span>         |
   |<span data-ttu-id="bec55-134">4</span><span class="sxs-lookup"><span data-stu-id="bec55-134">4</span></span>    |<span data-ttu-id="bec55-135">valore</span><span class="sxs-lookup"><span data-stu-id="bec55-135">Value</span></span>         |

8. <span data-ttu-id="bec55-136">Se l'entità è connessa all'entità cliente unificata tramite [relazioni](relationships.md), devi definire il percorso della relazione per creare un segmento valido.</span><span class="sxs-lookup"><span data-stu-id="bec55-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="bec55-137">Aggiungi le entità dal percorso della relazione fino a quando non puoi selezionare l'entità **Cliente: CustomerInsights** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="bec55-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="bec55-138">Quindi, scegli **Tutti i record** per ogni condizione.</span><span class="sxs-lookup"><span data-stu-id="bec55-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bec55-139">![Percorso di relazione durante la creazione del segmento](media/segments-multiple-relationships.png "Percorso di relazione durante la creazione del segmento")</span><span class="sxs-lookup"><span data-stu-id="bec55-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="bec55-140">Seleziona **Salva** per salvare il segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="bec55-141">Il segmento verrà salvato ed elaborato se tutti i requisiti vengono convalidati.</span><span class="sxs-lookup"><span data-stu-id="bec55-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="bec55-142">Altrimenti, verrà salvato come bozza.</span><span class="sxs-lookup"><span data-stu-id="bec55-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="bec55-143">Seleziona **Torna a Segmenti** per tornare alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="bec55-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="bec55-144">Gestire segmenti esistenti</span><span class="sxs-lookup"><span data-stu-id="bec55-144">Manage existing segments</span></span>

<span data-ttu-id="bec55-145">Nella pagina **Segmenti**, puoi visualizzare tutti i segmenti salvati e gestirli.</span><span class="sxs-lookup"><span data-stu-id="bec55-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="bec55-146">Ogni segmento è rappresentato da una riga che include informazioni aggiuntive sul segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="bec55-147">Puoi ordinare i segmenti in una colonna selezionando l'intestazione della colonna.</span><span class="sxs-lookup"><span data-stu-id="bec55-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="bec55-148">Utilizza la casella **Cerca** nell'angolo in alto a destra per filtrare i segmenti.</span><span class="sxs-lookup"><span data-stu-id="bec55-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bec55-149">![Opzioni per gestire un segmento esistente](media/segments-selected-segment.png "Opzioni per gestire un segmento esistente")</span><span class="sxs-lookup"><span data-stu-id="bec55-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="bec55-150">Quando selezioni un segmento sono disponibili le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="bec55-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="bec55-151">**Visualizza** i dettagli del segmento, inclusa la tendenza del conteggio dei membri, un'anteprima dei membri del segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="bec55-152">**Modifica** il segmento per modificarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="bec55-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="bec55-153">**Aggiorna** il segmento per includere gli ultimi dati.</span><span class="sxs-lookup"><span data-stu-id="bec55-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="bec55-154">**Attiva** o **Disattiva** il segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="bec55-155">I segmenti hanno due possibili stati: attivo o inattivo.</span><span class="sxs-lookup"><span data-stu-id="bec55-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="bec55-156">Questi stati sono utili quando si modifica un segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="bec55-157">Per i segmenti inattivi, la definizione del segmento esiste, ma non contiene ancora alcun cliente.</span><span class="sxs-lookup"><span data-stu-id="bec55-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="bec55-158">Quando attivi un segmento, il suo stato cambia da "inattivo" ad "attivo" e inizia a cercare i clienti che corrispondono alla definizione del segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="bec55-159">Se un [aggiornamento pianificato](system.md#schedule-tab) è configurato, i segmenti inattivi hanno **Stato** elencato come **Ignorato**, a indicare che non è stato nemmeno tentato un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="bec55-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="bec55-160">Quando un segmento inattivo viene attivato, verrà aggiornato e incluso negli aggiornamenti pianificati.</span><span class="sxs-lookup"><span data-stu-id="bec55-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="bec55-161">In alternativa, puoi utilizzare la funzionalità **Pianifica più tardi** nel menu a discesa **Attiva/Disattiva** per specificare una data e un'ora future per l'attivazione e la disattivazione di un particolare segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="bec55-162">**Rinomina** il segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-162">**Rename** the segment.</span></span>
- <span data-ttu-id="bec55-163">**Scarica** l'elenco dei membri in un file .CSV.</span><span class="sxs-lookup"><span data-stu-id="bec55-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="bec55-164">L'opzione **Aggiungi a** invia l'elenco degli ID cliente nel segmento per l'elaborazione in un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="bec55-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="bec55-165">**Elimina** il segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="bec55-166">Aggiornare i segmenti</span><span class="sxs-lookup"><span data-stu-id="bec55-166">Refresh segments</span></span>

<span data-ttu-id="bec55-167">Puoi aggiornare tutti i segmenti contemporaneamente selezionando **Aggiorna tutto** nella pagina **Segmenti** oppure puoi aggiornare uno o più segmenti quando li selezioni e scegli **Aggiorna** dalle opzioni.</span><span class="sxs-lookup"><span data-stu-id="bec55-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="bec55-168">In alternativa, puoi configurare un aggiornamento ricorrente in **Amministratore** > **Sistema** > **Pianifica**.</span><span class="sxs-lookup"><span data-stu-id="bec55-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="bec55-169">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="bec55-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="bec55-170">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="bec55-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="bec55-171">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="bec55-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="bec55-172">Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="bec55-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="bec55-173">Scaricare ed esportare segmenti</span><span class="sxs-lookup"><span data-stu-id="bec55-173">Download and export segments</span></span>

<span data-ttu-id="bec55-174">Puoi scaricare i tuoi segmenti in un file CSV o esportarli in Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bec55-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="bec55-175">Scaricare i segmenti in un file CSV</span><span class="sxs-lookup"><span data-stu-id="bec55-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="bec55-176">In Audience Insights, vai alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="bec55-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="bec55-177">Seleziona i puntini di sospensione nel riquadro di un segmento specifico.</span><span class="sxs-lookup"><span data-stu-id="bec55-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="bec55-178">Seleziona **Scarica come CSV** dall'elenco a discesa delle azioni.</span><span class="sxs-lookup"><span data-stu-id="bec55-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="bec55-179">Esportare segmenti in Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="bec55-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="bec55-180">Prima di esportare segmenti in Dynamics 365 Sales, un amministratore deve [creare la destinazione di esportazione](export-destinations.md) per Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bec55-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="bec55-181">In Audience Insights, vai alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="bec55-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="bec55-182">Seleziona i puntini di sospensione nel riquadro di un segmento specifico.</span><span class="sxs-lookup"><span data-stu-id="bec55-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="bec55-183">Seleziona **Aggiungi a** dall'elenco a discesa delle azioni e seleziona la destinazione di esportazione su cui vuoi inicare i dati.</span><span class="sxs-lookup"><span data-stu-id="bec55-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="bec55-184">Modalità bozza per i segmenti</span><span class="sxs-lookup"><span data-stu-id="bec55-184">Draft mode for segments</span></span>

<span data-ttu-id="bec55-185">Se non sono soddisfatti tutti i requisiti per elaborare un segmento, è possibile salvare il segmento come bozza e accedervi dalla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="bec55-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="bec55-186">Verrà salvato come segmento inattivo e non potrà essere attivato fino a quando non sarà valido.</span><span class="sxs-lookup"><span data-stu-id="bec55-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="bec55-187">Aggiungere più condizioni a un gruppo</span><span class="sxs-lookup"><span data-stu-id="bec55-187">Add more conditions to a group</span></span>

<span data-ttu-id="bec55-188">Per aggiungere più condizioni a un gruppo, è possibile utilizzare due operatori logici:</span><span class="sxs-lookup"><span data-stu-id="bec55-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="bec55-189">Operatore **AND**: entrambe le condizioni devono essere soddisfatte come parte del processo di segmentazione.</span><span class="sxs-lookup"><span data-stu-id="bec55-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="bec55-190">Questa opzione è molto utile quando si definiscono condizioni tra entità diverse.</span><span class="sxs-lookup"><span data-stu-id="bec55-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="bec55-191">Operatore **OR**: una delle condizioni deve essere soddisfatta come parte del processo di segmentazione.</span><span class="sxs-lookup"><span data-stu-id="bec55-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="bec55-192">Questa opzione è molto utile quando si definiscono più condizioni per la stessa entità.</span><span class="sxs-lookup"><span data-stu-id="bec55-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bec55-193">![Operatore OR in cui è necessario soddisfare una delle condizioni](media/segmentation-either-condition.png "Operatore OR in cui è necessario soddisfare una delle condizioni")</span><span class="sxs-lookup"><span data-stu-id="bec55-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="bec55-194">Al momento è possibile nidificare un operatore **OR** sotto un operatore **AND**, ma non il contrario.</span><span class="sxs-lookup"><span data-stu-id="bec55-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="bec55-195">Combinare più gruppi</span><span class="sxs-lookup"><span data-stu-id="bec55-195">Combine multiple groups</span></span>

<span data-ttu-id="bec55-196">Ogni gruppo produce un set specifico di clienti.</span><span class="sxs-lookup"><span data-stu-id="bec55-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="bec55-197">Puoi combinare questi gruppi per includere i clienti obbligatori per il tuo business case.</span><span class="sxs-lookup"><span data-stu-id="bec55-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="bec55-198">In Audience Insights, vai alla pagina **Segmenti** e seleziona un segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="bec55-199">Seleziona **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="bec55-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bec55-200">![Aggiungi gruppo per gruppo clienti](media/customer-group-add-group.png "Aggiungi gruppo per gruppo clienti")</span><span class="sxs-lookup"><span data-stu-id="bec55-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="bec55-201">Seleziona uno dei seguenti operatori di set: **Unione**, **Intersezione** o **Eccezione**.</span><span class="sxs-lookup"><span data-stu-id="bec55-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bec55-202">![Aggiungi Union per gruppo clienti](media/customer-group-union.png "Aggiungi Union per gruppo clienti")</span><span class="sxs-lookup"><span data-stu-id="bec55-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="bec55-203">Seleziona un operatore di set per definire un nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="bec55-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="bec55-204">Salva i differenti gruppi per determinare quali dati vengono conservati:</span><span class="sxs-lookup"><span data-stu-id="bec55-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="bec55-205">**Union** unisce i due gruppi.</span><span class="sxs-lookup"><span data-stu-id="bec55-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="bec55-206">**Intersect** sovrappone i due gruppi.</span><span class="sxs-lookup"><span data-stu-id="bec55-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="bec55-207">Solo i dati che *sono comuni* a entrambi i gruppi vengono mantenuti nel gruppo unificato.</span><span class="sxs-lookup"><span data-stu-id="bec55-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="bec55-208">**Ad eccezione di** combina i due gruppi.</span><span class="sxs-lookup"><span data-stu-id="bec55-208">**Except** combines the two groups.</span></span> <span data-ttu-id="bec55-209">Solo i dati nel gruppo A che *non sono comuni* ai dati nel gruppo B vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="bec55-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="bec55-210">Visualizzare la cronologia di elaborazione e i membri del segmento</span><span class="sxs-lookup"><span data-stu-id="bec55-210">View processing history and segment members</span></span>

<span data-ttu-id="bec55-211">Puoi visualizzare i dati consolidati di un segmento esaminandone i dettagli.</span><span class="sxs-lookup"><span data-stu-id="bec55-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="bec55-212">Nella pagina **Segmenti** seleziona il segmento da esaminare.</span><span class="sxs-lookup"><span data-stu-id="bec55-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="bec55-213">La parte superiore della pagina include un grafo di tendenza che visualizza le modifiche nel numero di membri.</span><span class="sxs-lookup"><span data-stu-id="bec55-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="bec55-214">Passa il mouse sopra i punti dati per vedere il numero di membri a una data specifica.</span><span class="sxs-lookup"><span data-stu-id="bec55-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="bec55-215">Puoi aggiornare l'intervallo di tempo della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="bec55-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bec55-216">![Intervallo di tempo segmento](media/segment-time-range.png "Intervallo di tempo segmento")</span><span class="sxs-lookup"><span data-stu-id="bec55-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="bec55-217">La parte inferiore contiene un elenco dei membri del segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="bec55-218">I campi che compaiono in questo elenco si basano sugli attributi delle entità del segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="bec55-219">L'elenco è un'anteprima dei membri del segmento corrispondenti e mostra i primi 100 record del segmento in modo da poterlo valutare rapidamente e rivederne le definizioni se necessario.</span><span class="sxs-lookup"><span data-stu-id="bec55-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="bec55-220">Per vedere tutti i record corrispondenti, è necessario [esportare il segmento](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bec55-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="bec55-221">Segmenti rapidi</span><span class="sxs-lookup"><span data-stu-id="bec55-221">Quick segments</span></span>

<span data-ttu-id="bec55-222">Oltre al generatore di segmenti, esiste un altro percorso per la creazione di segmenti.</span><span class="sxs-lookup"><span data-stu-id="bec55-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="bec55-223">I segmenti rapidi consentono di creare segmenti semplici (con un solo operatore) in modo rapido e con informazioni dettagliate immediate.</span><span class="sxs-lookup"><span data-stu-id="bec55-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="bec55-224">Nella pagina **Segmenti**, seleziona **Nuovo** > **Crea rapidamente da**.</span><span class="sxs-lookup"><span data-stu-id="bec55-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="bec55-225">Seleziona l'opzione **Profili** per creare un segmento basato sull'entità cliente unificata.</span><span class="sxs-lookup"><span data-stu-id="bec55-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="bec55-226">Seleziona l'opzione **Misure** per creare un segmento intorno a ciascun tipo di misure attributo cliente che hai precedentemente creato nella pagina **Misure**.</span><span class="sxs-lookup"><span data-stu-id="bec55-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="bec55-227">Seleziona l'opzione **Intelligenza** per creare un segmento attorno a una delle entità di output generate utilizzando le funzionalità **Previsioni** o **Modelli personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="bec55-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="bec55-228">Nella finestra di dialogo **Nuovo segmento rapido**, seleziona un attributo dal menu a discesa **Campo**.</span><span class="sxs-lookup"><span data-stu-id="bec55-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="bec55-229">Il sistema fornirà alcune informazioni dettagliate aggiuntive che ti aiuteranno a creare segmenti migliori dei tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="bec55-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="bec55-230">Per i campi di categoria, vengono visualizzati i primi 10 conteggi dei clienti.</span><span class="sxs-lookup"><span data-stu-id="bec55-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="bec55-231">Scegli un **valore** e seleziona **Revisione**.</span><span class="sxs-lookup"><span data-stu-id="bec55-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="bec55-232">Per un attributo numerico, il sistema mostrerà quale valore dell'attributo rientra nel percentile di ciascun cliente.</span><span class="sxs-lookup"><span data-stu-id="bec55-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="bec55-233">Scegli un **operatore** e un **valore**, quindi seleziona **Revisione**.</span><span class="sxs-lookup"><span data-stu-id="bec55-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="bec55-234">Il sistema fornirà una **dimensione stimata del segmento**.</span><span class="sxs-lookup"><span data-stu-id="bec55-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="bec55-235">Puoi scegliere se generare il segmento che hai definito o modificarlo prima per ottenere una dimensione del segmento diversa.</span><span class="sxs-lookup"><span data-stu-id="bec55-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bec55-236">![Nome e stima per un segmento rapido](media/quick-segment-name.png "Nome e stima per un segmento rapido")</span><span class="sxs-lookup"><span data-stu-id="bec55-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="bec55-237">Inserisci un **nome** per il segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="bec55-238">Se lo desideri, inserisci un **nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="bec55-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="bec55-239">Seleziona **Salva** per creare il segmento.</span><span class="sxs-lookup"><span data-stu-id="bec55-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="bec55-240">Al termine dell'elaborazione del segmento, puoi visualizzarlo come qualsiasi altro segmento che hai creato.</span><span class="sxs-lookup"><span data-stu-id="bec55-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="bec55-241">Per i seguenti scenari, si consiglia di utilizzare il generatore di segmenti anziché la funzionalità dei segmenti consigliati:</span><span class="sxs-lookup"><span data-stu-id="bec55-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="bec55-242">Creazione di segmenti con filtri su campi di categoria in cui l'operatore è diverso dall'operatore **Is**</span><span class="sxs-lookup"><span data-stu-id="bec55-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="bec55-243">Creazione di segmenti con filtri su campi numerici in cui l'operatore è diverso dagli operatori **Between**, **Greater than** e **Less than**</span><span class="sxs-lookup"><span data-stu-id="bec55-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="bec55-244">Creazione di segmenti con filtri nei campi del tipo di data</span><span class="sxs-lookup"><span data-stu-id="bec55-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="bec55-245">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="bec55-245">Next steps</span></span>

<span data-ttu-id="bec55-246">[Esporta un segmento](export-destinations.md) ed esplora [Scheda cliente](customer-card-add-in.md) e [Connettori](export-power-bi.md) per ottenere informazioni dettagliate a livello di cliente.</span><span class="sxs-lookup"><span data-stu-id="bec55-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
