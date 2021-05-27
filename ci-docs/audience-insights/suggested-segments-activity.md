---
title: Segmenti suggeriti in base all'impegno.
description: Lascia che l'apprendimento automatico ti aiuti a trovare segmenti nuovi e interessanti in base all'impegno dei clienti.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034085"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="bb872-103">Segmenti suggeriti in base ai dati dell'impegno (anteprima)</span><span class="sxs-lookup"><span data-stu-id="bb872-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="bb872-104">Scopri i segmenti interessanti dei tuoi clienti in base ai dati dell'impegno dei clienti inseriti in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bb872-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="bb872-105">Esempi di dati dell'impegno sono transazioni, durata della chiamata di assistenza, acquisti o resi.</span><span class="sxs-lookup"><span data-stu-id="bb872-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="bb872-106">Per suggerire i segmenti, i dati dell'impegno vengono analizzati per recency, frequenza e valore monetario (o durata).</span><span class="sxs-lookup"><span data-stu-id="bb872-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="bb872-107">In alternativa, puoi generare i [segmenti suggeriti per migliorare una misura o capire meglio cosa influenza un attributo](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="bb872-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Scheda Segmenti suggeriti che mostra i suggerimenti per i segmenti basati sull'impegno e sull'attributo.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="bb872-109">Classificare i clienti per impegno</span><span class="sxs-lookup"><span data-stu-id="bb872-109">Categorize customers by activity</span></span>

<span data-ttu-id="bb872-110">Con i [dati dell'impegno](activities.md) disponibili in Customer Insights, possiamo generare suggerimenti che rappresentano i gruppi di clienti:</span><span class="sxs-lookup"><span data-stu-id="bb872-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="bb872-111">i clienti più attivi</span><span class="sxs-lookup"><span data-stu-id="bb872-111">most active customers</span></span> 
- <span data-ttu-id="bb872-112">i clienti che hanno effettuato il maggior numero di acquisti</span><span class="sxs-lookup"><span data-stu-id="bb872-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="bb872-113">i clienti che hanno generato il maggior numero di ricavi</span><span class="sxs-lookup"><span data-stu-id="bb872-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="bb872-114">i clienti che non sono stati attivi di recente</span><span class="sxs-lookup"><span data-stu-id="bb872-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="bb872-115">i clienti che interagiscono frequentemente con la tua azienda</span><span class="sxs-lookup"><span data-stu-id="bb872-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="bb872-116">Se hai un'attività di vendita al dettaglio, potresti scoprire quali clienti generano il maggior numero di ricavi e premiarli con un coupon.</span><span class="sxs-lookup"><span data-stu-id="bb872-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="bb872-117">Oppure puoi identificare i clienti occasionali e offrire loro di partecipare a un programma a premi in modo che visitino la tua attività più spesso.</span><span class="sxs-lookup"><span data-stu-id="bb872-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="bb872-118">Se operi nel settore sanitario che fornisce assistenza sanitaria pubblica e il tuo obiettivo è ridurre al minimo le spese per i singoli pazienti.</span><span class="sxs-lookup"><span data-stu-id="bb872-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="bb872-119">Un modo per farlo potrebbe essere quello di ridurre le visite ricorrenti fornendo la migliore assistenza possibile nel minor numero di visite possibile.</span><span class="sxs-lookup"><span data-stu-id="bb872-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="bb872-120">In questo caso, l'obiettivo è mantenere bassa la frequenza delle visite e ridurre al minimo i costi ricorrenti per i pazienti.</span><span class="sxs-lookup"><span data-stu-id="bb872-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="bb872-121">Oppure è possibile identificare segmenti di pazienti che hanno appuntamenti frequenti e costi ricorrenti elevati e analizzare questi casi per migliorare il trattamento dell'individuo.</span><span class="sxs-lookup"><span data-stu-id="bb872-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="bb872-122">Dati obbligatori</span><span class="sxs-lookup"><span data-stu-id="bb872-122">Required data</span></span>

<span data-ttu-id="bb872-123">I suggerimenti vengono generati in base ai dati di input selezionati.</span><span class="sxs-lookup"><span data-stu-id="bb872-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="bb872-124">Profili dei clienti: tutti i clienti o membri di un segmento specifico.</span><span class="sxs-lookup"><span data-stu-id="bb872-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="bb872-125">Periodo di tempo: il mese scorso, l'anno scorso o qualsiasi intervallo di tempo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bb872-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="bb872-126">Tipo di impegno: acquisti, transazioni al dettaglio, transazioni online, casi di assistenza clienti, abbonamenti e così via.</span><span class="sxs-lookup"><span data-stu-id="bb872-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="bb872-127">Entità in Customer Insights che contiene i dati dell'attività: l'entità UnifiedActivity o l'entità per un impegno specifico.</span><span class="sxs-lookup"><span data-stu-id="bb872-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="bb872-128">Dimensioni da includere: recency, frequenza o dimensione monetaria, a seconda dei requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="bb872-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="bb872-129">Generare segmenti suggeriti</span><span class="sxs-lookup"><span data-stu-id="bb872-129">Generate suggested segments</span></span>

1. <span data-ttu-id="bb872-130">Vai a **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="bb872-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="bb872-131">Seleziona la scheda **Suggerimenti (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="bb872-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="bb872-132">Seleziona **Trova nuovi suggerimenti** e scegli **Visualizza o prevedi il comportamento del cliente**.</span><span class="sxs-lookup"><span data-stu-id="bb872-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="bb872-133">Seleziona **Avvia** per eseguire l'esperienza guidata.</span><span class="sxs-lookup"><span data-stu-id="bb872-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primo passaggio della configurazione guidata per un segmento suggerito in base all'impegno.":::

1. <span data-ttu-id="bb872-135">Fornisci i dati di input richiesti e seleziona **Avanti** per procedere.</span><span class="sxs-lookup"><span data-stu-id="bb872-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="bb872-136">Scegli i clienti: includi tutti i clienti o un segmento specifico.</span><span class="sxs-lookup"><span data-stu-id="bb872-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="bb872-137">Scegli impegno: seleziona il tipo di impegno e le entità che descrivono l'impegno.</span><span class="sxs-lookup"><span data-stu-id="bb872-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="bb872-138">Preferenze: imposta il periodo di tempo da considerare, i fattori per i suggerimenti e mappa gli attributi.</span><span class="sxs-lookup"><span data-stu-id="bb872-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="bb872-139">Rivedi il tuo input e seleziona **Esegui** per eseguire il modello e generare suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="bb872-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="bb872-140">A seconda del numero di profili dei clienti e delle attività selezionate, il completamento può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="bb872-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="bb872-141">Dopo aver generato i suggerimenti, puoi filtrarli in base alla dimensione o al valore che ti interessa di più.</span><span class="sxs-lookup"><span data-stu-id="bb872-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="bb872-142">Visualizzare i dettagli di un segmento suggerito</span><span class="sxs-lookup"><span data-stu-id="bb872-142">View details of a suggested segment</span></span>

<span data-ttu-id="bb872-143">Una volta generati i suggerimenti, li troverai elencati in **Segmenti** > **Suggerimenti (anteprima)** nella sezione **Suggerimenti basati su impegno**.</span><span class="sxs-lookup"><span data-stu-id="bb872-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Riquadro laterale espanso che mostra i dati dettagliati di un segmento suggerito.":::

<span data-ttu-id="bb872-145">Seleziona **Vedi suggerimento** su un segmento suggerito per visualizzare i dettagli di quel segmento.</span><span class="sxs-lookup"><span data-stu-id="bb872-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="bb872-146">Il riquadro laterale fornisce dettagli come l'estensione di ciascuna dimensione rispetto al gruppo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bb872-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="bb872-147">Evidenzia inoltre il numero di potenziali membri del segmento e la corrispondente percentuale del totale dei clienti.</span><span class="sxs-lookup"><span data-stu-id="bb872-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="bb872-148">Se desideri mantenere il suggerimento come segmento, seleziona **Crea segmento**.</span><span class="sxs-lookup"><span data-stu-id="bb872-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="bb872-149">Salvare un suggerimento come segmento</span><span class="sxs-lookup"><span data-stu-id="bb872-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="bb872-150">Vai a **Segmenti** > **Suggerimenti (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="bb872-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="bb872-151">Seleziona il segmento da salvare</span><span class="sxs-lookup"><span data-stu-id="bb872-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="bb872-152">Nel riquadro laterale seleziona **Crea segmento**.</span><span class="sxs-lookup"><span data-stu-id="bb872-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="bb872-153">Dopo aver salvato il segmento, verrà visualizzato nell'elenco dei segmenti nella scheda **Tutti i segmenti**. Ora può essere [aggiornato o eliminato come qualsiasi altro segmento](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bb872-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="bb872-154">Non puoi modificare i dettagli del segmento.</span><span class="sxs-lookup"><span data-stu-id="bb872-154">You can't edit the segment details.</span></span> <span data-ttu-id="bb872-155">Tuttavia, è possibile modificare i criteri di input per i suggerimenti e generare suggerimenti diversi.</span><span class="sxs-lookup"><span data-stu-id="bb872-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="bb872-156">Aggiornare o modificare una serie di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="bb872-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="bb872-157">Vai a **Segmenti** > **Suggerimenti (anteprima)** e cerca il segmento nella sezione **Suggerimenti basati su impegno**.</span><span class="sxs-lookup"><span data-stu-id="bb872-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="bb872-158">Seleziona **Aggiorna suggerimenti** per aggiornare i suggerimenti mantenendo gli attributi configurati.</span><span class="sxs-lookup"><span data-stu-id="bb872-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="bb872-159">Oppure seleziona **Modifica suggerimenti** per modificare gli attributi configurati.</span><span class="sxs-lookup"><span data-stu-id="bb872-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="bb872-160">Il sistema eseguirà nuovamente il processo, genererà suggerimenti di segmento in base ai dati più recenti e sostituirà i suggerimenti correnti.</span><span class="sxs-lookup"><span data-stu-id="bb872-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
