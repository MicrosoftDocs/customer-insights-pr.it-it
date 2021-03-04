---
title: Mappare le entità per l'unificazione dei dati
description: Mappare i dati per creare profili cliente unificati.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267040"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="c8e0c-103">Mappare entità e attributi</span><span class="sxs-lookup"><span data-stu-id="c8e0c-103">Map entities and attributes</span></span>

<span data-ttu-id="c8e0c-104">Un **mapping** è la prima fase del processo di unificazione di Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="c8e0c-105">Il mapping comporta tre fasi:</span><span class="sxs-lookup"><span data-stu-id="c8e0c-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="c8e0c-106">*Selezione entità*: identifica le entità combinabili che portano a un set di dati con informazioni più complete sui clienti.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="c8e0c-107">*Selezione attributi*: per ogni entità, identifica le colonne che vuoi combinare e riconciliare nelle fasi di *corrispondenza* e *unione*.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="c8e0c-108">Queste colonne sono denominate *Attributi*.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="c8e0c-109">*Selezione chiave primaria e tipo semantico*: per ogni entità, identifica un attributo che desideri definire come chiave primaria per quell'entità, e per ogni attributo, identifica un tipo semantico che meglio descrive quell'attributo.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="c8e0c-110">Per ulteriori informazioni sul flusso generale di unificazione dei dati, vedi [Unificare](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c8e0c-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="c8e0c-111">Selezionare le prime entità</span><span class="sxs-lookup"><span data-stu-id="c8e0c-111">Select the first entities</span></span>

1. <span data-ttu-id="c8e0c-112">In Audience Insights, vai a **Dati** > **Unifica** > **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="c8e0c-113">Inizia la fase di mapping selezionando **Seleziona entità**.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="c8e0c-114">Seleziona le entità e gli attributi che desideri utilizzare nelle fasi *corrispondenza* e *unione*.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="c8e0c-115">Puoi selezionare gli attributi necessari individualmente da un'entità o includere tutti gli attributi da un'entità selezionando la casella di controllo **Includi tutti i campi** a livello di entità.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="c8e0c-116">È consigliabile selezionare almeno due entità per trarre vantaggio dal processo di unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8e0c-117">![Esempio di Aggiungi entità](media/data-manager-configure-map-add-entities-example.png "Esempio di Aggiungi entità")</span><span class="sxs-lookup"><span data-stu-id="c8e0c-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="c8e0c-118">In questo esempio, stiamo aggiungendo le entità **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="c8e0c-119">Scegliendo queste entità, puoi ottenere informazioni dettagliate che ti indicano quali clienti online sono membri del programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="c8e0c-120">Puoi cercare parole chiave in tutti gli attributi e le entità per selezionare gli attributi richiesti che desideri mappare.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8e0c-121">![Esempio di campi di ricerca](media/data-manager-configure-map-search-fields-example.png "Esempio di campi di ricerca")</span><span class="sxs-lookup"><span data-stu-id="c8e0c-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="c8e0c-122">Seleziona **Applica** per confermare le selezioni.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="c8e0c-123">Selezionare la chiave primaria e il tipo semantico per gli attributi</span><span class="sxs-lookup"><span data-stu-id="c8e0c-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="c8e0c-124">Dopo aver selezionato le entità, la pagina **Mapping** elenca le entità selezionate per la revisione.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="c8e0c-125">Definisci la chiave primaria per un'entità e identifica il tipo semantico per un attributo nell'entità.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="c8e0c-126">**Chiave primaria** : seleziona un attributo come chiave primaria per ogni entità.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="c8e0c-127">Affinché un attributo sia una chiave primaria valida, non deve includere valori duplicati, valori mancanti o valori null.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="c8e0c-128">Gli attributi del tipo di dati String, integer e GUID sono supportati come chiavi primarie e verranno visualizzati in un campo da cui scegliere.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="c8e0c-129">**Tipo semantico attributi**: categorie degli attributi, ad esempio indirizzo e-mail o nome.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="c8e0c-130">Per utilizzare modelli di intelligenza artificiale per previsione intelligente della semantica, risparmiare tempo e migliorare la precisione, imposta **Mappatura intelligente** su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="c8e0c-131">La mappatura intelligente evidenzia l'elemento consigliato semantico basato su AI nel campo **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="c8e0c-132">Se lo imposti su **Disattivato**, vedrai gli elementi consigliati sulle mappe regolari.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="c8e0c-133">È possibile selezionare qualsiasi tipo semantico dall'elenco di opzioni disponibile e sovrascrivere la selezione suggerita.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8e0c-134">![Tipo di attributo e previsione semantica](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipo di attributo e previsione semantica")</span><span class="sxs-lookup"><span data-stu-id="c8e0c-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="c8e0c-135">È anche possibile aggiungere un tipo semantico personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="c8e0c-136">Seleziona il campo del tipo per un attributo e digita il nome del tipo semantico personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="c8e0c-137">In tal modo, puoi anche modificare i tipi di attributo identificati dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="c8e0c-138">Tutti gli attributi per i quali un tipo semantico viene identificato automaticamente sono raggruppati nella sezione **Rivedi campi mappati**.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="c8e0c-139">Esamina questi attributi e i relativi tipi semantici in quanto verranno utilizzati per combinare le tue entità nella fase di unione deell'unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="c8e0c-140">Gli attributi che non vengono mappati automaticamente a un tipo semantico vengono raggruppati nella sezione **Definisci i dati nei campi non mappati**.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="c8e0c-141">Seleziona il campo del tipo semantico per gli attributi non mappati o immetti il nome del tipo di attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8e0c-142">![Chiave primaria e tipo di attributo](media/data-manager-configure-map-add-attributes.png "Chiave primaria e tipo di attributo")</span><span class="sxs-lookup"><span data-stu-id="c8e0c-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="c8e0c-143">Un campo deve essere mappato al tipo semantico Person.FullName per popolare il nome del cliente nella scheda cliente.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="c8e0c-144">Altrimenti, le schede cliente appariranno senza nome.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="c8e0c-145">Aggiungere e rimuovere attributi ed entità</span><span class="sxs-lookup"><span data-stu-id="c8e0c-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="c8e0c-146">In **Unifica** > **Mapping**, seleziona **Modifica campi**.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="c8e0c-147">Nel riquadro **Modifica campi**, aggiungi o rimuovi attributi ed entità.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="c8e0c-148">Usa la funzionalità di ricerca o scorri per trovare e selezionare gli attributi e le entità che ti interessano.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="c8e0c-149">Non puoi rimuovere un attributo o un'entità se è già stata trovata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8e0c-150">![Aggiungere o rimuovere attributi](media/configure-data-map-edit.png "Aggiungere o rimuovere attributi")</span><span class="sxs-lookup"><span data-stu-id="c8e0c-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="c8e0c-151">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="c8e0c-152">Aggiungere immagini ai profili</span><span class="sxs-lookup"><span data-stu-id="c8e0c-152">Add images to profiles</span></span>

<span data-ttu-id="c8e0c-153">Se un'entità contiene URL per immagini o loghi di profilo disponibili pubblicamente, puoi aggiungerli al profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="c8e0c-154">Seleziona l'entità e trova il campo che contiene l'URL dell'immagine del profilo.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="c8e0c-155">Nel campo di input **Tipo**, immetti manualmente il valore seguente:</span><span class="sxs-lookup"><span data-stu-id="c8e0c-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="c8e0c-156">Per una persona: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="c8e0c-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="c8e0c-157">Per un'organizzazione: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="c8e0c-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="c8e0c-158">Continua con i passaggi di unificazione e assicurati che l'attributo che contiene l'URL dell'immagine venga aggiunto anche nel passaggio [Unione](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="c8e0c-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="c8e0c-159">Impostare attributi per le organizzazioni</span><span class="sxs-lookup"><span data-stu-id="c8e0c-159">Set attributes for organizations</span></span>

<span data-ttu-id="c8e0c-160">Per le organizzazioni (anteprima), il tipo di attributo deve essere mappato a "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="c8e0c-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8e0c-161">![Chiave primaria e tipo di attributo B2B](media/configure-data-map-edit-b2b.png "Chiave primaria e tipo di attributo B2B")</span><span class="sxs-lookup"><span data-stu-id="c8e0c-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="c8e0c-162">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c8e0c-162">Next step</span></span>

<span data-ttu-id="c8e0c-163">Come parte del processo di unificazione dei dati, vai alla pagina **Corrispondenza**.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="c8e0c-164">Visita [**Corrispondenza**](match-entities.md) per informazioni su questa fase.</span><span class="sxs-lookup"><span data-stu-id="c8e0c-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="c8e0c-165">Guarda il seguente video: [Guida introduttiva: Creazione di un profilo cliente unificato](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="c8e0c-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]