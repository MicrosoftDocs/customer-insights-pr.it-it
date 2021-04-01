---
title: Relazioni tra entità e percorsi di entità
description: Crea e gestisci relazioni tra entità in più origini dati.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595217"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="71c2e-103">Relazioni tra entità</span><span class="sxs-lookup"><span data-stu-id="71c2e-103">Relationships between entities</span></span>

<span data-ttu-id="71c2e-104">Le relaizoni consentono di connettere entità e a generare un grafico dei tuoi dati quando le entità condividono un identificatore comune (chiave esterna) a cui è possibile fare riferimento da un'entità all'altra.</span><span class="sxs-lookup"><span data-stu-id="71c2e-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="71c2e-105">Le entità connesse consentono di definire segmenti e misure in base a più origini dati.</span><span class="sxs-lookup"><span data-stu-id="71c2e-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="71c2e-106">Esistono due tipi di relazioni.</span><span class="sxs-lookup"><span data-stu-id="71c2e-106">There are two types of relationships.</span></span> <span data-ttu-id="71c2e-107">Relazioni di sistema non modificabili che vengono create automaticamente e relazioni personalizzate create e configurate dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="71c2e-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="71c2e-108">Durante i processi di corrispondenza e unione, le relazioni di sistema vengono create in background in base alla corrispondenza intelligente.</span><span class="sxs-lookup"><span data-stu-id="71c2e-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="71c2e-109">Queste relazioni aiutano a mettere in relazione i record del profilo cliente con i record di altre entità corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="71c2e-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="71c2e-110">Il diagramma seguente illustra la creazione di tre relazioni di sistema quando viene eseguita la corrispondenza tra l'entità cliente ed altre entità per produrre l'entità Profilo cliente finale.</span><span class="sxs-lookup"><span data-stu-id="71c2e-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="71c2e-111">![Creazione della relazione](media/relationships-entities-merge.png "Creazione della relazione")</span><span class="sxs-lookup"><span data-stu-id="71c2e-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="71c2e-112">La **relazione *CustomerToContact*** è stata creata tra l'entità cliente e l'entità contatto.</span><span class="sxs-lookup"><span data-stu-id="71c2e-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="71c2e-113">L'entità cliente ottiene il campo chiave **Contact_contactId** per creare una relazione con il campo Chiave entità contatto **contactID**.</span><span class="sxs-lookup"><span data-stu-id="71c2e-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="71c2e-114">La **relazione *CustomerToAccount*** è stata creata tra l'entità cliente e l'entità account.</span><span class="sxs-lookup"><span data-stu-id="71c2e-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="71c2e-115">L'entità cliente ottiene il campo chiave **Account_accountId** per creare una relazione con il campo Chiave entità account **accountID**.</span><span class="sxs-lookup"><span data-stu-id="71c2e-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="71c2e-116">La **relazione *CustomerToWebAccount*** è stata creata tra l'entità cliente e l'entità WebAccount.</span><span class="sxs-lookup"><span data-stu-id="71c2e-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="71c2e-117">L'entità cliente ottiene il campo chiave **WebAccount_webaccountId** per creare una relazione con il campo Chiave entità WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="71c2e-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="71c2e-118">Creare una relazione</span><span class="sxs-lookup"><span data-stu-id="71c2e-118">Create a relationship</span></span>

<span data-ttu-id="71c2e-119">Definire relazioni personalizzate nella pagina **Relazioni**.</span><span class="sxs-lookup"><span data-stu-id="71c2e-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="71c2e-120">Ogni relazione è costituita da un'entità di origine (l'entità che detiene la chiave esterna) e un'entità di destinazione (l'entità a cui punta la chiave esterna dell'entità di origine).</span><span class="sxs-lookup"><span data-stu-id="71c2e-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="71c2e-121">In Audience Insights, vai a **Dati** > **Relazioni**.</span><span class="sxs-lookup"><span data-stu-id="71c2e-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="71c2e-122">Seleziona **Nuova relazione**.</span><span class="sxs-lookup"><span data-stu-id="71c2e-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="71c2e-123">Nel riquadro **Aggiungi relazione**, immetti le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="71c2e-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="71c2e-124">![Inserire i dettagli della relazione](media/relationships-add.png "Inserire i dettagli della relazione")</span><span class="sxs-lookup"><span data-stu-id="71c2e-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="71c2e-125">**Nome relazione**: nome che riflette lo scopo della relazione (ad esempio, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="71c2e-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="71c2e-126">**Descrizione**: descrizione della relazione.</span><span class="sxs-lookup"><span data-stu-id="71c2e-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="71c2e-127">**Entità origine**: seleziona l'entità utilizzata come origine nella relazione (ad esempio, WebLog).</span><span class="sxs-lookup"><span data-stu-id="71c2e-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="71c2e-128">**Cardinalità**: seleziona la cardinalità dei record dell'entità di origine.</span><span class="sxs-lookup"><span data-stu-id="71c2e-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="71c2e-129">Ad esempio, "molti" significa che più record Weblog sono correlati a un WebAccount.</span><span class="sxs-lookup"><span data-stu-id="71c2e-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="71c2e-130">**Campo chiave origine**: rappresenta il campo chiave esterna nell'entità di origine.</span><span class="sxs-lookup"><span data-stu-id="71c2e-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="71c2e-131">Ad esempio, WebLog ha il campo chiave esterna **accountId**.</span><span class="sxs-lookup"><span data-stu-id="71c2e-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="71c2e-132">**Entità di destinazione**: seleziona l'entità utilizzata come destinazione nella relazione (ad esempio, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="71c2e-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="71c2e-133">**Cardinalità destinazione**: seleziona la cardinalità dei record dell'entità di destinazione.</span><span class="sxs-lookup"><span data-stu-id="71c2e-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="71c2e-134">Ad esempio, "uno" significa che più record Weblog sono correlati a un WebAccount.</span><span class="sxs-lookup"><span data-stu-id="71c2e-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="71c2e-135">**Campo chiave destinazione**: questo campo rappresenta il campo chiave dell'entità di destinazione.</span><span class="sxs-lookup"><span data-stu-id="71c2e-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="71c2e-136">Ad esempio, WebAccount ha il campo chiave **accountId**.</span><span class="sxs-lookup"><span data-stu-id="71c2e-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="71c2e-137">Sono supportate solo le relazioni molti-a-uno e uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="71c2e-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="71c2e-138">Le relazioni molti-a-molti possono essere create usando due relazioni molti-a-uno e un'entità di collegamento (un'entità utilizzata per connettere l'entità di origine e l'entità di destinazione).</span><span class="sxs-lookup"><span data-stu-id="71c2e-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="71c2e-139">Eliminare una relazione</span><span class="sxs-lookup"><span data-stu-id="71c2e-139">Delete a relationship</span></span>

1. <span data-ttu-id="71c2e-140">In Audience Insights, vai a **Dati** > **Relazioni**.</span><span class="sxs-lookup"><span data-stu-id="71c2e-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="71c2e-141">Seleziona le caselle di controllo per le relazioni che vuoi eliminare.</span><span class="sxs-lookup"><span data-stu-id="71c2e-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="71c2e-142">Seleziona **Elimina** nella parte superiore della tabella **Relazioni**.</span><span class="sxs-lookup"><span data-stu-id="71c2e-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="71c2e-143">Conferma l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="71c2e-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="71c2e-144">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="71c2e-144">Next step</span></span>

<span data-ttu-id="71c2e-145">Le relazioni di sistema e personalizzate vengono utilizzate per creare segmenti in base a più origini dati che non sono più in silo.</span><span class="sxs-lookup"><span data-stu-id="71c2e-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="71c2e-146">Per ulteriori informazioni, vedi [Segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="71c2e-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]