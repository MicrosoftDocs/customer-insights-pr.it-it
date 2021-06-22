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
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124370"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="f624a-103">Esportare segmenti in AdRoll (anteprima)</span><span class="sxs-lookup"><span data-stu-id="f624a-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="f624a-104">Esporta i segmenti dei profili cliente unificati in AdRoll e utilizzali per la pubblicità.</span><span class="sxs-lookup"><span data-stu-id="f624a-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f624a-105">Prerequisiti per una connessione</span><span class="sxs-lookup"><span data-stu-id="f624a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f624a-106">Devi disporre di un [account AdRoll](https://www.adroll.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f624a-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f624a-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="f624a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f624a-108">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="f624a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f624a-109">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="f624a-109">Known limitations</span></span>

- <span data-ttu-id="f624a-110">Puoi esportare fino a 250.000 profili per esportazione in AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f624a-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="f624a-111">Non puoi esportare segmenti con meno di 100 profili in AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f624a-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="f624a-112">L'esportazione in AdRoll è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="f624a-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="f624a-113">L'esportazione di un massimo di 250.000 profili in AdRoll può richiedere fino a 10 minuti per essere completata.</span><span class="sxs-lookup"><span data-stu-id="f624a-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="f624a-114">Il numero di profili che puoi esportare in AdRoll dipende ed è limitato dal tuo contratto con AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f624a-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="f624a-115">Configurare la connessione ad AdRoll</span><span class="sxs-lookup"><span data-stu-id="f624a-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="f624a-116">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="f624a-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f624a-117">Seleziona **Aggiungi connessione** e scegli **AdRoll** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="f624a-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="f624a-118">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="f624a-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f624a-119">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="f624a-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f624a-120">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="f624a-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f624a-121">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="f624a-121">Choose who can use this connection.</span></span> <span data-ttu-id="f624a-122">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="f624a-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f624a-123">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f624a-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f624a-124">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="f624a-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f624a-125">Seleziona **Connetti** per inizializzare la connessione ad AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f624a-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="f624a-126">Seleziona **Esegui autenticazione con AdRoll** e fornisci le tue credenziali di amministratore per AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f624a-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="f624a-127">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f624a-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f624a-128">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="f624a-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f624a-129">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="f624a-129">Configure an export</span></span>

<span data-ttu-id="f624a-130">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="f624a-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f624a-131">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f624a-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f624a-132">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="f624a-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f624a-133">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="f624a-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f624a-134">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f624a-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="f624a-135">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="f624a-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f624a-136">Inserisci il tuo **ID inserzionista AdRoll** Per ulteriori informazioni, vedi [Profili degli inserzionisti AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="f624a-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="f624a-137">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="f624a-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f624a-138">È necessario esportare i segmenti in AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f624a-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="f624a-139">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="f624a-139">Select the segments you want to export.</span></span> <span data-ttu-id="f624a-140">Seleziona un segmento con almeno 100 membri.</span><span class="sxs-lookup"><span data-stu-id="f624a-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="f624a-141">Non puoi esportare segmenti più piccoli.</span><span class="sxs-lookup"><span data-stu-id="f624a-141">You can't export smaller segments.</span></span> <span data-ttu-id="f624a-142">Inoltre, la dimensione massima di un segmento da esportare è di 250.000 membri per esportazione.</span><span class="sxs-lookup"><span data-stu-id="f624a-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="f624a-143">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f624a-143">Select **Save**.</span></span>

<span data-ttu-id="f624a-144">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="f624a-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f624a-145">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f624a-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f624a-146">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f624a-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f624a-147">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="f624a-147">Data privacy and compliance</span></span>

<span data-ttu-id="f624a-148">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati ad AdRoll, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="f624a-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f624a-149">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che AdRoll rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="f624a-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f624a-150">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f624a-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f624a-151">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f624a-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
