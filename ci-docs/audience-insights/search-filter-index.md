---
title: Cercare e filtrare profili cliente
description: Trova rapidamente informazioni sui profili cliente unificati e filtra per attributi specificati.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406139"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="1230d-103">Profili cliente: indice di ricerca e filtro</span><span class="sxs-lookup"><span data-stu-id="1230d-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="1230d-104">Il risultato dell'unificazione dei dati cliente è un'entità Profilo cliente che fornisce una visualizzazione unificata della base clienti totale.</span><span class="sxs-lookup"><span data-stu-id="1230d-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="1230d-105">Per [trovare rapidamente informazioni su un cliente o gruppo di clienti specifico](customer-profiles.md), puoi configurare le funzionalità **Cerca** o **Filtra** nella pagina **Cleinti**.</span><span class="sxs-lookup"><span data-stu-id="1230d-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="1230d-106">Continua a leggere per scoprire come gli amministratori possono modificare gli attributi nella pagina **Indicizzazione ricerca e filtro**, che sono disponibili per gli utenti per la ricerca e l'applicazione di filtri.</span><span class="sxs-lookup"><span data-stu-id="1230d-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1230d-107">![Filtro ricerca](media/search-filter.png "Filtro ricerca")</span><span class="sxs-lookup"><span data-stu-id="1230d-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="1230d-108">Aggiungere campi e specificare attributi</span><span class="sxs-lookup"><span data-stu-id="1230d-108">Add fields and specify attributes</span></span>

<span data-ttu-id="1230d-109">Se è la prima volta che si definiscono gli attributi ricercabili come amministratore, devi definire prima i campi indicizzati.</span><span class="sxs-lookup"><span data-stu-id="1230d-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="1230d-110">Ti consigliamo di scegliere tutti gli attributi in base ai quali gli utenti possono cercare e filtrare i clienti nella pagina **Clienti**.</span><span class="sxs-lookup"><span data-stu-id="1230d-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="1230d-111">Puoi specificare solo gli attributi presenti nell'entità Profilo cliente creata durante il processo di unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="1230d-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="1230d-112">Apri la pagina **Clienti** e seleziona **Indicizzazione ricerca e filtro**.</span><span class="sxs-lookup"><span data-stu-id="1230d-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="1230d-113">Creiamo una configurazione dell'indice di ricerca predefinita sugli attributi disponibili nell'entità Cliente dai seguenti tipi semantici, come definito nella pagina Mappa.</span><span class="sxs-lookup"><span data-stu-id="1230d-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="1230d-114">Nome, Cognome, Secondo nome, Nome completo</span><span class="sxs-lookup"><span data-stu-id="1230d-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="1230d-115">Nome organizzazione</span><span class="sxs-lookup"><span data-stu-id="1230d-115">Organization Name</span></span>
> - <span data-ttu-id="1230d-116">Indirizzo e-mail</span><span class="sxs-lookup"><span data-stu-id="1230d-116">Email address</span></span>
> - <span data-ttu-id="1230d-117">Numero di telefono</span><span class="sxs-lookup"><span data-stu-id="1230d-117">Phone number</span></span>
> - <span data-ttu-id="1230d-118">Informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="1230d-118">Location information</span></span>

2. <span data-ttu-id="1230d-119">Seleziona **+ Aggiungi** per specificare i campi indicizzati.</span><span class="sxs-lookup"><span data-stu-id="1230d-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="1230d-120">Seleziona gli attributi nell'elenco che vuoi aggiungere come campi indicizzati.</span><span class="sxs-lookup"><span data-stu-id="1230d-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="1230d-121">Puoi sempre aggiungere altri attributi selezionando **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1230d-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="1230d-122">Puoi anche rimuovere tutti gli attributi selezionati selezionando il simbolo **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="1230d-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="1230d-123">Esplorare la tabella Campi cliente indicizzati</span><span class="sxs-lookup"><span data-stu-id="1230d-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="1230d-124">Nella tabella vengono presentate le seguenti informazioni.</span><span class="sxs-lookup"><span data-stu-id="1230d-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="1230d-125">**Nome**: rappresenta il nome dell'attributo così come viene visualizzato nell'entità Profilo cliente.</span><span class="sxs-lookup"><span data-stu-id="1230d-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="1230d-126">**Tipo di dati**: specifica se il tipo di dati è una stringa, un numero o una data.</span><span class="sxs-lookup"><span data-stu-id="1230d-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="1230d-127">**Incluso nella ricerca**: specifica se questo attributo può essere utilizzato per la ricerca dei clienti nella pagina **Clienti** utilizzando il campo **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="1230d-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="1230d-128">**Aggiungi filgtro**: controllo per definire la modalità di utilizzo di questo attributo per il filtro nella pagina **Clienti**.</span><span class="sxs-lookup"><span data-stu-id="1230d-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="1230d-129">Modifica delle opzioni di filtro per un determinato attributo</span><span class="sxs-lookup"><span data-stu-id="1230d-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="1230d-130">Il menu **Filtra** nella pagina **Clienti** può includere un numero variabile di livelli di attributo (ad esempio, diverse fasce di età in base alle quali filtrare i clienti).</span><span class="sxs-lookup"><span data-stu-id="1230d-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="1230d-131">Seleziona **Aggiungi filtro** per un determinato attributon ella pagina **Indicizzazione ricerca e filtro**.</span><span class="sxs-lookup"><span data-stu-id="1230d-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="1230d-132">Puoi definire il numero di risultati e l'ordine in cui verranno organizzati.</span><span class="sxs-lookup"><span data-stu-id="1230d-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="1230d-133">A seconda del tipo di dati dell'attributo, viene visualizzato uno dei riquadri seguenti.</span><span class="sxs-lookup"><span data-stu-id="1230d-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="1230d-134">Attributi di tipo stringa: specifica il numero di risultati desiderati nel pannello **Opzioni di filtro stringa** e i criteri di ordine in base ai quali verranno organizzati.</span><span class="sxs-lookup"><span data-stu-id="1230d-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="1230d-135">Attributi di tipo numerico: specifica gli intervalli inclusi nel pannello **Opzioni di filtro numeri** e i criteri di ordine in base ai quali verranno organizzati.</span><span class="sxs-lookup"><span data-stu-id="1230d-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="1230d-136">Attributi di tipo data: specifica gli intervalli inclusi nel pannello **Opzioni filtro data** e i criteri di ordine in base ai quali verranno organizzati.</span><span class="sxs-lookup"><span data-stu-id="1230d-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="1230d-137">Seleziona **Salva** per applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1230d-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="1230d-138">Seleziona **Esegui** quando sei pronto per applicare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1230d-138">Select **Run** once you're ready to apply your settings.</span></span>
