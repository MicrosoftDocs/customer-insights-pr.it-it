---
title: Arricchimento con l'arricchimento di terze parti di HERE Technologies
description: Informazioni generali sull'arricchimento di terze parti di HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896056"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="3db3f-103">Arricchimento dei profili cliente con HERE Technologies (anteprima)</span><span class="sxs-lookup"><span data-stu-id="3db3f-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="3db3f-104">HERE Technologies è una società di piattaforme di localizzazione che fornisce dati e servizi incentrati sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="3db3f-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="3db3f-105">Con i servizi di arricchimento dei dati di HERE Technologies, puoi creare una comprensione più precisa della posizione dei tuoi clienti con la normalizzazione degli indirizzi, l'estrazione di latitudine e longitudine e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="3db3f-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3db3f-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3db3f-106">Prerequisites</span></span>

<span data-ttu-id="3db3f-107">Per configurare gli arricchimenti di HERE Technologies, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="3db3f-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3db3f-108">Devi disporre di una sottoscrizione di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3db3f-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="3db3f-109">Per ottenere una sottoscrizione, puoi [iscriverti qui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [contatta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direttamente.</span><span class="sxs-lookup"><span data-stu-id="3db3f-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="3db3f-110">Ulteriori informazioni sull'arricchimento della posizione di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3db3f-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="3db3f-111">C'è una [connessione](connections.md) HERE a disposizione *o* hai le autorizzazioni di [amministratore](permissions.md#administrator) e la chiave API di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3db3f-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="3db3f-112">Configurare l'arricchimento</span><span class="sxs-lookup"><span data-stu-id="3db3f-112">Configure the enrichment</span></span>

1. <span data-ttu-id="3db3f-113">Vai a **Dati** > **Arricchimento**.</span><span class="sxs-lookup"><span data-stu-id="3db3f-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="3db3f-114">Seleziona **Arricchisci i miei dati** nel riquadro HERE Technologies e seleziona **Attività iniziali**.</span><span class="sxs-lookup"><span data-stu-id="3db3f-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3db3f-115">![Riquadro HERE Technologies](media/HERE-tile.png "Riquadro HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="3db3f-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="3db3f-116">Seleziona una [connessione](connections.md) nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3db3f-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="3db3f-117">Contatta un amministratore se non è disponibile alcuna connessione.</span><span class="sxs-lookup"><span data-stu-id="3db3f-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="3db3f-118">Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="3db3f-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="3db3f-119">Scegli **HERE Technologies** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="3db3f-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="3db3f-120">Seleziona **Connettiti a HERE Technologies** per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="3db3f-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="3db3f-121">Seleziona **Avanti** e scegli il **set di dati del cliente** che desideri arricchire con i dati della posizione di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3db3f-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="3db3f-122">Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.</span><span class="sxs-lookup"><span data-stu-id="3db3f-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. <span data-ttu-id="3db3f-124">Scegli se desideri mappare i campi all'indirizzo principale e/o secondario.</span><span class="sxs-lookup"><span data-stu-id="3db3f-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="3db3f-125">Puoi specificare un mapping del campo per entrambi gli indirizzi e arricchire i profili per entrambi gli indirizzi separatamente.</span><span class="sxs-lookup"><span data-stu-id="3db3f-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="3db3f-126">Ad esempio, se sono presenti una casa e un indirizzo aziendale.</span><span class="sxs-lookup"><span data-stu-id="3db3f-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="3db3f-127">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3db3f-127">Select **Next**.</span></span>

1. <span data-ttu-id="3db3f-128">Definisci quali campi dei profili unificati devono essere utilizzati per cercare dati di localizzazione corrispondenti di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3db3f-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="3db3f-129">I campi **Via 1** e **Codice postale** sono obbligatori per l'indirizzo principale e/o secondario selezionato.</span><span class="sxs-lookup"><span data-stu-id="3db3f-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="3db3f-130">Per una maggiore precisione della corrispondenza, è possibile aggiungere più campi.</span><span class="sxs-lookup"><span data-stu-id="3db3f-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3db3f-131">![Pagina di configurazione dell'arricchimento di HERE Technologies](media/enrichment-HERE-configuration.png "Pagina di configurazione dell'arricchimento di HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="3db3f-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="3db3f-132">Seleziona **Avanti** per completare il mapping del campo.</span><span class="sxs-lookup"><span data-stu-id="3db3f-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="3db3f-133">Immetti un nome per l'arricchimento.</span><span class="sxs-lookup"><span data-stu-id="3db3f-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="3db3f-134">1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.</span><span class="sxs-lookup"><span data-stu-id="3db3f-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="3db3f-135">Configurare la connessione per HERE technologies</span><span class="sxs-lookup"><span data-stu-id="3db3f-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="3db3f-136">Devi essere un amministratore per configurare le connessioni.</span><span class="sxs-lookup"><span data-stu-id="3db3f-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="3db3f-137">Seleziona **Aggiungi connessione** quando si configura un arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro HERE technologies.</span><span class="sxs-lookup"><span data-stu-id="3db3f-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="3db3f-138">Immetti un nome per la connessione nella casella **nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="3db3f-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="3db3f-139">Fornisci una chiave API HERE Technologies valida.</span><span class="sxs-lookup"><span data-stu-id="3db3f-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="3db3f-140">Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**</span><span class="sxs-lookup"><span data-stu-id="3db3f-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="3db3f-141">Seleziona **Verifica** per convalidare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="3db3f-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="3db3f-142">Dopo aver completato la verifica, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3db3f-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="3db3f-143">![Pagina di configurazione della connessione di HERE technologies](media/enrichment-HERE-connection.png "Pagina di configurazione della connessione di HERE technologies")</span><span class="sxs-lookup"><span data-stu-id="3db3f-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="3db3f-144">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="3db3f-144">Enrichment results</span></span>

<span data-ttu-id="3db3f-145">Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="3db3f-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3db3f-146">Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3db3f-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3db3f-147">Il tempo di elaborazione dipenderà dalle dimensioni dei dati cliente e dai tempi di risposta API di HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3db3f-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="3db3f-148">Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**.</span><span class="sxs-lookup"><span data-stu-id="3db3f-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="3db3f-149">Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="3db3f-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3db3f-150">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="3db3f-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3db3f-151">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3db3f-151">Next steps</span></span>

<span data-ttu-id="3db3f-152">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="3db3f-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3db3f-153">Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="3db3f-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3db3f-154">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="3db3f-154">Data privacy and compliance</span></span>

<span data-ttu-id="3db3f-155">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a HERE Technologies, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="3db3f-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3db3f-156">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che HERE Technologies rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="3db3f-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3db3f-157">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3db3f-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3db3f-158">L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3db3f-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
