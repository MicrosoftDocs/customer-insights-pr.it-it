---
title: Creare e gestire segmenti
description: Crea segmenti di clienti per raggrupparli in base a vari attributi.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597057"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="b30ff-103">Creare e gestire segmenti</span><span class="sxs-lookup"><span data-stu-id="b30ff-103">Create and manage segments</span></span>

<span data-ttu-id="b30ff-104">I segmenti ti consentono di raggruppare i clienti in base ad attributi demografici, transazionali o comportamentali.</span><span class="sxs-lookup"><span data-stu-id="b30ff-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="b30ff-105">Puoi utilizzare i segmenti per indirizzare campagne promozionali, attività di vendita e azioni di assistenza clienti per raggiungere i tuoi obiettivi aziendali.</span><span class="sxs-lookup"><span data-stu-id="b30ff-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="b30ff-106">È possibile definire filtri complessi intorno all'entità Profilo cliente e alle entità correlate.</span><span class="sxs-lookup"><span data-stu-id="b30ff-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="b30ff-107">Ogni segmento, dopo l'elaborazione, crea una serie di record dei clienti che puoi esportare o su cui puoi intervenire.</span><span class="sxs-lookup"><span data-stu-id="b30ff-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="b30ff-108">Si applicano alcuni [limiti di servizio](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="b30ff-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="b30ff-109">Salvo diversa indicazione, tutti i segmenti sono **Segmenti dinamici**, che vengono aggiornati in base a una pianificazione ricorrente.</span><span class="sxs-lookup"><span data-stu-id="b30ff-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="b30ff-110">Il seguente esempio illustra la funzionalità di segmentazione.</span><span class="sxs-lookup"><span data-stu-id="b30ff-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="b30ff-111">Abbiamo definito un segmento per i clienti che hanno ordinato almeno $500 di merci negli ultimi 90 giorni *e* che sono stati coinvolti in una chiamata servizio clienti che è stata riassegnata.</span><span class="sxs-lookup"><span data-stu-id="b30ff-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b30ff-112">![Gruppi multipli](media/segmentation-group1-2.png "Gruppi multipli")</span><span class="sxs-lookup"><span data-stu-id="b30ff-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="b30ff-113">Creare un nuovo segmento</span><span class="sxs-lookup"><span data-stu-id="b30ff-113">Create a new segment</span></span>

<span data-ttu-id="b30ff-114">I segmenti sono gestiti nella pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="b30ff-115">In Audience Insights, vai alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="b30ff-116">Seleziona **Nuovo** > **Segmento vuoto**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="b30ff-117">Nel riquadro **Nuovo segmento**, scegli un tipo di segmento e assegna un **Nome**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="b30ff-118">Facoltativamente, fornisci un nome visualizzato e una descrizione che aiuti a identificare il segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="b30ff-119">Seleziona **Avanti** per andare alla pagina **Generatore di segmenti** in cui puoi definire un gruppo.</span><span class="sxs-lookup"><span data-stu-id="b30ff-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="b30ff-120">Un gruppo è un set di clienti.</span><span class="sxs-lookup"><span data-stu-id="b30ff-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="b30ff-121">Scegli l'entità che include l'attributo in base al quale vuoi segmentare.</span><span class="sxs-lookup"><span data-stu-id="b30ff-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="b30ff-122">Scegli l'attributo in base a cui segmentare.</span><span class="sxs-lookup"><span data-stu-id="b30ff-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="b30ff-123">Questo attributo può avere uno dei quattro tipi di valore: numerico, stringa, data o booleano.</span><span class="sxs-lookup"><span data-stu-id="b30ff-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="b30ff-124">Scegli un operatore e un valore per l'attributo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b30ff-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b30ff-125">![Filtro gruppo clienti](media/customer-group-numbers.png "Filtro gruppo clienti")</span><span class="sxs-lookup"><span data-stu-id="b30ff-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="b30ff-126">Numero</span><span class="sxs-lookup"><span data-stu-id="b30ff-126">Number</span></span> |<span data-ttu-id="b30ff-127">Definizione</span><span class="sxs-lookup"><span data-stu-id="b30ff-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="b30ff-128">1</span><span class="sxs-lookup"><span data-stu-id="b30ff-128">1</span></span>     |<span data-ttu-id="b30ff-129">Entity</span><span class="sxs-lookup"><span data-stu-id="b30ff-129">Entity</span></span>          |
   |<span data-ttu-id="b30ff-130">2</span><span class="sxs-lookup"><span data-stu-id="b30ff-130">2</span></span>     |<span data-ttu-id="b30ff-131">Attributo</span><span class="sxs-lookup"><span data-stu-id="b30ff-131">Attribute</span></span>          |
   |<span data-ttu-id="b30ff-132">3</span><span class="sxs-lookup"><span data-stu-id="b30ff-132">3</span></span>    |<span data-ttu-id="b30ff-133">Operatore</span><span class="sxs-lookup"><span data-stu-id="b30ff-133">Operator</span></span>         |
   |<span data-ttu-id="b30ff-134">4</span><span class="sxs-lookup"><span data-stu-id="b30ff-134">4</span></span>    |<span data-ttu-id="b30ff-135">valore</span><span class="sxs-lookup"><span data-stu-id="b30ff-135">Value</span></span>         |

8. <span data-ttu-id="b30ff-136">Se l'entità è connessa all'entità cliente unificata tramite [relazioni](relationships.md), devi definire il percorso della relazione per creare un segmento valido.</span><span class="sxs-lookup"><span data-stu-id="b30ff-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="b30ff-137">Aggiungi le entità dal percorso della relazione fino a quando non puoi selezionare l'entità **Cliente: CustomerInsights** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="b30ff-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="b30ff-138">Quindi, scegli **Tutti i record** per ogni condizione.</span><span class="sxs-lookup"><span data-stu-id="b30ff-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b30ff-139">![Percorso di relazione durante la creazione del segmento](media/segments-multiple-relationships.png "Percorso di relazione durante la creazione del segmento")</span><span class="sxs-lookup"><span data-stu-id="b30ff-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="b30ff-140">Per impostazione predefinita, i segmenti generano un'entità di output che contiene tutti gli attributi dei profili cliente che corrispondono ai filtri definiti.</span><span class="sxs-lookup"><span data-stu-id="b30ff-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="b30ff-141">Se un segmento è basato su entità diverse dall'entità *Cliente* puoi aggiungere più attributi da queste entità all'entità di output.</span><span class="sxs-lookup"><span data-stu-id="b30ff-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="b30ff-142">Seleziona **Attributi progetto** per scegliere gli attributi che verranno aggiunti all'entità di output.</span><span class="sxs-lookup"><span data-stu-id="b30ff-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="b30ff-143">Esempio: un segmento si basa su un'entità che contiene i dati sull'impegno del cliente correlati all'entità *Cliente*.</span><span class="sxs-lookup"><span data-stu-id="b30ff-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="b30ff-144">Il segmento cerca tutti i clienti che hanno chiamato l'help desk negli ultimi 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="b30ff-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="b30ff-145">Puoi scegliere di aggiungere la durata della chiamata e il numero di chiamate a tutti i record cliente corrispondenti nell'entità di output.</span><span class="sxs-lookup"><span data-stu-id="b30ff-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="b30ff-146">Queste informazioni potrebbero essere utili per inviare un'e-mail con collegamenti utili ad articoli della guida in linea e domande frequenti per i clienti che chiamano frequentemente.</span><span class="sxs-lookup"><span data-stu-id="b30ff-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="b30ff-147">Seleziona **Salva** per salvare il segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="b30ff-148">Il segmento verrà salvato ed elaborato se tutti i requisiti vengono convalidati.</span><span class="sxs-lookup"><span data-stu-id="b30ff-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="b30ff-149">Altrimenti, verrà salvato come bozza.</span><span class="sxs-lookup"><span data-stu-id="b30ff-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="b30ff-150">Seleziona **Torna a Segmenti** per tornare alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="b30ff-151">Gestire segmenti esistenti</span><span class="sxs-lookup"><span data-stu-id="b30ff-151">Manage existing segments</span></span>

<span data-ttu-id="b30ff-152">Nella pagina **Segmenti**, puoi visualizzare tutti i segmenti salvati e gestirli.</span><span class="sxs-lookup"><span data-stu-id="b30ff-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="b30ff-153">Ogni segmento è rappresentato da una riga che include informazioni aggiuntive sul segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="b30ff-154">Puoi ordinare i segmenti in una colonna selezionando l'intestazione della colonna.</span><span class="sxs-lookup"><span data-stu-id="b30ff-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="b30ff-155">Utilizza la casella **Cerca** nell'angolo in alto a destra per filtrare i segmenti.</span><span class="sxs-lookup"><span data-stu-id="b30ff-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b30ff-156">![Opzioni per gestire un segmento esistente](media/segments-selected-segment.png "Opzioni per gestire un segmento esistente")</span><span class="sxs-lookup"><span data-stu-id="b30ff-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="b30ff-157">Quando selezioni un segmento sono disponibili le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="b30ff-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="b30ff-158">**Visualizza** i dettagli del segmento, inclusa la tendenza del conteggio dei membri, un'anteprima dei membri del segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="b30ff-159">**Modifica** il segmento per modificarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="b30ff-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="b30ff-160">**Crea duplicato** di un segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="b30ff-161">Puoi scegliere di modificare subito le proprietà o semplicemente salvare il duplicato.</span><span class="sxs-lookup"><span data-stu-id="b30ff-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="b30ff-162">**Aggiorna** il segmento per includere gli ultimi dati.</span><span class="sxs-lookup"><span data-stu-id="b30ff-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="b30ff-163">**Attiva** o **Disattiva** il segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="b30ff-164">I segmenti hanno due possibili stati: attivo o inattivo.</span><span class="sxs-lookup"><span data-stu-id="b30ff-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="b30ff-165">Questi stati sono utili quando si modifica un segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="b30ff-166">Per i segmenti inattivi, la definizione del segmento esiste, ma non contiene ancora alcun cliente.</span><span class="sxs-lookup"><span data-stu-id="b30ff-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="b30ff-167">Quando attivi un segmento, il suo stato cambia da "inattivo" ad "attivo" e inizia a cercare i clienti che corrispondono alla definizione del segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="b30ff-168">Se un [aggiornamento pianificato](system.md#schedule-tab) è configurato, i segmenti inattivi hanno **Stato** elencato come **Ignorato**, a indicare che non è stato nemmeno tentato un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="b30ff-169">Quando un segmento inattivo viene attivato, verrà aggiornato e incluso negli aggiornamenti pianificati.</span><span class="sxs-lookup"><span data-stu-id="b30ff-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="b30ff-170">In alternativa, puoi utilizzare la funzionalità **Pianifica più tardi** nel menu a discesa **Attiva/Disattiva** per specificare una data e un'ora future per l'attivazione e la disattivazione di un particolare segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="b30ff-171">**Rinomina** il segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-171">**Rename** the segment.</span></span>
- <span data-ttu-id="b30ff-172">**Scarica** l'elenco dei membri in un file .CSV.</span><span class="sxs-lookup"><span data-stu-id="b30ff-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="b30ff-173">L'opzione **Aggiungi a** invia l'elenco degli ID cliente nel segmento per l'elaborazione in un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="b30ff-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="b30ff-174">**Elimina** il segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="b30ff-175">Aggiornare i segmenti</span><span class="sxs-lookup"><span data-stu-id="b30ff-175">Refresh segments</span></span>

<span data-ttu-id="b30ff-176">Puoi aggiornare tutti i segmenti contemporaneamente selezionando **Aggiorna tutto** nella pagina **Segmenti** oppure puoi aggiornare uno o più segmenti quando li selezioni e scegli **Aggiorna** dalle opzioni.</span><span class="sxs-lookup"><span data-stu-id="b30ff-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="b30ff-177">In alternativa, puoi configurare un aggiornamento ricorrente in **Amministratore** > **Sistema** > **Pianifica**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="b30ff-178">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="b30ff-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b30ff-179">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b30ff-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b30ff-180">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="b30ff-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b30ff-181">Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="b30ff-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="b30ff-182">Scaricare ed esportare segmenti</span><span class="sxs-lookup"><span data-stu-id="b30ff-182">Download and export segments</span></span>

<span data-ttu-id="b30ff-183">Puoi scaricare i tuoi segmenti in un file CSV o esportarli in Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b30ff-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="b30ff-184">Scaricare i segmenti in un file CSV</span><span class="sxs-lookup"><span data-stu-id="b30ff-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="b30ff-185">In Audience Insights, vai alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="b30ff-186">Seleziona i puntini di sospensione nel riquadro di un segmento specifico.</span><span class="sxs-lookup"><span data-stu-id="b30ff-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="b30ff-187">Seleziona **Scarica come CSV** dall'elenco a discesa delle azioni.</span><span class="sxs-lookup"><span data-stu-id="b30ff-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="b30ff-188">Esportare segmenti in Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="b30ff-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="b30ff-189">Prima di esportare segmenti in Dynamics 365 Sales, un amministratore deve [creare la destinazione di esportazione](export-destinations.md) per Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b30ff-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="b30ff-190">In Audience Insights, vai alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="b30ff-191">Seleziona i puntini di sospensione nel riquadro di un segmento specifico.</span><span class="sxs-lookup"><span data-stu-id="b30ff-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="b30ff-192">Seleziona **Aggiungi a** dall'elenco a discesa delle azioni e seleziona la destinazione di esportazione su cui vuoi inicare i dati.</span><span class="sxs-lookup"><span data-stu-id="b30ff-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="b30ff-193">Modalità bozza per i segmenti</span><span class="sxs-lookup"><span data-stu-id="b30ff-193">Draft mode for segments</span></span>

<span data-ttu-id="b30ff-194">Se non sono soddisfatti tutti i requisiti per elaborare un segmento, è possibile salvare il segmento come bozza e accedervi dalla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="b30ff-195">Verrà salvato come segmento inattivo e non potrà essere attivato fino a quando non sarà valido.</span><span class="sxs-lookup"><span data-stu-id="b30ff-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="b30ff-196">Aggiungere più condizioni a un gruppo</span><span class="sxs-lookup"><span data-stu-id="b30ff-196">Add more conditions to a group</span></span>

<span data-ttu-id="b30ff-197">Per aggiungere più condizioni a un gruppo, è possibile utilizzare due operatori logici:</span><span class="sxs-lookup"><span data-stu-id="b30ff-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="b30ff-198">Operatore **AND**: entrambe le condizioni devono essere soddisfatte come parte del processo di segmentazione.</span><span class="sxs-lookup"><span data-stu-id="b30ff-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="b30ff-199">Questa opzione è molto utile quando si definiscono condizioni tra entità diverse.</span><span class="sxs-lookup"><span data-stu-id="b30ff-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="b30ff-200">Operatore **OR**: una delle condizioni deve essere soddisfatta come parte del processo di segmentazione.</span><span class="sxs-lookup"><span data-stu-id="b30ff-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="b30ff-201">Questa opzione è molto utile quando si definiscono più condizioni per la stessa entità.</span><span class="sxs-lookup"><span data-stu-id="b30ff-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b30ff-202">![Operatore OR in cui è necessario soddisfare una delle condizioni](media/segmentation-either-condition.png "Operatore OR in cui è necessario soddisfare una delle condizioni")</span><span class="sxs-lookup"><span data-stu-id="b30ff-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="b30ff-203">Al momento è possibile nidificare un operatore **OR** sotto un operatore **AND**, ma non il contrario.</span><span class="sxs-lookup"><span data-stu-id="b30ff-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="b30ff-204">Combinare più gruppi</span><span class="sxs-lookup"><span data-stu-id="b30ff-204">Combine multiple groups</span></span>

<span data-ttu-id="b30ff-205">Ogni gruppo produce un set specifico di clienti.</span><span class="sxs-lookup"><span data-stu-id="b30ff-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="b30ff-206">Puoi combinare questi gruppi per includere i clienti obbligatori per il tuo business case.</span><span class="sxs-lookup"><span data-stu-id="b30ff-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="b30ff-207">In Audience Insights, vai alla pagina **Segmenti** e seleziona un segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="b30ff-208">Seleziona **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b30ff-209">![Aggiungi gruppo per gruppo clienti](media/customer-group-add-group.png "Aggiungi gruppo per gruppo clienti")</span><span class="sxs-lookup"><span data-stu-id="b30ff-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="b30ff-210">Seleziona uno dei seguenti operatori di set: **Unione**, **Intersezione** o **Eccezione**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b30ff-211">![Aggiungi Union per gruppo clienti](media/customer-group-union.png "Aggiungi Union per gruppo clienti")</span><span class="sxs-lookup"><span data-stu-id="b30ff-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="b30ff-212">Seleziona un operatore di set per definire un nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="b30ff-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="b30ff-213">Salva i differenti gruppi per determinare quali dati vengono conservati:</span><span class="sxs-lookup"><span data-stu-id="b30ff-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="b30ff-214">**Union** unisce i due gruppi.</span><span class="sxs-lookup"><span data-stu-id="b30ff-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="b30ff-215">**Intersect** sovrappone i due gruppi.</span><span class="sxs-lookup"><span data-stu-id="b30ff-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="b30ff-216">Solo i dati che *sono comuni* a entrambi i gruppi vengono mantenuti nel gruppo unificato.</span><span class="sxs-lookup"><span data-stu-id="b30ff-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="b30ff-217">**Ad eccezione di** combina i due gruppi.</span><span class="sxs-lookup"><span data-stu-id="b30ff-217">**Except** combines the two groups.</span></span> <span data-ttu-id="b30ff-218">Solo i dati nel gruppo A che *non sono comuni* ai dati nel gruppo B vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="b30ff-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="b30ff-219">Visualizzare la cronologia di elaborazione e i membri del segmento</span><span class="sxs-lookup"><span data-stu-id="b30ff-219">View processing history and segment members</span></span>

<span data-ttu-id="b30ff-220">Puoi visualizzare i dati consolidati di un segmento esaminandone i dettagli.</span><span class="sxs-lookup"><span data-stu-id="b30ff-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="b30ff-221">Nella pagina **Segmenti** seleziona il segmento da esaminare.</span><span class="sxs-lookup"><span data-stu-id="b30ff-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="b30ff-222">La parte superiore della pagina include un grafo di tendenza che visualizza le modifiche nel numero di membri.</span><span class="sxs-lookup"><span data-stu-id="b30ff-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="b30ff-223">Passa il mouse sopra i punti dati per vedere il numero di membri a una data specifica.</span><span class="sxs-lookup"><span data-stu-id="b30ff-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="b30ff-224">Puoi aggiornare l'intervallo di tempo della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b30ff-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b30ff-225">![Intervallo di tempo segmento](media/segment-time-range.png "Intervallo di tempo segmento")</span><span class="sxs-lookup"><span data-stu-id="b30ff-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="b30ff-226">La parte inferiore contiene un elenco dei membri del segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="b30ff-227">I campi che compaiono in questo elenco si basano sugli attributi delle entità del segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="b30ff-228">L'elenco è un'anteprima dei membri del segmento corrispondenti e mostra i primi 100 record del segmento in modo da poterlo valutare rapidamente e rivederne le definizioni se necessario.</span><span class="sxs-lookup"><span data-stu-id="b30ff-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="b30ff-229">Per vedere tutti i record corrispondenti, è necessario [esportare il segmento](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b30ff-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="b30ff-230">Segmenti rapidi</span><span class="sxs-lookup"><span data-stu-id="b30ff-230">Quick segments</span></span>

<span data-ttu-id="b30ff-231">Oltre al generatore di segmenti, esiste un altro percorso per la creazione di segmenti.</span><span class="sxs-lookup"><span data-stu-id="b30ff-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="b30ff-232">I segmenti rapidi consentono di creare segmenti semplici (con un solo operatore) in modo rapido e con informazioni dettagliate immediate.</span><span class="sxs-lookup"><span data-stu-id="b30ff-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="b30ff-233">Nella pagina **Segmenti**, seleziona **Nuovo** > **Crea rapidamente da**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="b30ff-234">Seleziona l'opzione **Profili** per creare un segmento basato sull'entità cliente unificata.</span><span class="sxs-lookup"><span data-stu-id="b30ff-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="b30ff-235">Seleziona l'opzione **Misure** per creare un segmento intorno a ciascun tipo di misure attributo cliente che hai precedentemente creato nella pagina **Misure**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="b30ff-236">Seleziona l'opzione **Intelligenza** per creare un segmento attorno a una delle entità di output generate utilizzando le funzionalità **Previsioni** o **Modelli personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="b30ff-237">Nella finestra di dialogo **Nuovo segmento rapido**, seleziona un attributo dal menu a discesa **Campo**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="b30ff-238">Il sistema fornirà alcune informazioni dettagliate aggiuntive che ti aiuteranno a creare segmenti migliori dei tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="b30ff-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="b30ff-239">Per i campi di categoria, vengono visualizzati i primi 10 conteggi dei clienti.</span><span class="sxs-lookup"><span data-stu-id="b30ff-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="b30ff-240">Scegli un **valore** e seleziona **Revisione**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="b30ff-241">Per un attributo numerico, il sistema mostrerà quale valore dell'attributo rientra nel percentile di ciascun cliente.</span><span class="sxs-lookup"><span data-stu-id="b30ff-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="b30ff-242">Scegli un **operatore** e un **valore**, quindi seleziona **Revisione**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="b30ff-243">Il sistema fornirà una **dimensione stimata del segmento**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="b30ff-244">Puoi scegliere se generare il segmento che hai definito o modificarlo prima per ottenere una dimensione del segmento diversa.</span><span class="sxs-lookup"><span data-stu-id="b30ff-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b30ff-245">![Nome e stima per un segmento rapido](media/quick-segment-name.png "Nome e stima per un segmento rapido")</span><span class="sxs-lookup"><span data-stu-id="b30ff-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="b30ff-246">Inserisci un **nome** per il segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="b30ff-247">Se lo desideri, inserisci un **nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="b30ff-248">Seleziona **Salva** per creare il segmento.</span><span class="sxs-lookup"><span data-stu-id="b30ff-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="b30ff-249">Al termine dell'elaborazione del segmento, puoi visualizzarlo come qualsiasi altro segmento che hai creato.</span><span class="sxs-lookup"><span data-stu-id="b30ff-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="b30ff-250">Per i seguenti scenari, si consiglia di utilizzare il generatore di segmenti anziché la funzionalità dei segmenti consigliati:</span><span class="sxs-lookup"><span data-stu-id="b30ff-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="b30ff-251">Creazione di segmenti con filtri su campi di categoria in cui l'operatore è diverso dall'operatore **Is**</span><span class="sxs-lookup"><span data-stu-id="b30ff-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="b30ff-252">Creazione di segmenti con filtri su campi numerici in cui l'operatore è diverso dagli operatori **Between**, **Greater than** e **Less than**</span><span class="sxs-lookup"><span data-stu-id="b30ff-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="b30ff-253">Creazione di segmenti con filtri nei campi del tipo di data</span><span class="sxs-lookup"><span data-stu-id="b30ff-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="b30ff-254">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b30ff-254">Next steps</span></span>

<span data-ttu-id="b30ff-255">[Esporta un segmento](export-destinations.md) ed esplora [Scheda cliente](customer-card-add-in.md) e [Connettori](export-power-bi.md) per ottenere informazioni dettagliate a livello di cliente.</span><span class="sxs-lookup"><span data-stu-id="b30ff-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]