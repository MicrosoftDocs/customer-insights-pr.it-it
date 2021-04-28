---
title: Esportare dati di Customer Insights in Autopilot
description: Scopri come configurare la connessione ed esportare in Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760148"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="ad4ea-103">Esportare segmenti in Autopilot (anteprima)</span><span class="sxs-lookup"><span data-stu-id="ad4ea-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="ad4ea-104">Esporta segmenti di profili cliente unificati in Autopilot e usali per l'e-mail marketing in Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ad4ea-105">Prerequisiti per una connessione</span><span class="sxs-lookup"><span data-stu-id="ad4ea-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ad4ea-106">Devi disporre di un [account Autopilot](https://www.autopilothq.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ad4ea-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ad4ea-108">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ad4ea-109">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="ad4ea-109">Known limitations</span></span>

- <span data-ttu-id="ad4ea-110">Puoi esportare in totale fino a 100.000 profili cliente in Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="ad4ea-111">L'esportazione in Autopilot è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="ad4ea-112">L'esportazione di un massimo di 100.000 profili in Autopilot può richiedere alcune ore per essere completata.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="ad4ea-113">Il numero di profili che puoi esportare in Autopilot dipende ed è limitato dal tuo contratto con Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="ad4ea-114">Configurare la connessione ad Autopilot</span><span class="sxs-lookup"><span data-stu-id="ad4ea-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="ad4ea-115">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ad4ea-116">Seleziona **Aggiungi connessione** e scegli **Autopilot** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="ad4ea-117">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ad4ea-118">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ad4ea-119">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ad4ea-120">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-120">Choose who can use this connection.</span></span> <span data-ttu-id="ad4ea-121">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ad4ea-122">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ad4ea-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="ad4ea-123">Immetti la [chiave API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="ad4ea-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="ad4ea-124">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ad4ea-125">Seleziona **Connetti** per inizializzare la connessione a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="ad4ea-126">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ad4ea-127">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ad4ea-128">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="ad4ea-128">Configure an export</span></span>

<span data-ttu-id="ad4ea-129">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ad4ea-130">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ad4ea-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ad4ea-131">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ad4ea-132">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ad4ea-133">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="ad4ea-134">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="ad4ea-135">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ad4ea-136">Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="ad4ea-137">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-137">Select the segments you want to export.</span></span> <span data-ttu-id="ad4ea-138">È fortemente **consigliato di non esportare più di 100.000 profili cliente in totale** in Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="ad4ea-139">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-139">Select **Save**.</span></span>

<span data-ttu-id="ad4ea-140">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ad4ea-141">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ad4ea-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ad4ea-142">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ad4ea-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ad4ea-143">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="ad4ea-143">Data privacy and compliance</span></span>

<span data-ttu-id="ad4ea-144">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Autopilot, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ad4ea-145">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Autopilot rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ad4ea-146">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ad4ea-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ad4ea-147">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ad4ea-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
