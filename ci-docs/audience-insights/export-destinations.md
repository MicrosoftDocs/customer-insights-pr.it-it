---
title: Esportare i dati da Customer Insights
description: Gestisci le esportazioni per condividere i dati.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016619"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="ed210-103">Panoramica delle esportazioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="ed210-103">Exports (preview) overview</span></span>

<span data-ttu-id="ed210-104">La pagina **Esportazioni** mostra tutte le esportazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="ed210-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="ed210-105">Le esportazioni condividono dati specifici con varie applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ed210-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="ed210-106">Possono includere profili o entità del cliente, schemi e dettagli di mappatura.</span><span class="sxs-lookup"><span data-stu-id="ed210-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="ed210-107">Ogni esportazione richiede una [connessione, impostata da un amministratore, per gestire l'autenticazione e l'accesso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="ed210-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="ed210-108">Vai a **Dati** > **Esportazioni** per visualizzare la pagina delle esportazioni.</span><span class="sxs-lookup"><span data-stu-id="ed210-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="ed210-109">Tutti i ruoli utente hanno accesso per visualizzare le esportazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="ed210-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="ed210-110">Utilizza il campo di ricerca nella barra dei comandi per trovare le esportazioni in base al nome, al nome della connessione o al tipo di connessione.</span><span class="sxs-lookup"><span data-stu-id="ed210-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="ed210-111">Configurare una nuova esportazione</span><span class="sxs-lookup"><span data-stu-id="ed210-111">Set up a new export</span></span>

<span data-ttu-id="ed210-112">Per impostare o modificare un'esportazione, è necessario avere delle connessioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="ed210-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="ed210-113">Le connessioni dipendono dal tuo [ruolo utente](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="ed210-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="ed210-114">Gli amministratori hanno accesso a tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="ed210-114">Administrators have access to all connections.</span></span> <span data-ttu-id="ed210-115">Possono anche creare nuove connessioni durante la configurazione di un'esportazione.</span><span class="sxs-lookup"><span data-stu-id="ed210-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="ed210-116">I collaboratori possono avere accesso a connessioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="ed210-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="ed210-117">Dipendono dagli amministratori per configurare e condividere le connessioni.</span><span class="sxs-lookup"><span data-stu-id="ed210-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="ed210-118">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ed210-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="ed210-119">I visualizzatori possono solo visualizzare le esportazioni esistenti ma non crearle.</span><span class="sxs-lookup"><span data-stu-id="ed210-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="ed210-120">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="ed210-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ed210-121">Seleziona **Aggiungi esportazione** per creare una nuova destinazione di esportazione.</span><span class="sxs-lookup"><span data-stu-id="ed210-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="ed210-122">Nel riquadro **Imposta esportazione** seleziona la connessione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ed210-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="ed210-123">[Le connessioni](connections.md) sono gestite dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="ed210-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="ed210-124">Fornisci i dettagli richiesti e seleziona **Salva** per creare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="ed210-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="ed210-125">Modificare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="ed210-125">Edit an export</span></span>

1. <span data-ttu-id="ed210-126">Seleziona i puntini di sospensione verticali per la destinazione di esportazione che vuoi modificare.</span><span class="sxs-lookup"><span data-stu-id="ed210-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="ed210-127">Dal menu a discesa seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ed210-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="ed210-128">Modifica i valori che vuoi aggiornare e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ed210-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="ed210-129">Visualizzare le esportazioni ed esportare i dettagli</span><span class="sxs-lookup"><span data-stu-id="ed210-129">View Exports and export details</span></span>

<span data-ttu-id="ed210-130">Dopo aver creato le destinazioni di esportazione, vengono elencate in **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="ed210-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="ed210-131">Tutti gli utenti possono vedere quali dati sono condivisi e il loro stato più recente.</span><span class="sxs-lookup"><span data-stu-id="ed210-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="ed210-132">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="ed210-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ed210-133">Gli utenti senza autorizzazioni di modifica selezionano **Visualizza** invece di **Modifica** per vedere i dettagli dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="ed210-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="ed210-134">Questo riquadro laterale mostra la configurazione di questa esportazione.</span><span class="sxs-lookup"><span data-stu-id="ed210-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="ed210-135">Senza le autorizzazioni di modifica, non è possibile modificare i valori.</span><span class="sxs-lookup"><span data-stu-id="ed210-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="ed210-136">Seleziona **Chiudi** per tornare alla pagina delle esportazioni.</span><span class="sxs-lookup"><span data-stu-id="ed210-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="ed210-137">Eseguire le esportazioni su richiesta</span><span class="sxs-lookup"><span data-stu-id="ed210-137">Run exports on demand</span></span>

<span data-ttu-id="ed210-138">Dopo aver configurato un'esportazione, verrà eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab) fintanto che ha una connessione funzionante.</span><span class="sxs-lookup"><span data-stu-id="ed210-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="ed210-139">Per esportare i dati senza attendere un aggiornamento pianificato, vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="ed210-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="ed210-140">è possibile procedere in due modi:</span><span class="sxs-lookup"><span data-stu-id="ed210-140">You have two options:</span></span>

- <span data-ttu-id="ed210-141">Per eseguire tutte le esportazioni, seleziona **Esegui tutto** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ed210-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="ed210-142">Per eseguire una singola esportazione, seleziona i puntini di sospensione (...) su un elemento dell'elenco e quindi scegli **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ed210-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="ed210-143">Rimuovere un'esportazione</span><span class="sxs-lookup"><span data-stu-id="ed210-143">Remove an Export</span></span>

1. <span data-ttu-id="ed210-144">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="ed210-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ed210-145">Seleziona i puntini di sospensione verticali per l'esportazione che vuoi rimuovere.</span><span class="sxs-lookup"><span data-stu-id="ed210-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="ed210-146">Seleziona **Rimuovi** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="ed210-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="ed210-147">Conferma la rimozione selezionando **Rimuovi** nella schermata di conferma.</span><span class="sxs-lookup"><span data-stu-id="ed210-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
