---
title: Connettore Power BI
description: Scopri come utilizzare il connettore Dynamics 365 Customer Insights in Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477093"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="1192b-103">Connettore per Power BI(anteprima)</span><span class="sxs-lookup"><span data-stu-id="1192b-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="1192b-104">Crea visualizzazioni per i dati con Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="1192b-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="1192b-105">Genera ulteriori informazioni dettagliate e crea report con i dati cliente unificati.</span><span class="sxs-lookup"><span data-stu-id="1192b-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1192b-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1192b-106">Prerequisites</span></span>

- <span data-ttu-id="1192b-107">Disponi di profili cliente unificati.</span><span class="sxs-lookup"><span data-stu-id="1192b-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="1192b-108">L'ultima versione di [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) è installata sul tuo computer.</span><span class="sxs-lookup"><span data-stu-id="1192b-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="1192b-109">[Scopri di più su Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="1192b-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="1192b-110">Configurare il connettore per Power BI</span><span class="sxs-lookup"><span data-stu-id="1192b-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="1192b-111">In Power BI Desktop, seleziona **File** > **Estrai dati**.</span><span class="sxs-lookup"><span data-stu-id="1192b-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="1192b-112">Seleziona **Altro** e cerca **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="1192b-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="1192b-113">Seleziona **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="1192b-113">Select **Connect**.</span></span>

1. <span data-ttu-id="1192b-114">**Accedi** con lo stesso account organizzativo utilizzato per Customer Insights e seleziona **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="1192b-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1192b-115">L'account indicato in questo passaggio viene utilizzato per recuperare i dati da Customer Insights e non è necessario che sia lo stesso con cui hai effettuato l'accesso a Power BI.</span><span class="sxs-lookup"><span data-stu-id="1192b-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="1192b-116">Per reimpostare l'account utilizzato per il recupero dei dati, apri Power BI e seleziona **File** > **Opzioni** > **Impostazioni** > **Impostazioni origine dati**.</span><span class="sxs-lookup"><span data-stu-id="1192b-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="1192b-117">Nell'elenco delle origini dati, seleziona **Accesso a Dynamics 365 Customer Insights**, quindi **Deseleziona autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="1192b-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="1192b-118">Nella finestra di dialogo **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="1192b-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="1192b-119">viene visualizzato l'elenco di tutti gli ambienti a cui hai accesso.</span><span class="sxs-lookup"><span data-stu-id="1192b-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="1192b-120">Espandi un ambiente e apri una qualsiasi delle cartelle (entità, misure, segmenti, arricchimenti).</span><span class="sxs-lookup"><span data-stu-id="1192b-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="1192b-121">Ad esempio, apri la cartella **Entità** per vedere tutte le entità che puoi importare.</span><span class="sxs-lookup"><span data-stu-id="1192b-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="1192b-122">![Esplorazione connettori Power BI](media/power-bi-navigator.png "Esplorazione connettori Power BI")</span><span class="sxs-lookup"><span data-stu-id="1192b-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="1192b-123">Seleziona le caselle di controllo accanto alle entità da includere e **Carica**.</span><span class="sxs-lookup"><span data-stu-id="1192b-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="1192b-124">Puoi selezionare più entità da più ambienti.</span><span class="sxs-lookup"><span data-stu-id="1192b-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="1192b-125">Durante il caricamento delle entità verrà visualizzata una finestra di dialogo di caricamento.</span><span class="sxs-lookup"><span data-stu-id="1192b-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="1192b-126">Una volta caricate tutte le entità selezionate, puoi utilizzare le funzionalità di Power BI per visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="1192b-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="1192b-127">Set di dati di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="1192b-127">Large data sets</span></span>

<span data-ttu-id="1192b-128">Il connettore Customer Insights per Power BI è progettato per funzionare con set di dati che contengono fino a 1 milione di profili cliente.</span><span class="sxs-lookup"><span data-stu-id="1192b-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="1192b-129">L'importazione di set di dati più grandi può funzionare, ma richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="1192b-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="1192b-130">Inoltre, potrebbe verificarsi un timeout nel processo a causa delle limitazioni di Power BI.</span><span class="sxs-lookup"><span data-stu-id="1192b-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="1192b-131">Per ulteriori informazioni, vedere [Power BI: raccomandazioni per set di dati di grandi dimensioni](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="1192b-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="1192b-132">Utilizzare un sottoinsieme di dati</span><span class="sxs-lookup"><span data-stu-id="1192b-132">Work with a subset of data</span></span>

<span data-ttu-id="1192b-133">Prendi in considerazione l'idea di utilizzare un sottoinsieme di dati.</span><span class="sxs-lookup"><span data-stu-id="1192b-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="1192b-134">Ad esempio, puoi creare [segmenti](segments.md) anziché esportare tutti i record del cliente in Power BI.</span><span class="sxs-lookup"><span data-stu-id="1192b-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1192b-135">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1192b-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="1192b-136">L'ambiente Customer Insights non viene visualizzato in Power BI</span><span class="sxs-lookup"><span data-stu-id="1192b-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="1192b-137">Ambienti che hanno più di una [relazione](relationships.md) definita tra due entità identiche in Audience Insights non saranno disponibili nel connettore di Power BI.</span><span class="sxs-lookup"><span data-stu-id="1192b-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="1192b-138">Puoi identificare e rimuovere le Relazioni duplicate.</span><span class="sxs-lookup"><span data-stu-id="1192b-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="1192b-139">In Audience Insights, vai a **Dati** > **Relazioni** nell'ambiente che ti manca in Power BI.</span><span class="sxs-lookup"><span data-stu-id="1192b-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="1192b-140">Identifica le relazioni duplicate:</span><span class="sxs-lookup"><span data-stu-id="1192b-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="1192b-141">Controlla se c'è più di una relazione definita tra le stesse due entità.</span><span class="sxs-lookup"><span data-stu-id="1192b-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="1192b-142">Controlla se esiste una relazione creata tra due entità che sono entrambe incluse nel processo di unificazione.</span><span class="sxs-lookup"><span data-stu-id="1192b-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="1192b-143">Esiste una relazione implicita definita tra tutte le entità incluse nel processo di unificazione.</span><span class="sxs-lookup"><span data-stu-id="1192b-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="1192b-144">Rimuovi qualsiasi Relazione duplicata identificata.</span><span class="sxs-lookup"><span data-stu-id="1192b-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="1192b-145">Dopo la rimozione delle Relazioni duplicate, prova a configurare il connettore di Power BI di nuovo.</span><span class="sxs-lookup"><span data-stu-id="1192b-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="1192b-146">L'ambiente dovrebbe essere disponibile ora.</span><span class="sxs-lookup"><span data-stu-id="1192b-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

