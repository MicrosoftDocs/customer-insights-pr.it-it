---
title: Connettore LiveRamp
description: Scopri come configurare la connessione ed esportare in LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760332"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="d23c3-103">Esportare segmenti in LiveRamp&reg; (anteprima)</span><span class="sxs-lookup"><span data-stu-id="d23c3-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="d23c3-104">Attiva i tuoi dati in LiveRamp per connetterti con oltre 500 piattaforme su digitale, social e TV.</span><span class="sxs-lookup"><span data-stu-id="d23c3-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="d23c3-105">Utilizza i tuoi dati in LiveRamp per indirizzare, eliminare e personalizzare le campagne pubblicitarie.</span><span class="sxs-lookup"><span data-stu-id="d23c3-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d23c3-106">Prerequisiti per una connessione</span><span class="sxs-lookup"><span data-stu-id="d23c3-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="d23c3-107">È necessario un abbonamento LiveRamp per utilizzare questo connettore.</span><span class="sxs-lookup"><span data-stu-id="d23c3-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="d23c3-108">Per ottenere un abbonamento, [contatta LiveRamp](https://liveramp.com/contact/) direttamente.</span><span class="sxs-lookup"><span data-stu-id="d23c3-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="d23c3-109">[Altre informazioni sull'oboarding di LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="d23c3-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="d23c3-110">Configurare la connessione a LiveRamp</span><span class="sxs-lookup"><span data-stu-id="d23c3-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="d23c3-111">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="d23c3-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d23c3-112">Seleziona **Aggiungi connessione** e scegli **LiveRamp** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="d23c3-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="d23c3-113">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="d23c3-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d23c3-114">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="d23c3-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d23c3-115">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="d23c3-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d23c3-116">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="d23c3-116">Choose who can use this connection.</span></span> <span data-ttu-id="d23c3-117">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="d23c3-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d23c3-118">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d23c3-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d23c3-119">Specifica un **Nome utente** e una **Password** per l'account LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="d23c3-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="d23c3-120">Queste credenziali possono essere diverse dalle credenziali di LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="d23c3-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="d23c3-121">Seleziona **Verificare** per testare la connessione a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="d23c3-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="d23c3-122">Dopo aver verificato con successo, fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="d23c3-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="d23c3-123">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="d23c3-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d23c3-124">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="d23c3-124">Configure an export</span></span>

<span data-ttu-id="d23c3-125">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="d23c3-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d23c3-126">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d23c3-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d23c3-127">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="d23c3-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d23c3-128">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="d23c3-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d23c3-129">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="d23c3-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="d23c3-130">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="d23c3-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d23c3-131">Nel campo **Scegli il tuo identificatore chiave**, seleziona **E-mail**, **Nome e indirizzo** o **Telefono** per inviare a LiveRamp per la risoluzione dell'identità.</span><span class="sxs-lookup"><span data-stu-id="d23c3-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d23c3-132">![Connettore LiveRamp con mappatura degli attributi](media/export-liveramp-segments.png "Connettore LiveRamp con mappatura degli attributi")</span><span class="sxs-lookup"><span data-stu-id="d23c3-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="d23c3-133">Mappa gli attributi corrispondenti dall'entità cliente unificata per l'identificatore chiave selezionato.</span><span class="sxs-lookup"><span data-stu-id="d23c3-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="d23c3-134">Seleziona **Aggiungi attributo** per mappare più attributi da inviare a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="d23c3-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="d23c3-135">L'invio di più attributi dell'identificatore chiave a LiveRamp probabilmente ti farà ottenere un tasso di corrispondenza più elevato.</span><span class="sxs-lookup"><span data-stu-id="d23c3-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="d23c3-136">Seleziona i segmenti che desideri esportare in LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="d23c3-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="d23c3-137">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d23c3-137">Select **Save**.</span></span>

<span data-ttu-id="d23c3-138">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="d23c3-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d23c3-139">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d23c3-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d23c3-140">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d23c3-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d23c3-141">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="d23c3-141">Data privacy and compliance</span></span>

<span data-ttu-id="d23c3-142">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Liveramp, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="d23c3-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d23c3-143">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Liveramp rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="d23c3-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d23c3-144">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d23c3-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d23c3-145">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d23c3-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
