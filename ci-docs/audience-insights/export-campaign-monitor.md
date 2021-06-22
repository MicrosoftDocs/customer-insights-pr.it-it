---
title: Esportare i dati di Customer Insights in Campaign Monitor
description: Scopri come configurare la connessione ed esportare in Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124186"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="54ca1-103">Esportare segmenti in Campaign Monitor (anteprima)</span><span class="sxs-lookup"><span data-stu-id="54ca1-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="54ca1-104">Esporta segmenti di profili cliente unificati in Campaign Monitor e utilizzali per le attività di marketing.</span><span class="sxs-lookup"><span data-stu-id="54ca1-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54ca1-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="54ca1-105">Prerequisites</span></span>

-   <span data-ttu-id="54ca1-106">Hai un [account Campaign Monitor](https://www.campaignmonitor.com/) e le corrispondenti credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="54ca1-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="54ca1-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="54ca1-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="54ca1-108">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="54ca1-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="54ca1-109">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="54ca1-109">Known limitations</span></span>

- <span data-ttu-id="54ca1-110">È possibile esportare fino a 1 milione di profili per esportazione in Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ca1-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="54ca1-111">L'esportazione in Campaign Monitor è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="54ca1-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="54ca1-112">L'esportazione fino a 1 milione di profili in Campaign Monitor può richiedere fino a 20 minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="54ca1-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="54ca1-113">Il numero di profili che puoi esportare in Campaign Monitor dipende ed è limitato dal tuo contratto con Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ca1-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="54ca1-114">Impostare la connessione a Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="54ca1-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="54ca1-115">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="54ca1-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="54ca1-116">Seleziona **Aggiungi connessione** e scegli **Campaign Monitor** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="54ca1-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="54ca1-117">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="54ca1-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="54ca1-118">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="54ca1-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="54ca1-119">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="54ca1-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="54ca1-120">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="54ca1-120">Choose who can use this connection.</span></span> <span data-ttu-id="54ca1-121">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="54ca1-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="54ca1-122">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="54ca1-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="54ca1-123">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="54ca1-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="54ca1-124">Seleziona **Connettiti** per inizializzare la connessione a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ca1-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="54ca1-125">Seleziona **Autentica con Campaign Monitor** e fornisci le tue credenziali di amministratore per Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ca1-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="54ca1-126">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="54ca1-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="54ca1-127">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="54ca1-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="54ca1-128">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="54ca1-128">Configure an export</span></span>

<span data-ttu-id="54ca1-129">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="54ca1-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="54ca1-130">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="54ca1-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="54ca1-131">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="54ca1-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="54ca1-132">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="54ca1-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="54ca1-133">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ca1-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="54ca1-134">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="54ca1-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="54ca1-135">Immetti il tuo [**ID elenco Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="54ca1-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="54ca1-136">[Genera la chiave API](https://www.campaignmonitor.com/api/getting-started/) dalle **Impostazioni dell'account** in Campaign Monitor prima per visualizzare l'ID elenco API.</span><span class="sxs-lookup"><span data-stu-id="54ca1-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="54ca1-137">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="54ca1-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="54ca1-138">È necessario per esportare i segmenti in Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ca1-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="54ca1-139">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="54ca1-139">Select **Save**.</span></span>

<span data-ttu-id="54ca1-140">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="54ca1-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="54ca1-141">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="54ca1-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="54ca1-142">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="54ca1-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="54ca1-143">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="54ca1-143">Data privacy and compliance</span></span>

<span data-ttu-id="54ca1-144">Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Campaign Monitor, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="54ca1-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="54ca1-145">Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che Campaign Monitor soddisfi eventuali obblighi di privacy o sicurezza che potresti avere.</span><span class="sxs-lookup"><span data-stu-id="54ca1-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="54ca1-146">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="54ca1-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="54ca1-147">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="54ca1-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
