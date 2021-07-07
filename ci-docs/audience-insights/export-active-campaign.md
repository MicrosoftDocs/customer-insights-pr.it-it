---
title: Esportazione dei dati di Customer Insights in ActiveCampaign
description: Scopri come configurare la connessione ed esportare in ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314632"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="8991f-103">Esportazione di segmenti in ActiveCampaign (anteprima)</span><span class="sxs-lookup"><span data-stu-id="8991f-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="8991f-104">Esporta segmenti di profili cliente unificati in ActiveCampaign e usali per attività di marketing.</span><span class="sxs-lookup"><span data-stu-id="8991f-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8991f-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8991f-105">Prerequisites</span></span>

-   <span data-ttu-id="8991f-106">Hai un [account ActiveCampaign](https://www.activecampaign.com/) e le corrispondenti credenziali amministratore.</span><span class="sxs-lookup"><span data-stu-id="8991f-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8991f-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="8991f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8991f-108">I profili cliente unificati nei segmenti esportati contengono un campo con un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="8991f-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8991f-109">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="8991f-109">Known limitations</span></span>

- <span data-ttu-id="8991f-110">Puoi esportare fino a 1 milione di profili per esportazione in ActiveCampaign e il completamento può richiedere fino a 90 minuti.</span><span class="sxs-lookup"><span data-stu-id="8991f-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="8991f-111">L'esportazione in ActiveCampaign è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="8991f-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="8991f-112">Il numero di profili che puoi esportare in ActiveCampaign dipende dal tuo contratto con ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8991f-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="8991f-113">Configurazione della connessione ad ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="8991f-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="8991f-114">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="8991f-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8991f-115">Seleziona **Aggiungi connessione** e scegli **Campagna attiva** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="8991f-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="8991f-116">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="8991f-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8991f-117">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="8991f-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8991f-118">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="8991f-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8991f-119">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="8991f-119">Choose who can use this connection.</span></span> <span data-ttu-id="8991f-120">Per impostazione predefinita, sono solo amministratori.</span><span class="sxs-lookup"><span data-stu-id="8991f-120">By default, it's only administrators.</span></span> <span data-ttu-id="8991f-121">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8991f-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8991f-122">Immetti [chiave API ActiveCampaign e nome host endpoint REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="8991f-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="8991f-123">Il nome host dell'endpoint REST è solo il nome host, senza https://.</span><span class="sxs-lookup"><span data-stu-id="8991f-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="8991f-124">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="8991f-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8991f-125">Seleziona **Connetti** per inizializzare la connessione ad ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8991f-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="8991f-126">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8991f-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8991f-127">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="8991f-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8991f-128">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="8991f-128">Configure an export</span></span>

<span data-ttu-id="8991f-129">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="8991f-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="8991f-130">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8991f-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8991f-131">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="8991f-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8991f-132">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="8991f-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8991f-133">Nel campo **Connessione per l'esportazione** scegli una connessione dalla sezione ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8991f-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="8991f-134">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="8991f-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8991f-135">Immetti l'[**ID elenco ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="8991f-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="8991f-136">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="8991f-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8991f-137">È necessario esportare segmenti in ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8991f-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="8991f-138">Facoltativamente, puoi esportare nome, cognome e telefono per creare e-mail più personalizzate.</span><span class="sxs-lookup"><span data-stu-id="8991f-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="8991f-139">Seleziona Aggiungi attributo per eseguire il mapping di questi campi.</span><span class="sxs-lookup"><span data-stu-id="8991f-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="8991f-140">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8991f-140">Select **Save**.</span></span>

<span data-ttu-id="8991f-141">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="8991f-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8991f-142">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8991f-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8991f-143">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8991f-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8991f-144">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="8991f-144">Data privacy and compliance</span></span>

<span data-ttu-id="8991f-145">Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati ad ActiveCampaign, consenti il trasferimento di dati al di fuori del limite di conformità per Dynamics 365 Customer Insights, inclusi i dati potenzialmente sensibili come i Dati Personali.</span><span class="sxs-lookup"><span data-stu-id="8991f-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8991f-146">Microsoft trasferirà tali dati alle tue condizioni, ma sei tu a dover garantire che ActiveCampaign soddisfi tutti gli obblighi di privacy e sicurezza che sei tenuto a rispettare.</span><span class="sxs-lookup"><span data-stu-id="8991f-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8991f-147">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8991f-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8991f-148">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8991f-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
