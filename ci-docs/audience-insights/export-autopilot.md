---
title: Esportare dati di Customer Insights in Autopilot
description: Scopri come configurare la connessione a Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269243"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="969ee-103">Connettore per Autopilot (anteprima)</span><span class="sxs-lookup"><span data-stu-id="969ee-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="969ee-104">Esporta segmenti di profili cliente unificati in Autopilot e usali per l'e-mail marketing in Autopilot.</span><span class="sxs-lookup"><span data-stu-id="969ee-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="969ee-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="969ee-105">Prerequisites</span></span>

-   <span data-ttu-id="969ee-106">Devi disporre di un [account Autopilot](https://www.autopilothq.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="969ee-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="969ee-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="969ee-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="969ee-108">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="969ee-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="969ee-109">Connettersi ad AutoPilot</span><span class="sxs-lookup"><span data-stu-id="969ee-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="969ee-110">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="969ee-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="969ee-111">In **Autopilot**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="969ee-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="969ee-112">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="969ee-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Riquadro di configurazione per la connessione ad Autopilot.":::

1. <span data-ttu-id="969ee-114">Inserisci la tua **Chiave API AutoPilot** [Chiave API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="969ee-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="969ee-115">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="969ee-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="969ee-116">Seleziona **Connetti** per inizializzare la connessione a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="969ee-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="969ee-117">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="969ee-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="969ee-118">Seleziona **Avanti** per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="969ee-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="969ee-119">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="969ee-119">Configure the connector</span></span>

1. <span data-ttu-id="969ee-120">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="969ee-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="969ee-121">Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**.</span><span class="sxs-lookup"><span data-stu-id="969ee-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="969ee-122">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="969ee-122">Select the segments you want to export.</span></span> <span data-ttu-id="969ee-123">È fortemente **consigliato di non esportare più di 100.000 profili cliente in totale** in Autopilot.</span><span class="sxs-lookup"><span data-stu-id="969ee-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="969ee-124">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="969ee-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="969ee-125">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="969ee-125">Export the data</span></span>

<span data-ttu-id="969ee-126">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="969ee-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="969ee-127">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="969ee-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="969ee-128">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="969ee-128">Known limitations</span></span>

- <span data-ttu-id="969ee-129">Puoi esportare in totale fino a 100.000 profili cliente in Autopilot.</span><span class="sxs-lookup"><span data-stu-id="969ee-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="969ee-130">L'esportazione in Autopilot è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="969ee-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="969ee-131">L'esportazione di un massimo di 100.000 profili in Autopilot può richiedere alcune ore per essere completata.</span><span class="sxs-lookup"><span data-stu-id="969ee-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="969ee-132">Il numero di profili che puoi esportare in Autopilot dipende ed è limitato dal tuo contratto con Autopilot.</span><span class="sxs-lookup"><span data-stu-id="969ee-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="969ee-133">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="969ee-133">Data privacy and compliance</span></span>

<span data-ttu-id="969ee-134">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Autopilot, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="969ee-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="969ee-135">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Autopilot rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="969ee-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="969ee-136">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="969ee-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="969ee-137">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="969ee-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]