---
title: Esportare dati di Customer Insights in Microsoft Advertising
description: Scopri come configurare la connessione ed eseguire l'esportazione in Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124507"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="4bba9-103">Esporta segmenti in Microsoft Advertising (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4bba9-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="4bba9-104">Esporta i segmenti di Customer Insights in Microsoft Advertising per creare segmenti di pubblico Customer Match.</span><span class="sxs-lookup"><span data-stu-id="4bba9-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="4bba9-105">Usa questi segmenti di pubblico per le tue campagne pubblicitarie.</span><span class="sxs-lookup"><span data-stu-id="4bba9-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4bba9-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4bba9-106">Prerequisites</span></span>

-   <span data-ttu-id="4bba9-107">Hai un [account Microsoft Advertising](https://ads.microsoft.com/) e le corrispondenti credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4bba9-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4bba9-108">Hai accettato i termini di utilizzo di Customer Match.</span><span class="sxs-lookup"><span data-stu-id="4bba9-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="4bba9-109">[Segmenti configurati](segments.md) nelle informazioni dettagliate del gruppo di destinatari.</span><span class="sxs-lookup"><span data-stu-id="4bba9-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4bba9-110">I profili cliente unificati nei segmenti esportati contengono un campo con un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="4bba9-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4bba9-111">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="4bba9-111">Known limitations</span></span>

- <span data-ttu-id="4bba9-112">È possibile esportare fino a 500 mila profili per esportazione in Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="4bba9-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="4bba9-113">L'esportazione in Microsoft Advertising è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="4bba9-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="4bba9-114">L'esportazione fino a 500 mila profili in Microsoft Advertising può richiedere fino a 10 minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="4bba9-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="4bba9-115">Configurare la connessione a Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="4bba9-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="4bba9-116">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="4bba9-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4bba9-117">Seleziona **Aggiungi connessione** e scegli **Microsoft Advertising** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="4bba9-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="4bba9-118">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="4bba9-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4bba9-119">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="4bba9-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4bba9-120">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="4bba9-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4bba9-121">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="4bba9-121">Choose who can use this connection.</span></span> <span data-ttu-id="4bba9-122">L'impostazione predefinita è amministratori.</span><span class="sxs-lookup"><span data-stu-id="4bba9-122">The default is administrators.</span></span> <span data-ttu-id="4bba9-123">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4bba9-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4bba9-124">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="4bba9-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4bba9-125">Seleziona **Connetti** per inizializzare la connessione a Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="4bba9-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="4bba9-126">Seleziona **Autentica con Microsoft Advertising** e fornisci le tue credenziali di amministratore per Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="4bba9-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="4bba9-127">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4bba9-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4bba9-128">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="4bba9-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4bba9-129">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="4bba9-129">Configure an export</span></span>

<span data-ttu-id="4bba9-130">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="4bba9-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4bba9-131">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4bba9-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4bba9-132">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="4bba9-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4bba9-133">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="4bba9-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4bba9-134">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="4bba9-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="4bba9-135">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="4bba9-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4bba9-136">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="4bba9-136">Select the segments to export.</span></span> <span data-ttu-id="4bba9-137">I gruppi di destinatari con corrispondenza con il cliente in Microsoft Advertising vengono creati automaticamente con il nome dei segmenti selezionati per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="4bba9-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="4bba9-138">Ciascun segmento risulterà in un gruppo di destinatari con corrispondenza con il cliente.</span><span class="sxs-lookup"><span data-stu-id="4bba9-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="4bba9-139">Inserisci il tuo **ID cliente Microsoft Advertising e il tuo ID account**.</span><span class="sxs-lookup"><span data-stu-id="4bba9-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="4bba9-140">Puoi trovare l'ID cliente (`cid`) e l'ID account (`aid`) nei parametri dell'URL quando sei connesso a Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="4bba9-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="4bba9-141">Nella sezione **Corrispondenza dati**, nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato con l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="4bba9-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="4bba9-142">È necessario esportare i segmenti in Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="4bba9-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="4bba9-143">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4bba9-143">Select **Save**.</span></span>

<span data-ttu-id="4bba9-144">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="4bba9-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4bba9-145">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4bba9-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4bba9-146">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4bba9-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4bba9-147">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="4bba9-147">Data privacy and compliance</span></span>

<span data-ttu-id="4bba9-148">Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Microsoft Advertising, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="4bba9-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4bba9-149">Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che Microsoft Advertising soddisfi eventuali obblighi di privacy o sicurezza che potresti avere.</span><span class="sxs-lookup"><span data-stu-id="4bba9-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4bba9-150">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4bba9-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="4bba9-151">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4bba9-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
