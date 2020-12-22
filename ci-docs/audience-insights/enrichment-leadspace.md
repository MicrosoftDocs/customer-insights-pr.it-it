---
title: Arricchimento dei profili aziendali con l'arricchimento di terze parti Leadspace
description: Informazioni generali sull'arricchimento di terze parti Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668728"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="97fb7-103">Arricchimento dei profili aziendali con Leadspace (anteprima)</span><span class="sxs-lookup"><span data-stu-id="97fb7-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="97fb7-104">Leadspace è una società di data science che fornisce una piattaforma dati per clienti B2B.</span><span class="sxs-lookup"><span data-stu-id="97fb7-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="97fb7-105">Consente ai clienti con profili cliente unificati per le aziende di arricchire i propri dati.</span><span class="sxs-lookup"><span data-stu-id="97fb7-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="97fb7-106">Gli arricchimenti includono attributi aggiuntivi come le dimensioni, l'ubicazione e il settore della società nonché altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="97fb7-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97fb7-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="97fb7-107">Prerequisites</span></span>

<span data-ttu-id="97fb7-108">Per configurare Leadspace, devono essere rispettati i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="97fb7-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="97fb7-109">Disponi di una licenza Leadspace attiva e la "chiave perpetua" (denominata **Token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="97fb7-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="97fb7-110">Contatta direttamente [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) per i dettagli sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="97fb7-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="97fb7-111">Devi avere autorizzazioni di [amministratore](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="97fb7-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="97fb7-112">Devi disporre di [profili cliente unificati](customer-profiles.md) per le aziende.</span><span class="sxs-lookup"><span data-stu-id="97fb7-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="97fb7-113">Configurazione</span><span class="sxs-lookup"><span data-stu-id="97fb7-113">Configuration</span></span>

1. <span data-ttu-id="97fb7-114">In Audience Insights, vai a **Dati** > **Arricchimento**.</span><span class="sxs-lookup"><span data-stu-id="97fb7-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="97fb7-115">Seleziona **Arricchisci i miei dati** sul riquadro Leadspace.</span><span class="sxs-lookup"><span data-stu-id="97fb7-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot del riquadro Leadspace.":::

1. <span data-ttu-id="97fb7-117">Seleziona **Inizia** e quindi immetti un **Token Leadspace** (chiave perpetua) attivo.</span><span class="sxs-lookup"><span data-stu-id="97fb7-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="97fb7-118">Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="97fb7-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="97fb7-119">Conferma entrambi gli input selezionando **Connetti a Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="97fb7-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="97fb7-120">Seleziona **Esegui mapping dei dati** e definisci quali campi dei profili unificati devono essere utilizzati per cercare dati aziendali corrispondenti in Leadspace.</span><span class="sxs-lookup"><span data-stu-id="97fb7-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="97fb7-121">Il campo **Nome della società** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="97fb7-121">The **Name of company** field is required.</span></span> <span data-ttu-id="97fb7-122">Per una maggiore precisione della corrispondenza, fino a due altri campi, **Sito web della società** e **Sede della società**, possono essere aggiunti.</span><span class="sxs-lookup"><span data-stu-id="97fb7-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Riquadro di mapping del campo Leadspace.":::
   
1. <span data-ttu-id="97fb7-124">Seleziona **Applica** per completare il mapping dei campi.</span><span class="sxs-lookup"><span data-stu-id="97fb7-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="97fb7-125">Seleziona **Esegui** per arricchire i profili aziendali.</span><span class="sxs-lookup"><span data-stu-id="97fb7-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="97fb7-126">La durata di un arricchimento dipende dal numero di profili cliente unificati.</span><span class="sxs-lookup"><span data-stu-id="97fb7-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="97fb7-127">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="97fb7-127">Enrichment results</span></span>

<span data-ttu-id="97fb7-128">Dopo aver aggiornato l'arricchimento, è possibile rivedere i dati aziendali appena arricchiti in [Arricchimenti personali](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="97fb7-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="97fb7-129">Puoi trovare l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="97fb7-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="97fb7-130">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="97fb7-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="97fb7-131">Per ulteriori informazioni, vedi [API di Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="97fb7-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="97fb7-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="97fb7-132">Next steps</span></span>

<span data-ttu-id="97fb7-133">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="97fb7-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="97fb7-134">Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="97fb7-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="97fb7-135">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="97fb7-135">Data privacy and compliance</span></span>

<span data-ttu-id="97fb7-136">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Leadspace, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="97fb7-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="97fb7-137">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Leadspace rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="97fb7-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="97fb7-138">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="97fb7-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="97fb7-139">L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="97fb7-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>