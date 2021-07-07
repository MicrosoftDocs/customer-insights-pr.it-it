---
title: Esportare dati di Customer Insights in AdRoll
description: Scopri come configurare la connessione ed esportare in AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304835"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="de3d7-103">Esportare segmenti in AdRoll (anteprima)</span><span class="sxs-lookup"><span data-stu-id="de3d7-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="de3d7-104">Esporta i segmenti dei profili cliente unificati in AdRoll e utilizzali per la pubblicità.</span><span class="sxs-lookup"><span data-stu-id="de3d7-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="de3d7-105">Prerequisiti per una connessione</span><span class="sxs-lookup"><span data-stu-id="de3d7-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="de3d7-106">Devi disporre di un [account AdRoll](https://www.adroll.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="de3d7-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="de3d7-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="de3d7-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="de3d7-108">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="de3d7-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="de3d7-109">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="de3d7-109">Known limitations</span></span>

- <span data-ttu-id="de3d7-110">Puoi esportare fino a 250.000 profili alla volta in AdRoll.</span><span class="sxs-lookup"><span data-stu-id="de3d7-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="de3d7-111">Non puoi esportare segmenti con meno di 100 profili in AdRoll.</span><span class="sxs-lookup"><span data-stu-id="de3d7-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="de3d7-112">L'esportazione in AdRoll è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="de3d7-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="de3d7-113">L'esportazione di un massimo di 250.000 profili in AdRoll può richiedere fino a 10 minuti per essere completata.</span><span class="sxs-lookup"><span data-stu-id="de3d7-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="de3d7-114">Il numero di profili che puoi esportare in AdRoll dipende dal tuo contratto con AdRoll.</span><span class="sxs-lookup"><span data-stu-id="de3d7-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="de3d7-115">Configurare la connessione ad AdRoll</span><span class="sxs-lookup"><span data-stu-id="de3d7-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="de3d7-116">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="de3d7-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="de3d7-117">Seleziona **Aggiungi connessione** e scegli **AdRoll** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="de3d7-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="de3d7-118">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="de3d7-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="de3d7-119">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="de3d7-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="de3d7-120">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="de3d7-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="de3d7-121">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="de3d7-121">Choose who can use this connection.</span></span> <span data-ttu-id="de3d7-122">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="de3d7-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="de3d7-123">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="de3d7-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="de3d7-124">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="de3d7-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="de3d7-125">Seleziona **Connetti** per inizializzare la connessione ad AdRoll.</span><span class="sxs-lookup"><span data-stu-id="de3d7-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="de3d7-126">Seleziona **Esegui autenticazione con AdRoll** e fornisci le tue credenziali di amministratore per AdRoll.</span><span class="sxs-lookup"><span data-stu-id="de3d7-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="de3d7-127">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="de3d7-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="de3d7-128">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="de3d7-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="de3d7-129">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="de3d7-129">Configure an export</span></span>

<span data-ttu-id="de3d7-130">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="de3d7-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="de3d7-131">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="de3d7-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="de3d7-132">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="de3d7-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="de3d7-133">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="de3d7-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="de3d7-134">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione AdRoll.</span><span class="sxs-lookup"><span data-stu-id="de3d7-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="de3d7-135">Se non vedi questo nome di sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="de3d7-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="de3d7-136">Immetti l'**ID inserzionista AdRoll**.</span><span class="sxs-lookup"><span data-stu-id="de3d7-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="de3d7-137">Per ulteriori informazioni, vedi [Profili inserzionisti AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="de3d7-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="de3d7-138">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="de3d7-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="de3d7-139">È necessario esportare i segmenti in AdRoll.</span><span class="sxs-lookup"><span data-stu-id="de3d7-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="de3d7-140">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="de3d7-140">Select the segments you want to export.</span></span> <span data-ttu-id="de3d7-141">Seleziona un segmento con almeno 100 membri.</span><span class="sxs-lookup"><span data-stu-id="de3d7-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="de3d7-142">Non puoi esportare segmenti più piccoli.</span><span class="sxs-lookup"><span data-stu-id="de3d7-142">You can't export smaller segments.</span></span> <span data-ttu-id="de3d7-143">Inoltre, la dimensione massima di un segmento da esportare è di 250.000 membri per esportazione.</span><span class="sxs-lookup"><span data-stu-id="de3d7-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="de3d7-144">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="de3d7-144">Select **Save**.</span></span>

<span data-ttu-id="de3d7-145">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="de3d7-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="de3d7-146">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="de3d7-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="de3d7-147">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="de3d7-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="de3d7-148">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="de3d7-148">Data privacy and compliance</span></span>

<span data-ttu-id="de3d7-149">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati ad AdRoll, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="de3d7-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="de3d7-150">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che AdRoll rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="de3d7-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="de3d7-151">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="de3d7-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="de3d7-152">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="de3d7-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
