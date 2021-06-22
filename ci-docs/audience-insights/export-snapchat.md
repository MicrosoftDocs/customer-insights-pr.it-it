---
title: Esportare i dati di Customer Insights in Snapchat
description: Scopri come configurare la connessione ed esportare in Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124048"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="f5c1e-103">Esportare segmenti in Snapchat (anteprima)</span><span class="sxs-lookup"><span data-stu-id="f5c1e-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="f5c1e-104">Esporta segmenti di profili cliente unificati in Snapchat e utilizzali per la pubblicità.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f5c1e-105">Prerequisiti per una connessione</span><span class="sxs-lookup"><span data-stu-id="f5c1e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f5c1e-106">Hai un [account Snapchat Business](https://business.snapchat.com/), un [account Snapchat Ads](https://ads.snapchat.com/) e le corrispondenti credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f5c1e-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f5c1e-108">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f5c1e-109">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="f5c1e-109">Known limitations</span></span>

- <span data-ttu-id="f5c1e-110">L'esportazione in Snapchat è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="f5c1e-111">L'esportazione fino a 1 milione di profili in Snapchat può richiedere fino a 15 minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="f5c1e-112">Configurare la connessione a Snapchat</span><span class="sxs-lookup"><span data-stu-id="f5c1e-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="f5c1e-113">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f5c1e-114">Seleziona **Aggiungi connessione** e scegli **Snapchat** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="f5c1e-115">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f5c1e-116">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f5c1e-117">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f5c1e-118">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-118">Choose who can use this connection.</span></span> <span data-ttu-id="f5c1e-119">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f5c1e-120">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f5c1e-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f5c1e-121">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f5c1e-122">Seleziona **Connettiti** per inizializzare la connessione a Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="f5c1e-123">Seleziona **Autentica con Snapchat** e fornisci le tue credenziali di amministratore per Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="f5c1e-124">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f5c1e-125">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f5c1e-126">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="f5c1e-126">Configure an export</span></span>

<span data-ttu-id="f5c1e-127">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f5c1e-128">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f5c1e-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f5c1e-129">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f5c1e-130">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f5c1e-131">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="f5c1e-132">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f5c1e-133">Inserisci l'[**ID gruppo di destinatari Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="f5c1e-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="f5c1e-134">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f5c1e-135">È necessario per esportare i segmenti in Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="f5c1e-136">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="f5c1e-137">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-137">Select **Save**.</span></span>

<span data-ttu-id="f5c1e-138">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f5c1e-139">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f5c1e-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f5c1e-140">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f5c1e-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f5c1e-141">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="f5c1e-141">Data privacy and compliance</span></span>

<span data-ttu-id="f5c1e-142">Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Snapchat, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f5c1e-143">Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che Snapchat soddisfi eventuali obblighi di privacy o sicurezza che potresti avere.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f5c1e-144">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f5c1e-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f5c1e-145">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f5c1e-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
