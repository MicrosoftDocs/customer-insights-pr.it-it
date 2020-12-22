---
title: Esportare dati di Customer Insights in Google Ads
description: Scopri come configurare la connessione a Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568457"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="55bda-103">Connettore per Google Ads (anteprima)</span><span class="sxs-lookup"><span data-stu-id="55bda-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="55bda-104">Esporta segmenti di profili cliente unificati nell'elenco destinatari di Google Ads e utilizzali per fare pubblicità su Google Search, Gmail, YouTube e Rete Display di Google.</span><span class="sxs-lookup"><span data-stu-id="55bda-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="55bda-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="55bda-105">Prerequisites</span></span>

-   <span data-ttu-id="55bda-106">Devi disporre di un [account Google Ads](https://ads.google.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="55bda-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="55bda-107">In Google Ads sono presenti destinatari e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="55bda-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="55bda-108">Per ulteriori informazioni, vedi [Destinatari Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="55bda-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="55bda-109">Disponi di [segmenti configurati](segments.md)</span><span class="sxs-lookup"><span data-stu-id="55bda-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="55bda-110">I profili cliente unificati nei segmenti esportati contengono campi che rappresentano un indirizzo e-mail, un nome e un cognome</span><span class="sxs-lookup"><span data-stu-id="55bda-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="55bda-111">Connettiti a Google Ads</span><span class="sxs-lookup"><span data-stu-id="55bda-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="55bda-112">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="55bda-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="55bda-113">Sotto **Google Ads**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="55bda-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="55bda-114">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="55bda-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="55bda-115">Immetti l'**[ID cliente Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="55bda-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="55bda-116">Immetti il **[Token per sviluppatori di Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="55bda-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="55bda-117">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="55bda-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="55bda-118">Immetti l'**[ID destinatario Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e seleziona **Connetti** per inizializzare la connessione a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="55bda-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="55bda-119">Seleziona **Esegui autenticazione con Google Ads** e fornisci le tue credenziali Google Ads.</span><span class="sxs-lookup"><span data-stu-id="55bda-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="55bda-120">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="55bda-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Screenshot di esportazione per la connessione a Google Ads":::

1. <span data-ttu-id="55bda-122">Seleziona **Avanti** per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="55bda-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="55bda-123">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="55bda-123">Configure the connector</span></span>

1. <span data-ttu-id="55bda-124">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="55bda-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="55bda-125">Ripeti gli stessi passaggi per i campi **Nome** e **Cognome**.</span><span class="sxs-lookup"><span data-stu-id="55bda-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="55bda-126">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="55bda-126">Select the segments you want to export.</span></span> <span data-ttu-id="55bda-127">Puoi esportare in totale fino a 1 milione di profili cliente in Google Ads.</span><span class="sxs-lookup"><span data-stu-id="55bda-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="55bda-128">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="55bda-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="55bda-129">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="55bda-129">Export the data</span></span>

<span data-ttu-id="55bda-130">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="55bda-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="55bda-131">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="55bda-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="55bda-132">I tuoi segmenti sono ora visualizzati sotto [Destinatari Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/) in Google Ads.</span><span class="sxs-lookup"><span data-stu-id="55bda-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="55bda-133">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="55bda-133">Known limitations</span></span>

- <span data-ttu-id="55bda-134">Fino a 1 milione di profili per esportazione in Google Ads.</span><span class="sxs-lookup"><span data-stu-id="55bda-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="55bda-135">L'esportazione in Google Ads è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="55bda-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="55bda-136">L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 5 minuti a causa delle limitazioni sul lato provider.</span><span class="sxs-lookup"><span data-stu-id="55bda-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="55bda-137">La corrispondenza in Google Ads può richiedere fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="55bda-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="55bda-138">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="55bda-138">Data privacy and compliance</span></span>

<span data-ttu-id="55bda-139">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Google Ads, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="55bda-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="55bda-140">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Google Ads rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="55bda-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="55bda-141">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="55bda-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="55bda-142">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="55bda-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
