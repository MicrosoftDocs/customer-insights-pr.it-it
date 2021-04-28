---
title: Esportare i dati di Customer Insights in RollWorks
description: Scopri come configurare la connessione ed esportare in RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760563"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="dfe73-103">Esportare elenchi di segmenti in RollWorks (anteprima)</span><span class="sxs-lookup"><span data-stu-id="dfe73-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="dfe73-104">Esporta segmenti di profili cliente unificati in RollWorks e utilizzali per la pubblicità.</span><span class="sxs-lookup"><span data-stu-id="dfe73-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="dfe73-105">Prerequisiti per una connessione</span><span class="sxs-lookup"><span data-stu-id="dfe73-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="dfe73-106">Hai un [account RollWorks](https://www.rollworks.com/) e le corrispondenti credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="dfe73-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="dfe73-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="dfe73-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="dfe73-108">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="dfe73-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dfe73-109">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="dfe73-109">Known limitations</span></span>

- <span data-ttu-id="dfe73-110">È possibile esportare fino a 250.000 profili per esportazione in RollWorks.</span><span class="sxs-lookup"><span data-stu-id="dfe73-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="dfe73-111">Non è possibile esportare segmenti con meno di 100 profili in RollWorks.</span><span class="sxs-lookup"><span data-stu-id="dfe73-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="dfe73-112">L'esportazione in RollWorks è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="dfe73-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="dfe73-113">L'esportazione di un massimo di 250.000 profili in RollWorks può richiedere fino a 10 minuti per essere completata.</span><span class="sxs-lookup"><span data-stu-id="dfe73-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="dfe73-114">Il numero di profili che puoi esportare in RollWorks dipende ed è limitato dal tuo contratto con RollWorks.</span><span class="sxs-lookup"><span data-stu-id="dfe73-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="dfe73-115">Configurare la connessione a RollWorks</span><span class="sxs-lookup"><span data-stu-id="dfe73-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="dfe73-116">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="dfe73-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dfe73-117">Seleziona **Aggiungi connessione** e scegli **RollWorks** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="dfe73-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="dfe73-118">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="dfe73-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dfe73-119">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="dfe73-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dfe73-120">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="dfe73-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dfe73-121">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="dfe73-121">Choose who can use this connection.</span></span> <span data-ttu-id="dfe73-122">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="dfe73-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dfe73-123">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dfe73-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dfe73-124">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="dfe73-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dfe73-125">Seleziona **Connettiti** per inizializzare la connessione a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="dfe73-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="dfe73-126">Seleziona **Autentica con RollWorks** e fornisci le tue credenziali di amministratore per RollWorks.</span><span class="sxs-lookup"><span data-stu-id="dfe73-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="dfe73-127">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dfe73-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="dfe73-128">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="dfe73-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="dfe73-129">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="dfe73-129">Configure an export</span></span>

<span data-ttu-id="dfe73-130">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="dfe73-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dfe73-131">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dfe73-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dfe73-132">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="dfe73-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dfe73-133">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="dfe73-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dfe73-134">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione RollWorks.</span><span class="sxs-lookup"><span data-stu-id="dfe73-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="dfe73-135">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="dfe73-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dfe73-136">Inserisci il tuo **ID inserzionista RollWorks** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="dfe73-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="dfe73-137">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="dfe73-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="dfe73-138">È necessario per esportare i segmenti in RollWorks.</span><span class="sxs-lookup"><span data-stu-id="dfe73-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="dfe73-139">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="dfe73-139">Select the segments you want to export.</span></span> <span data-ttu-id="dfe73-140">Seleziona un segmento con almeno 100 membri.</span><span class="sxs-lookup"><span data-stu-id="dfe73-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="dfe73-141">Non puoi esportare segmenti più piccoli.</span><span class="sxs-lookup"><span data-stu-id="dfe73-141">You can't export smaller segments.</span></span> <span data-ttu-id="dfe73-142">Inoltre, la dimensione massima di un segmento da esportare è di 250.000 membri per esportazione.</span><span class="sxs-lookup"><span data-stu-id="dfe73-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="dfe73-143">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dfe73-143">Select **Save**.</span></span>

<span data-ttu-id="dfe73-144">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="dfe73-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dfe73-145">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dfe73-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dfe73-146">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dfe73-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dfe73-147">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="dfe73-147">Data privacy and compliance</span></span>

<span data-ttu-id="dfe73-148">Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a RollWorks, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="dfe73-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dfe73-149">Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che RollWorks soddisfi eventuali obblighi di privacy o sicurezza che potresti avere.</span><span class="sxs-lookup"><span data-stu-id="dfe73-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dfe73-150">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dfe73-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="dfe73-151">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="dfe73-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
