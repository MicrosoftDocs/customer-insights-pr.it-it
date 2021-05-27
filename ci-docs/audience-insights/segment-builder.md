---
title: Creare e gestire segmenti
description: Crea segmenti di clienti per raggrupparli in base a vari attributi.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064942"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="683e9-103">Creare e gestire segmenti</span><span class="sxs-lookup"><span data-stu-id="683e9-103">Create and manage segments</span></span>

<span data-ttu-id="683e9-104">Definisci filtri complessi per all'entità cliente unificata e le sue entità correlate.</span><span class="sxs-lookup"><span data-stu-id="683e9-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="683e9-105">Ogni segmento, dopo l'elaborazione, crea una serie di record dei clienti che puoi esportare o su cui puoi intervenire.</span><span class="sxs-lookup"><span data-stu-id="683e9-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="683e9-106">I segmenti sono gestiti nella pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="683e9-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="683e9-107">Il seguente esempio illustra la funzionalità di segmentazione.</span><span class="sxs-lookup"><span data-stu-id="683e9-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="683e9-108">Abbiamo definito un segmento per i clienti che hanno ordinato almeno $500 di merci negli ultimi 90 giorni *e* che sono stati coinvolti in una chiamata servizio clienti che è stata riassegnata.</span><span class="sxs-lookup"><span data-stu-id="683e9-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Screenshot dell'interfaccia utente del generatore di segmenti con due gruppi che specificano un segmento di clienti.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="683e9-110">Creare un nuovo segmento</span><span class="sxs-lookup"><span data-stu-id="683e9-110">Create a new segment</span></span>

<span data-ttu-id="683e9-111">Un nuovo segmento può essere creato in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="683e9-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="683e9-112">Questa sezione descrive come creare un *segmento vuoto* da zero.</span><span class="sxs-lookup"><span data-stu-id="683e9-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="683e9-113">Puoi anche creare un *segmento veloce* basato su entità esistenti o utilizzare i modelli apprendimento automatico per ottenere *segmenti suggeriti*.</span><span class="sxs-lookup"><span data-stu-id="683e9-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="683e9-114">Ulteriori informazioni: [Panoramica dei segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="683e9-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="683e9-115">Durante la creazione di un segmento, puoi salvare una bozza.</span><span class="sxs-lookup"><span data-stu-id="683e9-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="683e9-116">Verrà salvata come segmento inattivo che non può essere attivato se non è terminato con una configurazione valida.</span><span class="sxs-lookup"><span data-stu-id="683e9-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="683e9-117">Vai alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="683e9-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="683e9-118">Seleziona **Nuovo** > **Segmento vuoto**.</span><span class="sxs-lookup"><span data-stu-id="683e9-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="683e9-119">Nel riquadro **Nuovo segmento** scegli un tipo di segmento:</span><span class="sxs-lookup"><span data-stu-id="683e9-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="683e9-120">**Segmenti dinamici** [aggiornati](segments.md#refresh-segments) su una pianificazione ricorrente.</span><span class="sxs-lookup"><span data-stu-id="683e9-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="683e9-121">**Segmenti statici** eseguiti una volta quando li crei.</span><span class="sxs-lookup"><span data-stu-id="683e9-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="683e9-122">Fornisci un **Nome entità di output** per il segmento.</span><span class="sxs-lookup"><span data-stu-id="683e9-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="683e9-123">Facoltativamente, fornisci un nome visualizzato e una descrizione che aiuti a identificare il segmento.</span><span class="sxs-lookup"><span data-stu-id="683e9-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="683e9-124">Seleziona **Avanti** per andare alla pagina **Generatore di segmenti** in cui puoi definire un gruppo.</span><span class="sxs-lookup"><span data-stu-id="683e9-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="683e9-125">Un gruppo è un set di clienti.</span><span class="sxs-lookup"><span data-stu-id="683e9-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="683e9-126">Scegli l'entità che include l'attributo in base al quale vuoi segmentare.</span><span class="sxs-lookup"><span data-stu-id="683e9-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="683e9-127">Scegli l'attributo in base a cui segmentare.</span><span class="sxs-lookup"><span data-stu-id="683e9-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="683e9-128">Questo attributo può avere uno dei quattro tipi di valore: numerico, stringa, data o booleano.</span><span class="sxs-lookup"><span data-stu-id="683e9-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="683e9-129">Scegli un operatore e un valore per l'attributo selezionato.</span><span class="sxs-lookup"><span data-stu-id="683e9-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="683e9-130">![Filtro gruppo clienti](media/customer-group-numbers.png "Filtro gruppo clienti")</span><span class="sxs-lookup"><span data-stu-id="683e9-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="683e9-131">Numero</span><span class="sxs-lookup"><span data-stu-id="683e9-131">Number</span></span> |<span data-ttu-id="683e9-132">Definizione</span><span class="sxs-lookup"><span data-stu-id="683e9-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="683e9-133">1</span><span class="sxs-lookup"><span data-stu-id="683e9-133">1</span></span>     |<span data-ttu-id="683e9-134">Entity</span><span class="sxs-lookup"><span data-stu-id="683e9-134">Entity</span></span>          |
   |<span data-ttu-id="683e9-135">2</span><span class="sxs-lookup"><span data-stu-id="683e9-135">2</span></span>     |<span data-ttu-id="683e9-136">Attributo</span><span class="sxs-lookup"><span data-stu-id="683e9-136">Attribute</span></span>          |
   |<span data-ttu-id="683e9-137">3</span><span class="sxs-lookup"><span data-stu-id="683e9-137">3</span></span>    |<span data-ttu-id="683e9-138">Operatore</span><span class="sxs-lookup"><span data-stu-id="683e9-138">Operator</span></span>         |
   |<span data-ttu-id="683e9-139">4</span><span class="sxs-lookup"><span data-stu-id="683e9-139">4</span></span>    |<span data-ttu-id="683e9-140">valore</span><span class="sxs-lookup"><span data-stu-id="683e9-140">Value</span></span>         |

   1. <span data-ttu-id="683e9-141">Per aggiungere più condizioni a un gruppo, è possibile utilizzare due operatori logici:</span><span class="sxs-lookup"><span data-stu-id="683e9-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="683e9-142">Operatore **AND**: entrambe le condizioni devono essere soddisfatte come parte del processo di segmentazione.</span><span class="sxs-lookup"><span data-stu-id="683e9-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="683e9-143">Questa opzione è molto utile quando si definiscono condizioni tra entità diverse.</span><span class="sxs-lookup"><span data-stu-id="683e9-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="683e9-144">Operatore **OR**: una delle condizioni deve essere soddisfatta come parte del processo di segmentazione.</span><span class="sxs-lookup"><span data-stu-id="683e9-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="683e9-145">Questa opzione è molto utile quando si definiscono più condizioni per la stessa entità.</span><span class="sxs-lookup"><span data-stu-id="683e9-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="683e9-146">![Operatore OR in cui è necessario soddisfare una delle condizioni](media/segmentation-either-condition.png "Operatore OR in cui è necessario soddisfare una delle condizioni")</span><span class="sxs-lookup"><span data-stu-id="683e9-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="683e9-147">Al momento è possibile nidificare un operatore **OR** sotto un operatore **AND**, ma non il contrario.</span><span class="sxs-lookup"><span data-stu-id="683e9-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="683e9-148">Ogni gruppo corrisponde a un set di clienti.</span><span class="sxs-lookup"><span data-stu-id="683e9-148">Each group matches set of customers.</span></span> <span data-ttu-id="683e9-149">Puoi combinare gruppi per includere i clienti richiesti per il tuo caso aziendale.</span><span class="sxs-lookup"><span data-stu-id="683e9-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="683e9-150">Seleziona **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="683e9-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="683e9-151">![Aggiungi gruppo per gruppo clienti](media/customer-group-add-group.png "Aggiungi gruppo per gruppo clienti")</span><span class="sxs-lookup"><span data-stu-id="683e9-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="683e9-152">Seleziona uno degli operatori impostati: **Unione**, **Intersecazione** o **Eccezione**.</span><span class="sxs-lookup"><span data-stu-id="683e9-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="683e9-153">![Aggiungi Union per gruppo clienti](media/customer-group-union.png "Aggiungi Union per gruppo clienti")</span><span class="sxs-lookup"><span data-stu-id="683e9-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="683e9-154">**Union** unisce i due gruppi.</span><span class="sxs-lookup"><span data-stu-id="683e9-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="683e9-155">**Intersect** sovrappone i due gruppi.</span><span class="sxs-lookup"><span data-stu-id="683e9-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="683e9-156">Solo i dati che *sono comuni* a entrambi i gruppi vengono mantenuti nel gruppo unificato.</span><span class="sxs-lookup"><span data-stu-id="683e9-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="683e9-157">**Ad eccezione di** combina i due gruppi.</span><span class="sxs-lookup"><span data-stu-id="683e9-157">**Except** combines the two groups.</span></span> <span data-ttu-id="683e9-158">Solo i dati nel gruppo A che *non sono comuni* ai dati nel gruppo B vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="683e9-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="683e9-159">Se l'entità è connessa all'entità cliente unificata tramite [relazioni](relationships.md), devi definire il percorso della relazione per creare un segmento valido.</span><span class="sxs-lookup"><span data-stu-id="683e9-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="683e9-160">Aggiungi le entità dal percorso della relazione fino a quando non puoi selezionare l'entità **Cliente: CustomerInsights** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="683e9-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="683e9-161">Quindi scegli **Tutti i record** per ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="683e9-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="683e9-162">![Percorso di relazione durante la creazione del segmento](media/segments-multiple-relationships.png "Percorso di relazione durante la creazione del segmento")</span><span class="sxs-lookup"><span data-stu-id="683e9-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="683e9-163">Per impostazione predefinita, i segmenti generano un'entità di output che contiene tutti gli attributi dei profili cliente che corrispondono ai filtri definiti.</span><span class="sxs-lookup"><span data-stu-id="683e9-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="683e9-164">Se un segmento è basato su entità diverse dall'entità *Cliente* puoi aggiungere più attributi da queste entità all'entità di output.</span><span class="sxs-lookup"><span data-stu-id="683e9-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="683e9-165">Seleziona **Attributi progetto** per scegliere gli attributi che verranno aggiunti all'entità di output.</span><span class="sxs-lookup"><span data-stu-id="683e9-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="683e9-166">Esempio: un segmento si basa su un'entità che contiene i dati sull'impegno del cliente correlati all'entità *Cliente*.</span><span class="sxs-lookup"><span data-stu-id="683e9-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="683e9-167">Il segmento cerca tutti i clienti che hanno chiamato l'help desk negli ultimi 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="683e9-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="683e9-168">Puoi scegliere di aggiungere la durata della chiamata e il numero di chiamate a tutti i record cliente corrispondenti nell'entità di output.</span><span class="sxs-lookup"><span data-stu-id="683e9-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="683e9-169">Queste informazioni potrebbero essere utili per inviare un'e-mail con collegamenti utili ad articoli della guida in linea e domande frequenti per i clienti che chiamano frequentemente.</span><span class="sxs-lookup"><span data-stu-id="683e9-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="683e9-170">Gli attributi previsti funzionano solo per entità che hanno la relazione uno-a-molti con l'entità cliente.</span><span class="sxs-lookup"><span data-stu-id="683e9-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="683e9-171">Ad esempio, un cliente può avere più abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="683e9-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="683e9-172">È possibile proiettare gli attributi solo da un'entità utilizzata in ogni gruppo della query di segmento che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="683e9-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="683e9-173">Gli attributi proiettati vengono presi in considerazione quando si utilizzano operatori di gruppo.</span><span class="sxs-lookup"><span data-stu-id="683e9-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="683e9-174">Seleziona **Salva** per salvare il segmento.</span><span class="sxs-lookup"><span data-stu-id="683e9-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="683e9-175">Il segmento verrà salvato ed elaborato se tutti i requisiti vengono convalidati.</span><span class="sxs-lookup"><span data-stu-id="683e9-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="683e9-176">Altrimenti, verrà salvato come bozza.</span><span class="sxs-lookup"><span data-stu-id="683e9-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="683e9-177">Seleziona **Torna a Segmenti** per tornare alla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="683e9-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="683e9-178">Segmenti rapidi</span><span class="sxs-lookup"><span data-stu-id="683e9-178">Quick segments</span></span>

<span data-ttu-id="683e9-179">I segmenti rapidi consentono di creare rapidamente segmenti semplici con un singolo operatore per ottenere informazioni più rapide.</span><span class="sxs-lookup"><span data-stu-id="683e9-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="683e9-180">Nella pagina **Segmenti**, seleziona **Nuovo** > **Crea a partire da**.</span><span class="sxs-lookup"><span data-stu-id="683e9-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="683e9-181">Seleziona l'opzione **Profili** per creare un segmento basato sull'*entità cliente unificata*.</span><span class="sxs-lookup"><span data-stu-id="683e9-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="683e9-182">Seleziona l'opzione **Misure** per creare un segmento per le misure create in precedenza.</span><span class="sxs-lookup"><span data-stu-id="683e9-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="683e9-183">Seleziona l'opzione **Intelligenza** per creare un segmento attorno a una delle entità di output generate utilizzando le funzionalità **Previsioni** o **Modelli personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="683e9-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="683e9-184">Nella finestra di dialogo **Nuovo segmento rapido**, seleziona un attributo dal menu a discesa **Campo**.</span><span class="sxs-lookup"><span data-stu-id="683e9-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="683e9-185">Il sistema fornirà alcune informazioni dettagliate aggiuntive che ti aiuteranno a creare segmenti migliori dei tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="683e9-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="683e9-186">Per i campi di categoria, vengono visualizzati i primi 10 conteggi dei clienti.</span><span class="sxs-lookup"><span data-stu-id="683e9-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="683e9-187">Scegli un **valore** e seleziona **Revisione**.</span><span class="sxs-lookup"><span data-stu-id="683e9-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="683e9-188">Per un attributo numerico, il sistema mostrerà quale valore dell'attributo rientra nel percentile di ciascun cliente.</span><span class="sxs-lookup"><span data-stu-id="683e9-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="683e9-189">Scegli un **operatore** e un **valore**, quindi seleziona **Revisione**.</span><span class="sxs-lookup"><span data-stu-id="683e9-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="683e9-190">Il sistema fornirà una **dimensione stimata del segmento**.</span><span class="sxs-lookup"><span data-stu-id="683e9-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="683e9-191">Puoi scegliere se generare il segmento che hai definito o modificarlo prima per ottenere una dimensione del segmento diversa.</span><span class="sxs-lookup"><span data-stu-id="683e9-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="683e9-192">![Nome e stima per un segmento rapido](media/quick-segment-name.png "Nome e stima per un segmento rapido")</span><span class="sxs-lookup"><span data-stu-id="683e9-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="683e9-193">Inserisci un **nome** per il segmento.</span><span class="sxs-lookup"><span data-stu-id="683e9-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="683e9-194">Se lo desideri, inserisci un **nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="683e9-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="683e9-195">Seleziona **Salva** per creare il segmento.</span><span class="sxs-lookup"><span data-stu-id="683e9-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="683e9-196">Al termine dell'elaborazione del segmento, puoi visualizzarlo come qualsiasi altro segmento che hai creato.</span><span class="sxs-lookup"><span data-stu-id="683e9-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="683e9-197">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="683e9-197">Next steps</span></span>

<span data-ttu-id="683e9-198">[Esporta un segmento](export-destinations.md) ed esplora [Scheda cliente](customer-card-add-in.md) e [Connettori](export-power-bi.md) per ottenere informazioni dettagliate a livello di cliente.</span><span class="sxs-lookup"><span data-stu-id="683e9-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
