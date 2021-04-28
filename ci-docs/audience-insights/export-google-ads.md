---
title: Esportare dati di Customer Insights in Google Ads
description: Scopri come configurare la connessione ed esportare in Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759698"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="06611-103">Esportare segmenti in Google Ads (anteprima)</span><span class="sxs-lookup"><span data-stu-id="06611-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="06611-104">Esporta segmenti di profili cliente unificati nell'elenco destinatari di Google Ads e utilizzali per fare pubblicità su Google Search, Gmail, YouTube e Rete Display di Google.</span><span class="sxs-lookup"><span data-stu-id="06611-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="06611-105">Prerequisiti per la connessione</span><span class="sxs-lookup"><span data-stu-id="06611-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="06611-106">Devi disporre di un [account Google Ads](https://ads.google.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="06611-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="06611-107">Hai un [token per sviluppatori Google Ads approvato](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="06611-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="06611-108">Soddisfi i requisiti dei [criteri di corrispondenza dei clienti](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="06611-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="06611-109">Soddisfi i requisiti delle [dimensioni degli elenchi per il remarketing](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="06611-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="06611-110">In Google Ads sono presenti destinatari e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="06611-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="06611-111">Per ulteriori informazioni, vedi [Destinatari Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="06611-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="06611-112">Disponi di [segmenti configurati](segments.md)</span><span class="sxs-lookup"><span data-stu-id="06611-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="06611-113">I profili cliente unificati nei segmenti esportati contengono campi che rappresentano un indirizzo e-mail, un nome e un cognome</span><span class="sxs-lookup"><span data-stu-id="06611-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="06611-114">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="06611-114">Known limitations</span></span>

- <span data-ttu-id="06611-115">Fino a 1 milione di profili per esportazione in Google Ads.</span><span class="sxs-lookup"><span data-stu-id="06611-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="06611-116">L'esportazione in Google Ads è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="06611-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="06611-117">L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 5 minuti a causa delle limitazioni sul lato provider.</span><span class="sxs-lookup"><span data-stu-id="06611-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="06611-118">La corrispondenza in Google Ads può richiedere fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="06611-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="06611-119">Configurare la connessione a Google Ads</span><span class="sxs-lookup"><span data-stu-id="06611-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="06611-120">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="06611-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="06611-121">Seleziona **Aggiungi connessione** e scegli **Google Ads** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="06611-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="06611-122">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="06611-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="06611-123">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="06611-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="06611-124">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="06611-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="06611-125">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="06611-125">Choose who can use this connection.</span></span> <span data-ttu-id="06611-126">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="06611-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="06611-127">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="06611-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="06611-128">Immetti l'**[ID cliente Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="06611-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="06611-129">Immetti il **[Token per sviluppatori di Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="06611-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="06611-130">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="06611-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="06611-131">Seleziona **Esegui autenticazione con Google Ads** e fornisci le tue credenziali Google Ads.</span><span class="sxs-lookup"><span data-stu-id="06611-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="06611-132">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="06611-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="06611-133">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="06611-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="06611-134">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="06611-134">Configure an export</span></span>

<span data-ttu-id="06611-135">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="06611-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="06611-136">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="06611-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="06611-137">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="06611-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="06611-138">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="06611-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="06611-139">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Google Ads.</span><span class="sxs-lookup"><span data-stu-id="06611-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="06611-140">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="06611-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="06611-141">Immetti l'**[ID destinatario Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e seleziona **Connetti** per inizializzare la connessione a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="06611-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="06611-142">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="06611-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="06611-143">Ripeti gli stessi passaggi per i campi **Nome** e **Cognome**.</span><span class="sxs-lookup"><span data-stu-id="06611-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="06611-144">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="06611-144">Select the segments you want to export.</span></span> <span data-ttu-id="06611-145">Puoi esportare in totale fino a 1 milione di profili cliente in Google Ads.</span><span class="sxs-lookup"><span data-stu-id="06611-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="06611-146">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="06611-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="06611-147">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="06611-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="06611-148">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="06611-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="06611-149">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="06611-149">Data privacy and compliance</span></span>

<span data-ttu-id="06611-150">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Google Ads, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="06611-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="06611-151">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Google Ads rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="06611-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="06611-152">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="06611-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="06611-153">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="06611-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
