---
title: Gestire le autorizzazioni utente
description: Informazioni su autorizzazioni e ruoli utente.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595707"
---
# <a name="user-permissions"></a><span data-ttu-id="71425-103">Autorizzazioni utente</span><span class="sxs-lookup"><span data-stu-id="71425-103">User permissions</span></span>

<span data-ttu-id="71425-104">La pagina **Autorizzazioni** consente di configurare ruoli e autorizzazioni per l'utilizzo di Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="71425-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="71425-105">Devi disporre delle autorizzazioni di amministratore per visualizzare la pagina.</span><span class="sxs-lookup"><span data-stu-id="71425-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="71425-106">Per accedere alla pagina delle autorizzazioni in Audience Insights, vai a **Amministratore** > **Autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="71425-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="71425-107">Esistono tre tipi di ruoli:</span><span class="sxs-lookup"><span data-stu-id="71425-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="71425-108">Visualizzatore</span><span class="sxs-lookup"><span data-stu-id="71425-108">Viewer</span></span>

- <span data-ttu-id="71425-109">Esplora informazioni dettagliate e segmenti nelle pagine **Home** e **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="71425-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="71425-110">Cerca e filtra i profili cliente utilizzando la pagina **Clienti**.</span><span class="sxs-lookup"><span data-stu-id="71425-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="71425-111">I campi devono essere ricercabili.</span><span class="sxs-lookup"><span data-stu-id="71425-111">Fields must be searchable.</span></span>
- <span data-ttu-id="71425-112">Visualizza ed esplora la pagina **Arricchimento**.</span><span class="sxs-lookup"><span data-stu-id="71425-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="71425-113">Esplora ed esporta entità usando la pagina **Entità**.</span><span class="sxs-lookup"><span data-stu-id="71425-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="71425-114">Visualizza lo stato dei processi di sistema utilizzando la pagina **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="71425-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="71425-115">Esporta segmenti dalla pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="71425-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="71425-116">Installa e usa il dashboard **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="71425-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="71425-117">Collaboratore</span><span class="sxs-lookup"><span data-stu-id="71425-117">Contributor</span></span>

- <span data-ttu-id="71425-118">Tutte le autorizzazioni disponibili per il visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="71425-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="71425-119">Carica e trasforma i dati utilizzando la pagina **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="71425-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="71425-120">Completa le sezioni *Unificazione dei dati* (**Mapping**, **Corrispondenza** e **Unione**) che risultano nell'entità profilo cliente unificata.</span><span class="sxs-lookup"><span data-stu-id="71425-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="71425-121">Definisci **Relazioni** e **Impegni**.</span><span class="sxs-lookup"><span data-stu-id="71425-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="71425-122">Crea segmenti usando la pagina **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="71425-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="71425-123">Crea misure utilizzando la pagina **Misure**.</span><span class="sxs-lookup"><span data-stu-id="71425-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="71425-124">Gestisci la configurazione e arricchisci i profili cliente dalla pagina **Arricchimento** (solo per arricchimenti del produttore).</span><span class="sxs-lookup"><span data-stu-id="71425-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="71425-125">Amministratore</span><span class="sxs-lookup"><span data-stu-id="71425-125">Administrator</span></span>

- <span data-ttu-id="71425-126">Tutte le autorizzazioni disponibili per il contributore.</span><span class="sxs-lookup"><span data-stu-id="71425-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="71425-127">Modifica le impostazioni nella pagina **Sistema**, inclusa la lingua di lavoro e gli orari di aggiornamento per i processi di sistema.</span><span class="sxs-lookup"><span data-stu-id="71425-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="71425-128">Visualizza e aggiungi le autorizzazioni usando la pagina **Autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="71425-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="71425-129">Imposta le definizioni di ricerca e filtro per la pagina Clienti utilizzando la pagina **Indicizzazione ricerca e filtro** (accessibile tramite la pagina **Clienti**).</span><span class="sxs-lookup"><span data-stu-id="71425-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="71425-130">Definisci le destinazioni dei segmenti Dynamics 365 Sales utilizzando la pagina **Destinazioni esportazione**.</span><span class="sxs-lookup"><span data-stu-id="71425-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="71425-131">Gestisci la configurazione e arricchisci i profili cliente dalla pagina **Arricchimento** (per tutti gli arricchimenti).</span><span class="sxs-lookup"><span data-stu-id="71425-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="71425-132">Installa e utilizza il **componente aggiuntivo Scheda cliente**.</span><span class="sxs-lookup"><span data-stu-id="71425-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="71425-133">Aggiungi e usa il **connettore Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="71425-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="71425-134">Abilita l'utilizzo delle [API di Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="71425-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="71425-135">Assegnare ruoli e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="71425-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="71425-136">In Audience Insights, vai a **Amministratore** > **Autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="71425-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="71425-137">Seleziona **Aggiungi utenti** per aprire il riquadro **Aggiungi/Modifica autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="71425-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="71425-138">Utilizza il campo **Cerca** per trovare il gruppo o l'utente Azure Active Directory di cui si desidera modificare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="71425-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="71425-139">Seleziona un **Ruolo** da assegnare a quell'utente o gruppo.</span><span class="sxs-lookup"><span data-stu-id="71425-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="71425-140">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="71425-140">Select **Save**.</span></span> <span data-ttu-id="71425-141">L'ambiente corrente verrà automaticamente condiviso con l'utente o i membri del gruppo di cui hai modificato le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="71425-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="71425-142">Gli utenti possono accedere all'app Customer Insights e utilizzarla in base al ruolo specificato.</span><span class="sxs-lookup"><span data-stu-id="71425-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="71425-143">Visualizzare le autorizzazioni correnti</span><span class="sxs-lookup"><span data-stu-id="71425-143">View current permissions</span></span>

<span data-ttu-id="71425-144">In Audience Insights, vai a **Amministratore** > **Autorizzazioni** per vedere quali assegnazioni di ruolo sono attualmente attive.</span><span class="sxs-lookup"><span data-stu-id="71425-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="71425-145">La colonna **Tipo** specifica un singolo utente, gruppo o applicazione.</span><span class="sxs-lookup"><span data-stu-id="71425-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="71425-146">Il sistema supporta singoli utenti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="71425-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="71425-147">I ruoli sono specificati nella colonna **Ruolo**.</span><span class="sxs-lookup"><span data-stu-id="71425-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="71425-148">Seleziona qualsiasi titolo di colonna per ordinare i risultati in base al valore di quella colonna.</span><span class="sxs-lookup"><span data-stu-id="71425-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="71425-149">Utilizza il campo **Cerca** nella parte superiore della pagina per individuare utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="71425-149">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]