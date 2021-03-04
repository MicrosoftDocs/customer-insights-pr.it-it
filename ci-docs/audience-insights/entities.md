---
title: Entità e set di dati
description: Visualizza i dati nella pagina Entità.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269381"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="11676-103">Entità in Audience Insights</span><span class="sxs-lookup"><span data-stu-id="11676-103">Entities in audience insights</span></span>

<span data-ttu-id="11676-104">Dopo [aver configurato le origini dati](data-sources.md), vai alla pagina **Entità** per valutare la qualità dei dati inseriti.</span><span class="sxs-lookup"><span data-stu-id="11676-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="11676-105">Le entità sono considerate set di dati.</span><span class="sxs-lookup"><span data-stu-id="11676-105">Entities are considered datasets.</span></span> <span data-ttu-id="11676-106">Molteplici funzionalità di Dynamics 365 Customer Insights sono basate su queste entità.</span><span class="sxs-lookup"><span data-stu-id="11676-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="11676-107">La loro stretta revisione può aiutare a convalidare l'output di tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="11676-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="11676-108">La pagina **Entità** elenca le entità e include diverse colonne:</span><span class="sxs-lookup"><span data-stu-id="11676-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="11676-109">**Nome**: il nome dell'entità di dati.</span><span class="sxs-lookup"><span data-stu-id="11676-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="11676-110">Se viene visualizzato un simbolo di avviso accanto al nome di un'entità, significa che i dati per tale entità non sono stati caricati correttamente.</span><span class="sxs-lookup"><span data-stu-id="11676-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="11676-111">**Origine**: il tipo di origine dati che hanno inserito l'entità</span><span class="sxs-lookup"><span data-stu-id="11676-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="11676-112">**Autore creazione**: nome della persona che ha creato l'entità</span><span class="sxs-lookup"><span data-stu-id="11676-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="11676-113">**Data di creazione**: data e ora di creazione dell'entità</span><span class="sxs-lookup"><span data-stu-id="11676-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="11676-114">**Aggiornato da**: nome della persona che ha aggiornato l'entità</span><span class="sxs-lookup"><span data-stu-id="11676-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="11676-115">**Ultimo aggiornamento**: data e ora dell'ultimo aggiornamento dell'entità</span><span class="sxs-lookup"><span data-stu-id="11676-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="11676-116">**Ultimo aggiornamento**: data e ora dell'ultimo aggiornamento dati</span><span class="sxs-lookup"><span data-stu-id="11676-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="11676-117">Esplorazione dei dati di un'entità specifica</span><span class="sxs-lookup"><span data-stu-id="11676-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="11676-118">Seleziona un'entità per esplorare i diversi campi e record inclusi all'interno dell'entità.</span><span class="sxs-lookup"><span data-stu-id="11676-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11676-119">![Seleziona un'entità](media/data-manager-entities-data.png "Seleziona un'entità")</span><span class="sxs-lookup"><span data-stu-id="11676-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="11676-120">La scheda **Dati** è selezionata per impostazione predefinita e mostra una tabella che elenca i dettagli sui singoli record dell'entità.</span><span class="sxs-lookup"><span data-stu-id="11676-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11676-121">![Tabella Campi](media/data-manager-entities-fields.PNG "Tabella Campi")</span><span class="sxs-lookup"><span data-stu-id="11676-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="11676-122">La scheda **Campi** mostra una tabella per esaminare i dettagli per l'entità selezionata, ad esempio i nomi dei campi, i tipi di dati e i tipi.</span><span class="sxs-lookup"><span data-stu-id="11676-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="11676-123">La colonna **Tipo** mostra i tipi associati a Common Data Model che vengono identificati automaticamente dal sistema o [mappati manualmente](map-entities.md) dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="11676-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="11676-124">Si tratta di tipi semantici che possono differire dai tipi di dati degli attributi; ad esempio il campo *E-mail* sotto ha come tipo di dati *Testo* ma il relativo tipo Common Data Model (semantico) potrebbe essere *Emai* o *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="11676-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="11676-125">Entrambe le tabelle mostrano solo un esempio dei dati dell'entità.</span><span class="sxs-lookup"><span data-stu-id="11676-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="11676-126">Per visualizzare il set di dati completo, vai alla pagina **Origini dati** seleziona un'entità, seleziona **Modifica**, quindi visualizza i dati di questa entità con l'editor Power Query come spiegato in [Origini dati](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="11676-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="11676-127">Per altre informazioni sui dati inseriti nell'entità, la colonna **Riepilogo** fornisce alcune caratteristiche importanti dei dati, ad esempio valori Null, valori mancanti, valori univoci, conteggi e distribuzioni, a seconda di come sono applicabili ai dati.</span><span class="sxs-lookup"><span data-stu-id="11676-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="11676-128">Seleziona l'icona del grafico per visualizzare il riepilogo dei dati.</span><span class="sxs-lookup"><span data-stu-id="11676-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11676-129">![Simbolo di riepilogo](media/data-manager-entities-summary.png "Tabella riepilogo dati")</span><span class="sxs-lookup"><span data-stu-id="11676-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="11676-130">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="11676-130">Next step</span></span>

<span data-ttu-id="11676-131">Vedi l'argomento [Unificare](data-unification.md) per informazioni sulle operazioni di *mapping*, *corrispondenza* e *Unione* sui dati inseriti.</span><span class="sxs-lookup"><span data-stu-id="11676-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]