---
title: Esportare dati di Customer Insights in Marketo
description: Scopri come configurare la connessione ed esportare in Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059321"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="e35d1-103">Esportare segmenti in Marketo (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e35d1-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="e35d1-104">Esporta segmenti di profili cliente unificati per generare campagne, fornire e-mail marketing e utilizzare gruppi specifici di clienti con Marketo.</span><span class="sxs-lookup"><span data-stu-id="e35d1-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e35d1-105">Prerequisiti per la connessione</span><span class="sxs-lookup"><span data-stu-id="e35d1-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e35d1-106">Devi disporre di un [account Marketo](https://login.marketo.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e35d1-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e35d1-107">In Marketo sono presenti elenchi e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e35d1-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="e35d1-108">Per ulteriori informazioni, vedi [Elenchi Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="e35d1-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="e35d1-109">Disponi di [segmenti configurati](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e35d1-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e35d1-110">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="e35d1-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e35d1-111">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="e35d1-111">Known limitations</span></span>

- <span data-ttu-id="e35d1-112">Fino a 1 milione di profili per esportazione in Marketo.</span><span class="sxs-lookup"><span data-stu-id="e35d1-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="e35d1-113">L'esportazione in Marketo è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="e35d1-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="e35d1-114">L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 3 ore.</span><span class="sxs-lookup"><span data-stu-id="e35d1-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="e35d1-115">Il numero di profili che puoi esportare in Marketo dipende ed è limitato dal tuo contratto con Marketo.</span><span class="sxs-lookup"><span data-stu-id="e35d1-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="e35d1-116">Configurare la connessione a Marketo</span><span class="sxs-lookup"><span data-stu-id="e35d1-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="e35d1-117">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="e35d1-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e35d1-118">Seleziona **Aggiungi connessione** e scegli **Marketo** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="e35d1-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="e35d1-119">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="e35d1-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e35d1-120">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="e35d1-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e35d1-121">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="e35d1-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e35d1-122">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="e35d1-122">Choose who can use this connection.</span></span> <span data-ttu-id="e35d1-123">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="e35d1-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e35d1-124">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e35d1-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e35d1-125">Immetti **[ID client Marketo, segreto client e nome host dell'endpoint REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="e35d1-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="e35d1-126">Il nome host dell'endpoint REST è solo il nome host, senza `https://`.</span><span class="sxs-lookup"><span data-stu-id="e35d1-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="e35d1-127">Esempio: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="e35d1-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="e35d1-128">Seleziona **Accetto** per confermare **Conformità e privacy dei dati** e seleziona **Connetti** per inizializzare la connessione a Marketo.</span><span class="sxs-lookup"><span data-stu-id="e35d1-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="e35d1-129">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e35d1-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e35d1-130">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="e35d1-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e35d1-131">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="e35d1-131">Configure an export</span></span>

<span data-ttu-id="e35d1-132">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="e35d1-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e35d1-133">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e35d1-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e35d1-134">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="e35d1-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e35d1-135">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="e35d1-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e35d1-136">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Marketo.</span><span class="sxs-lookup"><span data-stu-id="e35d1-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="e35d1-137">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="e35d1-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e35d1-138">Immetti l'**[ID elenco Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="e35d1-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="e35d1-139">L'ID elenco è un valore puramente numerico.</span><span class="sxs-lookup"><span data-stu-id="e35d1-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="e35d1-140">Ad esempio, se l'ID dell'elenco Marketo è ST12345A7, rimuovi il carattere prima e dopo i numeri e inserisci `12345`.</span><span class="sxs-lookup"><span data-stu-id="e35d1-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="e35d1-141">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="e35d1-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e35d1-142">Facoltativamente, puoi esportare **nome**, **cognome**, **città**, **stato**, e **Paese/Area geografica** per creare e-mail più personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e35d1-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="e35d1-143">Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.</span><span class="sxs-lookup"><span data-stu-id="e35d1-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e35d1-144">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="e35d1-144">Select the segments you want to export.</span></span> <span data-ttu-id="e35d1-145">Puoi esportare in totale fino a 1 milione di profili cliente in Marketo.</span><span class="sxs-lookup"><span data-stu-id="e35d1-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="e35d1-146">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e35d1-146">Select **Save**.</span></span>

<span data-ttu-id="e35d1-147">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="e35d1-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e35d1-148">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e35d1-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e35d1-149">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e35d1-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="e35d1-150">I tuoi segmenti sono ora visualizzati sotto [Elenchi Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) in Marketo.</span><span class="sxs-lookup"><span data-stu-id="e35d1-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e35d1-151">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="e35d1-151">Data privacy and compliance</span></span>

<span data-ttu-id="e35d1-152">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Marketo, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="e35d1-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e35d1-153">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Marketo rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="e35d1-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e35d1-154">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e35d1-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e35d1-155">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e35d1-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
