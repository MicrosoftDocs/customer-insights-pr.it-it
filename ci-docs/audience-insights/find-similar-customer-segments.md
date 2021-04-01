---
title: Trovare clienti simili con l'intelligenza artificiale
description: Trova segmenti di clienti simili con l'intelligenza artificiale.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596780"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="cc276-103">Clienti simili (anteprima)</span><span class="sxs-lookup"><span data-stu-id="cc276-103">Similar Customers (preview)</span></span>

<span data-ttu-id="cc276-104">Questa funzione ti consente di trovare clienti simili nella tua base di clienti usando l'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="cc276-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="cc276-105">Devi avere almeno un segmento creato per utilizzare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="cc276-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="cc276-106">L'espansione dei criteri di un segmento esistente consente di trovare clienti simili a quel segmento.</span><span class="sxs-lookup"><span data-stu-id="cc276-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="cc276-107">*Trova clienti simili* utilizza mezzi automatizzati per valutare i dati e fare previsioni basate sui dati e quindi può essere utilizzato come metodo di profiling, in quanto il termine è definito dal Regolamento generale sulla protezione dei dati ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="cc276-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="cc276-108">L'uso da parte del cliente di questa funzionalità per elaborare i dati può essere soggetto al GDPR o ad altre leggi o normative.</span><span class="sxs-lookup"><span data-stu-id="cc276-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="cc276-109">Devi assicurarti che il tuo utilizzo di Dynamics 365 Customer Insights, comprese le previsioni, sia conforme a tutte le leggi e le norme applicabili, comprese le leggi relative alla privacy, ai dati personali, ai dati biometrici, alla protezione dei dati e alla riservatezza delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="cc276-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="cc276-110">Trovare clienti simili</span><span class="sxs-lookup"><span data-stu-id="cc276-110">Finding similar customers</span></span>

1. <span data-ttu-id="cc276-111">In Audience Insights, vai a **Segmenti** e seleziona il segmento su cui desideri basare il nuovo segmento.</span><span class="sxs-lookup"><span data-stu-id="cc276-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="cc276-112">Questo è il tuo *segmento di origine*.</span><span class="sxs-lookup"><span data-stu-id="cc276-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="cc276-113">Nella barra delle azioni, seleziona **Trova clienti simili**.</span><span class="sxs-lookup"><span data-stu-id="cc276-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="cc276-114">Esamina il nome suggerito per il tuo nuovo segmento e modificalo se necessario.</span><span class="sxs-lookup"><span data-stu-id="cc276-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="cc276-115">Rivedi i campi che definiscono il tuo nuovo segmento.</span><span class="sxs-lookup"><span data-stu-id="cc276-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="cc276-116">Questi campi definiscono la base su cui il sistema proverà a trovare clienti simili al tuo segmento di origine.</span><span class="sxs-lookup"><span data-stu-id="cc276-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="cc276-117">Il sistema selezionerà i campi consigliati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cc276-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="cc276-118">I campi che possono ridurre significativamente le prestazioni del modello vengono automaticamente esclusi:</span><span class="sxs-lookup"><span data-stu-id="cc276-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="cc276-119">Campi con i seguenti tipi di dati: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="cc276-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="cc276-120">Campi con una cardinalità (il numero di elementi in un campo) inferiore a 2 o superiore a 30</span><span class="sxs-lookup"><span data-stu-id="cc276-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="cc276-121">Scegli se vuoi includere **Tutti i clienti** o solo i clienti di un **Segmento specifico esistente** nel tuo nuovo segmento.</span><span class="sxs-lookup"><span data-stu-id="cc276-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="cc276-122">Escludi i clienti nel segmento di origine selezionando la casella di controllo **Escludi tutti nel segmento di origine**.</span><span class="sxs-lookup"><span data-stu-id="cc276-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="cc276-123">Per impostazione predefinita, il sistema suggerisce di includere solo il 20% della dimensione destinatari di destinazione nell'output.</span><span class="sxs-lookup"><span data-stu-id="cc276-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="cc276-124">Modifica questa soglia secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="cc276-124">Edit this threshold as needed.</span></span> <span data-ttu-id="cc276-125">Aumentando la soglia si ridurrà la precisione.</span><span class="sxs-lookup"><span data-stu-id="cc276-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="cc276-126">Seleziona **Esegui** nella parte inferiore della pagina per avviare un'attività di classificazione binaria (un metodo di apprendimento automatico) che analizza il set di dati.</span><span class="sxs-lookup"><span data-stu-id="cc276-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="cc276-127">Visualizzare il segmento simile</span><span class="sxs-lookup"><span data-stu-id="cc276-127">View the similar segment</span></span>

<span data-ttu-id="cc276-128">Dopo aver elaborato il segmento simile, troverai il nuovo segmento elencato nella pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="cc276-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cc276-129">![Segmento di clienti simili](media/expanded-segment.png "Segmento di clienti simili")</span><span class="sxs-lookup"><span data-stu-id="cc276-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="cc276-130">Seleziona **Visualizza** nella barra delle azioni per aprire i dettagli del segmento.</span><span class="sxs-lookup"><span data-stu-id="cc276-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="cc276-131">Questa visualizzazione contiene informazioni sulla distribuzione dei risultati attraverso [punteggi di somiglianza](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="cc276-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="cc276-132">Troverai anche i valori del punteggio di somiglianza in **Anteprima dei membri del segmento**.</span><span class="sxs-lookup"><span data-stu-id="cc276-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="cc276-133">Usare l'output di un segmento simile</span><span class="sxs-lookup"><span data-stu-id="cc276-133">Use the output of a similar segment</span></span>

<span data-ttu-id="cc276-134">Puoi [utilizzare l'output di un segmento simile](segments.md) come fai con altri segmenti.</span><span class="sxs-lookup"><span data-stu-id="cc276-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="cc276-135">Ad esempio, esporta il segmento o crea una misura.</span><span class="sxs-lookup"><span data-stu-id="cc276-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="cc276-136">Aggiornare e modificare un segmento simile</span><span class="sxs-lookup"><span data-stu-id="cc276-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="cc276-137">Per aggiornare un segmento simile, selezionalo nella pagina **Segmenti** e seleziona **Aggiorna** nella barra delle azioni.</span><span class="sxs-lookup"><span data-stu-id="cc276-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="cc276-138">La modifica di un segmento simile rielaborerà i tuoi dati.</span><span class="sxs-lookup"><span data-stu-id="cc276-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="cc276-139">Il segmento creato in precedenza viene aggiornato con i dati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="cc276-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="cc276-140">Per modificare un segmento simile, selezionalo nella pagina **Segmenti** e seleziona **Modifica** nella barra delle azioni.</span><span class="sxs-lookup"><span data-stu-id="cc276-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="cc276-141">Applica le modifiche e seleziona **Esegui** per iniziare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="cc276-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="cc276-142">Eliminare un segmento simile</span><span class="sxs-lookup"><span data-stu-id="cc276-142">Delete a similar segment</span></span>

<span data-ttu-id="cc276-143">Seleziona il segmento nella pagina **Segmenti** e seleziona **Elimina** nella barra delle azioni.</span><span class="sxs-lookup"><span data-stu-id="cc276-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="cc276-144">Quindi, conferma l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="cc276-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="cc276-145">Informazioni sui punteggi di somiglianza</span><span class="sxs-lookup"><span data-stu-id="cc276-145">About similarity scores</span></span>

<span data-ttu-id="cc276-146">La classificazione binaria del modello apprendimento automatico assegna un punteggio ai clienti del segmento simile.</span><span class="sxs-lookup"><span data-stu-id="cc276-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="cc276-147">Il punteggio si basa sulla somiglianza con i clienti nel segmento di origine.</span><span class="sxs-lookup"><span data-stu-id="cc276-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="cc276-148">I punteggi di somiglianza inferiori a 0,55 sono i clienti classificati dal sistema come *non simili* ai clienti nel segmento di origine</span><span class="sxs-lookup"><span data-stu-id="cc276-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="cc276-149">I punteggi di somiglianza tra 0,55 e 0,7 sono classificati come *in qualche modo simili*</span><span class="sxs-lookup"><span data-stu-id="cc276-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="cc276-150">I punteggi di somiglianza tra 0,7 e 0,85 sono classificati come *simili*</span><span class="sxs-lookup"><span data-stu-id="cc276-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="cc276-151">I punteggi di somiglianza tra 0,85 e 1 sono i clienti classificati dal sistema come *molto simili*</span><span class="sxs-lookup"><span data-stu-id="cc276-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="cc276-152">I clienti con punteggi di somiglianza inferiori a 0,4 non sono inclusi nell'output del modello.</span><span class="sxs-lookup"><span data-stu-id="cc276-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="cc276-153">Il sistema non li considera abbastanza simili al segmento di origine.</span><span class="sxs-lookup"><span data-stu-id="cc276-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]