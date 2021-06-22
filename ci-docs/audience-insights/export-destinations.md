---
title: Esportare i dati da Customer Insights
description: Gestisci le esportazioni per condividere i dati.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253045"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="6c263-103">Panoramica delle esportazioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6c263-103">Exports (preview) overview</span></span>

<span data-ttu-id="6c263-104">La pagina **Esportazioni** mostra tutte le esportazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="6c263-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="6c263-105">Le esportazioni condividono dati specifici con varie applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6c263-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="6c263-106">Possono includere profili o entità del cliente, schemi e dettagli di mappatura.</span><span class="sxs-lookup"><span data-stu-id="6c263-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="6c263-107">Ogni esportazione richiede una [connessione, impostata da un amministratore, per gestire l'autenticazione e l'accesso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="6c263-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="6c263-108">Vai a **Dati** > **Esportazioni** per visualizzare la pagina delle esportazioni.</span><span class="sxs-lookup"><span data-stu-id="6c263-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="6c263-109">Tutti i ruoli utente hanno accesso per visualizzare le esportazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="6c263-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="6c263-110">Utilizza il campo di ricerca nella barra dei comandi per trovare le esportazioni in base al nome, al nome della connessione o al tipo di connessione.</span><span class="sxs-lookup"><span data-stu-id="6c263-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="6c263-111">Configurare una nuova esportazione</span><span class="sxs-lookup"><span data-stu-id="6c263-111">Set up a new export</span></span>

<span data-ttu-id="6c263-112">Per impostare o modificare un'esportazione, è necessario avere delle connessioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="6c263-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="6c263-113">Le connessioni dipendono dal tuo [ruolo utente](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="6c263-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="6c263-114">Gli amministratori hanno accesso a tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="6c263-114">Administrators have access to all connections.</span></span> <span data-ttu-id="6c263-115">Possono anche creare nuove connessioni durante la configurazione di un'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6c263-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="6c263-116">I collaboratori possono avere accesso a connessioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="6c263-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="6c263-117">Dipendono dagli amministratori per configurare e condividere le connessioni.</span><span class="sxs-lookup"><span data-stu-id="6c263-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="6c263-118">L'elenco delle esportazioni mostra ai contributori se possono modificare o visualizzare solo un'esportazione nella colonna **Le tue autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c263-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="6c263-119">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6c263-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="6c263-120">I visualizzatori possono solo visualizzare le esportazioni esistenti ma non crearle.</span><span class="sxs-lookup"><span data-stu-id="6c263-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="6c263-121">Definisci una nuova esportazione</span><span class="sxs-lookup"><span data-stu-id="6c263-121">Define a new export</span></span>

1. <span data-ttu-id="6c263-122">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c263-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c263-123">Per creare una nuova esportazione seleziona **Aggiungi esportazione**.</span><span class="sxs-lookup"><span data-stu-id="6c263-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="6c263-124">Nel riquadro **Imposta esportazione** seleziona la connessione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="6c263-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="6c263-125">[Le connessioni](connections.md) sono gestite dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="6c263-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="6c263-126">Fornisci i dettagli richiesti e seleziona **Salva** per creare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6c263-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="6c263-127">Definire una nuova esportazione basata su un'esportazione esistente</span><span class="sxs-lookup"><span data-stu-id="6c263-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="6c263-128">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c263-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c263-129">Nell'elenco delle esportazioni, seleziona l'esportazione da duplicare.</span><span class="sxs-lookup"><span data-stu-id="6c263-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="6c263-130">Seleziona **Crea duplicato** nella barra dei comandi per aprire il riquadro **Configura esportazione** con i dettagli dell'esportazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="6c263-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="6c263-131">Rivedi e adatta l'esportazione e seleziona **Salva** per creare una nuova esportazione.</span><span class="sxs-lookup"><span data-stu-id="6c263-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="6c263-132">Modificare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="6c263-132">Edit an export</span></span>

1. <span data-ttu-id="6c263-133">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c263-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c263-134">Nell'elenco delle esportazioni, seleziona l'esportazione da modificare.</span><span class="sxs-lookup"><span data-stu-id="6c263-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="6c263-135">Seleziona **Modifica** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6c263-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="6c263-136">Modifica i valori che vuoi aggiornare e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6c263-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="6c263-137">Visualizzare le esportazioni ed esporta i dettagli</span><span class="sxs-lookup"><span data-stu-id="6c263-137">View exports and export details</span></span>

<span data-ttu-id="6c263-138">Dopo aver creato le destinazioni di esportazione, vengono elencate in **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c263-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="6c263-139">Tutti gli utenti possono vedere quali dati sono condivisi e il loro stato più recente.</span><span class="sxs-lookup"><span data-stu-id="6c263-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="6c263-140">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c263-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c263-141">Gli utenti senza autorizzazioni di modifica selezionano **Visualizza** invece di **Modifica** per vedere i dettagli dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6c263-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="6c263-142">Il riquadro laterale mostra la configurazione di un'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6c263-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="6c263-143">Senza le autorizzazioni di modifica, non è possibile modificare i valori.</span><span class="sxs-lookup"><span data-stu-id="6c263-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="6c263-144">Seleziona **Chiudi** per tornare alla pagina delle esportazioni.</span><span class="sxs-lookup"><span data-stu-id="6c263-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="6c263-145">Pianifica ed esegui le esportazioni</span><span class="sxs-lookup"><span data-stu-id="6c263-145">Schedule and run exports</span></span>

<span data-ttu-id="6c263-146">Ogni esportazione configurata ha una pianificazione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="6c263-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="6c263-147">Durante un aggiornamento, il sistema cerca dati nuovi o aggiornati per includerli in un'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6c263-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="6c263-148">Per impostazione predefinita, le esportazioni vengono eseguite come parte di ogni [aggiornamento del sistema programmato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6c263-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6c263-149">Puoi personalizzare la pianificazione dell'aggiornamento o disattivarla per eseguire le esportazioni manualmente.</span><span class="sxs-lookup"><span data-stu-id="6c263-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="6c263-150">Le pianificazioni delle esportazioni dipendono dallo stato dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="6c263-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="6c263-151">Se ci sono aggiornamenti su [dipendenze](system.md#refresh-policies) in corso quando dovrebbe iniziare un'esportazione pianificata, il sistema completerà prima le dipendenze e quindi eseguirà l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6c263-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="6c263-152">Puoi vedere quando un'esportazione è stata aggiornata l'ultima volta nella colonna **Aggiornato**.</span><span class="sxs-lookup"><span data-stu-id="6c263-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="6c263-153">Pianifica esportazioni</span><span class="sxs-lookup"><span data-stu-id="6c263-153">Schedule exports</span></span>

<span data-ttu-id="6c263-154">È possibile definire pianificazioni di aggiornamento personalizzate per singole esportazioni o più esportazioni contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="6c263-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="6c263-155">Il programma attualmente definito è elencato nella colonna **Pianificazione** dell'elenco delle esportazioni.</span><span class="sxs-lookup"><span data-stu-id="6c263-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="6c263-156">L'autorizzazione alla modifica della pianificazione è uguale a quello per la [modifica e la definizione delle esportazioni](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6c263-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="6c263-157">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c263-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c263-158">Seleziona l'esportazione che desideri pianificare.</span><span class="sxs-lookup"><span data-stu-id="6c263-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="6c263-159">Seleziona **Pianifica** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6c263-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="6c263-160">Nel riquadro **Pianifica esportazione**, imposta **Pianifica esecuzione** su **Attivato** per eseguire l'esportazione automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6c263-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="6c263-161">Imposta su **Disattivato** per aggiornarla manualmente.</span><span class="sxs-lookup"><span data-stu-id="6c263-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="6c263-162">Per le esportazioni aggiornate automaticamente, scegli un valore **Ricorrenza** e specificane i dettagli.</span><span class="sxs-lookup"><span data-stu-id="6c263-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="6c263-163">Il tempo definito si applica a tutte le istanze di una ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="6c263-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="6c263-164">È il momento in cui un'esportazione dovrebbe iniziare ad aggiornarsi.</span><span class="sxs-lookup"><span data-stu-id="6c263-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="6c263-165">Applica e attiva le modifiche selezionando **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6c263-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="6c263-166">Quando si modifica la pianificazione per più esportazioni, è necessario effettuare una selezione in **Mantieni o sostituisci le pianificazioni**:</span><span class="sxs-lookup"><span data-stu-id="6c263-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="6c263-167">**Mantieni singole pianificazioni**: mantiene la pianificazione definita in precedenza per le esportazioni selezionate e le disabilita o le abilita solamente.</span><span class="sxs-lookup"><span data-stu-id="6c263-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="6c263-168">**Definisci una nuova pianificazione per tutte le esportazioni selezionate**: sovrascrive le pianificazioni esistenti delle esportazioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="6c263-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="6c263-169">Eseguire le esportazioni su richiesta</span><span class="sxs-lookup"><span data-stu-id="6c263-169">Run exports on demand</span></span>

<span data-ttu-id="6c263-170">Per esportare i dati senza attendere un aggiornamento pianificato, vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c263-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="6c263-171">Per eseguire tutte le esportazioni, seleziona **Esegui tutto** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6c263-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="6c263-172">Questa azione eseguirà solo le esportazioni con una pianificazione attiva.</span><span class="sxs-lookup"><span data-stu-id="6c263-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="6c263-173">Per eseguire una singola esportazione, selezionala nell'elenco quindi scegli **Esegui** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6c263-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="6c263-174">È così che esegui le esportazioni senza una pianificazione attiva.</span><span class="sxs-lookup"><span data-stu-id="6c263-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="6c263-175">Rimuovere un'esportazione</span><span class="sxs-lookup"><span data-stu-id="6c263-175">Remove an Export</span></span>

1. <span data-ttu-id="6c263-176">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c263-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c263-177">Selezionare l'esportazione che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="6c263-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="6c263-178">Seleziona **Rimuovi** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6c263-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="6c263-179">Conferma la rimozione selezionando **Rimuovi** nella schermata di conferma.</span><span class="sxs-lookup"><span data-stu-id="6c263-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
