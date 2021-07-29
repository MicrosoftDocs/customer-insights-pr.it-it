---
title: Dati di Customer Insights in Microsoft Dataverse
description: Utilizza le entità di Customer Insights come tabelle in Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 7157ad930f3cea17c12bd4f95028d291483329d3
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259196"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a><span data-ttu-id="9f191-103">Utilizzare i dati di Customer Insights in Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="9f191-103">Work with Customer Insights data in Microsoft Dataverse</span></span>

<span data-ttu-id="9f191-104">Customer Insights offre la possibilità di rendere disponibili entità di output in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md).</span><span class="sxs-lookup"><span data-stu-id="9f191-104">Customer Insights provides the option to make output entities available in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md).</span></span> <span data-ttu-id="9f191-105">Questa integrazione consente una facile condivisione dei dati e sviluppo personalizzato attraverso un approccio a uso limitato di codice/senza codice.</span><span class="sxs-lookup"><span data-stu-id="9f191-105">This integration enables easy data sharing and custom development through a low code / no code approach.</span></span> <span data-ttu-id="9f191-106">Le entità di output saranno disponibili come tabelle in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9f191-106">The output entities will be available as tables in Dataverse.</span></span> <span data-ttu-id="9f191-107">Queste tabelle consentono scenari come [flussi di lavoro automatizzati attraverso Power Automate](/power-automate/getting-started), [app basate su modelli](/powerapps/maker/model-driven-apps/) e [app canvas](/powerapps/maker/canvas-apps/) attraverso Power Apps.</span><span class="sxs-lookup"><span data-stu-id="9f191-107">These tables enable scenarios like [automated workflows through Power Automate](/power-automate/getting-started), [model-driven apps](/powerapps/maker/model-driven-apps/) and [canvas apps](/powerapps/maker/canvas-apps/) through Power Apps.</span></span> <span data-ttu-id="9f191-108">È possibile utilizzare i dati per qualsiasi altra applicazione basata su tabelle Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9f191-108">You can use the data for any other application that is based on Dataverse tables.</span></span> <span data-ttu-id="9f191-109">L'attuale implementazione supporta principalmente le ricerche in cui è possibile recuperare i dati dalle entità di approfondimenti destinatari disponibili per un determinato ID cliente.</span><span class="sxs-lookup"><span data-stu-id="9f191-109">The current implementation mainly supports lookups where data from the available audience insights entities can be fetched for a given customer ID.</span></span>

## <a name="attach-a-dataverse-environment-to-customer-insights"></a><span data-ttu-id="9f191-110">Allega un ambiente Dataverse a Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9f191-110">Attach a Dataverse environment to Customer Insights</span></span>

<span data-ttu-id="9f191-111">**Organizzazioni con ambienti Dataverse esistenti**</span><span class="sxs-lookup"><span data-stu-id="9f191-111">**Organizations with existing Dataverse environments**</span></span>

<span data-ttu-id="9f191-112">Le organizzazioni che già utilizzano Dataverse possono [usare uno dei loro ambienti Dataverse esistenti](manage-environments.md#create-an-environment-in-an-existing-organization) quando un amministratore imposta le informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="9f191-112">Organizations that already use Dataverse can [use one of their existing Dataverse environments](manage-environments.md#create-an-environment-in-an-existing-organization) when an administrator sets up audience insights.</span></span> <span data-ttu-id="9f191-113">Fornendo l'URL all'ambiente Dataverse, si collega al loro nuovo ambiente di informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="9f191-113">By providing the URL to the Dataverse environment, it's attaching to their new audience insights environment.</span></span> <span data-ttu-id="9f191-114">Per garantire le migliori prestazioni possibili, gli ambienti Customer Insights e Dataverse devono essere ospitati nella stessa regione.</span><span class="sxs-lookup"><span data-stu-id="9f191-114">To ensure the best possible performance, Customer Insights and Dataverse environments must be hosted in the same region.</span></span>

<span data-ttu-id="9f191-115">Per allegare un ambiente Dataverse, espandere le **Impostazioni avanzate** durante la creazione dell'ambiente di informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="9f191-115">To attach a Dataverse environment, expand the **Advanced settings** when creating the audience insights environment.</span></span> <span data-ttu-id="9f191-116">Fornire l'URL dell'ambiente **Microsoft Dataverse** e selezionare la casella di controllo per **Abilita la condivisione dei dati**.</span><span class="sxs-lookup"><span data-stu-id="9f191-116">Provide the **Microsoft Dataverse environment URL** and select the checkbox to **Enable data sharing**.</span></span>

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt":::

<span data-ttu-id="9f191-118">**Nuova organizzazione**</span><span class="sxs-lookup"><span data-stu-id="9f191-118">**New organization**</span></span>

<span data-ttu-id="9f191-119">Se crei una nuova organizzazione durante la configurazione di Customer Insights, otterrai automaticamente una nuovo ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9f191-119">If you create a new organization when setting up Customer Insights, you'll automatically get a new Dataverse environment.</span></span>

> [!NOTE]
> <span data-ttu-id="9f191-120">Se le tue organizzazioni utilizzano già Dataverse nel loro tenant, è importante ricordare che [la creazione dell'ambiente Dataverse è controllata da un amministratore](/power-platform/admin/control-environment-creation.md). Ad esempio, se stai configurando un nuovo ambiente di informazioni dettagliate con il tuo account aziendale e l'amministratore ha disabilitato la creazione di ambienti Dataverse di prova per tutti tranne per gli amministratori, non è possibile creare un nuovo ambiente di prova.</span><span class="sxs-lookup"><span data-stu-id="9f191-120">If your organizations already uses Dataverse in their tenant, it’s important to remember that [Dataverse environment creation is controlled by an admin](/power-platform/admin/control-environment-creation.md). For example, if a you're setting up a new audience insights environment with your organizational account and the admin has disabled the creation of Dataverse trial environments for everyone except admins, you can't create a new trial environment.</span></span>
> 
> <span data-ttu-id="9f191-121">Gli ambienti Dataverse di prova creati in Customer Insights dispongono di 3 GB di spazio di archiviazione che non verranno conteggiati ai fini della capacità complessiva a disposizione del tenant.</span><span class="sxs-lookup"><span data-stu-id="9f191-121">The Dataverse trial environments created in Customer Insights have 3 GB of storage which won't count towards the overall capacity entitled to the tenant.</span></span> <span data-ttu-id="9f191-122">Gli abbonamenti a pagamento ottengono il diritto a Dataverse di 15 GB per il database e 20 GB per l'archiviazione dei file.</span><span class="sxs-lookup"><span data-stu-id="9f191-122">Paid subscriptions get Dataverse entitlement of 15 GB for database and 20 GB for file storage.</span></span>

## <a name="output-entities"></a><span data-ttu-id="9f191-123">Entità di output</span><span class="sxs-lookup"><span data-stu-id="9f191-123">Output entities</span></span>

<span data-ttu-id="9f191-124">Alcune entità di output da informazioni dettagliate sono disponibili come tabelle in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9f191-124">Some output entities from audience insights are available as tables in Dataverse.</span></span> <span data-ttu-id="9f191-125">Le sezioni seguenti descrivono lo schema previsto di queste tabelle.</span><span class="sxs-lookup"><span data-stu-id="9f191-125">The sections below describe the expected schema of these tables.</span></span>

- [<span data-ttu-id="9f191-126">CustomerProfile</span><span class="sxs-lookup"><span data-stu-id="9f191-126">CustomerProfile</span></span>](#customerprofile)
- [<span data-ttu-id="9f191-127">AlternateKey</span><span class="sxs-lookup"><span data-stu-id="9f191-127">AlternateKey</span></span>](#alternatekey)
- [<span data-ttu-id="9f191-128">UnifiedActivity</span><span class="sxs-lookup"><span data-stu-id="9f191-128">UnifiedActivity</span></span>](#unifiedactivity)
- [<span data-ttu-id="9f191-129">CustomerMeasure</span><span class="sxs-lookup"><span data-stu-id="9f191-129">CustomerMeasure</span></span>](#customermeasure)
- [<span data-ttu-id="9f191-130">Arricchimento</span><span class="sxs-lookup"><span data-stu-id="9f191-130">Enrichment</span></span>](#enrichment)
- [<span data-ttu-id="9f191-131">Previsione</span><span class="sxs-lookup"><span data-stu-id="9f191-131">Prediction</span></span>](#prediction)


### <a name="customerprofile"></a><span data-ttu-id="9f191-132">CustomerProfile</span><span class="sxs-lookup"><span data-stu-id="9f191-132">CustomerProfile</span></span>

<span data-ttu-id="9f191-133">Questa tabella contiene il profilo cliente unificato di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9f191-133">This table contains the unified customer profile from Customer Insights.</span></span> <span data-ttu-id="9f191-134">Lo schema per un profilo cliente unificato dipende dalle entità e dagli attributi utilizzati nel processo di unione.</span><span class="sxs-lookup"><span data-stu-id="9f191-134">The schema for a unified customer profile depends on the entities and attributes used in the merge process.</span></span> <span data-ttu-id="9f191-135">Uno schema del profilo del cliente di solito contiene un sottoinsieme degli attributi dalla [Definizione del Common Data Model di CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).</span><span class="sxs-lookup"><span data-stu-id="9f191-135">A customer profile schema usually contains a subset of the attributes from the [Common Data Model definition of CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).</span></span>

### <a name="alternatekey"></a><span data-ttu-id="9f191-136">AlternateKey</span><span class="sxs-lookup"><span data-stu-id="9f191-136">AlternateKey</span></span>

<span data-ttu-id="9f191-137">La tabella AlternateKey contiene le chiavi delle entità che hanno partecipato al processo di unificazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-137">The AlternateKey table contains keys of the entities, which participated in the unify process.</span></span>

|<span data-ttu-id="9f191-138">Column</span><span class="sxs-lookup"><span data-stu-id="9f191-138">Column</span></span>  |<span data-ttu-id="9f191-139">Digita</span><span class="sxs-lookup"><span data-stu-id="9f191-139">Type</span></span>  |<span data-ttu-id="9f191-140">Description</span><span class="sxs-lookup"><span data-stu-id="9f191-140">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9f191-141">DataSourceName</span><span class="sxs-lookup"><span data-stu-id="9f191-141">DataSourceName</span></span>    |<span data-ttu-id="9f191-142">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-142">String</span></span>         | <span data-ttu-id="9f191-143">Nome origine dati.</span><span class="sxs-lookup"><span data-stu-id="9f191-143">Name of the data source.</span></span> <span data-ttu-id="9f191-144">Ad esempio: `datasource5`</span><span class="sxs-lookup"><span data-stu-id="9f191-144">For example: `datasource5`</span></span>        |
|<span data-ttu-id="9f191-145">EntityName</span><span class="sxs-lookup"><span data-stu-id="9f191-145">EntityName</span></span>        | <span data-ttu-id="9f191-146">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-146">String</span></span>        | <span data-ttu-id="9f191-147">Nome dell'entità utilizzata nelle informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="9f191-147">Name of the entity in audience insights.</span></span> <span data-ttu-id="9f191-148">Ad esempio: `contact1`</span><span class="sxs-lookup"><span data-stu-id="9f191-148">For example: `contact1`</span></span>        |
|<span data-ttu-id="9f191-149">AlternateValue</span><span class="sxs-lookup"><span data-stu-id="9f191-149">AlternateValue</span></span>    |<span data-ttu-id="9f191-150">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-150">String</span></span>         |<span data-ttu-id="9f191-151">ID alternativo mappato all'ID cliente.</span><span class="sxs-lookup"><span data-stu-id="9f191-151">Alternative ID that is mapped to the customer ID.</span></span> <span data-ttu-id="9f191-152">Esempio: `cntid_1078`</span><span class="sxs-lookup"><span data-stu-id="9f191-152">Example: `cntid_1078`</span></span>         |
|<span data-ttu-id="9f191-153">KeyRing</span><span class="sxs-lookup"><span data-stu-id="9f191-153">KeyRing</span></span>           | <span data-ttu-id="9f191-154">Testo su più righe</span><span class="sxs-lookup"><span data-stu-id="9f191-154">Multiline text</span></span>        | <span data-ttu-id="9f191-155">Valore JSON</span><span class="sxs-lookup"><span data-stu-id="9f191-155">JSON value</span></span>  </br> <span data-ttu-id="9f191-156">Esempio: [{"dataSourceName":" datasource5 ",</span><span class="sxs-lookup"><span data-stu-id="9f191-156">Sample: [{"dataSourceName":" datasource5 ",</span></span></br><span data-ttu-id="9f191-157">"entityName":" contact1",</span><span class="sxs-lookup"><span data-stu-id="9f191-157">"entityName":" contact1",</span></span></br><span data-ttu-id="9f191-158">"preferredKey":" cntid_1078",</span><span class="sxs-lookup"><span data-stu-id="9f191-158">"preferredKey":" cntid_1078",</span></span></br><span data-ttu-id="9f191-159">"keys":[" cntid_1078"]}]</span><span class="sxs-lookup"><span data-stu-id="9f191-159">"keys":[" cntid_1078"]}]</span></span>       |
|<span data-ttu-id="9f191-160">Customerid</span><span class="sxs-lookup"><span data-stu-id="9f191-160">CustomerId</span></span>         | <span data-ttu-id="9f191-161">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-161">String</span></span>        | <span data-ttu-id="9f191-162">ID del profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="9f191-162">ID of the unified customer profile.</span></span>         |
|<span data-ttu-id="9f191-163">AlternateKeyId</span><span class="sxs-lookup"><span data-stu-id="9f191-163">AlternateKeyId</span></span>     | <span data-ttu-id="9f191-164">GUID</span><span class="sxs-lookup"><span data-stu-id="9f191-164">GUID</span></span>         |  <span data-ttu-id="9f191-165">GUID deterministico AlternateKey basato su msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="9f191-165">AlternateKey deterministic GUID based on msdynci_identifier</span></span>       |
|<span data-ttu-id="9f191-166">msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="9f191-166">msdynci_identifier</span></span> |   <span data-ttu-id="9f191-167">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-167">String</span></span>      |   `DataSourceName|EntityName|AlternateValue`  </br> <span data-ttu-id="9f191-168">Esempio: `testdatasource|contact1|cntid_1078`</span><span class="sxs-lookup"><span data-stu-id="9f191-168">Sample: `testdatasource|contact1|cntid_1078`</span></span>    |

### <a name="unifiedactivity"></a><span data-ttu-id="9f191-169">UnifiedActivity</span><span class="sxs-lookup"><span data-stu-id="9f191-169">UnifiedActivity</span></span>

<span data-ttu-id="9f191-170">Questa tabella contiene le attività degli utenti disponibili in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9f191-170">This table contains activities by users that are available in Customer Insights.</span></span>

| <span data-ttu-id="9f191-171">Column</span><span class="sxs-lookup"><span data-stu-id="9f191-171">Column</span></span>            | <span data-ttu-id="9f191-172">Digita</span><span class="sxs-lookup"><span data-stu-id="9f191-172">Type</span></span>        | <span data-ttu-id="9f191-173">Description</span><span class="sxs-lookup"><span data-stu-id="9f191-173">Description</span></span>                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| <span data-ttu-id="9f191-174">Customerid</span><span class="sxs-lookup"><span data-stu-id="9f191-174">CustomerId</span></span>        | <span data-ttu-id="9f191-175">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-175">String</span></span>      | <span data-ttu-id="9f191-176">ID profilo cliente</span><span class="sxs-lookup"><span data-stu-id="9f191-176">Customer Profile ID</span></span>                                                                      |
| <span data-ttu-id="9f191-177">ActivityId</span><span class="sxs-lookup"><span data-stu-id="9f191-177">ActivityId</span></span>        | <span data-ttu-id="9f191-178">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-178">String</span></span>      | <span data-ttu-id="9f191-179">ID interno dell'attività del cliente (chiave primaria)</span><span class="sxs-lookup"><span data-stu-id="9f191-179">Internal ID of the customer activity (primary key)</span></span>                                       |
| <span data-ttu-id="9f191-180">SourceEntityName</span><span class="sxs-lookup"><span data-stu-id="9f191-180">SourceEntityName</span></span>  | <span data-ttu-id="9f191-181">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-181">String</span></span>      | <span data-ttu-id="9f191-182">Nome dell'entità di origine</span><span class="sxs-lookup"><span data-stu-id="9f191-182">Name of the source entity</span></span>                                                                |
| <span data-ttu-id="9f191-183">SourceActivityId</span><span class="sxs-lookup"><span data-stu-id="9f191-183">SourceActivityId</span></span>  | <span data-ttu-id="9f191-184">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-184">String</span></span>      | <span data-ttu-id="9f191-185">Chiave primaria dall'entità di origine</span><span class="sxs-lookup"><span data-stu-id="9f191-185">Primary key from the source entity</span></span>                                                       |
| <span data-ttu-id="9f191-186">ActivityType</span><span class="sxs-lookup"><span data-stu-id="9f191-186">ActivityType</span></span>      | <span data-ttu-id="9f191-187">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-187">String</span></span>      | <span data-ttu-id="9f191-188">Tipo di attività semantica o nome dell'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="9f191-188">Semantic activity type or name of custom activity</span></span>                                        |
| <span data-ttu-id="9f191-189">ActivityTimeStamp</span><span class="sxs-lookup"><span data-stu-id="9f191-189">ActivityTimeStamp</span></span> | <span data-ttu-id="9f191-190">DATETIME</span><span class="sxs-lookup"><span data-stu-id="9f191-190">DATETIME</span></span>    | <span data-ttu-id="9f191-191">Timestamp impegno</span><span class="sxs-lookup"><span data-stu-id="9f191-191">Activity Time stamp</span></span>                                                                      |
| <span data-ttu-id="9f191-192">Posizione</span><span class="sxs-lookup"><span data-stu-id="9f191-192">Title</span></span>             | <span data-ttu-id="9f191-193">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-193">String</span></span>      | <span data-ttu-id="9f191-194">Titolo o nome dell'impegno</span><span class="sxs-lookup"><span data-stu-id="9f191-194">Title or name of the activity</span></span>                                                               |
| <span data-ttu-id="9f191-195">Description</span><span class="sxs-lookup"><span data-stu-id="9f191-195">Description</span></span>       | <span data-ttu-id="9f191-196">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-196">String</span></span>      | <span data-ttu-id="9f191-197">Descrizione impegno</span><span class="sxs-lookup"><span data-stu-id="9f191-197">Activity description</span></span>                                                                     |
| <span data-ttu-id="9f191-198">URL</span><span class="sxs-lookup"><span data-stu-id="9f191-198">URL</span></span>               | <span data-ttu-id="9f191-199">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-199">String</span></span>      | <span data-ttu-id="9f191-200">Collegamento a un URL esterno specifico per l'impegno</span><span class="sxs-lookup"><span data-stu-id="9f191-200">Link to an external URL specific to the activity</span></span>                                         |
| <span data-ttu-id="9f191-201">SemanticData</span><span class="sxs-lookup"><span data-stu-id="9f191-201">SemanticData</span></span>      | <span data-ttu-id="9f191-202">Stringa JSON</span><span class="sxs-lookup"><span data-stu-id="9f191-202">JSON String</span></span> | <span data-ttu-id="9f191-203">Include un elenco di coppie chiave-valore per campi di mappatura semantica specifici per il tipo di attività</span><span class="sxs-lookup"><span data-stu-id="9f191-203">Includes a list of key value pairs for semantic mapping fields specific to the type of activity</span></span> |
| <span data-ttu-id="9f191-204">RangeIndex</span><span class="sxs-lookup"><span data-stu-id="9f191-204">RangeIndex</span></span>        | <span data-ttu-id="9f191-205">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-205">String</span></span>      | <span data-ttu-id="9f191-206">Timestamp Unix utilizzato per ordinare la sequenza temporale dell'attività e le query sull'intervallo effettivo</span><span class="sxs-lookup"><span data-stu-id="9f191-206">Unix timestamp used for sorting activity timeline and effective range queries</span></span> |
| <span data-ttu-id="9f191-207">mydynci_unifiedactivityid</span><span class="sxs-lookup"><span data-stu-id="9f191-207">mydynci_unifiedactivityid</span></span>   | <span data-ttu-id="9f191-208">GUID</span><span class="sxs-lookup"><span data-stu-id="9f191-208">GUID</span></span> | <span data-ttu-id="9f191-209">ID interno dell'attività del cliente (ActivityId)</span><span class="sxs-lookup"><span data-stu-id="9f191-209">Internal ID of the customer activity (ActivityId)</span></span> |

### <a name="customermeasure"></a><span data-ttu-id="9f191-210">CustomerMeasure</span><span class="sxs-lookup"><span data-stu-id="9f191-210">CustomerMeasure</span></span>

<span data-ttu-id="9f191-211">Questa tabella contiene i dati di output delle misure basate sugli attributi del cliente.</span><span class="sxs-lookup"><span data-stu-id="9f191-211">This table contains the output data of customer attribute-based measures.</span></span>

| <span data-ttu-id="9f191-212">Column</span><span class="sxs-lookup"><span data-stu-id="9f191-212">Column</span></span>             | <span data-ttu-id="9f191-213">Digita</span><span class="sxs-lookup"><span data-stu-id="9f191-213">Type</span></span>             | <span data-ttu-id="9f191-214">Description</span><span class="sxs-lookup"><span data-stu-id="9f191-214">Description</span></span>                 |
|--------------------|------------------|-----------------------------|
| <span data-ttu-id="9f191-215">Customerid</span><span class="sxs-lookup"><span data-stu-id="9f191-215">CustomerId</span></span>         | <span data-ttu-id="9f191-216">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-216">String</span></span>           | <span data-ttu-id="9f191-217">ID profilo cliente</span><span class="sxs-lookup"><span data-stu-id="9f191-217">Customer profile ID</span></span>        |
| <span data-ttu-id="9f191-218">Misure</span><span class="sxs-lookup"><span data-stu-id="9f191-218">Measures</span></span>           | <span data-ttu-id="9f191-219">Stringa JSON</span><span class="sxs-lookup"><span data-stu-id="9f191-219">JSON String</span></span>      | <span data-ttu-id="9f191-220">Include un elenco di coppie di valori chiave per il nome della misura e i valori per il cliente specificato</span><span class="sxs-lookup"><span data-stu-id="9f191-220">Includes a list of key value pairs for measure name and values for the given customer</span></span> | 
| <span data-ttu-id="9f191-221">msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="9f191-221">msdynci_identifier</span></span> | <span data-ttu-id="9f191-222">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-222">String</span></span>           | `Customer_Measure|CustomerId` |
| <span data-ttu-id="9f191-223">msdynci_customermeasureid</span><span class="sxs-lookup"><span data-stu-id="9f191-223">msdynci_customermeasureid</span></span> | <span data-ttu-id="9f191-224">GUID</span><span class="sxs-lookup"><span data-stu-id="9f191-224">GUID</span></span>      | <span data-ttu-id="9f191-225">ID profilo cliente</span><span class="sxs-lookup"><span data-stu-id="9f191-225">Customer profile ID</span></span> |


### <a name="enrichment"></a><span data-ttu-id="9f191-226">Arricchimento</span><span class="sxs-lookup"><span data-stu-id="9f191-226">Enrichment</span></span>

<span data-ttu-id="9f191-227">Questa tabella contiene l'output del processo di arricchimento.</span><span class="sxs-lookup"><span data-stu-id="9f191-227">This table contains the output of the enrichment process.</span></span>

| <span data-ttu-id="9f191-228">Column</span><span class="sxs-lookup"><span data-stu-id="9f191-228">Column</span></span>               | <span data-ttu-id="9f191-229">Digita</span><span class="sxs-lookup"><span data-stu-id="9f191-229">Type</span></span>             |  <span data-ttu-id="9f191-230">Description</span><span class="sxs-lookup"><span data-stu-id="9f191-230">Description</span></span>                                          |
|----------------------|------------------|------------------------------------------------------|
| <span data-ttu-id="9f191-231">Customerid</span><span class="sxs-lookup"><span data-stu-id="9f191-231">CustomerId</span></span>           | <span data-ttu-id="9f191-232">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-232">String</span></span>           | <span data-ttu-id="9f191-233">ID profilo cliente</span><span class="sxs-lookup"><span data-stu-id="9f191-233">Customer profile ID</span></span>                                 |
| <span data-ttu-id="9f191-234">EnrichmentProvider</span><span class="sxs-lookup"><span data-stu-id="9f191-234">EnrichmentProvider</span></span>   | <span data-ttu-id="9f191-235">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-235">String</span></span>           | <span data-ttu-id="9f191-236">Nome del provider per l'arricchimento</span><span class="sxs-lookup"><span data-stu-id="9f191-236">Name of the provider for the enrichment</span></span>                                  |
| <span data-ttu-id="9f191-237">EnrichmentType</span><span class="sxs-lookup"><span data-stu-id="9f191-237">EnrichmentType</span></span>       | <span data-ttu-id="9f191-238">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-238">String</span></span>           | <span data-ttu-id="9f191-239">Tipo di arricchimento</span><span class="sxs-lookup"><span data-stu-id="9f191-239">Type of enrichment</span></span>                                      |
| <span data-ttu-id="9f191-240">Valori</span><span class="sxs-lookup"><span data-stu-id="9f191-240">Values</span></span>               | <span data-ttu-id="9f191-241">Stringa JSON</span><span class="sxs-lookup"><span data-stu-id="9f191-241">JSON String</span></span>      | <span data-ttu-id="9f191-242">Elenco degli attributi prodotti dal processo di arricchimento</span><span class="sxs-lookup"><span data-stu-id="9f191-242">List of attributes produced by the enrichment process</span></span> |
| <span data-ttu-id="9f191-243">msdynci_enrichmentid</span><span class="sxs-lookup"><span data-stu-id="9f191-243">msdynci_enrichmentid</span></span> | <span data-ttu-id="9f191-244">GUID</span><span class="sxs-lookup"><span data-stu-id="9f191-244">GUID</span></span>             | <span data-ttu-id="9f191-245">GUID deterministico generato da msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="9f191-245">Deterministic GUID generated from msdynci_identifier</span></span> |
| <span data-ttu-id="9f191-246">msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="9f191-246">msdynci_identifier</span></span>   | <span data-ttu-id="9f191-247">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-247">String</span></span>           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a><span data-ttu-id="9f191-248">Previsione</span><span class="sxs-lookup"><span data-stu-id="9f191-248">Prediction</span></span>

<span data-ttu-id="9f191-249">Questa tabella contiene l'output delle previsioni del modello.</span><span class="sxs-lookup"><span data-stu-id="9f191-249">This table contains the output of the model predictions.</span></span>

| <span data-ttu-id="9f191-250">Column</span><span class="sxs-lookup"><span data-stu-id="9f191-250">Column</span></span>               | <span data-ttu-id="9f191-251">Digita</span><span class="sxs-lookup"><span data-stu-id="9f191-251">Type</span></span>        | <span data-ttu-id="9f191-252">Description</span><span class="sxs-lookup"><span data-stu-id="9f191-252">Description</span></span>                                          |
|----------------------|-------------|------------------------------------------------------|
| <span data-ttu-id="9f191-253">Customerid</span><span class="sxs-lookup"><span data-stu-id="9f191-253">CustomerId</span></span>           | <span data-ttu-id="9f191-254">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-254">String</span></span>      | <span data-ttu-id="9f191-255">ID profilo cliente</span><span class="sxs-lookup"><span data-stu-id="9f191-255">Customer Profile ID</span></span>                                  |
| <span data-ttu-id="9f191-256">ModelProvider</span><span class="sxs-lookup"><span data-stu-id="9f191-256">ModelProvider</span></span>        | <span data-ttu-id="9f191-257">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-257">String</span></span>      | <span data-ttu-id="9f191-258">Nome del provider del modello</span><span class="sxs-lookup"><span data-stu-id="9f191-258">Name of the provider of the model</span></span>                                      |
| <span data-ttu-id="9f191-259">Modello</span><span class="sxs-lookup"><span data-stu-id="9f191-259">Model</span></span>                | <span data-ttu-id="9f191-260">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-260">String</span></span>      | <span data-ttu-id="9f191-261">Nome modello</span><span class="sxs-lookup"><span data-stu-id="9f191-261">Model name</span></span>                                                |
| <span data-ttu-id="9f191-262">Valori</span><span class="sxs-lookup"><span data-stu-id="9f191-262">Values</span></span>               | <span data-ttu-id="9f191-263">Stringa JSON</span><span class="sxs-lookup"><span data-stu-id="9f191-263">JSON String</span></span> | <span data-ttu-id="9f191-264">Elenco degli attributi prodotti dal modello</span><span class="sxs-lookup"><span data-stu-id="9f191-264">List of attributes produced by the model</span></span> |
| <span data-ttu-id="9f191-265">msdynci_predictionid</span><span class="sxs-lookup"><span data-stu-id="9f191-265">msdynci_predictionid</span></span> | <span data-ttu-id="9f191-266">GUID</span><span class="sxs-lookup"><span data-stu-id="9f191-266">GUID</span></span>        | <span data-ttu-id="9f191-267">GUID deterministico generato da msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="9f191-267">Deterministic GUID generated from msdynci_identifier</span></span> | 
| <span data-ttu-id="9f191-268">msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="9f191-268">msdynci_identifier</span></span>   | <span data-ttu-id="9f191-269">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f191-269">String</span></span>      |  `Model|ModelProvider|CustomerId`                      |