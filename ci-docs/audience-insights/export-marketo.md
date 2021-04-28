---
title: Esportare dati di Customer Insights in Marketo
description: Scopri come configurare la connessione ed esportare in Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759826"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="57c97-103">Esportare segmenti in Marketo (anteprima)</span><span class="sxs-lookup"><span data-stu-id="57c97-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="57c97-104">Esporta segmenti di profili cliente unificati per generare campagne, fornire e-mail marketing e utilizzare gruppi specifici di clienti con Marketo.</span><span class="sxs-lookup"><span data-stu-id="57c97-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="57c97-105">Prerequisiti per la connessione</span><span class="sxs-lookup"><span data-stu-id="57c97-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="57c97-106">Devi disporre di un [account Marketo](https://login.marketo.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="57c97-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="57c97-107">In Marketo sono presenti elenchi e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="57c97-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="57c97-108">Per ulteriori informazioni, vedi [Elenchi Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="57c97-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="57c97-109">Disponi di [segmenti configurati](segments.md).</span><span class="sxs-lookup"><span data-stu-id="57c97-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="57c97-110">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="57c97-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="57c97-111">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="57c97-111">Known limitations</span></span>

- <span data-ttu-id="57c97-112">Fino a 1 milione di profili per esportazione in Marketo.</span><span class="sxs-lookup"><span data-stu-id="57c97-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="57c97-113">L'esportazione in Marketo è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="57c97-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="57c97-114">L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 3 ore.</span><span class="sxs-lookup"><span data-stu-id="57c97-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="57c97-115">Il numero di profili che puoi esportare in Marketo dipende ed è limitato dal tuo contratto con Marketo.</span><span class="sxs-lookup"><span data-stu-id="57c97-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="57c97-116">Configurare la connessione a Marketo</span><span class="sxs-lookup"><span data-stu-id="57c97-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="57c97-117">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="57c97-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="57c97-118">Seleziona **Aggiungi connessione** e scegli **Marketo** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="57c97-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="57c97-119">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="57c97-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="57c97-120">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="57c97-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="57c97-121">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="57c97-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="57c97-122">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="57c97-122">Choose who can use this connection.</span></span> <span data-ttu-id="57c97-123">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="57c97-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="57c97-124">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="57c97-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="57c97-125">Immetti **[ID client Marketo, segreto client e nome host dell'endpoint REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="57c97-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="57c97-126">Seleziona **Accetto** per confermare **Conformità e privacy dei dati** e seleziona **Connetti** per inizializzare la connessione a Marketo.</span><span class="sxs-lookup"><span data-stu-id="57c97-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="57c97-127">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="57c97-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="57c97-128">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="57c97-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="57c97-129">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="57c97-129">Configure an export</span></span>

<span data-ttu-id="57c97-130">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="57c97-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="57c97-131">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="57c97-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="57c97-132">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="57c97-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="57c97-133">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="57c97-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="57c97-134">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Marketo.</span><span class="sxs-lookup"><span data-stu-id="57c97-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="57c97-135">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="57c97-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="57c97-136">Immetti l'**[ID elenco Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="57c97-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="57c97-137">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="57c97-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="57c97-138">Facoltativamente, puoi esportare **nome**, **cognome**, **città**, **stato**, e **Paese/Area geografica** per creare e-mail più personalizzate.</span><span class="sxs-lookup"><span data-stu-id="57c97-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="57c97-139">Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.</span><span class="sxs-lookup"><span data-stu-id="57c97-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="57c97-140">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="57c97-140">Select the segments you want to export.</span></span> <span data-ttu-id="57c97-141">Puoi esportare in totale fino a 1 milione di profili cliente in Marketo.</span><span class="sxs-lookup"><span data-stu-id="57c97-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="57c97-142">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57c97-142">Select **Save**.</span></span>

<span data-ttu-id="57c97-143">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="57c97-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="57c97-144">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="57c97-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="57c97-145">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="57c97-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="57c97-146">I tuoi segmenti sono ora visualizzati sotto [Elenchi Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) in Marketo.</span><span class="sxs-lookup"><span data-stu-id="57c97-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="57c97-147">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="57c97-147">Data privacy and compliance</span></span>

<span data-ttu-id="57c97-148">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Marketo, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="57c97-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="57c97-149">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Marketo rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="57c97-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="57c97-150">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="57c97-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="57c97-151">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57c97-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]