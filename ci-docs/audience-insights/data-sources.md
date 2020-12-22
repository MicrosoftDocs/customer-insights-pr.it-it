---
title: Utilizzare origini dati per inserire dati
description: Scopri come importare dati da varie origini.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643958"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="8f8e1-103">Panoramica sulle origini dati</span><span class="sxs-lookup"><span data-stu-id="8f8e1-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8f8e1-104">La funzionalità Audience Insights in Dynamics 365 Customer Insights si connette ai dati da un ampio insieme di origini.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="8f8e1-105">La connessione a un'origine dati viene spesso definita processo di *inserimento dati*.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="8f8e1-106">Dopo aver inserito i dati, puoi [unificare](data-unification.md) e agire su di essi.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="8f8e1-107">Aggiungi un'origine dati</span><span class="sxs-lookup"><span data-stu-id="8f8e1-107">Add a data source</span></span>

<span data-ttu-id="8f8e1-108">Fai riferimento agli articoli dettagliati su come aggiungere un'origine dati, a seconda dell'opzione scelta.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="8f8e1-109">Puoi aggiungere un'origine dati in tre modi principali:</span><span class="sxs-lookup"><span data-stu-id="8f8e1-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="8f8e1-110">Attraverso dozzine di connettori Power Query</span><span class="sxs-lookup"><span data-stu-id="8f8e1-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="8f8e1-111">Da una cartella di Common Data Model</span><span class="sxs-lookup"><span data-stu-id="8f8e1-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="8f8e1-112">Dal tuo lake Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8f8e1-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="8f8e1-113">Non puoi ancora aggiungere dati da origini dati locale.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="8f8e1-114">Esamina i dati inseriti</span><span class="sxs-lookup"><span data-stu-id="8f8e1-114">Review ingested data</span></span>

<span data-ttu-id="8f8e1-115">Vedrai il nome di ciascuna origine dati inserita, il suo stato e l'ultima volta che i dati sono stati aggiornati per quell'origine.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="8f8e1-116">Puoi ordinare l'elenco delle origini dati per colonna.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8f8e1-117">![Origine dati aggiunta](media/configure-data-datasource-added.png "Origine dati aggiunta")</span><span class="sxs-lookup"><span data-stu-id="8f8e1-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="8f8e1-118">Stato</span><span class="sxs-lookup"><span data-stu-id="8f8e1-118">Status</span></span>  |<span data-ttu-id="8f8e1-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f8e1-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="8f8e1-120">Operazione riuscita</span><span class="sxs-lookup"><span data-stu-id="8f8e1-120">Successful</span></span>   |<span data-ttu-id="8f8e1-121">L'inserimento dell'origine dati è riuscito se un'ora è menzionata nella colonna **Aggiornato**.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="8f8e1-122">Non avviato</span><span class="sxs-lookup"><span data-stu-id="8f8e1-122">Not started</span></span>   |<span data-ttu-id="8f8e1-123">L'origine dati non è ancora stata inserita o è ancora in modalità bozza.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="8f8e1-124">Aggiornamento in corso</span><span class="sxs-lookup"><span data-stu-id="8f8e1-124">Refreshing</span></span>    |<span data-ttu-id="8f8e1-125">L'inserimento dati è in corso.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-125">Data ingestion is in progress.</span></span> <span data-ttu-id="8f8e1-126">Puoi annullare questa operazione selezionando **Arresta aggiornamento** nella colonna **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="8f8e1-127">L'interruzione dell'aggiornamento di un'origine dati la riporterà al suo ultimo stato di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="8f8e1-128">Non inviato</span><span class="sxs-lookup"><span data-stu-id="8f8e1-128">Failed</span></span>     |<span data-ttu-id="8f8e1-129">Si sono verificati errori durante l'inserimento dati.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="8f8e1-130">Seleziona **Aggiorna stato** per esaminare maggiori dettagli sullo stato di aggiornamento, inclusi i dettagli di errore e gli aggiornamenti del processo downstream.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="8f8e1-131">Il caricamento dei dati potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-131">Loading data can take some time.</span></span> <span data-ttu-id="8f8e1-132">Al termine del completamento dell'aggiornamento, i dati inseriti possono essere rivisti dalla pagina **Entità**.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="8f8e1-133">Per ulteriori informazioni, vedi [Entità](entities.md).</span><span class="sxs-lookup"><span data-stu-id="8f8e1-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="8f8e1-134">Aggiornare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="8f8e1-134">Refresh a data source</span></span>

<span data-ttu-id="8f8e1-135">Le origini dati possono essere aggiornate in base a una pianificazione automatica o manualmente su richiesta.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="8f8e1-136">Vai a **Amministratore** > **Sistema** > [**Pianifica**](system.md#schedule-tab) per configurare gli aggiornamenti pianificati di tutte le origini dati inserite.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="8f8e1-137">Per aggiornare un origine dati su richiesta, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="8f8e1-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="8f8e1-138">In Audience Insights, vai a **Dati** > **Origini dati**</span><span class="sxs-lookup"><span data-stu-id="8f8e1-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="8f8e1-139">Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri aggiornare e seleziona **Aggiorna** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="8f8e1-140">L'origine dati è ora attivata per un aggiornamento manuale.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="8f8e1-141">L'aggiornamento di un origine dati aggiornerà sia lo schema delle entità che i dati di tutte le entità specificate nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="8f8e1-142">Seleziona **Arresta aggiornamento** se desideri annullare un aggiornamento esistente e riportare l'origine dati allo stato dell'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="8f8e1-143">Eliminare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="8f8e1-143">Delete a data source</span></span>

1. <span data-ttu-id="8f8e1-144">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8f8e1-145">Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri rimuovere e seleziona **Elimina** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="8f8e1-146">Conferma l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-146">Confirm your deletion.</span></span>
