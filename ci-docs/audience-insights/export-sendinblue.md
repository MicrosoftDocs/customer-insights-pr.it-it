---
title: Esportazione dei dati di Customer Insights in Sendinblue
description: Scopri come configurare la connessione ed esportare in Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314631"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="cf4b7-103">Esportazione di segmenti in Sendinblue (anteprima)</span><span class="sxs-lookup"><span data-stu-id="cf4b7-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="cf4b7-104">Esporta i segmenti di profii clienti unificati per generare campagne, offrire e-mail marketing e utilizzare gruppi specifici di clienti con Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="cf4b7-105">Prerequisiti per la connessione</span><span class="sxs-lookup"><span data-stu-id="cf4b7-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="cf4b7-106">Hai un [account Sendinblue](https://www.sendinblue.com/) e le corrispondenti credenziali amministratore.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cf4b7-107">Vi sono elenchi esistenti in Sendinblue e gli ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="cf4b7-108">Disponi di [segmenti configurati](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cf4b7-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="cf4b7-109">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cf4b7-110">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="cf4b7-110">Known limitations</span></span>

- <span data-ttu-id="cf4b7-111">Fino a 1 milione di profili per esportazione in Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="cf4b7-112">L'esportazione in Sendinblue è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="cf4b7-113">L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 90 minuti.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="cf4b7-114">Il numero di profili che puoi esportare in Sendinblue dipende ed è limtato dal tuo contratto con Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="cf4b7-115">Configurazione della connessione con Sendinblue</span><span class="sxs-lookup"><span data-stu-id="cf4b7-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="cf4b7-116">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cf4b7-117">Seleziona **Aggiungi connessione** e scegli **Sendinblue** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="cf4b7-118">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cf4b7-119">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cf4b7-120">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cf4b7-121">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-121">Choose who can use this connection.</span></span> <span data-ttu-id="cf4b7-122">Per impostazione predefinita sono solo gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-122">By default it's only administrators.</span></span> <span data-ttu-id="cf4b7-123">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cf4b7-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="cf4b7-124">Immetti la **[chiave API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="cf4b7-125">Seleziona **Accetto** per confermare **Conformità e privacy dei dati** e seleziona **Connetti** per inizializzare la connessione a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="cf4b7-126">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="cf4b7-127">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="cf4b7-128">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="cf4b7-128">Configure an export</span></span>

<span data-ttu-id="cf4b7-129">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cf4b7-130">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cf4b7-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cf4b7-131">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cf4b7-132">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="cf4b7-133">Nel campo **Connessione per l'esportazione** scegli una connessione dalla sezione Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="cf4b7-134">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="cf4b7-135">Immissione dell'**ID elenco Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="cf4b7-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="cf4b7-136">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="cf4b7-137">Facoltativamente, puoi esportare **nome**, **cognome** e **telefono** per creare e-mail più personalizzate.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="cf4b7-138">Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="cf4b7-139">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="cf4b7-140">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-140">Select **Save**.</span></span>

<span data-ttu-id="cf4b7-141">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="cf4b7-142">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cf4b7-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cf4b7-143">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cf4b7-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cf4b7-144">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="cf4b7-144">Data privacy and compliance</span></span>

<span data-ttu-id="cf4b7-145">Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Sendinblue, consenti il trasferimento di dati al di fuori del limite di conformità per Dynamics 365 Customer Insights, inclusi i dati potenzialmente sensibili come i Dati Personali.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cf4b7-146">Microsoft trasferirà tali dati alle tue condizioni, ma sei tu a dover garantire che Sendinblue soddisfi tutti gli obblighi di privacy e sicurezza che sei tenuto a rispettare.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="cf4b7-147">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cf4b7-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cf4b7-148">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cf4b7-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
