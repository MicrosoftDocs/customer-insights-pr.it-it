---
title: Connettore LiveRamp
description: Scopri come esportare dati in LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270163"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="5a864-103">Connettore LiveRamp&reg; (anteprima)</span><span class="sxs-lookup"><span data-stu-id="5a864-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="5a864-104">Attiva i tuoi dati in LiveRamp per connetterti con oltre 500 piattaforme su ecosistemi digitali, social e TV.</span><span class="sxs-lookup"><span data-stu-id="5a864-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="5a864-105">Utilizza i tuoi dati in LiveRamp per indirizzare, eliminare e personalizzare le campagne pubblicitarie.</span><span class="sxs-lookup"><span data-stu-id="5a864-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a864-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5a864-106">Prerequisites</span></span>

- <span data-ttu-id="5a864-107">È necessario un abbonamento LiveRamp per utilizzare questo connettore.</span><span class="sxs-lookup"><span data-stu-id="5a864-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="5a864-108">Per ottenere un abbonamento, [contatta LiveRamp](https://liveramp.com/contact/) direttamente.</span><span class="sxs-lookup"><span data-stu-id="5a864-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="5a864-109">[Altre informazioni sull'oboarding di LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="5a864-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="5a864-110">Connettersi a LiveRamp</span><span class="sxs-lookup"><span data-stu-id="5a864-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="5a864-111">In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="5a864-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5a864-112">Nel riquadro **LiveRamp**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="5a864-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="5a864-113">Assegna alla tua destinazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="5a864-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="5a864-114">Specifica un **Nome utente** e una **Password** per l'account LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="5a864-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="5a864-115">Queste credenziali possono essere diverse dalle credenziali di LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="5a864-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="5a864-116">Seleziona **Verificare** per testare la connessione a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5a864-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="5a864-117">Dopo aver verificato con successo, fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="5a864-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="5a864-118">Seleziona **Avanti** per configurare il connettore LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5a864-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5a864-119">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="5a864-119">Configure the connector</span></span>

1. <span data-ttu-id="5a864-120">Nel campo **Scegli il tuo identificatore chiave**, seleziona **E-mail**, **Nome e indirizzo** o **Telefono** per inviare a LiveRamp per la risoluzione dell'identità.</span><span class="sxs-lookup"><span data-stu-id="5a864-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="5a864-121">Mappa gli attributi corrispondenti dall'entità cliente unificata per l'identificatore chiave selezionato.</span><span class="sxs-lookup"><span data-stu-id="5a864-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="5a864-122">Seleziona **Aggiungi attributo** per mappare altri attributi da inviare a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5a864-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="5a864-123">L'invio di più attributi dell'identificatore chiave a LiveRamp probabilmente ti farà ottenere un tasso di corrispondenza più elevato.</span><span class="sxs-lookup"><span data-stu-id="5a864-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="5a864-124">Seleziona i segmenti che desideri esportare in LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5a864-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="5a864-125">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5a864-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5a864-126">![Connettore LiveRamp con mappatura degli attributi](media/export-liveramp-segments.png "Connettore LiveRamp con mappatura degli attributi")</span><span class="sxs-lookup"><span data-stu-id="5a864-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5a864-127">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="5a864-127">Export the data</span></span>

<span data-ttu-id="5a864-128">L'esportazione inizierà a breve se tutti i prerequisiti per l'esportazione sono stati completati.</span><span class="sxs-lookup"><span data-stu-id="5a864-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="5a864-129">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5a864-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="5a864-130">Una volta completata correttamente l'esportazione, puoi accedere a LiveRamp Onboarding per attivare e distribuire i dati.</span><span class="sxs-lookup"><span data-stu-id="5a864-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5a864-131">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="5a864-131">Data privacy and compliance</span></span>

<span data-ttu-id="5a864-132">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Liveramp, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="5a864-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5a864-133">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Liveramp rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="5a864-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5a864-134">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5a864-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5a864-135">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5a864-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]