---
title: Arricchimento con l'arricchimento di terze parti di HERE Technologies
description: Informazioni generali sull'arricchimento di terze parti di HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668683"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="a71b6-103">Arricchimento dei profili cliente con HERE Technologies (anteprima)</span><span class="sxs-lookup"><span data-stu-id="a71b6-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="a71b6-104">HERE Technologies è una società di piattaforme di localizzazione che fornisce dati e servizi incentrati sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="a71b6-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="a71b6-105">Con i servizi di arricchimento dei dati di HERE Technologies, puoi creare una comprensione più precisa della posizione dei tuoi clienti con la normalizzazione degli indirizzi, l'estrazione di latitudine e longitudine e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="a71b6-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a71b6-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a71b6-106">Prerequisites</span></span>

<span data-ttu-id="a71b6-107">Per configurare gli arricchimenti di HERE Technologies, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="a71b6-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a71b6-108">Devi disporre di una sottoscrizione di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a71b6-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="a71b6-109">Per ottenere una sottoscrizione, puoi [iscriverti qui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [contatta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direttamente.</span><span class="sxs-lookup"><span data-stu-id="a71b6-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="a71b6-110">Ulteriori informazioni sull'arricchimento della posizione di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a71b6-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="a71b6-111">Devi disporre della chiave API di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a71b6-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="a71b6-112">Devi avere autorizzazioni di [amministratore](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="a71b6-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="a71b6-113">Configurazione</span><span class="sxs-lookup"><span data-stu-id="a71b6-113">Configuration</span></span>

1. <span data-ttu-id="a71b6-114">Vai a **Dati** > **Arricchimento**.</span><span class="sxs-lookup"><span data-stu-id="a71b6-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="a71b6-115">Seleziona **Arricchisci i miei dati** nel riquadro HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a71b6-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a71b6-116">![Riquadro HERE Technologies](media/HERE-tile.png "Riquadro HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="a71b6-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="a71b6-117">Immetti una **chiave API di HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="a71b6-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="a71b6-118">Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="a71b6-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="a71b6-119">Conferma entrambi gli input selezionando **Connettiti a HERE**.</span><span class="sxs-lookup"><span data-stu-id="a71b6-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="a71b6-120">Seleziona **Aggiungi dati** e scegli se desideri mappare i campi all'indirizzo principale e/o secondario.</span><span class="sxs-lookup"><span data-stu-id="a71b6-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="a71b6-121">Puoi specificare un mapping dei campi per entrambi gli indirizzi (ad esempio, un indirizzo abitazione e un indirizzo ufficio) e arricchire i profili per entrambi gli indirizzi separatamente.</span><span class="sxs-lookup"><span data-stu-id="a71b6-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="a71b6-122">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a71b6-122">Select **Next**.</span></span>

1. <span data-ttu-id="a71b6-123">Definisci quali campi dei profili unificati devono essere utilizzati per cercare dati di localizzazione corrispondenti di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a71b6-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="a71b6-124">I campi **Via 1** e **Codice postale** sono obbligatori per l'indirizzo principale e/o secondario selezionato.</span><span class="sxs-lookup"><span data-stu-id="a71b6-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="a71b6-125">Per una maggiore precisione della corrispondenza, è possibile aggiungere più campi.</span><span class="sxs-lookup"><span data-stu-id="a71b6-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a71b6-126">![Pagina di configurazione dell'arricchimento di HERE Technologies](media/enrichment-HERE-configuration.png "Pagina di configurazione dell'arricchimento di HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="a71b6-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="a71b6-127">Seleziona **Applica** per completare il mapping dei campi.</span><span class="sxs-lookup"><span data-stu-id="a71b6-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a71b6-128">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="a71b6-128">Enrichment results</span></span>

<span data-ttu-id="a71b6-129">Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a71b6-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a71b6-130">Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a71b6-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a71b6-131">Il tempo di elaborazione dipenderà dalle dimensioni dei dati cliente e dai tempi di risposta API di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a71b6-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="a71b6-132">Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**.</span><span class="sxs-lookup"><span data-stu-id="a71b6-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a71b6-133">Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="a71b6-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a71b6-134">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="a71b6-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a71b6-135">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a71b6-135">Next steps</span></span>

<span data-ttu-id="a71b6-136">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="a71b6-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a71b6-137">Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="a71b6-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a71b6-138">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="a71b6-138">Data privacy and compliance</span></span>

<span data-ttu-id="a71b6-139">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a HERE Technologies, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="a71b6-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a71b6-140">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che HERE Technologies rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="a71b6-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a71b6-141">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a71b6-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a71b6-142">L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a71b6-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
