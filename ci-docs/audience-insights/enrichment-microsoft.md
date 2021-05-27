---
title: Arricchire i profili dei clienti con i dati di Microsoft
description: Usa i dati proprietari di Microsoft per arricchire i dati dei tuoi clienti con affinità di marchio e interesse.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064896"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="76003-103">Arricchimento di profili cliente con le affinità relative al marchio e agli interessi (anteprima)</span><span class="sxs-lookup"><span data-stu-id="76003-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="76003-104">Usa i dati proprietari di Microsoft per arricchire i dati dei tuoi clienti con affinità di marchio e interesse.</span><span class="sxs-lookup"><span data-stu-id="76003-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="76003-105">Queste affinità sono determinate in base ai dati di persone con dati demografici simili ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="76003-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="76003-106">Queste informazioni ti consentono di comprendere e segmentare meglio i tuoi clienti in base alle loro affinità per specifici marchi e interessi.</span><span class="sxs-lookup"><span data-stu-id="76003-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="76003-107">In Audience Insights, vai a **Dati** > **Arricchimento** per [configurare e visualizzare gli arricchimenti](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="76003-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="76003-108">Per configurare l'arricchimento delle affinità del marchio, vai alla scheda **Individua** e seleziona **Arricchisci i miei dati** nel riquadro **Marchi**.</span><span class="sxs-lookup"><span data-stu-id="76003-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="76003-109">Per configurare l'arricchimento delle affinità degli interessi, vai alla scheda **Individua** e seleziona **Arricchisci i miei dati** nel riquadro **Interessi**.</span><span class="sxs-lookup"><span data-stu-id="76003-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="76003-110">![Riquadri Marchi e interessi](media/BrandsInterest-tile-Hub.png "Riquadri Marchi e interessi")</span><span class="sxs-lookup"><span data-stu-id="76003-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="76003-111">Come determiniamo le affinità</span><span class="sxs-lookup"><span data-stu-id="76003-111">How we determine affinities</span></span>

<span data-ttu-id="76003-112">Utilizziamo i dati della ricerca online di Microsoft per trovare affinità per marchi e interessi in vari segmenti demografici (definiti per età, sesso o posizione).</span><span class="sxs-lookup"><span data-stu-id="76003-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="76003-113">Il volume di ricerca online per un marchio o interesse determina quanta affinità un segmento demografico, rispetto ad altri segmenti, ha con quel marchio o interesse.</span><span class="sxs-lookup"><span data-stu-id="76003-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="76003-114">Livello e punteggio di affinità</span><span class="sxs-lookup"><span data-stu-id="76003-114">Affinity level and score</span></span>

<span data-ttu-id="76003-115">Per ogni profilo cliente arricchito forniamo due valori correlati: livello di affinità e punteggio di affinità.</span><span class="sxs-lookup"><span data-stu-id="76003-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="76003-116">Questi valori ti aiutano a determinare quanto sia forte l'affinità per il segmento demografico di quel profilo a un marchio o un interesse, rispetto ad altri segmenti demografici.</span><span class="sxs-lookup"><span data-stu-id="76003-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="76003-117">Il *livello di affinità* si compone di quattro livelli e il *punteggio di affinità* è calcolato su una scala di 100 punti mappata ai livelli di affinità.</span><span class="sxs-lookup"><span data-stu-id="76003-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="76003-118">Livello di affinità</span><span class="sxs-lookup"><span data-stu-id="76003-118">Affinity level</span></span> |<span data-ttu-id="76003-119">Punteggio di affinità</span><span class="sxs-lookup"><span data-stu-id="76003-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="76003-120">Molto alto</span><span class="sxs-lookup"><span data-stu-id="76003-120">Very high</span></span>     | <span data-ttu-id="76003-121">85-100</span><span class="sxs-lookup"><span data-stu-id="76003-121">85-100</span></span>       |
|<span data-ttu-id="76003-122">Alta</span><span class="sxs-lookup"><span data-stu-id="76003-122">High</span></span>     | <span data-ttu-id="76003-123">70-84</span><span class="sxs-lookup"><span data-stu-id="76003-123">70-84</span></span>        |
|<span data-ttu-id="76003-124">Medio</span><span class="sxs-lookup"><span data-stu-id="76003-124">Medium</span></span>     | <span data-ttu-id="76003-125">35-69</span><span class="sxs-lookup"><span data-stu-id="76003-125">35-69</span></span>        |
|<span data-ttu-id="76003-126">Bassa</span><span class="sxs-lookup"><span data-stu-id="76003-126">Low</span></span>     | <span data-ttu-id="76003-127">1-34</span><span class="sxs-lookup"><span data-stu-id="76003-127">1-34</span></span>        |

<span data-ttu-id="76003-128">A seconda della granularità che desideri per misurare l'affinità, puoi utilizzare il livello di affinità o il punteggio di affinità.</span><span class="sxs-lookup"><span data-stu-id="76003-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="76003-129">Il punteggio di affinità ti offre un controllo più preciso.</span><span class="sxs-lookup"><span data-stu-id="76003-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="76003-130">Paesi/aree geografiche supportati</span><span class="sxs-lookup"><span data-stu-id="76003-130">Supported countries/regions</span></span>

<span data-ttu-id="76003-131">Attualmente supportiamo le seguenti opzioni di paese/area geografica: Australia, Canada (inglese), Francia, Germania, Regno Unito o Stati Uniti (inglese).</span><span class="sxs-lookup"><span data-stu-id="76003-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="76003-132">Per selezionare un paese, apri **Arricchimento marchi** o **Arricchimento interessi** e seleziona **Cambia** accanto a **Paese**.</span><span class="sxs-lookup"><span data-stu-id="76003-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="76003-133">Nel riquadro **Impostazioni paese/area geografica**, scegli un'opzione e seleziona **Applica**.</span><span class="sxs-lookup"><span data-stu-id="76003-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="76003-134">Implicazioni relative alla selezione del paese</span><span class="sxs-lookup"><span data-stu-id="76003-134">Implications related to country selection</span></span>

- <span data-ttu-id="76003-135">Quando [scegli i tuoi marchi](#define-your-brands-or-interests), il sistema fornisce suggerimenti in base al paese o all'area geografica selezionati.</span><span class="sxs-lookup"><span data-stu-id="76003-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="76003-136">Quando [scegli un settore](#define-your-brands-or-interests), otterrai i marchi o gli interessi più pertinenti in base al paese o all'area geografica selezionati.</span><span class="sxs-lookup"><span data-stu-id="76003-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="76003-137">Quando [arricchisci i profili](#refresh-enrichment), arricchiremo tutti i profili dei clienti per i quali otteniamo i dati per i marchi e gli interessi selezionati.</span><span class="sxs-lookup"><span data-stu-id="76003-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="76003-138">Compresi i profili che non si trovano nel paese o nell'area geografica selezionata.</span><span class="sxs-lookup"><span data-stu-id="76003-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="76003-139">Ad esempio, se hai selezionato la Germania, arricchiremo i profili situati negli Stati Uniti se abbiamo dati disponibili per i marchi e gli interessi selezionati negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="76003-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="76003-140">Configurare l'arricchimento</span><span class="sxs-lookup"><span data-stu-id="76003-140">Configure Enrichment</span></span>

<span data-ttu-id="76003-141">Un'esperienza guidata ti aiuta nella configurazione degli arricchimenti.</span><span class="sxs-lookup"><span data-stu-id="76003-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="76003-142">Definisci i tuoi marchi o interessi</span><span class="sxs-lookup"><span data-stu-id="76003-142">Define your brands or interests</span></span>

<span data-ttu-id="76003-143">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76003-143">Select one of the following options:</span></span>

- <span data-ttu-id="76003-144">**Settore**: il sistema identifica i principali marchi o interessi rilevanti per il tuo settore e arricchisce i dati cliente con essi.</span><span class="sxs-lookup"><span data-stu-id="76003-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="76003-145">**Scegli il tuo**: seleziona fino a cinque voci dall'elenco di marchi o interessi più rilevanti per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="76003-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="76003-146">Per aggiungere un marchio o un interesse, immettilo nell'area di input per ottenere suggerimenti in base ai termini corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="76003-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="76003-147">Se non viene elencato un marchio o interesse che stai cercando, inviaci un feedback utilizzando il collegamento **Suggerisci**.</span><span class="sxs-lookup"><span data-stu-id="76003-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="76003-148">Rivedere le preferenze di arricchimento</span><span class="sxs-lookup"><span data-stu-id="76003-148">Review enrichment preferences</span></span>

<span data-ttu-id="76003-149">Rivedi le tue preferenze di arricchimento predefinite e aggiornale secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="76003-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Screenshot della finestra delle preferenze di arricchimento.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="76003-151">Selezionare l'entità da arricchire</span><span class="sxs-lookup"><span data-stu-id="76003-151">Select entity to enrich</span></span>

<span data-ttu-id="76003-152">Seleziona **Entità arricchita** e scegli il set di dati che desideri arricchire con i dati aziendali di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76003-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="76003-153">Puoi selezionare l'entità Cliente per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.</span><span class="sxs-lookup"><span data-stu-id="76003-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="76003-154">Esegui il mapping dei campi</span><span class="sxs-lookup"><span data-stu-id="76003-154">Map your fields</span></span>

<span data-ttu-id="76003-155">Mappa i campi dall'entità cliente unificata per definire il segmento demografico che desideri venga utilizzato per arricchire i tuoi dati cliente.</span><span class="sxs-lookup"><span data-stu-id="76003-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="76003-156">Mappa Paese/area geografica e almeno gli attributi Data di nascita o Sesso.</span><span class="sxs-lookup"><span data-stu-id="76003-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="76003-157">Inoltre, devi eseguire il mapping di almeno una città (e provincia) o un CAP.</span><span class="sxs-lookup"><span data-stu-id="76003-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="76003-158">Seleziona **Modifica** per definire la mappatura dei campi e al termine seleziona **Applica**.</span><span class="sxs-lookup"><span data-stu-id="76003-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="76003-159">Seleziona **Salva** per completare la mappatura dei campi.</span><span class="sxs-lookup"><span data-stu-id="76003-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="76003-160">Sono supportati i seguenti formati e valori, i valori non fanno distinzione tra maiuscole e minuscole:</span><span class="sxs-lookup"><span data-stu-id="76003-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="76003-161">**Data di nascita**: si consiglia di convertire la data di nascita nel tipo DateTime durante l'inserimento dati.</span><span class="sxs-lookup"><span data-stu-id="76003-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="76003-162">In alternativa, può essere una stringa nel formato "aaaa-MM-gg" o "aaaa-MM-ggTHH:mm:ssZ" [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).</span><span class="sxs-lookup"><span data-stu-id="76003-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="76003-163">**Sesso**: Maschio, Femmina, Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="76003-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="76003-164">**Codice postale**: codici postali a cinque cifre per gli Stati Uniti, codice postale standard per gli altri paesi</span><span class="sxs-lookup"><span data-stu-id="76003-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="76003-165">**Città**: nome della città in inglese</span><span class="sxs-lookup"><span data-stu-id="76003-165">**City**: City name in English</span></span>
- <span data-ttu-id="76003-166">**Stato/Provincia**: abbreviazione di due lettere per gli Stati Uniti e il Canada.</span><span class="sxs-lookup"><span data-stu-id="76003-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="76003-167">Abbreviazione di due o tre lettere per l'Australia.</span><span class="sxs-lookup"><span data-stu-id="76003-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="76003-168">Non applicabile per Francia, Germania o Regno Unito.</span><span class="sxs-lookup"><span data-stu-id="76003-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="76003-169">**Paese**:</span><span class="sxs-lookup"><span data-stu-id="76003-169">**Country/Region**:</span></span>

  - <span data-ttu-id="76003-170">US: Stati Uniti d'America, Stati Uniti, USA, US, America</span><span class="sxs-lookup"><span data-stu-id="76003-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="76003-171">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="76003-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="76003-172">GB: Regno Unito, UK, Gran Bretagna, GB, Regno Unito di Gran Bretagna e Irlanda del Nord, Regno Unito di Gran Bretagna</span><span class="sxs-lookup"><span data-stu-id="76003-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="76003-173">AU: Australia, AU, Commonwealth di Australia</span><span class="sxs-lookup"><span data-stu-id="76003-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="76003-174">FR: Francia, FR, Repubblica francese</span><span class="sxs-lookup"><span data-stu-id="76003-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="76003-175">DE: Germania, tedesco, Deutschland, Allemagne, DE, Repubblica Federale di Germania, Repubblica di Germania</span><span class="sxs-lookup"><span data-stu-id="76003-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="76003-176">Rivedere e dare un nome all'arricchimento</span><span class="sxs-lookup"><span data-stu-id="76003-176">Review and name the enrichment</span></span>

<span data-ttu-id="76003-177">Infine, puoi rivedere le informazioni e fornire un nome per l'arricchimento.</span><span class="sxs-lookup"><span data-stu-id="76003-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pagina di revisione e denominazione degli interessi.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="76003-179">Aggiornare l'arricchimento</span><span class="sxs-lookup"><span data-stu-id="76003-179">Refresh enrichment</span></span>

<span data-ttu-id="76003-180">Esegui l'arricchimento dopo aver configurato marchi, interessi e mappatura dei campi per i dati demografici.</span><span class="sxs-lookup"><span data-stu-id="76003-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="76003-181">Per avviare il processo, seleziona **Esegui** nella pagina di configurazione del marchio o degli interessi.</span><span class="sxs-lookup"><span data-stu-id="76003-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="76003-182">Inoltre, puoi consentire al sistema di eseguire automaticamente l'arricchimento come parte di un aggiornamento pianificato.</span><span class="sxs-lookup"><span data-stu-id="76003-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="76003-183">A seconda della dimensione dei dati cliente, potrebbero essere necessari alcuni minuti per completare l'esecuzione di un arricchimento.</span><span class="sxs-lookup"><span data-stu-id="76003-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="76003-184">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="76003-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="76003-185">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="76003-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="76003-186">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="76003-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="76003-187">Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="76003-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="76003-188">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="76003-188">Enrichment results</span></span>

<span data-ttu-id="76003-189">Dopo aver eseguito il processo di arricchimento, vai a **I miei arricchimenti** per rivedere il numero totale di clienti arricchiti e una suddivisione di marchi e interessi nei profili cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="76003-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Anteprima dei risultati dopo l'esecuzione del processo di arricchimento":::

<span data-ttu-id="76003-191">Rivedi i dati arricchiti selezionando **Visualizza dati arricchiti** nel grafico.</span><span class="sxs-lookup"><span data-stu-id="76003-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="76003-192">I dati arricchiti per i marchi vanno all'entità **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="76003-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="76003-193">I dati per gli interessi sono nell'entità **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="76003-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="76003-194">Troverai anche queste entità elencate nel gruppo **Arricchimento** in **Dati** > **Entità**.</span><span class="sxs-lookup"><span data-stu-id="76003-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="76003-195">Visualizzare i dati di arricchimento nella scheda cliente</span><span class="sxs-lookup"><span data-stu-id="76003-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="76003-196">Le affinità per marchi e interessi possono essere visualizzate anche nelle singole schede cliente.</span><span class="sxs-lookup"><span data-stu-id="76003-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="76003-197">Vai a **Clienti** e seleziona un profilo cliente.</span><span class="sxs-lookup"><span data-stu-id="76003-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="76003-198">Nella scheda cliente troverai i grafici per i marchi o gli interessi per i quali le persone nel profilo demografico del cliente hanno affinità.</span><span class="sxs-lookup"><span data-stu-id="76003-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Scheda cliente con dati arricchiti":::

## <a name="next-steps"></a><span data-ttu-id="76003-200">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="76003-200">Next steps</span></span>

<span data-ttu-id="76003-201">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="76003-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="76003-202">Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="76003-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
