---
title: Impegni cliente
description: Definisci gli impegni cliente e visualizzali nella sequenza temporale del cliente.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866412"
---
# <a name="customer-activities"></a><span data-ttu-id="f5e5e-103">Impegni cliente</span><span class="sxs-lookup"><span data-stu-id="f5e5e-103">Customer activities</span></span>

<span data-ttu-id="f5e5e-104">Combina le attività dei clienti da [varie origini di dati](data-sources.md) in Dynamics 365 Customer Insights per creare una sequenza temporale che elenchi le attività in ordine cronologico.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="f5e5e-105">Includi la sequenza temporale nelle app Dynamics 365 con la soluzione [Componente aggiuntivo Scheda cliente](customer-card-add-in.md) o in un dashboard Power BI.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="f5e5e-106">Definire un impegno</span><span class="sxs-lookup"><span data-stu-id="f5e5e-106">Define an activity</span></span>

<span data-ttu-id="f5e5e-107">Le tue origini dati possono includere entità con dati transazionali e dati di impegni provenienti da più origini dati.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="f5e5e-108">Identifica queste entità e seleziona gli impegni che vuoi visualizzare nella sequenza temporale del cliente.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="f5e5e-109">Scegli l'entità che include il tuo impegno o i tuoi impegni di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="f5e5e-110">Un'entità deve avere almeno un attributo di tipo **Data** per essere incluso in una sequenza temporale del cliente e non puoi aggiungere entità senza campi **Data**.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="f5e5e-111">Il controllo **Aggiungi impegno** è disabilitato se non viene trovata tale entità.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="f5e5e-112">In Audience Insights, vai a **Dati** > **Impegni**.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="f5e5e-113">Seleziona **Aggiungi impegno** per avviare l'esperienza guidata per il processo di configurazione dell'impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="f5e5e-114">Nel passaggio **Dati sull'impegno** imposta i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="f5e5e-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="f5e5e-115">**Nome impegno**: Seleziona un nome per l'impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="f5e5e-116">**Entità**: seleziona un'entità che include dati transazionali o di impegni.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="f5e5e-117">**Chiave primaria**: seleziona il campo che identifica in modo univoco un record.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="f5e5e-118">Non deve contenere valori duplicati, valori vuoti o valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Imposta i dati dell'impegno con nome, entità e chiave primaria.":::

1. <span data-ttu-id="f5e5e-120">Seleziona **Avanti** per procedere al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="f5e5e-121">Nel passaggio **Relazione**, configura i dettagli per connettere i dati dell'impegno al cliente corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="f5e5e-122">Questo passaggio visualizza la connessione tra le entità.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="f5e5e-123">**Primo**: Campo esterno nell'entità dell'impegno che verrà utilizzato per stabilire una relazione con un'altra entità.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="f5e5e-124">**Secondo**: Entità cliente di origine corrispondente con la quale l'entità impegno sarà in relazione.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="f5e5e-125">È possibile fare riferimento solo alle entità del cliente di origine utilizzate nel processo di unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="f5e5e-126">**Terzo**: Se esiste già una relazione tra questa entità impegno e l'entità cliente di origine selezionata, il nome della relazione sarà in modalità di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="f5e5e-127">Se non esiste una relazione di questo tipo, verrà creata una nuova relazione con il nome fornito in questa casella.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definisci la relazione dell'entità.":::

1. <span data-ttu-id="f5e5e-129">Seleziona **Avanti** per procedere al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="f5e5e-130">Nel passaggio **Unificazione impegno**, scegli l'evento dell'impegno e l'ora di inizio dell'impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="f5e5e-131">**Campi obbligatori**</span><span class="sxs-lookup"><span data-stu-id="f5e5e-131">**Required fields**</span></span>
      1. <span data-ttu-id="f5e5e-132">**Impegno evento**: Campo che rappresenta l'evento per questo impegno</span><span class="sxs-lookup"><span data-stu-id="f5e5e-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="f5e5e-133">**Timestamp**: Campo che rappresenta l'ora di inizio dell'impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="f5e5e-134">**Campi facoltativi**</span><span class="sxs-lookup"><span data-stu-id="f5e5e-134">**Optional fields**</span></span>
      1. <span data-ttu-id="f5e5e-135">**Ulteriori dettagli**: Campo con informazioni rilevanti per questo impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="f5e5e-136">**Icona**: Icona che rappresenta al meglio questo tipo di impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="f5e5e-137">**indirizzo Web**: Campo contenente un URL con informazioni su questo impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="f5e5e-138">Ad esempio, il sistema transazionale che genera questo impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="f5e5e-139">Questo URL può essere qualsiasi campo di origine dati oppure può essere costruito come un nuovo campo usando una trasformazione Power Query.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="f5e5e-140">I dati dell'URL verranno archiviati nell'entità *Impegno unificato* che può essere consumata a valle utilizzando le [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="f5e5e-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Specifica i dati dell'impegno del cliente in un'entità Impegno unificato.":::

1. <span data-ttu-id="f5e5e-142">Seleziona **Avanti** per passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="f5e5e-143">Puoi selezionare **Termina e rivedi** per salvare l'impegno ora con il tipo di impegno impostato su **Altro**.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="f5e5e-144">Nel passaggio **Tipo di impegno** scegli il tipo di impegno e, facoltativamente, seleziona se vuoi mappare semanticamente alcuni tipi di impegno da utilizzare in altre aree di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="f5e5e-145">Attualmente, i tipi di impegno *Sottoscrizione* & *SalesOrderLine* possono essere mappati semanticamente dopo aver accettato di mappare i campi.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="f5e5e-146">Se un tipo di impegno non è pertinente per il nuovo impegno, puoi scegliere *Altro* o *Crea nuovo* per un tipo di impegno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="f5e5e-147">Seleziona **Avanti** per passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="f5e5e-148">Nel passaggio **Rivedi**, verifica le tue selezioni.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="f5e5e-149">Torna a uno dei passaggi precedenti e aggiorna le informazioni se necessario.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Rivedi i campi specificati per un impegno.":::
   
1. <span data-ttu-id="f5e5e-151">Seleziona **Salva impegno** per applicare le modifiche e seleziona **Fatto** per tornare a **Dati** > **Impegni**.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="f5e5e-152">Qui puoi vedere quali impegni sono impostati per essere mostrati nella sequenza temporale.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="f5e5e-153">Nella pagina **Impegni** seleziona **Esegui** per elaborare l'impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="f5e5e-154">Esistono [sei tipi di stato](system.md#status-types) per attività/processi.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f5e5e-155">Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f5e5e-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f5e5e-156">Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f5e5e-157">Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="f5e5e-158">Gestire gli impegni esistenti</span><span class="sxs-lookup"><span data-stu-id="f5e5e-158">Manage existing activities</span></span>

<span data-ttu-id="f5e5e-159">In **Dati** > **Impegni**, puoi visualizzare tutti gli impegni salvati e gestirli.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="f5e5e-160">Ogni impegno è rappresentato da una riga che include anche i dettagli sull'origine, l'entità e il tipo di impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="f5e5e-161">Le seguenti azioni sono disponibili quando selezioni un impegno.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="f5e5e-162">**Modifica**: Apre la configurazione dell'impegno nella fase di revisione.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="f5e5e-163">Puoi modificare parte o tutta la configurazione corrente da questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="f5e5e-164">Dopo aver modificato la configurazione, seleziona **Salva impegno** e poi seleziona **Esegui** per elaborare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="f5e5e-165">**Rinomina**: Apre una finestra di dialogo in cui inserire un nome diverso per l'impegno selezionato.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="f5e5e-166">Seleziona **Salva** per applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="f5e5e-167">**Elimina**: Apre una finestra di dialogo per confermare l'eliminazione dell'impegno selezionato.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="f5e5e-168">È inoltre possibile eliminare più di un impegno contemporaneamente selezionando gli impegni e quindi l'icona di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="f5e5e-169">Per confermare l'eliminazione seleziona **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="f5e5e-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
