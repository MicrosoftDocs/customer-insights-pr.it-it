---
title: Aggiornamento incrementale per origini dati basate su Power Query
description: Aggiorna i dati nuovi e aggiornati per origini dati di grandi dimensioni basate su Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406127"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="89010-103">Aggiornamento incrementale per origini dati basate su Power Query</span><span class="sxs-lookup"><span data-stu-id="89010-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="89010-104">L'aggiornamento incrementale per le origini dati offre i seguenti vantaggi:</span><span class="sxs-lookup"><span data-stu-id="89010-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="89010-105">**Aggiornamenti più rapidi** - Vengono aggiornati solo i dati che sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="89010-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="89010-106">Ad esempio, potresti aggiornare solo gli ultimi cinque giorni di uno set di dati storici.</span><span class="sxs-lookup"><span data-stu-id="89010-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="89010-107">**Maggiore affidabilità** - Con aggiornamenti più piccoli, non è necessario mantenere le connessioni a sistemi di origine volatili per lungo tempo, riducendo il rischio di problemi di connessione.</span><span class="sxs-lookup"><span data-stu-id="89010-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="89010-108">**Utilizzo ridotto delle risorse** - L'aggiornamento di un solo sottoinsieme dei dati totali comporta un uso più efficiente delle risorse di elaborazione e riduce l'impatto ambientale.</span><span class="sxs-lookup"><span data-stu-id="89010-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="89010-109">Configura aggiornamento incrementale</span><span class="sxs-lookup"><span data-stu-id="89010-109">Configure incremental refresh</span></span>

<span data-ttu-id="89010-110">Audience Insights consente l'aggiornamento incrementale delle origini dati importate tramite Power Query che supportano l'inserimento incrementale.</span><span class="sxs-lookup"><span data-stu-id="89010-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="89010-111">Ad esempio, i database SQL di Azure con campi di data e ora, che indicano quando è stato effettuato l'ultimo aggiornamento dei record di dati.</span><span class="sxs-lookup"><span data-stu-id="89010-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="89010-112">[Crea una nuova origine dati basata su Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="89010-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="89010-113">Immetti un nome per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="89010-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="89010-114">Seleziona un origine dati che supporta l'aggiornamento incrementale, come il database SQL di Azure.</span><span class="sxs-lookup"><span data-stu-id="89010-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="89010-115">Seleziona le entità o le tabelle da inserire.</span><span class="sxs-lookup"><span data-stu-id="89010-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="89010-116">Completa i passaggi per la trasformazione e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="89010-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="89010-117">Nella finestra di dialogo **Configura aggiornamento incrementale**, seleziona **Configura** per aprire le **impostazioni di aggiornamento incrementali**.</span><span class="sxs-lookup"><span data-stu-id="89010-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="89010-118">Se selezioni **Ignora**, l'origine dati aggiornerà l'intero set di dati.</span><span class="sxs-lookup"><span data-stu-id="89010-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="89010-119">Puoi anche applicare l'aggiornamento incrementale in seguito modificando un origine dati esistente.</span><span class="sxs-lookup"><span data-stu-id="89010-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="89010-120">In **Impostazioni aggiornamento incrementale**, configurerai l'aggiornamento incrementale di tutte le entità selezionate durante la creazione dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="89010-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="89010-121">![Configurare le entità in un origine dati per l'aggiornamento incrementale](media/incremental-refresh-settings.png "Configurare le entità in un origine dati per l'aggiornamento incrementale")</span><span class="sxs-lookup"><span data-stu-id="89010-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="89010-122">Seleziona un'entità e fornisci i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="89010-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="89010-123">**Seleziona la chiave primaria**: seleziona una chiave primaria per l'entità o la tabella.</span><span class="sxs-lookup"><span data-stu-id="89010-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="89010-124">**Definisci il campo "Ultimo aggiornamento"**: in questo campo verranno visualizzati solo gli attributi di tipo data o ora.</span><span class="sxs-lookup"><span data-stu-id="89010-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="89010-125">Seleziona un attributo che indica quando i record sono stati aggiornati l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="89010-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="89010-126">Verrà utilizzato per identificare i record che rientrano nell'intervallo di tempo dell'aggiornamento incrementale.</span><span class="sxs-lookup"><span data-stu-id="89010-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="89010-127">**Verifica la presenza di aggiornamenti ogni**: specifica l'intervallo di tempo dell'aggiornamento incrementale.</span><span class="sxs-lookup"><span data-stu-id="89010-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="89010-128">Seleziona **Salva** per completare la creazione dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="89010-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="89010-129">L'aggiornamento iniziale dei dati sarà un aggiornamento completo.</span><span class="sxs-lookup"><span data-stu-id="89010-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="89010-130">Successivamente, l'aggiornamento incrementale dei dati avviene come configurato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="89010-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
