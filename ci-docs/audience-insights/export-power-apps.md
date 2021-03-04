---
title: Connettore Power Apps
description: Connettiti con Power Apps e Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268921"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="8990c-103">Connettore Microsoft Power Apps (anteprima)</span><span class="sxs-lookup"><span data-stu-id="8990c-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="8990c-104">Importa i profili cliente unificati nelle tue app personalizzate con Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8990c-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="8990c-105">Eseguire la connessione a Power Apps e Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8990c-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="8990c-106">Customer Insights è una delle tante [origini disponibili per i dati in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="8990c-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="8990c-107">Fai riferimento alla documentazione di Power Apps per scoprire come [aggiungere una connessione dati a un'app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="8990c-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="8990c-108">Ti consigliamo di leggere anche [Utilizzo in Power Apps della delega per gestire set di dati di grandi dimensioni nelle app canvas](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="8990c-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="8990c-109">Entità disponibili</span><span class="sxs-lookup"><span data-stu-id="8990c-109">Available entities</span></span>

<span data-ttu-id="8990c-110">Dopo aver aggiunto Customer Insights come connessione dati, puoi scegliere le seguenti entità in Power Apps:</span><span class="sxs-lookup"><span data-stu-id="8990c-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="8990c-111">Cliente: per utilizzare i dati dal [profilo cliente unificato](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8990c-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="8990c-112">UnifiedActivity: per visualizzare la [sequenza temporale degli impegni](activities.md) sull'app.</span><span class="sxs-lookup"><span data-stu-id="8990c-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="8990c-113">Limiti</span><span class="sxs-lookup"><span data-stu-id="8990c-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="8990c-114">Entità recuperabili</span><span class="sxs-lookup"><span data-stu-id="8990c-114">Retrievable entities</span></span>

<span data-ttu-id="8990c-115">Puoi recuperare solo le entità **Cliente**, **UnifiedActivity** e **Segmenti** attraverso il connettore Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8990c-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="8990c-116">Vengono visualizzate altre entità perché il connettore sottostante le supporta tramite trigger in Power Automate.</span><span class="sxs-lookup"><span data-stu-id="8990c-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="8990c-117">Delega</span><span class="sxs-lookup"><span data-stu-id="8990c-117">Delegation</span></span>

<span data-ttu-id="8990c-118">La delega funziona per l'entità Cliente e l'entità UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="8990c-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="8990c-119">Delega per l'entità **Cliente**: per utilizzare la delega per questa entità, i campi devono essere indicizzati in [Indicizzazione ricerca e filtro](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="8990c-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="8990c-120">Delega per **UnifiedActivity**: la delega per questa entità funziona solo per i campi **ActivityId** e **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="8990c-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="8990c-121">Per ulteriori informazioni sulla delega, vedi [Funzioni e operazioni delegabili di Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="8990c-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="8990c-122">Esempio di controllo della raccolta</span><span class="sxs-lookup"><span data-stu-id="8990c-122">Example gallery control</span></span>

<span data-ttu-id="8990c-123">Ad esempio, aggiungi profili cliente a un [controllo della raccolta](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="8990c-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="8990c-124">Aggiungi un controlo **Raccolta** a un'app che stai creando.</span><span class="sxs-lookup"><span data-stu-id="8990c-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8990c-125">![Aggiungere un elemento della raccolta](media/connector-powerapps9.png "Aggiungere un elemento della raccolta")</span><span class="sxs-lookup"><span data-stu-id="8990c-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="8990c-126">Seleziona **Cliente** come origine dati per gli elementi.</span><span class="sxs-lookup"><span data-stu-id="8990c-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8990c-127">![Selezionare un'origine dati](media/choose-datasource-powerapps.png "Selezionare un'origine dati")</span><span class="sxs-lookup"><span data-stu-id="8990c-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="8990c-128">Puoimodificare il pannello dati a destra per selezionare quale campo deve essere visualizzato nella raccolta per l'entità Cliente.</span><span class="sxs-lookup"><span data-stu-id="8990c-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="8990c-129">Se desideri mostrare nella raccolta qualsiasi campo del cliente selezionato, compila la proprietà Testo di un'etichetta: **{Name_of_the_gallery} .Selezionato. {property_name}**</span><span class="sxs-lookup"><span data-stu-id="8990c-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="8990c-130">Esempio: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="8990c-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="8990c-131">Per visualizzare la sequenza temporale unificata per un cliente, aggiungi un elemento Raccolta e aggiungi la proprietà Elementi: **Filtro ("UnifiedActivity", CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="8990c-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="8990c-132">Esempio: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="8990c-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]