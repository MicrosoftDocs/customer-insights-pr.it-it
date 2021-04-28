---
title: Esportare i dati di Customer Insights in Constant Contact
description: Scopri come configurare la connessione ed esportare in Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760561"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="97b26-103">Esportare elenchi di segmenti in Constant Contact (anteprima)</span><span class="sxs-lookup"><span data-stu-id="97b26-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="97b26-104">Esporta segmenti di profili cliente unificati in Constant Contact e utilizzali per le attività di marketing.</span><span class="sxs-lookup"><span data-stu-id="97b26-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="97b26-105">Prerequisiti per una connessione</span><span class="sxs-lookup"><span data-stu-id="97b26-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="97b26-106">Hai un [account Constant Contact](https://www.constantcontact.com/account-home) e le corrispondenti credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="97b26-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="97b26-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="97b26-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="97b26-108">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="97b26-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="97b26-109">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="97b26-109">Known limitations</span></span>

- <span data-ttu-id="97b26-110">È possibile esportare fino a 1 milione di profili per esportazione in Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="97b26-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="97b26-111">L'esportazione in Constant Contact è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="97b26-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="97b26-112">L'esportazione fino a 1 milione di profili in Constant Contact può richiedere fino a 1 ora per il completamento.</span><span class="sxs-lookup"><span data-stu-id="97b26-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="97b26-113">Il numero di profili che puoi esportare in Constant Contact dipende ed è limitato dal tuo contratto con Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="97b26-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="97b26-114">Impostare la connessione a Constant Contact</span><span class="sxs-lookup"><span data-stu-id="97b26-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="97b26-115">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="97b26-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="97b26-116">Seleziona **Aggiungi connessione** e scegli **Constant Contact** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="97b26-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="97b26-117">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="97b26-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="97b26-118">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="97b26-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="97b26-119">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="97b26-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="97b26-120">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="97b26-120">Choose who can use this connection.</span></span> <span data-ttu-id="97b26-121">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="97b26-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="97b26-122">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="97b26-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="97b26-123">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="97b26-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="97b26-124">Seleziona **Connettiti** per inizializzare la connessione a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="97b26-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="97b26-125">Seleziona **Autentica con AdRoll** e fornisci le tue credenziali di amministratore per Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="97b26-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="97b26-126">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="97b26-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="97b26-127">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="97b26-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="97b26-128">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="97b26-128">Configure an export</span></span>

<span data-ttu-id="97b26-129">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="97b26-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="97b26-130">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="97b26-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="97b26-131">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="97b26-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="97b26-132">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="97b26-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="97b26-133">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="97b26-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="97b26-134">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="97b26-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="97b26-135">Immetti il tuo [**ID elenco Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="97b26-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="97b26-136">Apri un elenco in Constant Contact per trovare l'ID elenco nell'URL.</span><span class="sxs-lookup"><span data-stu-id="97b26-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="97b26-137">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="97b26-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="97b26-138">È necessario per esportare i segmenti in Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="97b26-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="97b26-139">Facoltativamente, puoi esportare Nome e Cognome come campi aggiuntivi per creare messaggi e-mail più personalizzati.</span><span class="sxs-lookup"><span data-stu-id="97b26-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="97b26-140">Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.</span><span class="sxs-lookup"><span data-stu-id="97b26-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="97b26-141">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="97b26-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="97b26-142">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="97b26-142">Select **Save**.</span></span>

<span data-ttu-id="97b26-143">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="97b26-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="97b26-144">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="97b26-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="97b26-145">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="97b26-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="97b26-146">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="97b26-146">Data privacy and compliance</span></span>

<span data-ttu-id="97b26-147">Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Constant Contact, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="97b26-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="97b26-148">Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che Constant Contact soddisfi eventuali obblighi di privacy o sicurezza che potresti avere.</span><span class="sxs-lookup"><span data-stu-id="97b26-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="97b26-149">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="97b26-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="97b26-150">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="97b26-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
