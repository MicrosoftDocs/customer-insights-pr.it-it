---
title: Relazioni tra entità e percorsi di entità
description: Crea e gestisci relazioni tra entità in più origini dati.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171169"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="dbd32-103">Relazioni tra entità</span><span class="sxs-lookup"><span data-stu-id="dbd32-103">Relationships between entities</span></span>

<span data-ttu-id="dbd32-104">Relazioni collega le entità e definisce un grafico dei tuoi dati quando le entità condividono un identificatore comune, una chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="dbd32-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="dbd32-105">È possibile fare riferimento a questa chiave esterna da un'entità a un'altra.</span><span class="sxs-lookup"><span data-stu-id="dbd32-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="dbd32-106">Le entità connesse abilitano la definizione di segmenti e misure in base a più origini dati.</span><span class="sxs-lookup"><span data-stu-id="dbd32-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="dbd32-107">Esistono tre tipi di Relazioni:</span><span class="sxs-lookup"><span data-stu-id="dbd32-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="dbd32-108">Relazioni di sistema non modificabili, create dal sistema come parte del processo di unificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="dbd32-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="dbd32-109">Relazioni ereditate non modificabili, create automaticamente dall'importazione di origini dati</span><span class="sxs-lookup"><span data-stu-id="dbd32-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="dbd32-110">Relazioni personalizzate modificabili, create e configurate dagli utenti</span><span class="sxs-lookup"><span data-stu-id="dbd32-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="dbd32-111">Relazioni di sistema non modificabili</span><span class="sxs-lookup"><span data-stu-id="dbd32-111">Non-editable system relationships</span></span>

<span data-ttu-id="dbd32-112">Durante l'unificazione dei dati, le relazioni del sistema vengono create automaticamente in base alla corrispondenza intelligente.</span><span class="sxs-lookup"><span data-stu-id="dbd32-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="dbd32-113">Queste relazioni aiutano a mettere in relazione i record del profilo cliente con i record corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="dbd32-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="dbd32-114">Il diagramma seguente illustra la creazione di tre relazioni basate sul sistema.</span><span class="sxs-lookup"><span data-stu-id="dbd32-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="dbd32-115">L'entità cliente è abbinata ad altre entità per produrre l'entità *Cliente* unificata.</span><span class="sxs-lookup"><span data-stu-id="dbd32-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagramma con percorsi di relazioni per l'entità cliente con tre relazioni 1-n.":::

- <span data-ttu-id="dbd32-117">La **relazione *CustomerToContact*** è stata creata tra l'entità *Cliente* e l'entità *Contatto*.</span><span class="sxs-lookup"><span data-stu-id="dbd32-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="dbd32-118">L'entità *Cliente* ottiene il campo chiave **Contact_contactID** per creare una relazione con il campo dell'entità chiave *Contatto* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="dbd32-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="dbd32-119">La **relazione *CustomerToAccount*** è stata creata tra l'entità *Cliente* e l'entità *Account*.</span><span class="sxs-lookup"><span data-stu-id="dbd32-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="dbd32-120">L'entità *Cliente* ottiene il campo chiave **Account_accountID** per creare una relazione con il campo entità chiave *Account* **accountID**.</span><span class="sxs-lookup"><span data-stu-id="dbd32-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="dbd32-121">La **relazione *CustomerToWebAccount*** è stata creata tra l'entità *Cliente* e l'entità *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="dbd32-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="dbd32-122">L'entità *Cliente* ottiene il campo chiave **WebAccount_webaccountID** per creare una relazione con il campo entità chiave *WebAccount* **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="dbd32-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="dbd32-123">Relazioni ereditate non modificabili</span><span class="sxs-lookup"><span data-stu-id="dbd32-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="dbd32-124">Durante il processo di acquisizione dei dati, il sistema controlla le origini dati per le relazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="dbd32-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="dbd32-125">Se non esiste alcuna relazione, il sistema le crea automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dbd32-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="dbd32-126">Queste relazioni sono utilizzate anche nei processi a valle.</span><span class="sxs-lookup"><span data-stu-id="dbd32-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="dbd32-127">Creare una relazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="dbd32-127">Create a custom relationship</span></span>

<span data-ttu-id="dbd32-128">La relazione consiste in una *entità di origine* contenente la chiave esterna e una *entità di destinazione* a cui fa riferimento la chiave esterna dell'entità di origine.</span><span class="sxs-lookup"><span data-stu-id="dbd32-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="dbd32-129">In Audience Insights, vai a **Dati** > **Relazioni**.</span><span class="sxs-lookup"><span data-stu-id="dbd32-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="dbd32-130">Seleziona **Nuova relazione**.</span><span class="sxs-lookup"><span data-stu-id="dbd32-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="dbd32-131">Nel riquadro **Nuova relazione**, immetti le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="dbd32-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Nuovo riquadro laterale delle relazioni con campi di input vuoti.":::

   - <span data-ttu-id="dbd32-133">**Nome relazione**: nome che riflette lo scopo della relazione.</span><span class="sxs-lookup"><span data-stu-id="dbd32-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="dbd32-134">Esempio: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="dbd32-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="dbd32-135">**Descrizione**: descrizione della relazione.</span><span class="sxs-lookup"><span data-stu-id="dbd32-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="dbd32-136">**Entità di origine**: Entità utilizzata come origine nella relazione.</span><span class="sxs-lookup"><span data-stu-id="dbd32-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="dbd32-137">Esempio: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="dbd32-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="dbd32-138">**Entità di destinazione**: Entità utilizzata come destinazione nella relazione.</span><span class="sxs-lookup"><span data-stu-id="dbd32-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="dbd32-139">Esempio: cliente.</span><span class="sxs-lookup"><span data-stu-id="dbd32-139">Example: Customer.</span></span>
   - <span data-ttu-id="dbd32-140">**Cardinalità di origine**: specificare la cardinalità dell'entità di origine.</span><span class="sxs-lookup"><span data-stu-id="dbd32-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="dbd32-141">La cardinalità descrive il numero di possibili elementi in un insieme.</span><span class="sxs-lookup"><span data-stu-id="dbd32-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="dbd32-142">Si riferisce sempre alla cardinalità di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dbd32-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="dbd32-143">Puoi scegliere tra **Uno** e **Molti**.</span><span class="sxs-lookup"><span data-stu-id="dbd32-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="dbd32-144">Sono supportate solo le relazioni molti-a-uno e uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="dbd32-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="dbd32-145">Molti a uno: più record di origine possono essere correlati a un record di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dbd32-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="dbd32-146">Esempio: più casi di supporto da un singolo cliente.</span><span class="sxs-lookup"><span data-stu-id="dbd32-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="dbd32-147">Uno a uno: un singolo record di origine è correlato a un record di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dbd32-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="dbd32-148">Esempio: un ID fedeltà per un singolo cliente.</span><span class="sxs-lookup"><span data-stu-id="dbd32-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="dbd32-149">Relazioni Molti a molti possono essere create utilizzando due relazioni molti a uno e un'entità di collegamento, che collega l'entità di origine e l'entità di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dbd32-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="dbd32-150">**Cardinalità destinazione**: seleziona la cardinalità dei record dell'entità di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dbd32-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="dbd32-151">**Campo chiave di origine**: il campo della chiave esterna nell'entità di origine.</span><span class="sxs-lookup"><span data-stu-id="dbd32-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="dbd32-152">Esempio: SupportCase potrebbe utilizzare CaseID come campo chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="dbd32-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="dbd32-153">**Campo chiave di destinazione**: il campo chiave dell'entità di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dbd32-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="dbd32-154">Esempio Il cliente potrebbe utilizzare il campo chiave **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="dbd32-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="dbd32-155">Seleziona **Salva** per creare la relazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dbd32-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="dbd32-156">Visualizza Relazioni</span><span class="sxs-lookup"><span data-stu-id="dbd32-156">View relationships</span></span>

<span data-ttu-id="dbd32-157">La pagina Relazioni elenca tutte le Relazioni che sono state create.</span><span class="sxs-lookup"><span data-stu-id="dbd32-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="dbd32-158">Ogni riga rappresenta una relazione, che include anche dettagli sull'entità di origine, sull'entità di destinazione e sulla cardinalità.</span><span class="sxs-lookup"><span data-stu-id="dbd32-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Elenco di relazioni e opzioni nella barra delle azioni della pagina Relazioni.":::

<span data-ttu-id="dbd32-160">Questa pagina offre una serie di opzioni per relazioni esistenti e nuove:</span><span class="sxs-lookup"><span data-stu-id="dbd32-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="dbd32-161">**Nuova relazione**: [Crea una relazione personalizzata](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="dbd32-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="dbd32-162">**Visualizzatore**: [Esplora il visualizzatore di relazioni](#explore-the-relationship-visualizer) per visualizzare un diagramma di rete delle relazioni esistenti e della relativa cardinalità.</span><span class="sxs-lookup"><span data-stu-id="dbd32-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="dbd32-163">**Filtra per**: Scegli il tipo di relazioni da mostrare nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dbd32-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="dbd32-164">**Cerca relazioni**: utilizza una ricerca basata sul testo nelle proprietà delle relazioni.</span><span class="sxs-lookup"><span data-stu-id="dbd32-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="dbd32-165">Esplora il visualizzatore di relazioni</span><span class="sxs-lookup"><span data-stu-id="dbd32-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="dbd32-166">Il visualizzatore delle relazioni consente di visualizzare un diagramma di rete delle relazioni esistenti tra le entità connesse e la relativa cardinalità.</span><span class="sxs-lookup"><span data-stu-id="dbd32-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="dbd32-167">Per personalizzare la visualizzazione, puoi modificare la posizione delle caselle trascinandole sulla canvas.</span><span class="sxs-lookup"><span data-stu-id="dbd32-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Screenshot del diagramma di rete del visualizzatore delle relazioni con le connessioni tra entità correlate.":::

<span data-ttu-id="dbd32-169">Opzioni disponibili:</span><span class="sxs-lookup"><span data-stu-id="dbd32-169">Available options:</span></span> 
- <span data-ttu-id="dbd32-170">**Esporta come immagine**: salva la vista corrente come file immagine.</span><span class="sxs-lookup"><span data-stu-id="dbd32-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="dbd32-171">**Passa al layout orizzontale/verticale**: modifica l'allineamento delle entità e delle relazioni.</span><span class="sxs-lookup"><span data-stu-id="dbd32-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="dbd32-172">**Modifica**: aggiorna le proprietà delle relazioni personalizzate nel riquadro di modifica e salva le modifiche.</span><span class="sxs-lookup"><span data-stu-id="dbd32-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="dbd32-173">Gestisci relazioni esistenti</span><span class="sxs-lookup"><span data-stu-id="dbd32-173">Manage existing relationships</span></span> 

<span data-ttu-id="dbd32-174">Nella pagina Relazioni, ogni relazione è rappresentata da una riga.</span><span class="sxs-lookup"><span data-stu-id="dbd32-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="dbd32-175">Seleziona una relazione e scegli una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="dbd32-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="dbd32-176">**Modifica**: aggiorna le proprietà delle relazioni personalizzate nel riquadro di modifica e salva le modifiche.</span><span class="sxs-lookup"><span data-stu-id="dbd32-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="dbd32-177">**Elimina**: elimina le relazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="dbd32-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="dbd32-178">**Visualizza**: visualizza le relazioni create ed ereditate dal sistema.</span><span class="sxs-lookup"><span data-stu-id="dbd32-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="dbd32-179">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="dbd32-179">Next step</span></span>

<span data-ttu-id="dbd32-180">Le relazioni di sistema e personalizzate vengono utilizzate per [creare segmenti](segments.md) in base a più origini dati che non sono più in silo.</span><span class="sxs-lookup"><span data-stu-id="dbd32-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
