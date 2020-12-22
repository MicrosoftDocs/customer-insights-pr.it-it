---
title: Connettersi alle entità nel data lake gestito di Common Data Service
description: Importa dati da un data lake Common Data Service gestito.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643403"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="56cdd-103">Connessione ai dati in un Data Lake gestito di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="56cdd-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="56cdd-104">Questo articolo fornisce informazioni su come i clienti Dynamics 365 esistenti possono connettersi rapidamente alle loro entità analitiche nel lake Common Data Service gestito.</span><span class="sxs-lookup"><span data-stu-id="56cdd-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="56cdd-105">Devi essere un amministratore dell'organizzazione Common Data Service per procedere e vedere l'elenco delle entità disponibili nel lake gestito.</span><span class="sxs-lookup"><span data-stu-id="56cdd-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="56cdd-106">Considerazioni importanti</span><span class="sxs-lookup"><span data-stu-id="56cdd-106">Important considerations</span></span>

<span data-ttu-id="56cdd-107">I dati archiviati nei servizi online come Azure Data Lake Storage possono essere archiviati in una posizione diversa rispetto a quella in cui i dati vengono elaborati o archiviati in Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="56cdd-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="56cdd-108">Importando o connettendoti a dati archiviati nei servizi online, accetti che i dati possano essere trasferiti e archiviati con Dynamics 365 Customer Insights. [Altre informazioni sono disponibili nel Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="56cdd-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="56cdd-109">Connettersi a un data lake gestito Common Data Service</span><span class="sxs-lookup"><span data-stu-id="56cdd-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="56cdd-110">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="56cdd-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="56cdd-111">Seleziona **Aggiungi origine dati**.</span><span class="sxs-lookup"><span data-stu-id="56cdd-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="56cdd-112">Seleziona **Connetti a Common Data Service** e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="56cdd-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="56cdd-113">Immetti un **nome** per l'origine dati e quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="56cdd-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="56cdd-114">Fornisci l'**Indirizzo server** per l'organizzazione Common Data Service e seleziona **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="56cdd-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56cdd-115">![Finestra di dialogo per inserire l'indirizzo del server Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="56cdd-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="56cdd-116">Seleziona le entità che desideri inserire dall'elenco disponibile.</span><span class="sxs-lookup"><span data-stu-id="56cdd-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="56cdd-117">Se alcune entità sono già selezionate, potrebbero essere utilizzate da altre applicazioni di Dynamics 365 (come Dynamics 365 Sales Insights o Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="56cdd-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="56cdd-118">Non è possibile modificare la selezione.</span><span class="sxs-lookup"><span data-stu-id="56cdd-118">You can't change the selection.</span></span> <span data-ttu-id="56cdd-119">Queste entità saranno disponibili una volta creata l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="56cdd-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56cdd-120">![Finestra di dialogo che mostra un elenco di entità nell'organizzazione Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="56cdd-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="56cdd-121">Salva la selezione per iniziare a sincronizzare le entità selezionate nel data lake gestito Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="56cdd-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="56cdd-122">Troverai la connessione appena aggiunta nella pagina **Origine dati**.</span><span class="sxs-lookup"><span data-stu-id="56cdd-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="56cdd-123">Sarà messa in coda per l'aggiornamento e mostrerà un numero di entità pari a 0 fino a quando tutte le entità sono sincronizzate.</span><span class="sxs-lookup"><span data-stu-id="56cdd-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="56cdd-124">Solo un'origine dati di un ambiente può utilizzare contemporaneamente lo stesso data lake gestito di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="56cdd-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="56cdd-125">Modificare l'origine dati di un data lake gestito Common Data Service</span><span class="sxs-lookup"><span data-stu-id="56cdd-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="56cdd-126">Modifichi la selezione dell'entità solo dopo aver creato l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="56cdd-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="56cdd-127">Ad esempio, se sono state aggiunte ulteriori entità a Common Data Service e vuoi importare anche quelle.</span><span class="sxs-lookup"><span data-stu-id="56cdd-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="56cdd-128">Per connettersi a un Common Data Service diverso, [creare una nuova origine dati](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="56cdd-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="56cdd-129">In Audience Insights, vai a **Dati** > **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="56cdd-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="56cdd-130">Accanto all'origine dati che vuoi aggiornare, seleziona i puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="56cdd-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="56cdd-131">Seleziona l'opzione **Modifica** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="56cdd-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="56cdd-132">Seleziona le entità aggiuntive dall'elenco disponibile di entità e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="56cdd-132">Select additional entities from the available list of entities and select **Save**.</span></span>
