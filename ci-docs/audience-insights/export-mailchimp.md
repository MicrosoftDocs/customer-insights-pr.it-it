---
title: Esportare dati di Customer Insights in Mailchimp
description: Scopri come configurare la connessione a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267178"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="642a8-103">Connettore per Mailchimp (anteprima)</span><span class="sxs-lookup"><span data-stu-id="642a8-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="642a8-104">Esporta segmenti di profili cliente unificati in Mailchimp per creare newsletters e campagne tramite messaggi e-mail.</span><span class="sxs-lookup"><span data-stu-id="642a8-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="642a8-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="642a8-105">Prerequisites</span></span>

-   <span data-ttu-id="642a8-106">Devi disporre di un [account Mailchimp](https://mailchimp.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="642a8-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="642a8-107">In Mailchimp sono presenti destinatari e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="642a8-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="642a8-108">Per ulteriori informazioni, vedi [Destinatari Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="642a8-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="642a8-109">Disponi di [segmenti configurati](segments.md)</span><span class="sxs-lookup"><span data-stu-id="642a8-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="642a8-110">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="642a8-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="642a8-111">Connettiti a MailChimp</span><span class="sxs-lookup"><span data-stu-id="642a8-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="642a8-112">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="642a8-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="642a8-113">Sotto **Mailchimp**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="642a8-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="642a8-114">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="642a8-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="642a8-115">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="642a8-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="642a8-116">Immetti l'**[ID destinatario Mailchimp](https://mailchimp.com/help/find-audience-id/)** e seleziona **Connetti** per inizializzare la connessione a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="642a8-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="642a8-117">Seleziona **Esegui autenticazione con MailChimp** e fornisci le tue credenziali Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="642a8-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="642a8-118">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="642a8-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Screenshot di esportazione per la connessione a Mailchimp":::

1. <span data-ttu-id="642a8-120">Seleziona **Avanti** per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="642a8-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="642a8-121">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="642a8-121">Configure the connector</span></span>

1. <span data-ttu-id="642a8-122">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="642a8-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="642a8-123">Facoltativamente, puoi esportare **Nome** e **Cognome** come campi aggiuntivi per creare messaggi e-mail più personalizzati.</span><span class="sxs-lookup"><span data-stu-id="642a8-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="642a8-124">Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.</span><span class="sxs-lookup"><span data-stu-id="642a8-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="642a8-125">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="642a8-125">Select the segments you want to export.</span></span> <span data-ttu-id="642a8-126">Puoi esportare in totale fino a 1 milione di profili cliente in Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="642a8-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Selezionare campi e segmenti da esportare in Mailchimp":::

1. <span data-ttu-id="642a8-128">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="642a8-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="642a8-129">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="642a8-129">Export the data</span></span>

<span data-ttu-id="642a8-130">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="642a8-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="642a8-131">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="642a8-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="642a8-132">I tuoi segmenti sono ora visualizzati sotto [Destinatari Marketo](https://mailchimp.com/help/create-audience/) in Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="642a8-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="642a8-133">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="642a8-133">Known limitations</span></span>

- <span data-ttu-id="642a8-134">Fino a 1 milione di profili per esportazione in Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="642a8-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="642a8-135">L'esportazione in Mailchimp è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="642a8-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="642a8-136">L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a tre ore a causa delle limitazioni sul lato provider.</span><span class="sxs-lookup"><span data-stu-id="642a8-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="642a8-137">Il numero di profili che puoi esportare in Mailchimp dipende ed è limitato dal tuo contratto con Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="642a8-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="642a8-138">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="642a8-138">Data privacy and compliance</span></span>

<span data-ttu-id="642a8-139">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Mailchimp, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="642a8-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="642a8-140">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Mailchimp rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="642a8-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="642a8-141">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="642a8-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="642a8-142">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="642a8-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]