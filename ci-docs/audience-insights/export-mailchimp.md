---
title: Esportare dati di Customer Insights in Mailchimp
description: Scopri come configurare la connessione a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406098"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="7bd8a-103">Connettore per Mailchimp (anteprima)</span><span class="sxs-lookup"><span data-stu-id="7bd8a-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="7bd8a-104">Esporta segmenti di profili cliente unificati in Mailchimp per creare newsletters e campagne tramite messaggi e-mail.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7bd8a-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7bd8a-105">Prerequisites</span></span>

-   <span data-ttu-id="7bd8a-106">Devi disporre di un [account Mailchimp](https://mailchimp.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7bd8a-107">In Mailchimp sono presenti destinatari e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="7bd8a-108">Per ulteriori informazioni, vedi [Destinatari Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="7bd8a-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="7bd8a-109">Disponi di [segmenti configurati](segments.md)</span><span class="sxs-lookup"><span data-stu-id="7bd8a-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="7bd8a-110">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="7bd8a-111">Connettiti a MailChimp</span><span class="sxs-lookup"><span data-stu-id="7bd8a-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="7bd8a-112">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7bd8a-113">Sotto **Mailchimp**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="7bd8a-114">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7bd8a-115">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7bd8a-116">Immetti l'**[ID destinatario Mailchimp](https://mailchimp.com/help/find-audience-id/)** e seleziona **Connetti** per inizializzare la connessione a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="7bd8a-117">Seleziona **Esegui autenticazione con MailChimp** e fornisci le tue credenziali Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="7bd8a-118">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Screenshot di esportazione per la connessione a Mailchimp":::

1. <span data-ttu-id="7bd8a-120">Seleziona **Avanti** per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="7bd8a-121">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="7bd8a-121">Configure the connector</span></span>

1. <span data-ttu-id="7bd8a-122">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="7bd8a-123">Facoltativamente, puoi esportare **Nome** e **Cognome** come campi aggiuntivi per creare messaggi e-mail più personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="7bd8a-124">Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="7bd8a-125">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-125">Select the segments you want to export.</span></span> <span data-ttu-id="7bd8a-126">Puoi esportare in totale fino a 1 milione di profili cliente in Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Selezionare campi e segmenti da esportare in Mailchimp":::

1. <span data-ttu-id="7bd8a-128">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7bd8a-129">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="7bd8a-129">Export the data</span></span>

<span data-ttu-id="7bd8a-130">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7bd8a-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7bd8a-131">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7bd8a-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7bd8a-132">I tuoi segmenti sono ora visualizzati sotto [Destinatari Marketo](https://mailchimp.com/help/create-audience/) in Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7bd8a-133">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="7bd8a-133">Known limitations</span></span>

- <span data-ttu-id="7bd8a-134">Fino a 1 milione di profili per esportazione in Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="7bd8a-135">L'esportazione in Mailchimp è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="7bd8a-136">L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a tre ore a causa delle limitazioni sul lato provider.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="7bd8a-137">Il numero di profili che puoi esportare in Mailchimp dipende ed è limitato dal tuo contratto con Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7bd8a-138">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="7bd8a-138">Data privacy and compliance</span></span>

<span data-ttu-id="7bd8a-139">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Mailchimp, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7bd8a-140">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Mailchimp rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7bd8a-141">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7bd8a-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7bd8a-142">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7bd8a-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>