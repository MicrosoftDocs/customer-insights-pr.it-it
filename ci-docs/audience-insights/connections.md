---
title: Connessioni ad altri servizi da Customer Insights.
description: Condividi i dati con altri servizi.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304977"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="633ee-103">Panoramica delle connessioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="633ee-103">Connections (preview) overview</span></span>

<span data-ttu-id="633ee-104">Le connessioni sono la chiave per abilitare la condivisione dei dati da e verso Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="633ee-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="633ee-105">Ogni connessione stabilisce la condivisione dei dati con un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="633ee-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="633ee-106">Le connessioni sono la base per [configurare arricchimenti di terze parti](enrichment-hub.md) e [configurare le esportazioni](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="633ee-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="633ee-107">La stessa connessione può essere utilizzata più volte.</span><span class="sxs-lookup"><span data-stu-id="633ee-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="633ee-108">Ad esempio, una connessione a Dynamics 365 Marketing funziona per più esportazioni e una connessione Leadspace può essere utilizzata per diversi arricchimenti.</span><span class="sxs-lookup"><span data-stu-id="633ee-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="633ee-109">Vai a **Amministratore** > **Connessioni** per creare e visualizzare le connessioni.</span><span class="sxs-lookup"><span data-stu-id="633ee-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="633ee-110">La scheda **Connessioni** mostra tutte le connessioni attive.</span><span class="sxs-lookup"><span data-stu-id="633ee-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="633ee-111">L'elenco mostra una riga per ogni connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="633ee-112">Ottieni una rapida panoramica, una descrizione e scopri cosa puoi fare con ciascuna opzione di estensibilità nella scheda **Individua**.</span><span class="sxs-lookup"><span data-stu-id="633ee-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="633ee-113">Esportazioni</span><span class="sxs-lookup"><span data-stu-id="633ee-113">Exports</span></span>

<span data-ttu-id="633ee-114">Solo gli amministratori possono configurare nuove connessioni, ma possono concedere l'accesso ai collaboratori per utilizzare le connessioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="633ee-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="633ee-115">Gli amministratori controllano dove possono andare i dati, i collaboratori definiscono il carico utile e la frequenza che si adatta alle loro esigenze.</span><span class="sxs-lookup"><span data-stu-id="633ee-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="633ee-116">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="633ee-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="633ee-117">Arricchimenti</span><span class="sxs-lookup"><span data-stu-id="633ee-117">Enrichments</span></span>

<span data-ttu-id="633ee-118">Solo gli amministratori possono configurare nuove connessioni, ma le connessioni create sono sempre disponibili sia per gli amministratori che per i collaboratori.</span><span class="sxs-lookup"><span data-stu-id="633ee-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="633ee-119">Gli amministratori gestiscono le credenziali e danno il consenso al trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="633ee-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="633ee-120">Le connessioni possono essere utilizzate per gli arricchimenti da amministratori e collaboratori.</span><span class="sxs-lookup"><span data-stu-id="633ee-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="633ee-121">Aggiungere una nuova connessione</span><span class="sxs-lookup"><span data-stu-id="633ee-121">Add a new connection</span></span>

<span data-ttu-id="633ee-122">Per aggiungere connessioni, devi avere le [autorizzazioni di amministratore](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="633ee-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="633ee-123">Se ti connetti ad altri servizi Microsoft, presumiamo che entrambi i servizi appartengano alla stessa organizzazione.</span><span class="sxs-lookup"><span data-stu-id="633ee-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="633ee-124">Vai ad **Amministratore** > **Connessioni (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="633ee-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="633ee-125">Passa alla scheda **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="633ee-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="633ee-126">Seleziona **Aggiungi connessione** per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="633ee-127">Scegli dal menu a tendina che tipo di connessione vuoi creare.</span><span class="sxs-lookup"><span data-stu-id="633ee-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="633ee-128">Nel riquadro **Configura connessione** fornisci i dettagli richiesti.</span><span class="sxs-lookup"><span data-stu-id="633ee-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="633ee-129">Il **nome visualizzato** e il tipo di connessione descrivono una connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="633ee-130">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo di questa connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="633ee-131">I campi esatti dipendono dal servizio a cui ti stai connettendo.</span><span class="sxs-lookup"><span data-stu-id="633ee-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="633ee-132">Puoi conoscere i dettagli di un tipo di connessione specifico nell'articolo sul servizio di destinazione.</span><span class="sxs-lookup"><span data-stu-id="633ee-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="633ee-133">Per creare la connessione seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="633ee-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="633ee-134">Puoi anche selezionare **Configura** su un riquadro della scheda **Scopri**.</span><span class="sxs-lookup"><span data-stu-id="633ee-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="633ee-135">Consentire ai collaboratori di utilizzare una connessione per le esportazioni</span><span class="sxs-lookup"><span data-stu-id="633ee-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="633ee-136">Quando si imposta o si modifica una connessione di esportazione, si sceglie a quali utenti è consentito utilizzare questa connessione specifica per la definizione delle [esportazioni](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="633ee-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="633ee-137">Per impostazione predefinita, una connessione è disponibile per gli utenti con un ruolo amministratore.</span><span class="sxs-lookup"><span data-stu-id="633ee-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="633ee-138">Puoi modificare questa impostazione in **Scegli chi può utilizzare questa connessione** e consentire agli utenti con il ruolo collaboratore di utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="633ee-139">I collaboratori non saranno in grado di visualizzare o modificare la connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="633ee-140">Vedranno solo il nome visualizzato e il tipo durante la creazione di un'esportazione.</span><span class="sxs-lookup"><span data-stu-id="633ee-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="633ee-141">Condividendo una connessione, consenti ai collaboratori di utilizzare una connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="633ee-142">I collaboratori vedranno le connessioni condivise quando configurano le esportazioni.</span><span class="sxs-lookup"><span data-stu-id="633ee-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="633ee-143">Possono gestire ogni esportazione che utilizza questa specifica connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="633ee-144">Puoi modificare questa impostazione mantenendo le esportazioni che sono già state definite dai collaboratori.</span><span class="sxs-lookup"><span data-stu-id="633ee-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="633ee-145">Modificare una connessione</span><span class="sxs-lookup"><span data-stu-id="633ee-145">Edit a connection</span></span>

1. <span data-ttu-id="633ee-146">Vai ad **Amministratore** > **Connessioni (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="633ee-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="633ee-147">Passa alla scheda **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="633ee-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="633ee-148">Seleziona i puntini di sospensione verticali per la connessione che vuoi modificare.</span><span class="sxs-lookup"><span data-stu-id="633ee-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="633ee-149">Seleziona **Modifica**</span><span class="sxs-lookup"><span data-stu-id="633ee-149">Select **Edit**.</span></span>

1. <span data-ttu-id="633ee-150">Modifica i valori che vuoi aggiornare e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="633ee-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="633ee-151">Rimuovere una connessione</span><span class="sxs-lookup"><span data-stu-id="633ee-151">Remove a connection</span></span>

<span data-ttu-id="633ee-152">Se la connessione che stai rimuovendo viene utilizzata da arricchimenti o esportazioni, devi prima scollegarli o rimuoverli.</span><span class="sxs-lookup"><span data-stu-id="633ee-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="633ee-153">La finestra di dialogo Rimuovi ti guiderà agli arricchimenti o alle esportazioni pertinenti.</span><span class="sxs-lookup"><span data-stu-id="633ee-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="633ee-154">Gli arricchimenti e le esportazioni distaccati diventano inattivi.</span><span class="sxs-lookup"><span data-stu-id="633ee-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="633ee-155">Li riattivi aggiungendo loro un'altra connessione nella pagina [Arricchimenti](enrichment-hub.md) o [Esportazioni](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="633ee-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="633ee-156">Vai ad **Amministratore** > **Connessioni (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="633ee-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="633ee-157">Passa alla scheda **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="633ee-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="633ee-158">Seleziona i puntini di sospensione verticali per la connessione che vuoi rimuovere.</span><span class="sxs-lookup"><span data-stu-id="633ee-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="633ee-159">Seleziona **Rimuovi** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="633ee-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="633ee-160">Viene visualizzata una finestra di dialogo di conferma.</span><span class="sxs-lookup"><span data-stu-id="633ee-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="633ee-161">Se sono presenti arricchimenti o esportazioni che utilizzano questa connessione, seleziona il pulsante per vedere cosa sta utilizzando la connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="633ee-162">**Esportazioni:** Puoi scegliere di rimuovere o disconnettere le esportazioni per poter rimuovere la connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="633ee-163">Per disconnettere un'esportazione, gli amministratori possono utilizzare l'azione **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="633ee-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="633ee-164">Questa azione è disponibile per esportazioni singole e multiple selezionate.</span><span class="sxs-lookup"><span data-stu-id="633ee-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="633ee-165">Scollegandoti mantieni la configurazione di esportazione, ma non verrà eseguita fino a quando non verrà aggiunta un'altra connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="633ee-166">**Arricchimenti:** Puoi scegliere di rimuovere o disattivare gli arricchimenti per poter rimuovere la connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="633ee-167">Una volta che la connessione non ha più dipendenze, torna a **Amministratore** > **Connessioni** e prova a rimuovere di nuovo la connessione.</span><span class="sxs-lookup"><span data-stu-id="633ee-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="633ee-168">Per confermare l'eliminazione seleziona **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="633ee-168">To confirm the deletion, select **Remove**.</span></span>

