---
title: Esportare dati di Customer Insights in Mailchimp
description: Scopri come configurare la connessione ed esportare in Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124232"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="60644-103">Esportare segmenti in Mailchimp (anteprima)</span><span class="sxs-lookup"><span data-stu-id="60644-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="60644-104">Esporta segmenti di profili cliente unificati in Mailchimp per creare newsletters e campagne tramite messaggi e-mail.</span><span class="sxs-lookup"><span data-stu-id="60644-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="60644-105">Prerequisiti per la connessione</span><span class="sxs-lookup"><span data-stu-id="60644-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="60644-106">Devi disporre di un [account Mailchimp](https://mailchimp.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="60644-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="60644-107">In Mailchimp sono presenti destinatari e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="60644-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="60644-108">Per ulteriori informazioni, vedi [Destinatari Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="60644-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="60644-109">Disponi di [segmenti configurati](segments.md)</span><span class="sxs-lookup"><span data-stu-id="60644-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="60644-110">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="60644-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="60644-111">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="60644-111">Known limitations</span></span>

- <span data-ttu-id="60644-112">Fino a 1 milione di profili per esportazione in Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="60644-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="60644-113">L'esportazione in Mailchimp è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="60644-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="60644-114">L'esportazione di segmenti con 1 milione di profili può richiedere fino a tre ore.</span><span class="sxs-lookup"><span data-stu-id="60644-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="60644-115">Il numero di profili che puoi esportare in Mailchimp dipende ed è limitato dal tuo contratto con Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="60644-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="60644-116">Configurare la connessione a Mailchimp</span><span class="sxs-lookup"><span data-stu-id="60644-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="60644-117">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="60644-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="60644-118">Seleziona **Aggiungi connessione** e scegli **Autopilot** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="60644-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="60644-119">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="60644-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="60644-120">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="60644-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="60644-121">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="60644-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="60644-122">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="60644-122">Choose who can use this connection.</span></span> <span data-ttu-id="60644-123">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="60644-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="60644-124">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="60644-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="60644-125">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="60644-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="60644-126">Seleziona **Connettiti** per inizializzare la connessione a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="60644-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="60644-127">Seleziona **Esegui autenticazione con MailChimp** e fornisci le tue credenziali Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="60644-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="60644-128">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="60644-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="60644-129">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="60644-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="60644-130">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="60644-130">Configure the connector</span></span>

<span data-ttu-id="60644-131">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="60644-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="60644-132">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="60644-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="60644-133">Vai a **Dati**> **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="60644-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="60644-134">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="60644-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="60644-135">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="60644-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="60644-136">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="60644-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="60644-137">Immetti il tuo **[ID gruppo di destinatari Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="60644-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="60644-138">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="60644-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="60644-139">Facoltativamente, puoi esportare **nome** e **cognome** per creare e-mail più personalizzate.</span><span class="sxs-lookup"><span data-stu-id="60644-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="60644-140">Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.</span><span class="sxs-lookup"><span data-stu-id="60644-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="60644-141">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="60644-141">Select the segments you want to export.</span></span> <span data-ttu-id="60644-142">Puoi esportare in totale fino a 1 milione di profili cliente in Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="60644-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="60644-143">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="60644-143">Select **Save**.</span></span>

<span data-ttu-id="60644-144">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="60644-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="60644-145">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="60644-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="60644-146">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="60644-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="60644-147">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="60644-147">Data privacy and compliance</span></span>

<span data-ttu-id="60644-148">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Mailchimp, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="60644-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="60644-149">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Mailchimp rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="60644-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="60644-150">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="60644-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="60644-151">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="60644-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
