---
title: Arricchimento con l'arricchimento di terze parti Experian
description: Informazioni generali sull'arricchimento di terze parti Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597792"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="04b0c-103">Arricchisci i profili cliente con i dati demografici di Experian (anteprima)</span><span class="sxs-lookup"><span data-stu-id="04b0c-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="04b0c-104">Experian è un leader globale nei servizi di marketing e reporting del credito al consumo e alle imprese.</span><span class="sxs-lookup"><span data-stu-id="04b0c-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="04b0c-105">Con Servizi di arricchimento dei dati di Experian, puoi acquisire una conoscenza più approfondita dei tuoi clienti arricchendo i tuoi profili cliente con dati demografici come le dimensioni del nucleo familiare, il reddito e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="04b0c-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="04b0c-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="04b0c-106">Prerequisites</span></span>

<span data-ttu-id="04b0c-107">Per configurare Experian, devono essere rispettati i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="04b0c-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="04b0c-108">Hai un abbonamento Experian attivo.</span><span class="sxs-lookup"><span data-stu-id="04b0c-108">You have an active Experian subscription.</span></span> <span data-ttu-id="04b0c-109">Per ottenere un abbonamento, [contatta Experian](https://www.experian.com/marketing-services/contact) direttamente.</span><span class="sxs-lookup"><span data-stu-id="04b0c-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="04b0c-110">[Altre informazioni sull'arricchimento dei dati Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="04b0c-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="04b0c-111">Disponi dell'ID utente, dell'ID parte e del numero di modello del tuo account Secure Transport (ST) abilitato per SSH che Experian ha creato per te.</span><span class="sxs-lookup"><span data-stu-id="04b0c-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="04b0c-112">Disponi di autorizzazioni di [amministratore](permissions.md#administrator) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="04b0c-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="04b0c-113">Configurazione</span><span class="sxs-lookup"><span data-stu-id="04b0c-113">Configuration</span></span>

1. <span data-ttu-id="04b0c-114">Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.</span><span class="sxs-lookup"><span data-stu-id="04b0c-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="04b0c-115">Seleziona **Arricchisci i miei dati** nel riquadro Experian.</span><span class="sxs-lookup"><span data-stu-id="04b0c-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="04b0c-116">![Riquadro Experian](media/experian-tile.png "Riquadro Experian")</span><span class="sxs-lookup"><span data-stu-id="04b0c-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="04b0c-117">Seleziona **Inizia** e inserisci l'ID utente, l'ID parte e il numero di modello per il tuo account Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="04b0c-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="04b0c-118">Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="04b0c-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="04b0c-119">Conferma tutti gli input selezionando **Applica**.</span><span class="sxs-lookup"><span data-stu-id="04b0c-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="04b0c-120">Esegui il mapping dei campi</span><span class="sxs-lookup"><span data-stu-id="04b0c-120">Map your fields</span></span>

1.  <span data-ttu-id="04b0c-121">Seleziona **Aggiungi dati** e scegli il **Set di dati cliente** che vuoi arricchire con i dati demografici di Experian.</span><span class="sxs-lookup"><span data-stu-id="04b0c-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="04b0c-122">Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.</span><span class="sxs-lookup"><span data-stu-id="04b0c-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="04b0c-123">Seleziona gli identificatori chiave da **Nome e indirizzo**, **E-mail** o **Telefono** da inviare a Experian per la risoluzione dell'identità.</span><span class="sxs-lookup"><span data-stu-id="04b0c-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="04b0c-124">Più attributi dell'identificatore chiave inviati a Experian probabilmente producono un tasso di corrispondenza più elevato.</span><span class="sxs-lookup"><span data-stu-id="04b0c-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="04b0c-125">Seleziona **Avanti** e mappa gli attributi corrispondenti dall'entità cliente unificata per i campi dell'identificatore chiave selezionati.</span><span class="sxs-lookup"><span data-stu-id="04b0c-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="04b0c-126">Seleziona **Aggiungi attributo** per mappare eventuali attributi aggiuntivi che desideri inviare a Experian.</span><span class="sxs-lookup"><span data-stu-id="04b0c-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="04b0c-127">Seleziona **Salva** per completare la mappatura dei campi.</span><span class="sxs-lookup"><span data-stu-id="04b0c-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04b0c-128">![Mapping del campo Experian](media/experian-field-mapping.png "Mapping del campo Experian")</span><span class="sxs-lookup"><span data-stu-id="04b0c-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="04b0c-129">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="04b0c-129">Enrichment results</span></span>

<span data-ttu-id="04b0c-130">Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="04b0c-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="04b0c-131">Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="04b0c-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="04b0c-132">Il tempo di elaborazione dipenderà dalle dimensioni dei tuoi dati cliente e dai processi di arricchimento impostati per il tuo account da Experian.</span><span class="sxs-lookup"><span data-stu-id="04b0c-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="04b0c-133">Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**.</span><span class="sxs-lookup"><span data-stu-id="04b0c-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="04b0c-134">Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="04b0c-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="04b0c-135">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="04b0c-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="04b0c-136">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="04b0c-136">Next steps</span></span>

<span data-ttu-id="04b0c-137">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="04b0c-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="04b0c-138">Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="04b0c-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="04b0c-139">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="04b0c-139">Data privacy and compliance</span></span>

<span data-ttu-id="04b0c-140">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Experian, consenti il trasferimento di dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="04b0c-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="04b0c-141">Microsoft trasferirà tali dati secondo le tue istruzioni, ma hai la responsabilità di assicurarti che Experian rispetti gli obblighi di privacy o sicurezza che potresti avere.</span><span class="sxs-lookup"><span data-stu-id="04b0c-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="04b0c-142">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="04b0c-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="04b0c-143">L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="04b0c-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]