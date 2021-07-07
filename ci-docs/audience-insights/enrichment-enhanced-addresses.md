---
title: Arricchimento migliorato dell'indirizzo
description: Arricchisci e normalizza le informazioni sugli indirizzi dei profili dei clienti con i modelli Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305437"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="299e6-103">Arricchimento dei profili dei clienti con indirizzi avanzati</span><span class="sxs-lookup"><span data-stu-id="299e6-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="299e6-104">Gli indirizzi nei tuoi dati possono essere non strutturati, incompleti o errati.</span><span class="sxs-lookup"><span data-stu-id="299e6-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="299e6-105">Usa i modelli di Microsoft per normalizzare e arricchire i tuoi indirizzi nel [formato Common Data Model](/common-data-model/schema/core/applicationcommon/address) per una migliore precisione e informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="299e6-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="299e6-106">Come migliorare gli indirizzi</span><span class="sxs-lookup"><span data-stu-id="299e6-106">How we enhance addresses</span></span>

<span data-ttu-id="299e6-107">Il nostro modello passa attraverso un processo in due fasi per migliorare un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="299e6-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="299e6-108">Innanzitutto, analizza l'indirizzo per identificare i suoi componenti e li inserisce in un formato strutturato.</span><span class="sxs-lookup"><span data-stu-id="299e6-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="299e6-109">Quindi, utilizziamo l'intelligenza artificiale per correggere, completare e standardizzare i valori nell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="299e6-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="299e6-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="299e6-110">Example</span></span>

<span data-ttu-id="299e6-111">Le informazioni sull'indirizzo potrebbero essere in un formato non standard e contenere errori di ortografia.</span><span class="sxs-lookup"><span data-stu-id="299e6-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="299e6-112">Il modello può risolvere questi problemi e creare indirizzi coerenti nei profili dei clienti unificati.</span><span class="sxs-lookup"><span data-stu-id="299e6-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="299e6-113">Limiti</span><span class="sxs-lookup"><span data-stu-id="299e6-113">Limitations</span></span>

<span data-ttu-id="299e6-114">Gli indirizzi avanzati funzionano solo con i valori già presenti nei dati degli indirizzi inseriti.</span><span class="sxs-lookup"><span data-stu-id="299e6-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="299e6-115">Il modello non:</span><span class="sxs-lookup"><span data-stu-id="299e6-115">The model doesn't:</span></span> 

1. <span data-ttu-id="299e6-116">Verifica se l'indirizzo è un indirizzo valido.</span><span class="sxs-lookup"><span data-stu-id="299e6-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="299e6-117">Verifica se uno qualsiasi dei valori, come codici postali o nomi di strade, è valido.</span><span class="sxs-lookup"><span data-stu-id="299e6-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="299e6-118">Cambia i valori che non riconosce.</span><span class="sxs-lookup"><span data-stu-id="299e6-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="299e6-119">Il modello utilizza tecniche basate sull'apprendimento automatico per migliorare gli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="299e6-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="299e6-120">Sebbene applichiamo una soglia di confidenza elevata per quando il modello modifica un valore di input, come con qualsiasi modello basato sull'apprendimento automatico, l'accuratezza del 100% non è garantita.</span><span class="sxs-lookup"><span data-stu-id="299e6-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="299e6-121">Paesi o aree geografiche supportati</span><span class="sxs-lookup"><span data-stu-id="299e6-121">Supported countries or regions</span></span>

<span data-ttu-id="299e6-122">Attualmente supportiamo indirizzi di arricchimento in questi paesi o aree geografiche:</span><span class="sxs-lookup"><span data-stu-id="299e6-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="299e6-123">Australia</span><span class="sxs-lookup"><span data-stu-id="299e6-123">Australia</span></span>
- <span data-ttu-id="299e6-124">Canada</span><span class="sxs-lookup"><span data-stu-id="299e6-124">Canada</span></span>
- <span data-ttu-id="299e6-125">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="299e6-125">United Kingdom</span></span>
- <span data-ttu-id="299e6-126">Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="299e6-126">United States</span></span>

<span data-ttu-id="299e6-127">Gli indirizzi devono contenere un valore di paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="299e6-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="299e6-128">Non elaboriamo gli indirizzi per paesi o aree geografiche non supportati e gli indirizzi per cui non è fornito alcun paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="299e6-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="299e6-129">Configurare l'arricchimento</span><span class="sxs-lookup"><span data-stu-id="299e6-129">Configure the enrichment</span></span>

1. <span data-ttu-id="299e6-130">Vai a **Dati** > **Arricchimento**.</span><span class="sxs-lookup"><span data-stu-id="299e6-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="299e6-131">Seleziona **Arricchisci i miei dati** nel riquadro **Indirizzi avanzati**.</span><span class="sxs-lookup"><span data-stu-id="299e6-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Screenshot del riquadro Indirizzi avanzati.":::

1. <span data-ttu-id="299e6-133">Seleziona il **set di dati del cliente** e scegli l'entità contenente gli indirizzi che vuoi arricchire.</span><span class="sxs-lookup"><span data-stu-id="299e6-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="299e6-134">Puoi selezionare l'entità *Cliente* per arricchire gli indirizzi in tutti i profili dei clienti o selezionare un'entità segmento per arricchire gli indirizzi solo nei profili dei clienti contenuti in quel segmento.</span><span class="sxs-lookup"><span data-stu-id="299e6-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="299e6-135">Seleziona il formato degli indirizzi nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="299e6-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="299e6-136">Scegli **Indirizzo ad attributo singolo** se gli indirizzi nei tuoi dati utilizzano un unico campo.</span><span class="sxs-lookup"><span data-stu-id="299e6-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="299e6-137">Scegli **Indirizzo a più attributi** se gli indirizzi nei tuoi dati utilizzano più di un campo dati.</span><span class="sxs-lookup"><span data-stu-id="299e6-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="299e6-138">Il valore di paese/area geografica è obbligatorio sia negli indirizzi con attributo singolo che con più attributi.</span><span class="sxs-lookup"><span data-stu-id="299e6-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="299e6-139">Gli indirizzi che non contengono valori di paese/area geografica validi o supportati non verranno arricchiti.</span><span class="sxs-lookup"><span data-stu-id="299e6-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="299e6-140">Mappa i campi dell'indirizzo dalla tua entità cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="299e6-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Pagina di mappatura dei campi degli indirizzi migliorata.":::

1. <span data-ttu-id="299e6-142">Seleziona **Avanti** per completare il mapping del campo.</span><span class="sxs-lookup"><span data-stu-id="299e6-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="299e6-143">Fornisci un nome per l'arricchimento e l'entità di output.</span><span class="sxs-lookup"><span data-stu-id="299e6-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="299e6-144">Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.</span><span class="sxs-lookup"><span data-stu-id="299e6-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="299e6-145">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="299e6-145">Enrichment results</span></span>

<span data-ttu-id="299e6-146">Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="299e6-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="299e6-147">Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="299e6-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="299e6-148">Il tempo di elaborazione dipende dalle dimensioni dei dati del cliente.</span><span class="sxs-lookup"><span data-stu-id="299e6-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="299e6-149">Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**.</span><span class="sxs-lookup"><span data-stu-id="299e6-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="299e6-150">Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="299e6-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="299e6-151">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="299e6-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="299e6-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="299e6-152">Next steps</span></span>

<span data-ttu-id="299e6-153">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="299e6-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="299e6-154">Crea [segmenti](segments.md) e [misure](measures.md) e persino [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="299e6-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
