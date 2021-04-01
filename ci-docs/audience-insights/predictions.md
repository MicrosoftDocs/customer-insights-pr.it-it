---
title: Completare i dati parziali con le previsioni
description: Utilizza le previsioni per riempire dati cliente incompleti.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595906"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="59c55-103">Completare i dati parziali con le previsioni</span><span class="sxs-lookup"><span data-stu-id="59c55-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="59c55-104">Le previsioni consentono di creare facilmente valori stimati che possono migliorare la comprensione di un cliente.</span><span class="sxs-lookup"><span data-stu-id="59c55-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="59c55-105">Nella pagina **Intelligenza** > **Predizioni**, puoi selezionare **Le mie previsioni** per visualizzare le previsioni che hai configurato in altre parti di Audience Insights e consentirti di personalizzarle ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="59c55-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="59c55-106">Non è possibile usare questa funzionalità se l'ambiente usa l'archiviazione di Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="59c55-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="59c55-107">La funzione di previsione utilizza strumenti automatici per valutare i dati e fare previsioni basate su tali dati, quindi può essere utilizzata come metodo di profiling, in base a come tale termine è definito dal Regolamento generale sulla protezione dei dati ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="59c55-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="59c55-108">L'uso da parte del cliente di questa funzionalità per elaborare i dati può essere soggetto al GDPR o ad altre leggi o normative.</span><span class="sxs-lookup"><span data-stu-id="59c55-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="59c55-109">Devi assicurarti che il tuo utilizzo di Dynamics 365 Customer Insights, comprese le previsioni, sia conforme a tutte le leggi e le norme applicabili, comprese le leggi relative alla privacy, ai dati personali, ai dati biometrici, alla protezione dei dati e alla riservatezza delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="59c55-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59c55-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="59c55-110">Prerequisites</span></span>

<span data-ttu-id="59c55-111">Prima che l'organizzazione possa utilizzare la funzionalità di previsioni, i prerequisiti seguenti devono essere soddisfatti:</span><span class="sxs-lookup"><span data-stu-id="59c55-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="59c55-112">La tua organizzazione ha un'istanza [configurata in Common Data Service](/ai-builder/build-model#prerequisites) ed è nella stessa organizzazione di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="59c55-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="59c55-113">L'ambiente è associato alla tua istanza di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="59c55-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="59c55-114">Se [crei un nuovo ambiente](manage-environments.md), configuralo nella finestra di dialogo **Crea ambiente** e seleziona **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="59c55-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="59c55-115">Se hai già creato un ambiente, vai alle relative impostazioni e seleziona **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="59c55-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="59c55-116">In ogni caso, nella sezione **Usa previsioni**, inserisci l'URL dell'istanza Common Data Service a cui desideri associare il tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="59c55-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="59c55-117">Creare una previsione nell'entità Cliente</span><span class="sxs-lookup"><span data-stu-id="59c55-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="59c55-118">In Audience Insights, vai a **Dati** > **Entità**.</span><span class="sxs-lookup"><span data-stu-id="59c55-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="59c55-119">Seleziona l'entità **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="59c55-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="59c55-120">Nell'entità **Cliente: CustomerInsights** seleziona la scheda **Campi**.</span><span class="sxs-lookup"><span data-stu-id="59c55-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="59c55-121">Individua il nome dell'attributo per il quale desideri prevedere i valori, quindi seleziona l'icona **Panoramica** nella colonna **Riepilogo**.</span><span class="sxs-lookup"><span data-stu-id="59c55-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="59c55-122">![Icona Panoramica](media/intelligence-overviewicon.png "Icona Panoramica")</span><span class="sxs-lookup"><span data-stu-id="59c55-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="59c55-123">Se è presente un'alta percentuale di valori mancanti per l'attributo, seleziona **Prevedi valori mancanti** per continuare con la previsione.</span><span class="sxs-lookup"><span data-stu-id="59c55-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="59c55-124">![Stato Panoramica con il pulsante Prevedi valori mancanti visualizzato](media/intelligence-overviewpredictmissingvalues.png "Stato Panoramica con il pulsante Prevedi valori mancanti visualizzato")</span><span class="sxs-lookup"><span data-stu-id="59c55-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="59c55-125">Inserisci un **nome visualizzato** e un **nome di entità output** per i risultati della previsione.</span><span class="sxs-lookup"><span data-stu-id="59c55-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="59c55-126">Un elenco precompilato di opzioni mostrerà dove è possibile mappare i valori a una categoria stimata.</span><span class="sxs-lookup"><span data-stu-id="59c55-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="59c55-127">In questo caso, le uniche opzioni di categoria saranno 0 o 1 in quanto vengono mappate alla natura vera/falsa o binaria della previsione.</span><span class="sxs-lookup"><span data-stu-id="59c55-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="59c55-128">Nella colonna Categoria, mappa i valori dei campi che desideri classificare come "0" nella previsione finale a "0" e gli elementi che desideri classificare come "1" nella previsione finale a "1".</span><span class="sxs-lookup"><span data-stu-id="59c55-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="59c55-129">![Esempio che mostra i valori dei campi mappati alle categorie](media/intelligence-categorymapping.png "Esempio che mostra i valori dei campi mappati alle categorie")</span><span class="sxs-lookup"><span data-stu-id="59c55-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="59c55-130">Seleziona **Fatto** e la previsione verrà elaborata.</span><span class="sxs-lookup"><span data-stu-id="59c55-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="59c55-131">L'elaborazione richiederà del tempo, a seconda delle dimensioni e della complessità dei dati.</span><span class="sxs-lookup"><span data-stu-id="59c55-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="59c55-132">I risultati saranno disponibili in una nuova entità basata sul **nome dell'entità output** della previsione creata.</span><span class="sxs-lookup"><span data-stu-id="59c55-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="59c55-133">Creare una previsione durante la creazione di un segmento</span><span class="sxs-lookup"><span data-stu-id="59c55-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="59c55-134">La previsione dei valori mancanti per un attributo specifico è possibile anche durante la creazione di un segmento.</span><span class="sxs-lookup"><span data-stu-id="59c55-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="59c55-135">In particolare, quando crei rapidamente un segmento basato sull'entità cliente unificata o sull'entità Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="59c55-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="59c55-136">Come parte di questo flusso scegli un attributo specifico su cui basare il segmento, ad esempio Soddisfazione del cliente o Importo acquisto.</span><span class="sxs-lookup"><span data-stu-id="59c55-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="59c55-137">Alla creazione del segmento, il sistema suggerirà un metodo per prevedere eventuali valori mancanti per questo attributo.</span><span class="sxs-lookup"><span data-stu-id="59c55-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="59c55-138">In Audience Insights, vai a **Segmenti** e seleziona il riquadro **Profili**.</span><span class="sxs-lookup"><span data-stu-id="59c55-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="59c55-139">Scegli un **campo** su cui creare un segmento e seleziona un **operatore** , quindi seleziona **Revisione**.</span><span class="sxs-lookup"><span data-stu-id="59c55-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="59c55-140">Assegna un **nome** e un **nome visualizzato** al segmento.</span><span class="sxs-lookup"><span data-stu-id="59c55-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="59c55-141">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="59c55-141">Select **Save**.</span></span>

5. <span data-ttu-id="59c55-142">Se il segmento creato contiene dati incompleti nel campo di origine, è possibile scegliere di prevedere i valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="59c55-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="59c55-143">![Pulsante Previsione](media/segments-predictoption.png "Pulsante Previsione")</span><span class="sxs-lookup"><span data-stu-id="59c55-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="59c55-144">Inserisci un **nome visualizzato** e un **nome di entità output** per i risultati della previsione.</span><span class="sxs-lookup"><span data-stu-id="59c55-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="59c55-145">Seleziona **Fine**.</span><span class="sxs-lookup"><span data-stu-id="59c55-145">Select **Done**.</span></span> <span data-ttu-id="59c55-146">La previsione verrà generata a breve in una nuova entità con il nome fornito per il **nome dell'entità output**.</span><span class="sxs-lookup"><span data-stu-id="59c55-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="59c55-147">Visualizzare una previsione</span><span class="sxs-lookup"><span data-stu-id="59c55-147">View a prediction</span></span>

1. <span data-ttu-id="59c55-148">In Audience Insights, vai a **Intelligenza** > **Previsioni** > **Le mie previsioni**.</span><span class="sxs-lookup"><span data-stu-id="59c55-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="59c55-149">Seleziona la previsione da rivedere.</span><span class="sxs-lookup"><span data-stu-id="59c55-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="59c55-150">Seleziona i puntini di sospensione nella colonna **Azioni** e scegli **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="59c55-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="59c55-151">Vedrai una serie di punti dati nella visualizzazione della previsione.</span><span class="sxs-lookup"><span data-stu-id="59c55-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="59c55-152">![Pagina Previsioni](media/intelligence-predictionsviewpage.png "Pagina Previsioni")</span><span class="sxs-lookup"><span data-stu-id="59c55-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="59c55-153">I **valori previsti** mostrano il mapping creato durante la fase di mapping del valore Campo alla Categoria.</span><span class="sxs-lookup"><span data-stu-id="59c55-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="59c55-154">Questi sono i valori nel set di dati che sono stati mappati a una categoria specifica.</span><span class="sxs-lookup"><span data-stu-id="59c55-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="59c55-155">-**I principali influencer** sono i fattori all'interno del set di dati che hanno più probabilità di influenzare l'attendibilità della previsione del valore Campo mappato a una categoria specifica.</span><span class="sxs-lookup"><span data-stu-id="59c55-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="59c55-156">**Le prestazioni** indicano l'andamento delle previsioni.</span><span class="sxs-lookup"><span data-stu-id="59c55-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="59c55-157">Per ulteriori informazioni, seleziona il collegamento.</span><span class="sxs-lookup"><span data-stu-id="59c55-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="59c55-158">**L'anteprima** mostra esempi del set di dati di output dalla previsione e la probabilità, o l'attendibilità, del valore previsto, dove 0 è incerto e 1 è certo.</span><span class="sxs-lookup"><span data-stu-id="59c55-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="59c55-159">Aggiornare una previsione</span><span class="sxs-lookup"><span data-stu-id="59c55-159">Update a prediction</span></span>

1. <span data-ttu-id="59c55-160">In Audience Insights, vai a **Intelligenza** > **Previsioni** > **Le mie previsioni**.</span><span class="sxs-lookup"><span data-stu-id="59c55-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="59c55-161">Seleziona la previsione da aggiornare e seleziona l'icona **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="59c55-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="59c55-162">La previsione verrà pianificata per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="59c55-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="59c55-163">È possibile visualizzare l'ora dell'ultimo aggiornamento nella colonna **Aggiornato** della pagina **Previsioni**.</span><span class="sxs-lookup"><span data-stu-id="59c55-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="59c55-164">Modificare una previsione</span><span class="sxs-lookup"><span data-stu-id="59c55-164">Edit a prediction</span></span>

<span data-ttu-id="59c55-165">Dopo aver creato una previsione, è possibile personalizzare il modello in AI Builder per aumentare l'efficacia del modello.</span><span class="sxs-lookup"><span data-stu-id="59c55-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="59c55-166">In Audience Insights, vai a **Intelligenza** > **Previsioni** > **Le mie previsioni**.</span><span class="sxs-lookup"><span data-stu-id="59c55-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="59c55-167">Seleziona la previsione che desideri modificare.</span><span class="sxs-lookup"><span data-stu-id="59c55-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="59c55-168">Seleziona i puntini di sospensione nella colonna **Azioni** e scegli **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="59c55-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="59c55-169">Seleziona **Personalizza in AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="59c55-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="59c55-170">Aggiorna il modello in AI Builder.</span><span class="sxs-lookup"><span data-stu-id="59c55-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="59c55-171">[Ulteriori informazioni sulla gestione dei modelli in AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="59c55-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="59c55-172">La successiva esecuzione della previsione utilizzerà il modello aggiornato creato.</span><span class="sxs-lookup"><span data-stu-id="59c55-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="59c55-173">I nuovi modelli creati in AI Builder non verranno visualizzati in Audience Insights a meno che il modello non sia stato creato sulla base delle esperienze elencate sopra.</span><span class="sxs-lookup"><span data-stu-id="59c55-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="59c55-174">Rimuovere una previsione</span><span class="sxs-lookup"><span data-stu-id="59c55-174">Remove a prediction</span></span>

1. <span data-ttu-id="59c55-175">In Audience Insights, vai a **Intelligenza** > **Previsioni** > **Le mie previsioni**.</span><span class="sxs-lookup"><span data-stu-id="59c55-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="59c55-176">Seleziona la previsione che desideri eliminare.</span><span class="sxs-lookup"><span data-stu-id="59c55-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="59c55-177">Seleziona i puntini di sospensione nella colonna **Azioni** e scegli **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="59c55-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="59c55-178">Conferma l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="59c55-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="59c55-179">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="59c55-179">Troubleshooting</span></span>

<span data-ttu-id="59c55-180">Se non riesci a completare il processo di Common Data Service associato a causa di un errore, puoi provare a completare il processo manualmente.</span><span class="sxs-lookup"><span data-stu-id="59c55-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="59c55-181">Esistono due problemi noti che possono verificarsi nel processo di collegamento:</span><span class="sxs-lookup"><span data-stu-id="59c55-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="59c55-182">Il componente aggiuntivo Scheda cliente non è installato.</span><span class="sxs-lookup"><span data-stu-id="59c55-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="59c55-183">Completa le istruzioni per [installare e configurare la soluzione](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="59c55-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="59c55-184">Le autorizzazioni dell'app non sono concesse.</span><span class="sxs-lookup"><span data-stu-id="59c55-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="59c55-185">Passare a [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="59c55-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="59c55-186">Seleziona **Ambienti**.</span><span class="sxs-lookup"><span data-stu-id="59c55-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="59c55-187">Seleziona i puntini di sospensione accanto all'ambiente a cui desideri aggiungere l'autorizzazione e seleziona **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="59c55-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="59c55-188">Espandi **Utenti + autorizzazioni** e seleziona **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="59c55-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="59c55-189">Seleziona **+ Nuovo** e seleziona **Utente**.</span><span class="sxs-lookup"><span data-stu-id="59c55-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="59c55-190">Seleziona **Utente dell'applicazione** se non è già selezionato e immetti le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="59c55-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="59c55-191">**Nome utente:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="59c55-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="59c55-192">**ID applicazione:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="59c55-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="59c55-193">**Nome:** cliente</span><span class="sxs-lookup"><span data-stu-id="59c55-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="59c55-194">**Cognome:** informazioni dettagliate</span><span class="sxs-lookup"><span data-stu-id="59c55-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="59c55-195">**Indirizzo di posta elettronica primario:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="59c55-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="59c55-196">Seleziona **Salva e chiudi**.</span><span class="sxs-lookup"><span data-stu-id="59c55-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="59c55-197">Seleziona l'utente appena creata.</span><span class="sxs-lookup"><span data-stu-id="59c55-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="59c55-198">Seleziona **Gestisci ruoli** nella barra di menu superiore.</span><span class="sxs-lookup"><span data-stu-id="59c55-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="59c55-199">Seleziona **Amministratore di sistema**, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="59c55-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]