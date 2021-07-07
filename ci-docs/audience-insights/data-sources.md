---
title: Utilizzare origini dati per inserire dati
description: Scopri come importare dati da varie origini.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304701"
---
# <a name="data-sources-overview"></a><span data-ttu-id="8c004-103">Panoramica delle origini dati</span><span class="sxs-lookup"><span data-stu-id="8c004-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8c004-104">La funzionalità Audience Insights in Dynamics 365 Customer Insights si connette ai dati da un ampio insieme di origini.</span><span class="sxs-lookup"><span data-stu-id="8c004-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="8c004-105">La connessione a un'origine dati viene spesso definita processo di *inserimento dati*.</span><span class="sxs-lookup"><span data-stu-id="8c004-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="8c004-106">Dopo aver inserito i dati, puoi [unificare](data-unification.md) e agire su di essi.</span><span class="sxs-lookup"><span data-stu-id="8c004-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="8c004-107">Aggiungi un'origine dati</span><span class="sxs-lookup"><span data-stu-id="8c004-107">Add a data source</span></span>

<span data-ttu-id="8c004-108">Fai riferimento agli articoli dettagliati su come aggiungere un'origine dati, a seconda dell'opzione scelta.</span><span class="sxs-lookup"><span data-stu-id="8c004-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="8c004-109">Puoi aggiungere un'origine dati in tre modi principali:</span><span class="sxs-lookup"><span data-stu-id="8c004-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="8c004-110">Attraverso dozzine di connettori Power Query</span><span class="sxs-lookup"><span data-stu-id="8c004-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="8c004-111">Da una cartella di Common Data Model</span><span class="sxs-lookup"><span data-stu-id="8c004-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="8c004-112">Dal tuo lake Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="8c004-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="8c004-113">Aggiungere dati dalle origini dati locale</span><span class="sxs-lookup"><span data-stu-id="8c004-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="8c004-114">L'inserimento di dati da origini dati locale in informazioni dettagliate gruppo di destinatari è supportata in base ai flussi di dati Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="8c004-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="8c004-115">I flussi di dati possono essere abilitati in Customer Insights [fornendo l'URL dell'ambiente Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) quando si imposta l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8c004-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="8c004-116">Le origini dati create dopo l'associazione di un ambiente Dataverse con Customer Insights utilizzeranno i [flussi di dati Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8c004-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="8c004-117">I flussi di dati supportano la connettività locale utilizzando il gateway di dati.</span><span class="sxs-lookup"><span data-stu-id="8c004-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="8c004-118">Rimuovi e ricrea le origini dati che esistevano prima che un ambiente Dataverse fosse associato per [utilizzare i gateway di dati locale](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="8c004-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="8c004-119">I gateway dati di un ambiente esistente Power BI o Power Apps saranno visibili e potrai riutilizzarli in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8c004-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="8c004-120">La pagina delle origini dati mostra i collegamenti per andare all'ambiente Microsoft Power Platform in cui è possibile visualizzare e configurare i gateway dati locale.</span><span class="sxs-lookup"><span data-stu-id="8c004-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="8c004-121">Esamina i dati inseriti</span><span class="sxs-lookup"><span data-stu-id="8c004-121">Review ingested data</span></span>

<span data-ttu-id="8c004-122">Vedrai il nome di ciascuna origine dati inserita, il suo stato e l'ultima volta che i dati sono stati aggiornati per quell'origine.</span><span class="sxs-lookup"><span data-stu-id="8c004-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="8c004-123">Puoi ordinare l'elenco delle origini dati per colonna.</span><span class="sxs-lookup"><span data-stu-id="8c004-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8c004-124">![Origine dati aggiunta](media/configure-data-datasource-added.png "Origine dati aggiunta")</span><span class="sxs-lookup"><span data-stu-id="8c004-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="8c004-125">Stato</span><span class="sxs-lookup"><span data-stu-id="8c004-125">Status</span></span>  |<span data-ttu-id="8c004-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c004-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="8c004-127">Operazione riuscita</span><span class="sxs-lookup"><span data-stu-id="8c004-127">Successful</span></span>   |<span data-ttu-id="8c004-128">L'inserimento dell'origine dati è riuscito se un'ora è menzionata nella colonna **Aggiornato**.</span><span class="sxs-lookup"><span data-stu-id="8c004-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="8c004-129">Non avviato</span><span class="sxs-lookup"><span data-stu-id="8c004-129">Not started</span></span>   |<span data-ttu-id="8c004-130">L'origine dati non è ancora stata inserita o è ancora in modalità bozza.</span><span class="sxs-lookup"><span data-stu-id="8c004-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="8c004-131">Aggiornamento in corso</span><span class="sxs-lookup"><span data-stu-id="8c004-131">Refreshing</span></span>    |<span data-ttu-id="8c004-132">L'inserimento dati è in corso.</span><span class="sxs-lookup"><span data-stu-id="8c004-132">Data ingestion is in progress.</span></span> <span data-ttu-id="8c004-133">Puoi annullare questa operazione selezionando **Arresta aggiornamento** nella colonna **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="8c004-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="8c004-134">L'interruzione dell'aggiornamento di un'origine dati la riporterà al suo ultimo stato di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="8c004-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="8c004-135">Non inviato</span><span class="sxs-lookup"><span data-stu-id="8c004-135">Failed</span></span>     |<span data-ttu-id="8c004-136">Si sono verificati errori durante l'inserimento dati.</span><span class="sxs-lookup"><span data-stu-id="8c004-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="8c004-137">Seleziona il valore nella colonna **Stato** di qualsiasi origine dati per esaminare maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="8c004-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="8c004-138">Nel riquadro **Dettagli stato** espandi **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="8c004-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="8c004-139">Seleziona **Vedi dettagli** per altre informazioni sullo stato di aggiornamento, inclusi i dettagli di errore e gli aggiornamenti del processo downstream.</span><span class="sxs-lookup"><span data-stu-id="8c004-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="8c004-140">Il caricamento dei dati può richiedere tempo.</span><span class="sxs-lookup"><span data-stu-id="8c004-140">Loading data can take time.</span></span> <span data-ttu-id="8c004-141">Al termine del completamento dell'aggiornamento, i dati inseriti possono essere rivisti dalla pagina **Entità**.</span><span class="sxs-lookup"><span data-stu-id="8c004-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="8c004-142">Per ulteriori informazioni, vedi [Entità](entities.md).</span><span class="sxs-lookup"><span data-stu-id="8c004-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="8c004-143">Aggiornare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="8c004-143">Refresh a data source</span></span>

<span data-ttu-id="8c004-144">Le origini dati possono essere aggiornate in base a una pianificazione automatica o manualmente su richiesta.</span><span class="sxs-lookup"><span data-stu-id="8c004-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="8c004-145">Vai a **Amministratore** > **Sistema** > [**Pianifica**](system.md#schedule-tab) per configurare gli aggiornamenti pianificati di tutte le origini dati inserite.</span><span class="sxs-lookup"><span data-stu-id="8c004-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="8c004-146">Per aggiornare un origine dati su richiesta, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="8c004-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="8c004-147">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="8c004-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8c004-148">Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri aggiornare e seleziona **Aggiorna** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8c004-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="8c004-149">L'origine dati è ora attivata per un aggiornamento manuale.</span><span class="sxs-lookup"><span data-stu-id="8c004-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="8c004-150">L'aggiornamento di un'origine dati aggiornerà sia lo schema dell'entità che i dati per tutte le entità specificate nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8c004-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="8c004-151">Seleziona **Arresta aggiornamento** se desideri annullare un aggiornamento esistente e riportare l'origine dati allo stato dell'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="8c004-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="8c004-152">Eliminare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="8c004-152">Delete a data source</span></span>

1. <span data-ttu-id="8c004-153">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="8c004-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8c004-154">Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri rimuovere e seleziona **Elimina** dal menu a tendina.</span><span class="sxs-lookup"><span data-stu-id="8c004-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="8c004-155">Conferma l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="8c004-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
