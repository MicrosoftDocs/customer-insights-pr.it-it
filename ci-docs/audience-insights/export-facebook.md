---
title: Esportare dati di Customer Insights in Gestione inserzioni di Facebook
description: Scopri come configurare la connessione a Gestione inserzioni di Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643688"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="cb934-103">Connettore per Gestione inserzioni di Facebook (anteprima)</span><span class="sxs-lookup"><span data-stu-id="cb934-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="cb934-104">Esporta segmenti di profili cliente unificati in Gestione inserzioni di Facebook per creare campagne in Facebook e Instagram.</span><span class="sxs-lookup"><span data-stu-id="cb934-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb934-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cb934-105">Prerequisites</span></span>

- <span data-ttu-id="cb934-106">Devi avere un [account inserzionista **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) che include un [account **Facebook Business**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="cb934-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="cb934-107">Devi essere un amministratore nell'[account inserzionista **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="cb934-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="cb934-108">Connessione a Gestione inserzioni di Facebook</span><span class="sxs-lookup"><span data-stu-id="cb934-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="cb934-109">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="cb934-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cb934-110">In **Gestione inserzioni di Facebook**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="cb934-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="cb934-111">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="cb934-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="cb934-112">Seleziona **Continua con Facebook** per accedere al tuo account inserzionista Facebook.</span><span class="sxs-lookup"><span data-stu-id="cb934-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="cb934-113">Consenti l'autorizzazione **ads_management** dopo l'autenticazione con Facebook.</span><span class="sxs-lookup"><span data-stu-id="cb934-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="cb934-114">Seleziona l'**account inserzionista Facebook** che vuoi utilizzare.</span><span class="sxs-lookup"><span data-stu-id="cb934-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="cb934-115">Seleziona i **destinatari personalizzati esistenti** dall'elenco a discesa o crea **nuovi destinatari personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="cb934-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="cb934-116">Per ulteriori informazioni, vedi [**Destinatari in Gestione inserzioni di Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="cb934-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="cb934-117">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="cb934-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cb934-118">Seleziona **Avanti** per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="cb934-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="cb934-119">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="cb934-119">Configure the connector</span></span>

1. <span data-ttu-id="cb934-120">Nel **campo Scegli identificatore chiave**, seleziona **E-mail**, **Nome e indirizzo** o **Telefono** per inviare a Gestione inserzioni di Facebook.</span><span class="sxs-lookup"><span data-stu-id="cb934-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="cb934-121">Mappa gli attributi corrispondenti dall'entità cliente unificata per l'identificatore chiave selezionato.</span><span class="sxs-lookup"><span data-stu-id="cb934-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="cb934-122">[SUGGERIMENTO] Le migliori possibilità di corrispondenza si hanno se selezioni **E-mail** come identificatore chiave.</span><span class="sxs-lookup"><span data-stu-id="cb934-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="cb934-123">L'aggiunta di identificatori aggiuntivi può migliorare la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="cb934-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="cb934-124">Seleziona **Aggiungi attributo** per mappare ulteriori attributi da inviare a Gestione inserzioni di Facebook.</span><span class="sxs-lookup"><span data-stu-id="cb934-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="cb934-125">Gli attributi di Gestione inserzioni di Facebook sono mapping ai seguenti nomi descrittivi per l'utente: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span><span class="sxs-lookup"><span data-stu-id="cb934-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="cb934-126">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="cb934-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="cb934-127">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cb934-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cb934-128">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="cb934-128">Export the data</span></span>

<span data-ttu-id="cb934-129">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cb934-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cb934-130">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cb934-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cb934-131">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="cb934-131">Data privacy and compliance</span></span>

<span data-ttu-id="cb934-132">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Gestione inserzioni di Facebook, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="cb934-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cb934-133">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Facebook rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="cb934-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="cb934-134">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cb934-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cb934-135">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cb934-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
