---
title: Informazioni dettagliate sui segmenti esistenti
description: Ottieni informazioni dettagliate sui segmenti esistenti per scoprire cosa li differenzia e cosa hanno in comune.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2856888d6ac64d5daabcc5a234f13bc6f88bb3df
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306079"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="845f4-103">Informazioni dettagliate sui segmenti (anteprima)</span><span class="sxs-lookup"><span data-stu-id="845f4-103">Segment insights (preview)</span></span>

<span data-ttu-id="845f4-104">Scopri ulteriori informazioni e informazioni dettagliate sui segmenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="845f4-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="845f4-105">Scopri cosa differenzia due segmenti o cosa hanno in comune.</span><span class="sxs-lookup"><span data-stu-id="845f4-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="845f4-106">Sovrapposizione segmenti</span><span class="sxs-lookup"><span data-stu-id="845f4-106">Segment overlap</span></span>

<span data-ttu-id="845f4-107">L'analisi di sovrapposizione dei segmenti mostra quanti e quali clienti sono comuni a due o più segmenti.</span><span class="sxs-lookup"><span data-stu-id="845f4-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="845f4-108">Ad esempio, come un segmento di clienti frequenti si sovrappone a un segmento che contiene clienti che sono soddisfatti del servizio o del prodotto.</span><span class="sxs-lookup"><span data-stu-id="845f4-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="845f4-109">Puoi anche analizzare come cambia la sovrapposizione per attributi specifici.</span><span class="sxs-lookup"><span data-stu-id="845f4-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="845f4-110">Eseguire un'analisi di sovrapposizione</span><span class="sxs-lookup"><span data-stu-id="845f4-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="845f4-111">Vai a **Segmenti** e seleziona la scheda **Informazioni dettagliate (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="845f4-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="845f4-112">Seleziona **Nuovo** e scegli l'opzione **Sovrapposizione** nel riquadro **Scegli tipo di informazioni dettagliate**.</span><span class="sxs-lookup"><span data-stu-id="845f4-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="845f4-113">Scegli i segmenti di interesse e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="845f4-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="845f4-114">Facoltativamente, scegli uno o più campi di interesse per analizzare le sovrapposizioni per ogni possibile valore del campo e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="845f4-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="845f4-115">Fornisci un nome per l'analisi di sovrapposizione, un nome visualizzato opzionale e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="845f4-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="845f4-116">Seleziona **Salva** per iniziare l'analisi.</span><span class="sxs-lookup"><span data-stu-id="845f4-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="845f4-117">L'analisi di sovrapposizione è pronta quando lo stato passa da Aggiornamento in corso a Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="845f4-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="845f4-118">Visualizzare e ottimizzare un'analisi di sovrapposizione</span><span class="sxs-lookup"><span data-stu-id="845f4-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="845f4-119">Dopo aver completato l'analisi, trova i dettagli su questa informazione dettagliata in **Segmenti** > **Informazioni dettagliate (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="845f4-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Dettagli delle informazioni sulla sovrapposizione del segmento":::

<span data-ttu-id="845f4-121">Seleziona una informazione per vedere i risultati dell'analisi:</span><span class="sxs-lookup"><span data-stu-id="845f4-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="845f4-122">Il numero di membri che si sovrappongono ai segmenti selezionati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="845f4-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="845f4-123">Il numero di membri inclusi in uno dei segmenti ma non nel resto dei segmenti.</span><span class="sxs-lookup"><span data-stu-id="845f4-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="845f4-124">Se hai selezionato i campi durante la configurazione dell'analisi di sovrapposizione, li troverai nelle schede corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="845f4-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="845f4-125">Puoi utilizzare il menu a discesa del filtro per selezionare qualsiasi livello di attributo di interesse e la tabella in basso mostrerà i dati corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="845f4-125">You can use the filter dropdown to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="845f4-126">Differenziatori segmento</span><span class="sxs-lookup"><span data-stu-id="845f4-126">Segment differentiators</span></span>

<span data-ttu-id="845f4-127">I differenziatori di segmento ti aiutano a scoprire cosa differenzia un segmento dal resto dei tuoi clienti o da un altro segmento.</span><span class="sxs-lookup"><span data-stu-id="845f4-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="845f4-128">Devi solo selezionare un segmento e il sistema identificherà gli attributi del profilo e le misure che distinguono il segmento selezionato.</span><span class="sxs-lookup"><span data-stu-id="845f4-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="845f4-129">Eseguire l'analisi del differenziatore</span><span class="sxs-lookup"><span data-stu-id="845f4-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="845f4-130">Vai a **Segmenti** e seleziona la scheda **Informazioni dettagliate (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="845f4-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="845f4-131">Seleziona **Nuovo** e scegli l'opzione **Sovrapposizione** nel riquadro **Scegli tipo di informazioni dettagliate**.</span><span class="sxs-lookup"><span data-stu-id="845f4-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="845f4-132">Scegli il segmento che desideri analizzare come **Segmento primario** e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="845f4-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="845f4-133">Scegli **Tutti i clienti** o un **segmento secondario** con cui confrontare il segmento primario e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="845f4-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="845f4-134">Facoltativamente, scegli uno o più campi di interesse per attivare l'analisi su attributi specifici e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="845f4-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="845f4-135">Fornisci un nome per l'analisi di sovrapposizione, un nome visualizzato opzionale e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="845f4-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="845f4-136">Seleziona **Salva** per iniziare l'analisi.</span><span class="sxs-lookup"><span data-stu-id="845f4-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="845f4-137">L'analisi di sovrapposizione è pronta quando lo stato passa da Aggiornamento in corso a Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="845f4-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="845f4-138">Visualizzare e ottimizzare l'analisi dei differenziatori</span><span class="sxs-lookup"><span data-stu-id="845f4-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="845f4-139">Dopo aver completato l'analisi, trova i dettagli su questa informazione dettagliata in **Segmenti** > **Informazioni dettagliate (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="845f4-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Dettagli delle informazioni sul differenziatore del segmento":::

<span data-ttu-id="845f4-141">Seleziona una informazione per vedere i risultati dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="845f4-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="845f4-142">L'analisi del differenziatore include due schede.</span><span class="sxs-lookup"><span data-stu-id="845f4-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="845f4-143">La scheda **Attributi** elenca gli attributi del profilo considerati come differenziatori.</span><span class="sxs-lookup"><span data-stu-id="845f4-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="845f4-144">La scheda **Misure** elenca i differenziatori.</span><span class="sxs-lookup"><span data-stu-id="845f4-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="845f4-145">Ogni scheda include i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="845f4-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="845f4-146">Elenco classificato dei differenziatori, ordinato per punteggio di differenza.</span><span class="sxs-lookup"><span data-stu-id="845f4-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="845f4-147">Il **Punteggio di differenza** per ogni differenziatore.</span><span class="sxs-lookup"><span data-stu-id="845f4-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="845f4-148">Il punteggio differenza rappresenta il grado di differenza di un attributo tra due segmenti.</span><span class="sxs-lookup"><span data-stu-id="845f4-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="845f4-149">Maggiore è il punteggio di differenza, più gli attributi differiscono tra i due segmenti.</span><span class="sxs-lookup"><span data-stu-id="845f4-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="845f4-150">Seleziona un punteggio per aprire il riquadro **Punteggio di differenza** con le distribuzioni dei valori per quell'attributo.</span><span class="sxs-lookup"><span data-stu-id="845f4-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="845f4-151">Gestire le informazioni dettagliate del segmento</span><span class="sxs-lookup"><span data-stu-id="845f4-151">Manage segment insights</span></span>

<span data-ttu-id="845f4-152">Puoi utilizzare le seguenti opzioni nelle informazioni dettagliate dalla barra dei comandi:</span><span class="sxs-lookup"><span data-stu-id="845f4-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="845f4-153">**Indietro** per tornare all'elenco di informazioni dettagliate</span><span class="sxs-lookup"><span data-stu-id="845f4-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="845f4-154">**Aggiorna** per eseguire nuovamente l'analisi</span><span class="sxs-lookup"><span data-stu-id="845f4-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="845f4-155">**Elimina** per rimuovere le informazioni dettagliate</span><span class="sxs-lookup"><span data-stu-id="845f4-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]