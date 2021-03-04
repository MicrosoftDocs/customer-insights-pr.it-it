---
title: Esportare dati di Customer Insights in SendGrid
description: Scopri come configurare la connessione a SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268737"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="0b817-103">Connettore per SendGrid (anteprima)</span><span class="sxs-lookup"><span data-stu-id="0b817-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="0b817-104">Esporta segmenti di profili cliente unificati nell'elenco di contatti SendGrid e usali per campagne e e-mail marketing in SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0b817-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0b817-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0b817-105">Prerequisites</span></span>

-   <span data-ttu-id="0b817-106">Devi disporre di un [account SendGrid](https://sendgrid.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="0b817-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0b817-107">In SendGrid sono presenti elenchi di contatti e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="0b817-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="0b817-108">Per ulteriori informazioni, vedere [SendGrid: gestire i contatti](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="0b817-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="0b817-109">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="0b817-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0b817-110">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="0b817-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="0b817-111">Connettersi a SendGrid</span><span class="sxs-lookup"><span data-stu-id="0b817-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="0b817-112">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="0b817-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0b817-113">In **SendGrid**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="0b817-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="0b817-114">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="0b817-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Riquadro di configurazione dell'esportazione in SendGrid.":::

1. <span data-ttu-id="0b817-116">Inserisci la tua **Chiave API SendGrid** [Chiave API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="0b817-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="0b817-117">Immetti l'**[ID elenco SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="0b817-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="0b817-118">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="0b817-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0b817-119">Seleziona **Connetti** per inizializzare la connessione a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0b817-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="0b817-120">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0b817-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0b817-121">Seleziona **Avanti** per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="0b817-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0b817-122">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="0b817-122">Configure the connector</span></span>

1. <span data-ttu-id="0b817-123">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="0b817-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0b817-124">Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**, **Paese/area geografica**, **Stato**, **Città** e **Codice postale**.</span><span class="sxs-lookup"><span data-stu-id="0b817-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="0b817-125">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="0b817-125">Select the segments you want to export.</span></span> <span data-ttu-id="0b817-126">È fortemente **consigliato di non esportare più di 100.000 profili cliente in totale** in SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0b817-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="0b817-127">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0b817-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0b817-128">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="0b817-128">Export the data</span></span>

<span data-ttu-id="0b817-129">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0b817-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0b817-130">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0b817-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0b817-131">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="0b817-131">Known limitations</span></span>

- <span data-ttu-id="0b817-132">Fino a 100.000 profili in totale a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0b817-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="0b817-133">L'esportazione in SendGrid è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="0b817-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="0b817-134">L'esportazione di un massimo di 100.000 profili in SendGrid può richiedere alcune ore per essere completata.</span><span class="sxs-lookup"><span data-stu-id="0b817-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0b817-135">Il numero di profili che puoi esportare in SendGrid dipende ed è limitato dal tuo contratto con SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0b817-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0b817-136">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="0b817-136">Data privacy and compliance</span></span>

<span data-ttu-id="0b817-137">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a SendGrid, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="0b817-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0b817-138">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che SendGrid rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="0b817-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0b817-139">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0b817-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0b817-140">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0b817-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]