---
title: Visualizzare profili cliente
description: Ottieni una visualizzazione combinata dei dati cliente unificati.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: c9adb4d7db74573d0512ae7a68a0e7ab51c994a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304609"
---
# <a name="customer-profiles"></a><span data-ttu-id="18421-103">Profili cliente</span><span class="sxs-lookup"><span data-stu-id="18421-103">Customer profiles</span></span>

<span data-ttu-id="18421-104">La pagina **Clienti** mostra una visualizzazione combinata dei tuoi clienti, basata sui dati del profilo di [tutte le origini dati](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="18421-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="18421-105">I profili dei clienti sono disponibili una volta [creata l'entità cliente unificata](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="18421-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="18421-106">Assicurati di completare il processo di unificazione dei dati per ottenere visualizzazioni più complete dei tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="18421-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="18421-107">La pagina consente anche di cercare clienti.</span><span class="sxs-lookup"><span data-stu-id="18421-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="18421-108">I clienti possono essere persone fisiche o organizzazioni (anteprima).</span><span class="sxs-lookup"><span data-stu-id="18421-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="18421-109">Ogni profilo cliente o organizzazione è rappresentato da un riquadro.</span><span class="sxs-lookup"><span data-stu-id="18421-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="18421-110">Seleziona un riquadro per visualizzare ulteriori informazioni su quel cliente o organizzazione specifici.</span><span class="sxs-lookup"><span data-stu-id="18421-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="18421-111">Utilizza i controlli di impaginazione nella parte inferiore della pagina per visualizzare altri record.</span><span class="sxs-lookup"><span data-stu-id="18421-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="18421-112">![Profili cliente B2C](media/profiles-customers.png "Profili cliente B2C")</span><span class="sxs-lookup"><span data-stu-id="18421-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="18421-113">Organizzazioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="18421-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="18421-114">![Profili cliente B2B](media/profile-customers-b2b.png "Profili cliente B2B")</span><span class="sxs-lookup"><span data-stu-id="18421-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="18421-115">Se non riesci a vedere i riquadri quando selezioni **Clienti** nello spostamento, l'amministratore deve [definire almeno un attributo ricercabile](search-filter-index.md) nell'**indice di ricerca e filtro**.</span><span class="sxs-lookup"><span data-stu-id="18421-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="18421-116">Cercare clienti</span><span class="sxs-lookup"><span data-stu-id="18421-116">Search for customers</span></span>

<span data-ttu-id="18421-117">Cerca i clienti inserendo un nome o un altro attributo nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="18421-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="18421-118">La ricerca funziona solo all'interno dell'entità Profilo cliente creata durante il processo di unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="18421-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="18421-119">Come amministratore, puoi configurare gli attributi ricercabili mediante la pagina **Indicizzazione ricerca e filtro**.</span><span class="sxs-lookup"><span data-stu-id="18421-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="18421-120">Per ulteriori informazioni, vedi [Gestisci l'indice di ricerca e filtro](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="18421-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="18421-121">Filtrare i clienti</span><span class="sxs-lookup"><span data-stu-id="18421-121">Filter customers</span></span>

<span data-ttu-id="18421-122">Puoi filtrare i clienti in base ai campi dell'entità Profilo cliente.</span><span class="sxs-lookup"><span data-stu-id="18421-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="18421-123">Simile alla ricerca, l'amministratore dovrà prima definire i campi come filtrabili utilizzando la pagina **Indicizzazione ricerca e filtro**.</span><span class="sxs-lookup"><span data-stu-id="18421-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="18421-124">Seleziona **Filtra** nella pagina **Clienti**.</span><span class="sxs-lookup"><span data-stu-id="18421-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="18421-125">Seleziona le caselle di controllo accanto agli attributi in base a cui vuoi filtrare i clienti.</span><span class="sxs-lookup"><span data-stu-id="18421-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="18421-126">![Profili cliente](media/profiles-customers3.png "Profili cliente")</span><span class="sxs-lookup"><span data-stu-id="18421-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="18421-127">Rimuovi i filtri selezionando **Cancella filtri** nella pagina **Clienti**.</span><span class="sxs-lookup"><span data-stu-id="18421-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="18421-128">Pagina Dettagli cliente</span><span class="sxs-lookup"><span data-stu-id="18421-128">Customer details page</span></span>

<span data-ttu-id="18421-129">Seleziona uno dei riquadri del cliente per aprire la **pagina Dettagli cliente**.</span><span class="sxs-lookup"><span data-stu-id="18421-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="18421-130">Questa visualizzazione contiene informazioni unificate per il cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="18421-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="18421-131">I dettagli del cliente includono:</span><span class="sxs-lookup"><span data-stu-id="18421-131">Customer details include:</span></span>

-   <span data-ttu-id="18421-132">**Riquadro Profilo cliente**: questo riquadro mostra i diversi valori dell'entità del profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="18421-132">**Customer profile tile**: This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="18421-133">Questi dettagli possono includere indirizzo e-mail, nome, città e così via.</span><span class="sxs-lookup"><span data-stu-id="18421-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="18421-134">**Interessi potenziali, Marchi potenziali**: mostra se hai configurato un arricchimento di prima parte.</span><span class="sxs-lookup"><span data-stu-id="18421-134">**Potential interests, potential brands**: Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="18421-135">Rappresenta potenziali interessi e affinità per i marchi che un cliente con un profilo simile a questo cliente potrebbe avere.</span><span class="sxs-lookup"><span data-stu-id="18421-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="18421-136">Per ulteriori informazioni, vedi [Arricchire profili cliente con affinità di marchi e interessi](enrichment-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="18421-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="18421-137">**Misure**: mostra se hai configurato una o più misure di un tipo specifico: misure attributo cliente.</span><span class="sxs-lookup"><span data-stu-id="18421-137">**Measures**: Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="18421-138">Includono KPI calcolati relativi ai clienti a livello di singolo cliente.</span><span class="sxs-lookup"><span data-stu-id="18421-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="18421-139">Per ulteriori informazioni, vedi [Definire e gestire misure](measures.md).</span><span class="sxs-lookup"><span data-stu-id="18421-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="18421-140">**Sequenza temporale impegni**: mostra se hai configurato impegni.</span><span class="sxs-lookup"><span data-stu-id="18421-140">**Activity timeline**: Shows if you have configured activities.</span></span> <span data-ttu-id="18421-141">La visualizzazione della sequenza temporale contiene impegni ordinati cronologicamente di questo cliente, a partire dall'impegno più recente.</span><span class="sxs-lookup"><span data-stu-id="18421-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="18421-142">Per altre informazioni, vedi [Impegni cliente](activities.md).</span><span class="sxs-lookup"><span data-stu-id="18421-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="18421-143">Seleziona **Torna a Clienti** per tornare alla pagina di ricerca del cliente.</span><span class="sxs-lookup"><span data-stu-id="18421-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="18421-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="18421-144">Next steps</span></span>

<span data-ttu-id="18421-145">[Aggiungere più origini dati](data-sources.md) o [creare segmenti di clienti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="18421-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
