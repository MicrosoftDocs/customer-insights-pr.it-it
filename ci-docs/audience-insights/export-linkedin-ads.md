---
title: Esportare i dati di Customer Insights in LinkedIn Ads
description: Scopri come configurare la connessione ed esportare in LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124509"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="41c71-103">Esportare segmenti in LinkedIn Ads (anteprima)</span><span class="sxs-lookup"><span data-stu-id="41c71-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="41c71-104">Esporta segmenti di profili cliente unificati in LinkedIn Ads per creare segmenti di pubblico corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="41c71-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="41c71-105">Utilizza i segmenti di pubblico corrispondenti per il targeting aziendale e il targeting per contatto.</span><span class="sxs-lookup"><span data-stu-id="41c71-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41c71-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="41c71-106">Prerequisites</span></span>

-   <span data-ttu-id="41c71-107">Hai un [account LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e le corrispondenti credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="41c71-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="41c71-108">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="41c71-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="41c71-109">I profili cliente nei segmenti esportati contengono un campo con un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="41c71-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="41c71-110">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="41c71-110">Known limitations</span></span>

- <span data-ttu-id="41c71-111">È possibile esportare fino a 100.000 profili per esportazione in LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="41c71-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="41c71-112">L'esportazione in LinkedIn Ads è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="41c71-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="41c71-113">L'esportazione fino a 100.000 profili in LinkedIn Ads può richiedere fino a 10 minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="41c71-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="41c71-114">Configurare la connessione a LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="41c71-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="41c71-115">In informazioni dettagliate sul gruppo di destinatari, vai a **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="41c71-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="41c71-116">Seleziona **Aggiungi connessione** e scegli **LinkedIn Ads** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="41c71-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="41c71-117">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="41c71-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="41c71-118">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="41c71-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="41c71-119">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="41c71-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="41c71-120">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="41c71-120">Choose who can use this connection.</span></span> <span data-ttu-id="41c71-121">Se non esegui alcuna azione, l'impostazione predefinita è Amministratori.</span><span class="sxs-lookup"><span data-stu-id="41c71-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="41c71-122">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="41c71-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="41c71-123">Fornisci il tuo [ID per l'account LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="41c71-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="41c71-124">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="41c71-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="41c71-125">Seleziona **Connettiti** per inizializzare la connessione a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="41c71-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="41c71-126">Seleziona **Autentica con LinkedIn** e fornisci le tue credenziali di amministratore per LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="41c71-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="41c71-127">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="41c71-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="41c71-128">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="41c71-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="41c71-129">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="41c71-129">Configure an export</span></span>

<span data-ttu-id="41c71-130">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="41c71-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="41c71-131">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="41c71-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="41c71-132">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="41c71-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="41c71-133">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="41c71-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="41c71-134">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="41c71-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="41c71-135">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="41c71-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="41c71-136">Scegli se vuoi esportare i dati per il [targeting per contatto](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [targeting aziendale](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) su LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="41c71-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="41c71-137">Nella sezione **Corrispondenza dati**, seleziona il campo nel tuo profilo cliente unificato che rappresenta un indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="41c71-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="41c71-138">È necessario esportare i segmenti in LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="41c71-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="41c71-139">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="41c71-139">Select the segments you want to export.</span></span> <span data-ttu-id="41c71-140">I segmenti di pubblico corrispondenti in LinkedIn Campaign Manager verranno creati automaticamente con il nome dei segmenti che hai selezionato per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="41c71-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="41c71-141">Ciascun segmento risulterà in un gruppo di destinatari con corrispondenza con segmenti di pubblico corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="41c71-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="41c71-142">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="41c71-142">Select **Save**.</span></span>

<span data-ttu-id="41c71-143">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="41c71-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="41c71-144">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="41c71-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="41c71-145">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="41c71-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="41c71-146">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="41c71-146">Data privacy and compliance</span></span>

<span data-ttu-id="41c71-147">Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a LinkedIn Ads, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="41c71-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="41c71-148">Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che LinkedIn Ads soddisfi eventuali obblighi di privacy o sicurezza che potresti avere.</span><span class="sxs-lookup"><span data-stu-id="41c71-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="41c71-149">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="41c71-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="41c71-150">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="41c71-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
