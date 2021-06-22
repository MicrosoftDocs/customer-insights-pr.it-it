---
title: Esportare i dati di Customer Insights in Omnisend
description: Scopri come configurare la connessione ed esportare in Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124508"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="9060f-103">Esportare segmenti in Omnisend (anteprima)</span><span class="sxs-lookup"><span data-stu-id="9060f-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="9060f-104">Esporta segmenti di profili cliente unificati in Omnisend e utilizzali per le attività di marketing.</span><span class="sxs-lookup"><span data-stu-id="9060f-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9060f-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9060f-105">Prerequisites</span></span>

-   <span data-ttu-id="9060f-106">Hai un [account Omnisend](https://www.omnisend.com/) e le corrispondenti credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="9060f-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9060f-107">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="9060f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9060f-108">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="9060f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9060f-109">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="9060f-109">Known limitations</span></span>

- <span data-ttu-id="9060f-110">Puoi esportare fino a 1 milione di profili per l'esportazione in Omnisend e il completamento può richiedere fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="9060f-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="9060f-111">L'esportazione in Omnisend è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="9060f-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="9060f-112">Il numero di profili che puoi esportare in Omnisend dipende dal tuo contratto con Omnisend.</span><span class="sxs-lookup"><span data-stu-id="9060f-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="9060f-113">Configurare la connessione a Omnisend</span><span class="sxs-lookup"><span data-stu-id="9060f-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="9060f-114">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="9060f-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9060f-115">Seleziona **Aggiungi connessione** e scegli **Omnisend** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="9060f-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="9060f-116">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="9060f-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9060f-117">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="9060f-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9060f-118">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="9060f-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9060f-119">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="9060f-119">Choose who can use this connection.</span></span> <span data-ttu-id="9060f-120">Per impostazione predefinita sono solo gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="9060f-120">By default it's only administrators.</span></span> <span data-ttu-id="9060f-121">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9060f-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9060f-122">Immetti la [chiave API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="9060f-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="9060f-123">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="9060f-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9060f-124">Seleziona **Connettiti** per inizializzare la connessione a Omnisend.</span><span class="sxs-lookup"><span data-stu-id="9060f-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="9060f-125">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9060f-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9060f-126">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="9060f-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9060f-127">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="9060f-127">Configure an export</span></span>

<span data-ttu-id="9060f-128">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="9060f-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9060f-129">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9060f-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9060f-130">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="9060f-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9060f-131">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="9060f-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9060f-132">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Omnisend.</span><span class="sxs-lookup"><span data-stu-id="9060f-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="9060f-133">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="9060f-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9060f-134">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="9060f-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9060f-135">È necessario per esportare i segmenti in Omnisend.</span><span class="sxs-lookup"><span data-stu-id="9060f-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="9060f-136">Facoltativamente, puoi esportare nome, cognome, indirizzo, Paese/Area geografica, stato, città e codice postale per creare e-mail più personalizzate.</span><span class="sxs-lookup"><span data-stu-id="9060f-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="9060f-137">Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.</span><span class="sxs-lookup"><span data-stu-id="9060f-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9060f-138">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9060f-138">Select **Save**.</span></span>

<span data-ttu-id="9060f-139">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="9060f-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9060f-140">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9060f-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9060f-141">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9060f-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9060f-142">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="9060f-142">Data privacy and compliance</span></span>

<span data-ttu-id="9060f-143">Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Ommisend, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="9060f-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9060f-144">Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che Ommisend soddisfi eventuali obblighi di privacy o sicurezza che potresti avere.</span><span class="sxs-lookup"><span data-stu-id="9060f-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9060f-145">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9060f-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="9060f-146">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9060f-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
