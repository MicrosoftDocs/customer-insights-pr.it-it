---
title: Arricchimento dei profili aziendali con l'arricchimento di terze parti Leadspace
description: Informazioni generali sull'arricchimento di terze parti Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305207"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="c3933-103">Arricchimento dei profili aziendali con Leadspace (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c3933-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="c3933-104">Leadspace è una società di data science che fornisce una piattaforma dati per clienti B2B.</span><span class="sxs-lookup"><span data-stu-id="c3933-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="c3933-105">Consente ai clienti con profili cliente unificati per le aziende di arricchire i propri dati.</span><span class="sxs-lookup"><span data-stu-id="c3933-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="c3933-106">Gli arricchimenti includono altri attributi ad esempio dimensioni, ubicazione, settore della società e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="c3933-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c3933-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c3933-107">Prerequisites</span></span>

<span data-ttu-id="c3933-108">Per configurare Leadspace, devono essere rispettati i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="c3933-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c3933-109">Hai una licenza Leadspace attiva.</span><span class="sxs-lookup"><span data-stu-id="c3933-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="c3933-110">Devi disporre di [profili cliente unificati](customer-profiles.md) per le aziende.</span><span class="sxs-lookup"><span data-stu-id="c3933-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="c3933-111">Una connessione Leadspace è già stata configurata da un amministratore o hai le autorizzazioni di [amministratore](permissions.md#administrator) e la "chiave perpetua" (denominata **token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="c3933-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="c3933-112">Contatta [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direttamente per i dettagli sul loro prodotto.</span><span class="sxs-lookup"><span data-stu-id="c3933-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="c3933-113">Configurare l'arricchimento</span><span class="sxs-lookup"><span data-stu-id="c3933-113">Configure the enrichment</span></span>

1. <span data-ttu-id="c3933-114">In Audience Insights, vai a **Dati** > **Arricchimento**.</span><span class="sxs-lookup"><span data-stu-id="c3933-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="c3933-115">Seleziona **Arricchisci i miei dati** nel riquadro Leadspace e seleziona **Attività iniziali**.</span><span class="sxs-lookup"><span data-stu-id="c3933-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot del riquadro Leadspace.":::

1. <span data-ttu-id="c3933-117">Seleziona una [connessione](connections.md) dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3933-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="c3933-118">Contatta un amministratore se non è disponibile alcuna connessione.</span><span class="sxs-lookup"><span data-stu-id="c3933-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="c3933-119">Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione** e scegliendo **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="c3933-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="c3933-120">Seleziona **Connettiti a Leadspace** per confermare la connessione.</span><span class="sxs-lookup"><span data-stu-id="c3933-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="c3933-121">Seleziona **Avanti** e scegli il **set di dati del cliente** che desideri arricchire con i dati aziendali di Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c3933-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="c3933-122">Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.</span><span class="sxs-lookup"><span data-stu-id="c3933-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. <span data-ttu-id="c3933-124">Seleziona **Avanti** e definisci quali campi dei profili unificati vengono utilizzati per cercare i dati aziendali corrispondenti di Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c3933-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="c3933-125">Il campo **Nome della società** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c3933-125">The **Name of company** field is required.</span></span> <span data-ttu-id="c3933-126">Per una maggiore precisione della corrispondenza, fino a due altri campi, **Sito web della società** e **Sede della società**, possono essere aggiunti.</span><span class="sxs-lookup"><span data-stu-id="c3933-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Riquadro di mapping del campo Leadspace.":::

1. <span data-ttu-id="c3933-128">Seleziona **Avanti** per completare il mapping del campo.</span><span class="sxs-lookup"><span data-stu-id="c3933-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="c3933-129">Fornisci un nome per l'arricchimento e seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.</span><span class="sxs-lookup"><span data-stu-id="c3933-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="c3933-130">Configurare la connessione per Leadspace</span><span class="sxs-lookup"><span data-stu-id="c3933-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="c3933-131">Devi essere un amministratore per configurare le connessioni.</span><span class="sxs-lookup"><span data-stu-id="c3933-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c3933-132">Seleziona **Aggiungi connessione** quando si configura un arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c3933-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="c3933-133">Seleziona **Inizia subito**.</span><span class="sxs-lookup"><span data-stu-id="c3933-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="c3933-134">Immetti un nome per la connessione nella casella **nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="c3933-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c3933-135">Fornisci un token di Leadspace valido.</span><span class="sxs-lookup"><span data-stu-id="c3933-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="c3933-136">Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="c3933-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="c3933-137">Seleziona **Verifica** per convalidare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="c3933-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c3933-138">Dopo aver completato la verifica, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c3933-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Pagina di configurazione della connessione di Leadspace":::

## <a name="enrichment-results"></a><span data-ttu-id="c3933-140">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="c3933-140">Enrichment results</span></span>

<span data-ttu-id="c3933-141">Dopo aver aggiornato l'arricchimento, è possibile rivedere i dati aziendali appena arricchiti in [Arricchimenti personali](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="c3933-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="c3933-142">Puoi trovare l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="c3933-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c3933-143">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="c3933-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="c3933-144">Per ulteriori informazioni, vedi [API di Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="c3933-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c3933-145">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c3933-145">Next steps</span></span>

<span data-ttu-id="c3933-146">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="c3933-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c3933-147">Crea [segmenti](segments.md) e [misure](measures.md) e persino [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="c3933-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c3933-148">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="c3933-148">Data privacy and compliance</span></span>

<span data-ttu-id="c3933-149">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Leadspace, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="c3933-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c3933-150">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Leadspace rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="c3933-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c3933-151">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c3933-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c3933-152">L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c3933-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
