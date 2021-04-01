---
title: Impegni cliente
description: Definisci gli impegni cliente e visualizzali nella sequenza temporale del cliente.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596734"
---
# <a name="customer-activities"></a><span data-ttu-id="e7613-103">Impegni cliente</span><span class="sxs-lookup"><span data-stu-id="e7613-103">Customer activities</span></span>

<span data-ttu-id="e7613-104">Combina gli impegni cliente da [varie origini dati](data-sources.md) in Dynamics 365 Customer Insights per creare la sequenza temporale di un cliente che elenchi gli impegni in ordine cronologico.</span><span class="sxs-lookup"><span data-stu-id="e7613-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="e7613-105">Puoi includere la sequenza temporale nelle app di interazione con i clienti in Dynamics 365 tramite il [componente aggiuntivo Scheda cliente](customer-card-add-in.md) o in un dashboard di Power BI.</span><span class="sxs-lookup"><span data-stu-id="e7613-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="e7613-106">Definire un impegno</span><span class="sxs-lookup"><span data-stu-id="e7613-106">Define an activity</span></span>

<span data-ttu-id="e7613-107">Le tue origini dati includono entità con dati transazionali e dati di impegni provenienti da più origini dati.</span><span class="sxs-lookup"><span data-stu-id="e7613-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="e7613-108">Identifica queste entità e seleziona gli impegni che vuoi visualizzare nella sequenza temporale del cliente.</span><span class="sxs-lookup"><span data-stu-id="e7613-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="e7613-109">Scegli l'entità che include il tuo impegno o i tuoi impegni di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e7613-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="e7613-110">In Audience Insights, vai a **Dati** > **Impegni**.</span><span class="sxs-lookup"><span data-stu-id="e7613-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="e7613-111">Seleziona **Aggiungi impegno**.</span><span class="sxs-lookup"><span data-stu-id="e7613-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e7613-112">Un'entità deve avere almeno un attributo di tipo **Data** per essere incluso in una sequenza temporale del cliente e non puoi aggiungere entità senza campi **Data**.</span><span class="sxs-lookup"><span data-stu-id="e7613-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="e7613-113">Il controllo **Aggiungi impegno** è disabilitato se non viene trovata tale entità.</span><span class="sxs-lookup"><span data-stu-id="e7613-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="e7613-114">Nel riquadro **Aggiungi impegno**, imposta i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e7613-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="e7613-115">**Entità**: seleziona un'entità che include dati transazionali o di impegni.</span><span class="sxs-lookup"><span data-stu-id="e7613-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="e7613-116">**Chiave primaria**: seleziona il campo che identifica in modo univoco un record.</span><span class="sxs-lookup"><span data-stu-id="e7613-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="e7613-117">Non deve contenere valori duplicati, valori vuoti o valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="e7613-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="e7613-118">**Timestamp**: seleziona il campo che rappresenta l'ora di inizio dell'impegno.</span><span class="sxs-lookup"><span data-stu-id="e7613-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="e7613-119">**Evento**: seleziona il campo che è l'evento per l'impegno.</span><span class="sxs-lookup"><span data-stu-id="e7613-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="e7613-120">**Indirizzo Web**: seleziona il campo che rappresenta un URL che fornisce informazioni aggiuntive su questo impegno.</span><span class="sxs-lookup"><span data-stu-id="e7613-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="e7613-121">Ad esempio, il sistema transazionale che genera questo impegno.</span><span class="sxs-lookup"><span data-stu-id="e7613-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="e7613-122">Questo URL può essere qualsiasi campo di origine dati oppure può essere costruito come un nuovo campo usando una trasformazione Power Query.</span><span class="sxs-lookup"><span data-stu-id="e7613-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="e7613-123">Questi dati URL verranno archiviati nell'entità Impegno unificata, che può essere consumata a valle utilizzando le API.</span><span class="sxs-lookup"><span data-stu-id="e7613-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="e7613-124">**Dettagli**: facoltativamente, seleziona il campo che viene aggiunto per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="e7613-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="e7613-125">**Icona**: opzionalmente, seleziona l'icona che rappresenta questo impegno.</span><span class="sxs-lookup"><span data-stu-id="e7613-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="e7613-126">**Tipo di impegno**: definisci il riferimento del tipo di impegno al Common Data Model che meglio descrive la definizione semantica dell'impegno.</span><span class="sxs-lookup"><span data-stu-id="e7613-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="e7613-127">Nella sezione **Configura relazione**, configura i dettagli per connettere i dati dei tuopi impegni al cliente corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e7613-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="e7613-128">**Campo dell'entità Impegno**: seleziona il campo nell'entità impegno che verrà utilizzato per stabilire una relazione con un'altra entità.</span><span class="sxs-lookup"><span data-stu-id="e7613-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="e7613-129">**Entità cliente**: seleziona l'entità cliente di origine corrispondente con cui l'entità impegno sarà in relazione.</span><span class="sxs-lookup"><span data-stu-id="e7613-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="e7613-130">Puoi creare una correlazione solo con quelle entità cliente di origine utilizzate nel processo di unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e7613-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="e7613-131">**Campo entità cliente**: questo campo mostra la chiave primaria dell'entità cliente di origine come selezionata nel processo di mapping.</span><span class="sxs-lookup"><span data-stu-id="e7613-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="e7613-132">Questo campo chiave primaria nell'entità cliente di origine viene utilizzato per stabilire una relazione con l'entità impegno.</span><span class="sxs-lookup"><span data-stu-id="e7613-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="e7613-133">**Nome**: se esiste già una relazione tra questa entità impegno e l'entità cliente di origine selezionata, il nome della relazione sarà in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e7613-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="e7613-134">Se tale relazione non esiste, verrà creata una nuova relazione con il nome fornito qui.</span><span class="sxs-lookup"><span data-stu-id="e7613-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7613-135">![Definire la relazione dell'entità](media/activities-entities-define.png "Definire la relazione dell'entità")</span><span class="sxs-lookup"><span data-stu-id="e7613-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="e7613-136">Seleziona **Salva** per applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e7613-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="e7613-137">Nella pagina **Impegni** seleziona **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e7613-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="e7613-138">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="e7613-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e7613-139">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e7613-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e7613-140">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="e7613-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e7613-141">Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="e7613-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="e7613-142">Modifica un impegno</span><span class="sxs-lookup"><span data-stu-id="e7613-142">Edit an activity</span></span>

1. <span data-ttu-id="e7613-143">In Audience Insights, vai a **Dati** > **Impegni**.</span><span class="sxs-lookup"><span data-stu-id="e7613-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="e7613-144">Seleziona l'entità impegno che vuoi modificare e seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e7613-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="e7613-145">In alternativa, puoi passare con il mouse sopra la riga dell'entità e selezionare l'icona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e7613-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="e7613-146">Fate clic sull'icona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e7613-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="e7613-147">Nel riquadro **Modifica impegno**, aggiorna i valori e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e7613-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="e7613-148">Nella pagina **Impegni** seleziona **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e7613-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="e7613-149">Eliminare un impegno</span><span class="sxs-lookup"><span data-stu-id="e7613-149">Delete an activity</span></span>

1. <span data-ttu-id="e7613-150">In Audience Insights, vai a **Dati** > **Impegni**.</span><span class="sxs-lookup"><span data-stu-id="e7613-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="e7613-151">Seleziona l'entità impegno che vuoi rimuovere e seleziona **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e7613-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="e7613-152">In alternativa, puoi passare con il mouse sopra la riga dell'entità e selezionare l'icona **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e7613-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="e7613-153">Inoltre, puoi selezionare più entità impegno da eliminare contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e7613-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7613-154">![Modificare o eliminare la relazione di entità](media/activities-entities-edit-delete.png "Modificare o eliminare la relazione di entità")</span><span class="sxs-lookup"><span data-stu-id="e7613-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="e7613-155">Seleziona l'icona **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e7613-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="e7613-156">Conferma l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="e7613-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]