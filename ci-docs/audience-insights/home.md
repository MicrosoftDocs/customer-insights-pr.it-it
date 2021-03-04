---
title: Home page di Audience Insights
description: Esplora l'app nella home page.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477046"
---
# <a name="create-a-new-environment"></a><span data-ttu-id="7914b-103">Crea un nuovo ambiente</span><span class="sxs-lookup"><span data-stu-id="7914b-103">Create a new environment</span></span>

## <a name="create-a-trial-environment"></a><span data-ttu-id="7914b-104">Crea un ambiente di valutazione</span><span class="sxs-lookup"><span data-stu-id="7914b-104">Create a trial environment</span></span>

<span data-ttu-id="7914b-105">Puoi registrarti per una versione di valutazione nella [pagina di iscrizione alla versione di valutazione](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span><span class="sxs-lookup"><span data-stu-id="7914b-105">You can sign up for a trial on the [trial sign up page](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span></span> 

> [!NOTE]
> <span data-ttu-id="7914b-106">Le versioni di valutazione scadono dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="7914b-106">Trials expire after 30 days.</span></span>

1. <span data-ttu-id="7914b-107">Scegli l'opzione **Iscriviti a una versione di prova gratuita** e seleziona **Iscriviti ora**.</span><span class="sxs-lookup"><span data-stu-id="7914b-107">Choose the **Sign up for a free trial** option and select **Sign up now**.</span></span>

1. <span data-ttu-id="7914b-108">Fornisci il tuo indirizzo e-mail di lavoro o della scuola, raccontaci qualcosa di te e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7914b-108">Provide your work or school email address, tell us a more about yourself and select **Next**.</span></span>

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Finestra di dialogo per iscriversi a una versione di valutazione":::

1. <span data-ttu-id="7914b-110">Fornisci un **nome** per il tuo nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="7914b-110">Provide a **Name** for your new environment.</span></span> 

1. <span data-ttu-id="7914b-111">Selezionare il tipo di versione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="7914b-111">Select the trial type.</span></span>

1. <span data-ttu-id="7914b-112">Scegli l'**area** per il tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="7914b-112">Choose the **Region** for your environment.</span></span>

1. <span data-ttu-id="7914b-113">Facoltativamente, per gli amministratori di un'organizzazione Dynamics 365: seleziona **Impostazioni avanzate** e fornisci l'URL della tua organizzazione per utilizzare le funzionalità previsione come l'abbandono dei clienti.</span><span class="sxs-lookup"><span data-stu-id="7914b-113">Optionally, for admins of a Dynamics 365 organization: Select **Advanced settings** and provide the URL of your organization to use prediction features like customer churn.</span></span>

1. <span data-ttu-id="7914b-114">Seleziona **Crea**.</span><span class="sxs-lookup"><span data-stu-id="7914b-114">Select **Create**.</span></span> 

<span data-ttu-id="7914b-115">Dopo che l'ambiente è stato creato, vedrai l'ambiente **Demo** che ti consente di esplorare l'app con dati fittizi.</span><span class="sxs-lookup"><span data-stu-id="7914b-115">After the environment was created, you'll see the **Demo** environment which lets you explore the app with fictitious data.</span></span> <span data-ttu-id="7914b-116">Puoi modificare i dati di esempio con quelli del tuo settore.</span><span class="sxs-lookup"><span data-stu-id="7914b-116">You can change the sample data to match your industry.</span></span> <span data-ttu-id="7914b-117">Seleziona l'icona **Impostazioni** nell'intestazione e seleziona **Impostazioni demo**.</span><span class="sxs-lookup"><span data-stu-id="7914b-117">Select the **Settings** icon in the header and select **Demo settings**.</span></span> <span data-ttu-id="7914b-118">Inoltre, puoi cambiare il tema visivo.</span><span class="sxs-lookup"><span data-stu-id="7914b-118">Additionally, you can change the visual theme.</span></span> 

<span data-ttu-id="7914b-119">Puoi [passare all'ambiente](#switch-environments) creato durante il processo di registrazione per lavorare con i tuoi dati.</span><span class="sxs-lookup"><span data-stu-id="7914b-119">You [switch to the environment](#switch-environments) you created during the sign-up process to work with your own data.</span></span>

## <a name="create-a-new-production-or-sandbox-environment"></a><span data-ttu-id="7914b-120">Crea un nuovo ambiente sandbox o di produzione</span><span class="sxs-lookup"><span data-stu-id="7914b-120">Create a new production or sandbox environment</span></span>

<span data-ttu-id="7914b-121">Nel tuo ambiente, seleziona il selettore **Ambienti** nell'intestazione dell'app e seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7914b-121">In your environment, select the **Environments** picker in the app header and select **New**.</span></span>

<span data-ttu-id="7914b-122">Segui i passaggi come per [creare un ambiente di prova](#create-a-trial-environment).</span><span class="sxs-lookup"><span data-stu-id="7914b-122">Follow the steps as if you [create a trial environment](#create-a-trial-environment).</span></span> <span data-ttu-id="7914b-123">Per impostazione predefinita, i dati vengono archiviati nel data lake gestito di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7914b-123">By default, data is stored in the Customer Insights managed data lake.</span></span> <span data-ttu-id="7914b-124">Ottieni un'opzione aggiuntiva quando selezioni **Impostazioni avanzate** per archiviare i dati nel tuo Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="7914b-124">You get an additional option when selecting **Advanced settings** to store your data in your own Azure Data Lake.</span></span> <span data-ttu-id="7914b-125">Fornisci il nome e la chiave dell'account per stabilire una connessione al tuo Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="7914b-125">Provide your account name and account key to establish a connection to your Azure Data Lake.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7914b-126">Salvando i dati in Azure Data Lake Storage, accetti che i dati vengano trasferiti e archiviati nella posizione geografica appropriata per tale account di archiviazione di Azure, che può essere diversa da quella in cui sono archiviati i dati in Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7914b-126">By saving data to your Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="7914b-127">Altre informazioni nel Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="7914b-127">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a><span data-ttu-id="7914b-128">Esplorare la home page</span><span class="sxs-lookup"><span data-stu-id="7914b-128">Explore the home page</span></span>

<span data-ttu-id="7914b-129">Puoi [accedere a Audience Insights da Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) con il seguente URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="7914b-129">You can [access audience insights from Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) on the following URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span></span>
<span data-ttu-id="7914b-130">La **home page** mostra una panoramica di segmenti, misure e dati di arricchimento (se configurati) dopo aver completato le fasi [mapping](map-entities.md), [corrispondenza](match-entities.md), e [unione](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="7914b-130">The **Home** page shows an overview of segments, measures, and enrichment data (if configured)after completing the [map](map-entities.md), [match](match-entities.md), and [merge](merge-entities.md) phases.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="7914b-131">![Informazioni dettagliate nella home page](media/home-page-insights.png "Informazioni dettagliate nella home page")</span><span class="sxs-lookup"><span data-stu-id="7914b-131">![Insights on Home page](media/home-page-insights.png "Insights on Home page")</span></span>

<span data-ttu-id="7914b-132">Sotto **Segmenti recenti**, sono visualizzati gruppi di clienti in base ad attributi demografici, comportamentali o transazionali che hai definito.</span><span class="sxs-lookup"><span data-stu-id="7914b-132">Under **Recent segments**, you see groups of customers based on demographic, behavioral, or transactional attributes that you've defined.</span></span> <span data-ttu-id="7914b-133">[La creazione di segmenti](segments.md) ti aiuta a raggruppare la tua base di clienti e ad indirizzare meglio le tue attività commerciali.</span><span class="sxs-lookup"><span data-stu-id="7914b-133">[Creating segments](segments.md) helps you to group your customer base and better target your business activities.</span></span>

<span data-ttu-id="7914b-134">**Misure recenti** mostra i riquadri con [gli indicatori di prestazioni chiave](measures.md) che hai definito.</span><span class="sxs-lookup"><span data-stu-id="7914b-134">**Recent measures** show tiles with [key performance indicators (KPIs)](measures.md) that you've defined.</span></span> <span data-ttu-id="7914b-135">Ad esempio, la probabilità media di abbandono di un cliente o la spesa media online per cliente.</span><span class="sxs-lookup"><span data-stu-id="7914b-135">For example, average likelihood of a customer to churn or the average online spend per customer.</span></span>

<span data-ttu-id="7914b-136">La sezione **Arricchimenti recenti** elenca i risultati delle esecuzioni di arricchimento completate di recente.</span><span class="sxs-lookup"><span data-stu-id="7914b-136">The **Recent enrichments** section lists the results of the enrichment runs that completed recently.</span></span> <span data-ttu-id="7914b-137">Gli [arricchimenti](enrichment-hub.md) aggiungono informazioni sulla base di clienti.</span><span class="sxs-lookup"><span data-stu-id="7914b-137">[Enrichments](enrichment-hub.md) add information about your customer base.</span></span> <span data-ttu-id="7914b-138">Ad esempio, comprendendo gli interessi e i marchi con cui hanno affinità.</span><span class="sxs-lookup"><span data-stu-id="7914b-138">For example, by understanding the interests and brands that they have affinity for.</span></span>

## <a name="switch-environments"></a><span data-ttu-id="7914b-139">Cambiare ambiente</span><span class="sxs-lookup"><span data-stu-id="7914b-139">Switch environments</span></span>

<span data-ttu-id="7914b-140">Seleziona il controllo **Ambiente** nell'angolo superiore destro della pagina per modificare gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="7914b-140">Select the **Environment** control in the upper-right corner of the page to change environments.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="7914b-141">![Cambia ambiente](media/home-page-environment-switcher.png "Cambia ambiente")</span><span class="sxs-lookup"><span data-stu-id="7914b-141">![Switch environment](media/home-page-environment-switcher.png "Switch environment")</span></span>

<span data-ttu-id="7914b-142">Gli amministratori possono creare e gestire [ambienti multipli](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="7914b-142">Administrators can create and manage [multiple environments](manage-environments.md).</span></span> <span data-ttu-id="7914b-143">Il mantenimento di più di un ambiente può essere utile se, ad esempio, la tua organizzazione opera a livello internazionale e devi separare dati e informazioni dettagliate in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="7914b-143">Maintaining more than one environment may be useful if, for example, your organization operates internationally and you need to segregate data and insights in different ways.</span></span>

## <a name="next-step"></a><span data-ttu-id="7914b-144">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7914b-144">Next step</span></span>

<span data-ttu-id="7914b-145">Per vedere le tue informazioni dettagliate sulla home page, dovrai prima [aggiungere le origini dati](data-sources.md) e [unifica](data-unification.md) i tuoi dati per creare profili cliente.</span><span class="sxs-lookup"><span data-stu-id="7914b-145">To see your own insights on the home page, you'll first need to [add data sources](data-sources.md) and [unify](data-unification.md) your data to build customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]