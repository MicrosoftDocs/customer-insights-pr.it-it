---
title: Esportare dati di Customer Insights in DotDigital
description: Scopri come configurare la connessione a DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644453"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="a69a9-103">Connettore per DotDigital (anteprima)</span><span class="sxs-lookup"><span data-stu-id="a69a9-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="a69a9-104">Esporta segmenti di profili cliente unificati nelle rubriche di DotDigital e usali per campagne, messaggi e-mail di marketing e per costruire segmenti di clientela con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a69a9-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a69a9-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a69a9-105">Prerequisites</span></span>

-   <span data-ttu-id="a69a9-106">Devi disporre di un [account DotDigital](https://dotdigital.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="a69a9-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a69a9-107">In DotDigital sono presenti rubriche e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="a69a9-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="a69a9-108">L'ID è presente nell'URL quando selezioni e apri una rubrica.</span><span class="sxs-lookup"><span data-stu-id="a69a9-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="a69a9-109">Per ulteriori informazioni, vedi [Rubriche di DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="a69a9-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="a69a9-110">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="a69a9-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a69a9-111">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="a69a9-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="a69a9-112">Connettersi a DotDigital</span><span class="sxs-lookup"><span data-stu-id="a69a9-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="a69a9-113">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="a69a9-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a69a9-114">Sotto **DotDigital**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="a69a9-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="a69a9-115">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="a69a9-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Riquadro di configurazione per l'esportazione in DotDigital.":::

1. <span data-ttu-id="a69a9-117">Immetti il **nome utente e la password di DogDigital**.</span><span class="sxs-lookup"><span data-stu-id="a69a9-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="a69a9-118">Immetti l'**[ID rubrica DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="a69a9-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="a69a9-119">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="a69a9-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a69a9-120">Seleziona **Connetti** per inizializzare la connessione a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a69a9-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="a69a9-121">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a69a9-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a69a9-122">Seleziona **Avanti** per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="a69a9-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a69a9-123">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="a69a9-123">Configure the connector</span></span>

1. <span data-ttu-id="a69a9-124">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="a69a9-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a69a9-125">Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**, **Nome completo**, **Sesso** e **Codice postale**.</span><span class="sxs-lookup"><span data-stu-id="a69a9-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="a69a9-126">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="a69a9-126">Select the segments you want to export.</span></span> <span data-ttu-id="a69a9-127">Puoi esportare in totale fino a 1 milione di profili cliente in DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a69a9-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="a69a9-128">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a69a9-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a69a9-129">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="a69a9-129">Export the data</span></span>

<span data-ttu-id="a69a9-130">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a69a9-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a69a9-131">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a69a9-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a69a9-132">I tuoi segmenti sono ora visualizzati sotto [Rubriche DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) in DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a69a9-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a69a9-133">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="a69a9-133">Known limitations</span></span>

- <span data-ttu-id="a69a9-134">Fino a 1 milione di profili per esportazione in DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a69a9-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="a69a9-135">L'esportazione in DotDigital è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="a69a9-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="a69a9-136">L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 3 ore a causa delle limitazioni sul lato provider.</span><span class="sxs-lookup"><span data-stu-id="a69a9-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="a69a9-137">Il numero di profili che puoi esportare in DotDigital dipende ed è limitato dal tuo contratto con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a69a9-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a69a9-138">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="a69a9-138">Data privacy and compliance</span></span>

<span data-ttu-id="a69a9-139">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a DotDigital, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="a69a9-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a69a9-140">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che DotDigital rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="a69a9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a69a9-141">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a69a9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a69a9-142">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a69a9-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
