---
title: Segmenti nelle informazioni dettagliate sul gruppo di destinatari
description: Panoramica sui segmenti e su come crearli e gestirli.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306262"
---
# <a name="segments-overview"></a><span data-ttu-id="3f3e7-103">Panoramica dei segmenti</span><span class="sxs-lookup"><span data-stu-id="3f3e7-103">Segments overview</span></span>

<span data-ttu-id="3f3e7-104">I segmenti ti consentono di raggruppare i clienti in base ad attributi demografici, transazionali o comportamentali.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="3f3e7-105">Puoi utilizzare i segmenti per indirizzare campagne promozionali, attività di vendita e azioni di assistenza clienti per raggiungere i tuoi obiettivi aziendali.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="3f3e7-106">I profili del cliente che corrispondono ai filtri di una definizione di segmento sono indicati come *membri* di un segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="3f3e7-107">Si applicano alcuni [limiti di servizio](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="3f3e7-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="3f3e7-108">Creare un nuovo segmento</span><span class="sxs-lookup"><span data-stu-id="3f3e7-108">Create a new segment</span></span>

<span data-ttu-id="3f3e7-109">Un nuovo segmento può essere creato in modi diversi:</span><span class="sxs-lookup"><span data-stu-id="3f3e7-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="3f3e7-110">Segmento complesso con generatore di segmenti: [segmento vuoto](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="3f3e7-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="3f3e7-111">Segmenti semplici con un operatore: [segmento veloce](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="3f3e7-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="3f3e7-112">Modo basato sull'intelligenza artificiale per trovare clienti simili: [clienti simili](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="3f3e7-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="3f3e7-113">Suggerimenti basati sull'intelligenza artificiale per misure o attributi: [segmenti suggeriti per migliorare le misure](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="3f3e7-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="3f3e7-114">Suggerimenti basati sulle attività: [segmenti suggeriti in base all'attività del cliente](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="3f3e7-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="3f3e7-115">Gestire segmenti esistenti</span><span class="sxs-lookup"><span data-stu-id="3f3e7-115">Manage existing segments</span></span>

<span data-ttu-id="3f3e7-116">Vai alla pagina **Segmenti** per visualizzare tutti i segmenti salvati e gestirli.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="3f3e7-117">Ogni segmento è rappresentato da una riga che include informazioni aggiuntive sul segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento selezionato con elenco a discesa delle opzioni e opzioni disponibili.":::

<span data-ttu-id="3f3e7-119">Quando selezioni un segmento sono disponibili le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="3f3e7-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="3f3e7-120">**Visualizza** i dettagli del segmento, inclusa la tendenza del conteggio dei membri, un'anteprima dei membri del segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="3f3e7-121">**Modifica** il segmento per modificarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="3f3e7-122">**Crea duplicato** di un segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="3f3e7-123">Puoi scegliere di modificare subito le proprietà o semplicemente salvare il duplicato.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="3f3e7-124">**Aggiorna** il segmento per includere gli ultimi dati.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="3f3e7-125">**Attiva** o **Disattiva** il segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="3f3e7-126">I segmenti hanno due possibili stati: attivo o inattivo.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="3f3e7-127">Questi stati sono utili quando si modifica un segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="3f3e7-128">Per i segmenti inattivi, la definizione del segmento esiste, ma non contiene ancora alcun cliente.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="3f3e7-129">Quando attivi un segmento, il suo stato cambia da "inattivo" ad "attivo" e inizia a cercare i clienti che corrispondono alla definizione del segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="3f3e7-130">Se un [aggiornamento pianificato](system.md#schedule-tab) è configurato, i segmenti inattivi hanno **Stato** elencato come **Ignorato**, a indicare che non è stato nemmeno tentato un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="3f3e7-131">Quando un segmento inattivo viene attivato, verrà aggiornato e incluso negli aggiornamenti pianificati.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="3f3e7-132">In alternativa, puoi utilizzare la funzionalità **Pianifica più tardi** nel menu a discesa **Attiva/Disattiva** per specificare una data e un'ora future per l'attivazione e la disattivazione di un particolare segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="3f3e7-133">**Rinomina** il segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-133">**Rename** the segment.</span></span>
- <span data-ttu-id="3f3e7-134">**Scarica** l'elenco dei membri in un file .CSV.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="3f3e7-135">**Gestisci esportazioni** per vedere i segmenti relativi alle esportazioni e gestirli.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="3f3e7-136">Altre informazioni sulle esportazioni.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="3f3e7-137">**Elimina** il segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="3f3e7-138">Aggiornare i segmenti</span><span class="sxs-lookup"><span data-stu-id="3f3e7-138">Refresh segments</span></span>

<span data-ttu-id="3f3e7-139">Puoi aggiornare tutti i segmenti contemporaneamente selezionando **Aggiorna tutto** nella pagina **Segmenti** oppure puoi aggiornare uno o più segmenti quando li selezioni e scegli **Aggiorna** dalle opzioni.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="3f3e7-140">In alternativa, puoi configurare un aggiornamento ricorrente in **Amministratore** > **Sistema** > **Pianifica**.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="3f3e7-141">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3f3e7-142">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3f3e7-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3f3e7-143">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3f3e7-144">Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="3f3e7-145">Esportare segmenti</span><span class="sxs-lookup"><span data-stu-id="3f3e7-145">Export segments</span></span>

<span data-ttu-id="3f3e7-146">Puoi esportare un segmento dalla pagina dei segmenti o dalla [pagina delle esportazioni](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3f3e7-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="3f3e7-147">Vai alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="3f3e7-148">Seleziona **Mostra più [...]** per il segmento che desideri esportare.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="3f3e7-149">Seleziona **Gestisci esportazioni** dall'elenco a discesa delle azioni.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="3f3e7-150">La pagina **Esportazioni (anteprima) per segmento** si apre.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="3f3e7-151">Puoi vedere tutte le esportazioni configurate raggruppate per esportazioni che contengono il segmento corrente o non lo contengono.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="3f3e7-152">Per aggiungere il segmento selezionato a un'esportazione, seleziona l'esportazione nell'elenco e seleziona **Aggiungi segmento**.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="3f3e7-153">Per creare una nuova esportazione con il segmento selezionato, seleziona **Aggiungi esportazione**.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="3f3e7-154">Per ulteriori informazioni sulla creazione di esportazioni, vedi [Configura una nuova esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3f3e7-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3f3e7-155">Seleziona **Indietro** per tornare alla pagina principale dei segmenti.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="3f3e7-156">Visualizzare la cronologia di elaborazione e i membri del segmento</span><span class="sxs-lookup"><span data-stu-id="3f3e7-156">View processing history and segment members</span></span>

<span data-ttu-id="3f3e7-157">Puoi visualizzare i dati consolidati di un segmento esaminandone i dettagli.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="3f3e7-158">Nella pagina **Segmenti** seleziona il segmento da esaminare.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="3f3e7-159">La parte superiore della pagina include un grafo di tendenza che visualizza le modifiche nel numero di membri.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="3f3e7-160">Passa il mouse sopra i punti dati per vedere il numero di membri a una data specifica.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="3f3e7-161">Puoi aggiornare l'intervallo di tempo della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3f3e7-162">![Intervallo di tempo segmento](media/segment-time-range.png "Intervallo di tempo segmento")</span><span class="sxs-lookup"><span data-stu-id="3f3e7-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="3f3e7-163">La parte inferiore contiene un elenco dei membri del segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="3f3e7-164">I campi che compaiono in questo elenco si basano sugli attributi delle entità del segmento.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="3f3e7-165">L'elenco è un'anteprima dei membri del segmento corrispondenti e mostra i primi 100 record del segmento in modo da poterlo valutare rapidamente e rivederne le definizioni se necessario.</span><span class="sxs-lookup"><span data-stu-id="3f3e7-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="3f3e7-166">Per vedere tutti i record corrispondenti, è necessario [esportare il segmento](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3f3e7-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
