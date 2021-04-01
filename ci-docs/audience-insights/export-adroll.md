---
title: Esportare dati di Customer Insights in AdRoll
description: Scopri come configurare la connessione ad AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697079"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="c919e-103">Connettore per AdRoll (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c919e-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="c919e-104">Esporta i segmenti dei profili cliente unificati in AdRoll e utilizzali per la pubblicità.</span><span class="sxs-lookup"><span data-stu-id="c919e-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c919e-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c919e-105">Prerequisites</span></span>

-   <span data-ttu-id="c919e-106">Devi disporre di un [account AdRoll](https://www.adroll.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c919e-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c919e-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="c919e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c919e-108">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="c919e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="c919e-109">Connetti ad AdRoll</span><span class="sxs-lookup"><span data-stu-id="c919e-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="c919e-110">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="c919e-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c919e-111">Sotto **AdRoll**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="c919e-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="c919e-112">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="c919e-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Riquadro di configurazione per la connessione ad AdRoll.":::

1. <span data-ttu-id="c919e-114">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="c919e-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c919e-115">Seleziona **Connetti** per inizializzare la connessione ad AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c919e-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="c919e-116">Seleziona **Esegui autenticazione con AdRoll** e fornisci le tue credenziali di amministratore per AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c919e-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="c919e-117">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c919e-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c919e-118">Inserisci lil tuo **ID inserzionista AdRoll** [Inserzionista AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="c919e-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="c919e-119">Seleziona **Avanti** per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="c919e-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c919e-120">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="c919e-120">Configure the connector</span></span>

1. <span data-ttu-id="c919e-121">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="c919e-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c919e-122">È necessario esportare i segmenti in AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c919e-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="c919e-123">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="c919e-123">Select the segments you want to export.</span></span> <span data-ttu-id="c919e-124">Seleziona un segmento con almeno 100 membri.</span><span class="sxs-lookup"><span data-stu-id="c919e-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="c919e-125">Non puoi esportare segmenti più piccoli.</span><span class="sxs-lookup"><span data-stu-id="c919e-125">You can't export smaller segments.</span></span> <span data-ttu-id="c919e-126">Inoltre, la dimensione massima di un segmento da esportare è di 250.000 membri per esportazione.</span><span class="sxs-lookup"><span data-stu-id="c919e-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="c919e-127">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c919e-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c919e-128">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="c919e-128">Export the data</span></span>

<span data-ttu-id="c919e-129">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c919e-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c919e-130">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c919e-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c919e-131">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="c919e-131">Known limitations</span></span>

- <span data-ttu-id="c919e-132">Puoi esportare fino a 250.000 profili per esportazione in AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c919e-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="c919e-133">Non puoi esportare segmenti con meno di 100 profili in AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c919e-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="c919e-134">L'esportazione in AdRoll è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="c919e-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="c919e-135">L'esportazione di un massimo di 250.000 profili in AdRoll può richiedere fino a 10 minuti per essere completata.</span><span class="sxs-lookup"><span data-stu-id="c919e-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="c919e-136">Il numero di profili che puoi esportare in AdRoll dipende ed è limitato dal tuo contratto con AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c919e-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c919e-137">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="c919e-137">Data privacy and compliance</span></span>

<span data-ttu-id="c919e-138">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati ad AdRoll, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="c919e-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c919e-139">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che AdRoll rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="c919e-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c919e-140">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c919e-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c919e-141">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c919e-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
