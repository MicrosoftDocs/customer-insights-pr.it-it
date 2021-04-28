---
title: Esportare dati di Customer Insights in SendGrid
description: Scopri come configurare la connessione ed esportare in SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759770"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="f1469-103">Esportare segmenti in SendGrid (anteprima)</span><span class="sxs-lookup"><span data-stu-id="f1469-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="f1469-104">Esporta segmenti di profili cliente unificati nell'elenco di contatti SendGrid e usali per campagne e e-mail marketing in SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f1469-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f1469-105">Prerequisiti per una connessione</span><span class="sxs-lookup"><span data-stu-id="f1469-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f1469-106">Devi disporre di un [account SendGrid](https://sendgrid.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f1469-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f1469-107">In SendGrid sono presenti elenchi di contatti e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f1469-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="f1469-108">Per ulteriori informazioni, vedere [SendGrid: gestire i contatti](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="f1469-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="f1469-109">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="f1469-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f1469-110">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="f1469-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f1469-111">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="f1469-111">Known limitations</span></span>

- <span data-ttu-id="f1469-112">Fino a 100.000 profili in totale a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f1469-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="f1469-113">L'esportazione in SendGrid è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="f1469-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="f1469-114">L'esportazione di un massimo di 100.000 profili in SendGrid può richiedere alcune ore per essere completata.</span><span class="sxs-lookup"><span data-stu-id="f1469-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f1469-115">Il numero di profili che puoi esportare in SendGrid dipende ed è limitato dal tuo contratto con SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f1469-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="f1469-116">Configurare la connessione a SendGrid</span><span class="sxs-lookup"><span data-stu-id="f1469-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="f1469-117">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="f1469-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f1469-118">Seleziona **Aggiungi connessione** e scegli **SendGrid** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="f1469-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="f1469-119">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="f1469-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f1469-120">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="f1469-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f1469-121">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="f1469-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f1469-122">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="f1469-122">Choose who can use this connection.</span></span> <span data-ttu-id="f1469-123">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="f1469-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f1469-124">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f1469-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f1469-125">Inserisci la tua **Chiave API SendGrid** [Chiave API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="f1469-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="f1469-126">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="f1469-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f1469-127">Seleziona **Connetti** per inizializzare la connessione a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f1469-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="f1469-128">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f1469-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f1469-129">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="f1469-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f1469-130">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="f1469-130">Configure an export</span></span>

<span data-ttu-id="f1469-131">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="f1469-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f1469-132">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f1469-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f1469-133">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="f1469-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f1469-134">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="f1469-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f1469-135">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f1469-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="f1469-136">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="f1469-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f1469-137">Immetti l'**[ID elenco SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="f1469-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="f1469-138">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="f1469-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f1469-139">Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**, **Paese/area geografica**, **Stato**, **Città** e **Codice postale**.</span><span class="sxs-lookup"><span data-stu-id="f1469-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="f1469-140">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="f1469-140">Select the segments you want to export.</span></span> <span data-ttu-id="f1469-141">È fortemente **consigliato di non esportare più di 100.000 profili cliente in totale** in SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f1469-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="f1469-142">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1469-142">Select **Save**.</span></span>

<span data-ttu-id="f1469-143">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="f1469-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f1469-144">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f1469-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f1469-145">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f1469-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f1469-146">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="f1469-146">Data privacy and compliance</span></span>

<span data-ttu-id="f1469-147">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a SendGrid, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="f1469-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f1469-148">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che SendGrid rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="f1469-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f1469-149">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f1469-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f1469-150">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f1469-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]