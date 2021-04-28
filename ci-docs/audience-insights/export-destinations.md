---
title: Esportare i dati da Customer Insights
description: Gestisci le esportazioni per condividere i dati.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896148"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="83c0c-103">Panoramica delle esportazioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="83c0c-103">Exports (preview) overview</span></span>

<span data-ttu-id="83c0c-104">La pagina **Esportazioni** mostra tutte le esportazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="83c0c-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="83c0c-105">Le esportazioni condividono dati specifici con varie applicazioni.</span><span class="sxs-lookup"><span data-stu-id="83c0c-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="83c0c-106">Possono includere profili o entità del cliente, schemi e dettagli di mappatura.</span><span class="sxs-lookup"><span data-stu-id="83c0c-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="83c0c-107">Ogni esportazione richiede una [connessione, impostata da un amministratore, per gestire l'autenticazione e l'accesso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="83c0c-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="83c0c-108">Fino a marzo 2021, le esportazioni creavano automaticamente una connessione al servizio corrispondente.</span><span class="sxs-lookup"><span data-stu-id="83c0c-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="83c0c-109">Le esportazioni ora richiedono una [connessione, creata e condivisa da un amministratore](connections.md) prima di poterle creare.</span><span class="sxs-lookup"><span data-stu-id="83c0c-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="83c0c-110">Vai a **Dati** > **Esportazioni** per visualizzare la pagina delle esportazioni.</span><span class="sxs-lookup"><span data-stu-id="83c0c-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="83c0c-111">Tutti i ruoli utente hanno accesso per visualizzare le esportazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="83c0c-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="83c0c-112">Utilizza il campo di ricerca nella barra dei comandi per trovare le esportazioni in base al nome, al nome della connessione o al tipo di connessione.</span><span class="sxs-lookup"><span data-stu-id="83c0c-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="83c0c-113">Configurare una nuova esportazione</span><span class="sxs-lookup"><span data-stu-id="83c0c-113">Set up a new export</span></span>

<span data-ttu-id="83c0c-114">Per impostare o modificare un'esportazione, è necessario avere delle connessioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="83c0c-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="83c0c-115">Le connessioni dipendono dal tuo [ruolo utente](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="83c0c-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="83c0c-116">Gli amministratori hanno accesso a tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="83c0c-116">Administrators have access to all connections.</span></span> <span data-ttu-id="83c0c-117">Possono anche creare nuove connessioni durante la configurazione di un'esportazione.</span><span class="sxs-lookup"><span data-stu-id="83c0c-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="83c0c-118">I collaboratori possono avere accesso a connessioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="83c0c-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="83c0c-119">Dipendono dagli amministratori per configurare e condividere le connessioni.</span><span class="sxs-lookup"><span data-stu-id="83c0c-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="83c0c-120">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="83c0c-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="83c0c-121">I visualizzatori possono solo visualizzare le esportazioni esistenti ma non crearle.</span><span class="sxs-lookup"><span data-stu-id="83c0c-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="83c0c-122">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="83c0c-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="83c0c-123">Seleziona **Aggiungi esportazione** per creare una nuova destinazione di esportazione.</span><span class="sxs-lookup"><span data-stu-id="83c0c-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="83c0c-124">Nel riquadro **Imposta esportazione** seleziona la connessione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="83c0c-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="83c0c-125">[Le connessioni](connections.md) sono gestite dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="83c0c-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="83c0c-126">Fornisci i dettagli richiesti e seleziona **Salva** per creare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="83c0c-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="83c0c-127">Modificare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="83c0c-127">Edit an export</span></span>

1. <span data-ttu-id="83c0c-128">Seleziona i puntini di sospensione verticali per la destinazione di esportazione che vuoi modificare.</span><span class="sxs-lookup"><span data-stu-id="83c0c-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="83c0c-129">Dal menu a discesa seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="83c0c-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="83c0c-130">Modifica i valori che vuoi aggiornare e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="83c0c-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="83c0c-131">Visualizzare le esportazioni ed esportare i dettagli</span><span class="sxs-lookup"><span data-stu-id="83c0c-131">View Exports and export details</span></span>

<span data-ttu-id="83c0c-132">Dopo aver creato le destinazioni di esportazione, vengono elencate in **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="83c0c-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="83c0c-133">Tutti gli utenti possono vedere quali dati sono condivisi e il loro stato più recente.</span><span class="sxs-lookup"><span data-stu-id="83c0c-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="83c0c-134">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="83c0c-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="83c0c-135">Gli utenti senza autorizzazioni di modifica selezionano **Visualizza** invece di **Modifica** per vedere i dettagli dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="83c0c-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="83c0c-136">Questo riquadro laterale mostra la configurazione di questa esportazione.</span><span class="sxs-lookup"><span data-stu-id="83c0c-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="83c0c-137">Senza le autorizzazioni di modifica, non è possibile modificare i valori.</span><span class="sxs-lookup"><span data-stu-id="83c0c-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="83c0c-138">Seleziona **Chiudi** per tornare alla pagina delle esportazioni.</span><span class="sxs-lookup"><span data-stu-id="83c0c-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="83c0c-139">Eseguire le esportazioni su richiesta</span><span class="sxs-lookup"><span data-stu-id="83c0c-139">Run exports on demand</span></span>

<span data-ttu-id="83c0c-140">Dopo aver configurato un'esportazione, verrà eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab) fintanto che ha una connessione funzionante.</span><span class="sxs-lookup"><span data-stu-id="83c0c-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="83c0c-141">Per esportare i dati senza attendere un aggiornamento pianificato, vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="83c0c-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="83c0c-142">è possibile procedere in due modi:</span><span class="sxs-lookup"><span data-stu-id="83c0c-142">You have two options:</span></span>

- <span data-ttu-id="83c0c-143">Per eseguire tutte le esportazioni, seleziona **Esegui tutto** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="83c0c-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="83c0c-144">Per eseguire una singola esportazione, seleziona i puntini di sospensione (...) su un elemento dell'elenco e quindi scegli **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="83c0c-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="83c0c-145">Rimuovere un'esportazione</span><span class="sxs-lookup"><span data-stu-id="83c0c-145">Remove an Export</span></span>

1. <span data-ttu-id="83c0c-146">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="83c0c-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="83c0c-147">Seleziona i puntini di sospensione verticali per l'esportazione che vuoi rimuovere.</span><span class="sxs-lookup"><span data-stu-id="83c0c-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="83c0c-148">Seleziona **Rimuovi** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="83c0c-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="83c0c-149">Conferma la rimozione selezionando **Rimuovi** nella schermata di conferma.</span><span class="sxs-lookup"><span data-stu-id="83c0c-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
