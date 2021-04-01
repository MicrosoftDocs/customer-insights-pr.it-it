---
title: Utilizzare origini dati per inserire dati
description: Scopri come importare dati da varie origini.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595952"
---
# <a name="data-sources-overview"></a><span data-ttu-id="456bd-103">Panoramica delle origini dati</span><span class="sxs-lookup"><span data-stu-id="456bd-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="456bd-104">La funzionalità Audience Insights in Dynamics 365 Customer Insights si connette ai dati da un ampio insieme di origini.</span><span class="sxs-lookup"><span data-stu-id="456bd-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="456bd-105">La connessione a un'origine dati viene spesso definita processo di *inserimento dati*.</span><span class="sxs-lookup"><span data-stu-id="456bd-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="456bd-106">Dopo aver inserito i dati, puoi [unificare](data-unification.md) e agire su di essi.</span><span class="sxs-lookup"><span data-stu-id="456bd-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="456bd-107">Aggiungi un'origine dati</span><span class="sxs-lookup"><span data-stu-id="456bd-107">Add a data source</span></span>

<span data-ttu-id="456bd-108">Fai riferimento agli articoli dettagliati su come aggiungere un'origine dati, a seconda dell'opzione scelta.</span><span class="sxs-lookup"><span data-stu-id="456bd-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="456bd-109">Puoi aggiungere un'origine dati in tre modi principali:</span><span class="sxs-lookup"><span data-stu-id="456bd-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="456bd-110">Attraverso dozzine di connettori Power Query</span><span class="sxs-lookup"><span data-stu-id="456bd-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="456bd-111">Da una cartella di Common Data Model</span><span class="sxs-lookup"><span data-stu-id="456bd-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="456bd-112">Dal tuo lake Common Data Service</span><span class="sxs-lookup"><span data-stu-id="456bd-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="456bd-113">Non puoi ancora aggiungere dati da origini dati locale.</span><span class="sxs-lookup"><span data-stu-id="456bd-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="456bd-114">Esamina i dati inseriti</span><span class="sxs-lookup"><span data-stu-id="456bd-114">Review ingested data</span></span>

<span data-ttu-id="456bd-115">Vedrai il nome di ciascuna origine dati inserita, il suo stato e l'ultima volta che i dati sono stati aggiornati per quell'origine.</span><span class="sxs-lookup"><span data-stu-id="456bd-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="456bd-116">Puoi ordinare l'elenco delle origini dati per colonna.</span><span class="sxs-lookup"><span data-stu-id="456bd-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="456bd-117">![Origine dati aggiunta](media/configure-data-datasource-added.png "Origine dati aggiunta")</span><span class="sxs-lookup"><span data-stu-id="456bd-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="456bd-118">Stato</span><span class="sxs-lookup"><span data-stu-id="456bd-118">Status</span></span>  |<span data-ttu-id="456bd-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="456bd-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="456bd-120">Operazione riuscita</span><span class="sxs-lookup"><span data-stu-id="456bd-120">Successful</span></span>   |<span data-ttu-id="456bd-121">L'inserimento dell'origine dati è riuscito se un'ora è menzionata nella colonna **Aggiornato**.</span><span class="sxs-lookup"><span data-stu-id="456bd-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="456bd-122">Non avviato</span><span class="sxs-lookup"><span data-stu-id="456bd-122">Not started</span></span>   |<span data-ttu-id="456bd-123">L'origine dati non è ancora stata inserita o è ancora in modalità bozza.</span><span class="sxs-lookup"><span data-stu-id="456bd-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="456bd-124">Aggiornamento in corso</span><span class="sxs-lookup"><span data-stu-id="456bd-124">Refreshing</span></span>    |<span data-ttu-id="456bd-125">L'inserimento dati è in corso.</span><span class="sxs-lookup"><span data-stu-id="456bd-125">Data ingestion is in progress.</span></span> <span data-ttu-id="456bd-126">Puoi annullare questa operazione selezionando **Arresta aggiornamento** nella colonna **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="456bd-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="456bd-127">L'interruzione dell'aggiornamento di un'origine dati la riporterà al suo ultimo stato di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="456bd-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="456bd-128">Non inviato</span><span class="sxs-lookup"><span data-stu-id="456bd-128">Failed</span></span>     |<span data-ttu-id="456bd-129">Si sono verificati errori durante l'inserimento dati.</span><span class="sxs-lookup"><span data-stu-id="456bd-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="456bd-130">Seleziona il valore nella colonna **Stato** di qualsiasi origine dati per esaminare maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="456bd-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="456bd-131">Nel riquadro **Dettagli stato** espandi **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="456bd-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="456bd-132">Seleziona **Vedi dettagli** per altre informazioni sullo stato di aggiornamento, inclusi i dettagli di errore e gli aggiornamenti del processo downstream.</span><span class="sxs-lookup"><span data-stu-id="456bd-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="456bd-133">Il caricamento dei dati potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="456bd-133">Loading data can take some time.</span></span> <span data-ttu-id="456bd-134">Al termine del completamento dell'aggiornamento, i dati inseriti possono essere rivisti dalla pagina **Entità**.</span><span class="sxs-lookup"><span data-stu-id="456bd-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="456bd-135">Per ulteriori informazioni, vedi [Entità](entities.md).</span><span class="sxs-lookup"><span data-stu-id="456bd-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="456bd-136">Aggiornare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="456bd-136">Refresh a data source</span></span>

<span data-ttu-id="456bd-137">Le origini dati possono essere aggiornate in base a una pianificazione automatica o manualmente su richiesta.</span><span class="sxs-lookup"><span data-stu-id="456bd-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="456bd-138">Vai a **Amministratore** > **Sistema** > [**Pianifica**](system.md#schedule-tab) per configurare gli aggiornamenti pianificati di tutte le origini dati inserite.</span><span class="sxs-lookup"><span data-stu-id="456bd-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="456bd-139">Per aggiornare un origine dati su richiesta, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="456bd-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="456bd-140">In Audience Insights, vai a **Dati** > **Origini dati**</span><span class="sxs-lookup"><span data-stu-id="456bd-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="456bd-141">Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri aggiornare e seleziona **Aggiorna** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="456bd-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="456bd-142">L'origine dati è ora attivata per un aggiornamento manuale.</span><span class="sxs-lookup"><span data-stu-id="456bd-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="456bd-143">L'aggiornamento di un origine dati aggiornerà sia lo schema delle entità che i dati di tutte le entità specificate nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="456bd-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="456bd-144">Seleziona **Arresta aggiornamento** se desideri annullare un aggiornamento esistente e riportare l'origine dati allo stato dell'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="456bd-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="456bd-145">Eliminare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="456bd-145">Delete a data source</span></span>

1. <span data-ttu-id="456bd-146">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="456bd-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="456bd-147">Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri rimuovere e seleziona **Elimina** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="456bd-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="456bd-148">Conferma l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="456bd-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]