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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887899"
---
# <a name="data-sources-overview"></a><span data-ttu-id="b1161-103">Panoramica delle origini dati</span><span class="sxs-lookup"><span data-stu-id="b1161-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b1161-104">La funzionalità Audience Insights in Dynamics 365 Customer Insights si connette ai dati da un ampio insieme di origini.</span><span class="sxs-lookup"><span data-stu-id="b1161-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="b1161-105">La connessione a un'origine dati viene spesso definita processo di *inserimento dati*.</span><span class="sxs-lookup"><span data-stu-id="b1161-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="b1161-106">Dopo aver inserito i dati, puoi [unificare](data-unification.md) e agire su di essi.</span><span class="sxs-lookup"><span data-stu-id="b1161-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="b1161-107">Aggiungi un'origine dati</span><span class="sxs-lookup"><span data-stu-id="b1161-107">Add a data source</span></span>

<span data-ttu-id="b1161-108">Fai riferimento agli articoli dettagliati su come aggiungere un'origine dati, a seconda dell'opzione scelta.</span><span class="sxs-lookup"><span data-stu-id="b1161-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="b1161-109">Puoi aggiungere un'origine dati in tre modi principali:</span><span class="sxs-lookup"><span data-stu-id="b1161-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="b1161-110">Attraverso dozzine di connettori Power Query</span><span class="sxs-lookup"><span data-stu-id="b1161-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="b1161-111">Da una cartella di Common Data Model</span><span class="sxs-lookup"><span data-stu-id="b1161-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="b1161-112">Dal tuo lake Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b1161-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="b1161-113">Aggiungere dati dalle origini dati locale</span><span class="sxs-lookup"><span data-stu-id="b1161-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="b1161-114">L'inserimento di dati da origini dati locale in Informazioni dettagliate gruppo di destinatari è supportata in base ai flussi di dati Power Platform.</span><span class="sxs-lookup"><span data-stu-id="b1161-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="b1161-115">I flussi di dati possono essere abilitati in Customer Insights [fornendo l'URL dell'ambiente Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) quando si imposta l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="b1161-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="b1161-116">Le origini dati create dopo l'associazione di un ambiente Dataverse con Customer Insights utilizzeranno i [flussi di dati Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b1161-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="b1161-117">I flussi di dati supportano la connettività locale utilizzando i gateway di dati.</span><span class="sxs-lookup"><span data-stu-id="b1161-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="b1161-118">Rimuovi e ricrea le origini dati che esistevano prima che un ambiente Dataverse fosse associato per utilizzare i gateway di dati locale.</span><span class="sxs-lookup"><span data-stu-id="b1161-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="b1161-119">I gateway dati di un ambiente esistente Power BI o Power Apps saranno visibili e potrai riutilizzarli in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b1161-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="b1161-120">La pagina delle origini dati mostra i collegamenti per andare all'ambiente Power Platform in cui è possibile visualizzare e configurare gateway dati locali.</span><span class="sxs-lookup"><span data-stu-id="b1161-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Screenshot della pagina delle origini dati che mostra i collegamenti che puntano all'ambiente Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="b1161-122">Esamina i dati inseriti</span><span class="sxs-lookup"><span data-stu-id="b1161-122">Review ingested data</span></span>

<span data-ttu-id="b1161-123">Vedrai il nome di ciascuna origine dati inserita, il suo stato e l'ultima volta che i dati sono stati aggiornati per quell'origine.</span><span class="sxs-lookup"><span data-stu-id="b1161-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="b1161-124">Puoi ordinare l'elenco delle origini dati per colonna.</span><span class="sxs-lookup"><span data-stu-id="b1161-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1161-125">![Origine dati aggiunta](media/configure-data-datasource-added.png "Origine dati aggiunta")</span><span class="sxs-lookup"><span data-stu-id="b1161-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="b1161-126">Stato</span><span class="sxs-lookup"><span data-stu-id="b1161-126">Status</span></span>  |<span data-ttu-id="b1161-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1161-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b1161-128">Operazione riuscita</span><span class="sxs-lookup"><span data-stu-id="b1161-128">Successful</span></span>   |<span data-ttu-id="b1161-129">L'inserimento dell'origine dati è riuscito se un'ora è menzionata nella colonna **Aggiornato**.</span><span class="sxs-lookup"><span data-stu-id="b1161-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="b1161-130">Non avviato</span><span class="sxs-lookup"><span data-stu-id="b1161-130">Not started</span></span>   |<span data-ttu-id="b1161-131">L'origine dati non è ancora stata inserita o è ancora in modalità bozza.</span><span class="sxs-lookup"><span data-stu-id="b1161-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="b1161-132">Aggiornamento in corso</span><span class="sxs-lookup"><span data-stu-id="b1161-132">Refreshing</span></span>    |<span data-ttu-id="b1161-133">L'inserimento dati è in corso.</span><span class="sxs-lookup"><span data-stu-id="b1161-133">Data ingestion is in progress.</span></span> <span data-ttu-id="b1161-134">Puoi annullare questa operazione selezionando **Arresta aggiornamento** nella colonna **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="b1161-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="b1161-135">L'interruzione dell'aggiornamento di un'origine dati la riporterà al suo ultimo stato di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b1161-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="b1161-136">Non inviato</span><span class="sxs-lookup"><span data-stu-id="b1161-136">Failed</span></span>     |<span data-ttu-id="b1161-137">Si sono verificati errori durante l'inserimento dati.</span><span class="sxs-lookup"><span data-stu-id="b1161-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="b1161-138">Seleziona il valore nella colonna **Stato** di qualsiasi origine dati per esaminare maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="b1161-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="b1161-139">Nel riquadro **Dettagli stato** espandi **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="b1161-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="b1161-140">Seleziona **Vedi dettagli** per altre informazioni sullo stato di aggiornamento, inclusi i dettagli di errore e gli aggiornamenti del processo downstream.</span><span class="sxs-lookup"><span data-stu-id="b1161-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="b1161-141">Il caricamento dei dati potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="b1161-141">Loading data can take some time.</span></span> <span data-ttu-id="b1161-142">Al termine del completamento dell'aggiornamento, i dati inseriti possono essere rivisti dalla pagina **Entità**.</span><span class="sxs-lookup"><span data-stu-id="b1161-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="b1161-143">Per ulteriori informazioni, vedi [Entità](entities.md).</span><span class="sxs-lookup"><span data-stu-id="b1161-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="b1161-144">Aggiornare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="b1161-144">Refresh a data source</span></span>

<span data-ttu-id="b1161-145">Le origini dati possono essere aggiornate in base a una pianificazione automatica o manualmente su richiesta.</span><span class="sxs-lookup"><span data-stu-id="b1161-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="b1161-146">Vai a **Amministratore** > **Sistema** > [**Pianifica**](system.md#schedule-tab) per configurare gli aggiornamenti pianificati di tutte le origini dati inserite.</span><span class="sxs-lookup"><span data-stu-id="b1161-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="b1161-147">Per aggiornare un origine dati su richiesta, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="b1161-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="b1161-148">In Audience Insights, vai a **Dati** > **Origini dati**</span><span class="sxs-lookup"><span data-stu-id="b1161-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="b1161-149">Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri aggiornare e seleziona **Aggiorna** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b1161-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="b1161-150">L'origine dati è ora attivata per un aggiornamento manuale.</span><span class="sxs-lookup"><span data-stu-id="b1161-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="b1161-151">L'aggiornamento di un'origine dati aggiornerà sia lo schema dell'entità che i dati per tutte le entità specificate nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="b1161-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="b1161-152">Seleziona **Arresta aggiornamento** se desideri annullare un aggiornamento esistente e riportare l'origine dati allo stato dell'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b1161-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="b1161-153">Eliminare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="b1161-153">Delete a data source</span></span>

1. <span data-ttu-id="b1161-154">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="b1161-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b1161-155">Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri rimuovere e seleziona **Elimina** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="b1161-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="b1161-156">Conferma l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="b1161-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
