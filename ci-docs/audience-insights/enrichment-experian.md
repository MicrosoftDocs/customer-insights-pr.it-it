---
title: Arricchimento con l'arricchimento di terze parti Experian
description: Informazioni generali sull'arricchimento di terze parti Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668817"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="dc9e8-103">Arricchisci i profili cliente con i dati demografici di Experian (anteprima)</span><span class="sxs-lookup"><span data-stu-id="dc9e8-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="dc9e8-104">Experian è un leader globale nei servizi di marketing e reporting del credito al consumo e alle imprese.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="dc9e8-105">Con Servizi di arricchimento dei dati di Experian, puoi acquisire una conoscenza più approfondita dei tuoi clienti arricchendo i tuoi profili cliente con dati demografici come le dimensioni del nucleo familiare, il reddito e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc9e8-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="dc9e8-106">Prerequisites</span></span>

<span data-ttu-id="dc9e8-107">Per configurare Experian, devono essere rispettati i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="dc9e8-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dc9e8-108">Hai un abbonamento Experian attivo.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-108">You have an active Experian subscription.</span></span> <span data-ttu-id="dc9e8-109">Per ottenere un abbonamento, [contatta Experian](https://www.experian.com/marketing-services/contact) direttamente.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="dc9e8-110">[Altre informazioni sull'arricchimento dei dati Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="dc9e8-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="dc9e8-111">Disponi dell'ID utente, dell'ID parte e del numero di modello del tuo account Secure Transport (ST) abilitato per SSH che Experian ha creato per te.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="dc9e8-112">Disponi di autorizzazioni di [amministratore](permissions.md#administrator) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="dc9e8-113">Configurazione</span><span class="sxs-lookup"><span data-stu-id="dc9e8-113">Configuration</span></span>

1. <span data-ttu-id="dc9e8-114">Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="dc9e8-115">Seleziona **Arricchisci i miei dati** nel riquadro Experian.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dc9e8-116">![Riquadro Experian](media/experian-tile.png "Riquadro Experian")</span><span class="sxs-lookup"><span data-stu-id="dc9e8-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="dc9e8-117">Seleziona **Inizia** e inserisci l'ID utente, l'ID parte e il numero di modello per il tuo account Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="dc9e8-118">Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="dc9e8-119">Conferma tutti gli input selezionando **Applica**.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="dc9e8-120">Esegui il mapping dei campi</span><span class="sxs-lookup"><span data-stu-id="dc9e8-120">Map your fields</span></span>

1. <span data-ttu-id="dc9e8-121">Seleziona **Aggiungi dati** e scegli i tuoi identificatori chiave da **Nome e indirizzo**, **E-mail** o **Telefono** da inviare a Experian per la risoluzione dell'identità.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="dc9e8-122">Più attributi dell'identificatore chiave inviati a Experian probabilmente producono un tasso di corrispondenza più elevato.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="dc9e8-123">Seleziona **Avanti** e mappa gli attributi corrispondenti dall'entità cliente unificata per i campi dell'identificatore chiave selezionati.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="dc9e8-124">Seleziona **Aggiungi attributo** per mappare eventuali attributi aggiuntivi che desideri inviare a Experian.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="dc9e8-125">Seleziona **Salva** per completare la mappatura dei campi.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dc9e8-126">![Mapping del campo Experian](media/experian-field-mapping.png "Mapping del campo Experian")</span><span class="sxs-lookup"><span data-stu-id="dc9e8-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="dc9e8-127">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="dc9e8-127">Enrichment results</span></span>

<span data-ttu-id="dc9e8-128">Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dc9e8-129">Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dc9e8-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dc9e8-130">Il tempo di elaborazione dipenderà dalle dimensioni dei tuoi dati cliente e dai processi di arricchimento impostati per il tuo account da Experian.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="dc9e8-131">Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="dc9e8-132">Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dc9e8-133">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dc9e8-134">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="dc9e8-134">Next steps</span></span>

<span data-ttu-id="dc9e8-135">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dc9e8-136">Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dc9e8-137">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="dc9e8-137">Data privacy and compliance</span></span>

<span data-ttu-id="dc9e8-138">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Experian, consenti il trasferimento di dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dc9e8-139">Microsoft trasferirà tali dati secondo le tue istruzioni, ma hai la responsabilità di assicurarti che Experian rispetti gli obblighi di privacy o sicurezza che potresti avere.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dc9e8-140">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dc9e8-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dc9e8-141">L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
