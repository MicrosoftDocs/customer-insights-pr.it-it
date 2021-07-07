---
title: Esportare dati di Customer Insights in Gestione inserzioni di Facebook
description: Scopri come configurare la connessione ed esportare in Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305115"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="b1d9b-103">Esportare l'elenco di segmenti in Facebook Ads Manager (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b1d9b-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="b1d9b-104">Esporta segmenti di profili cliente unificati in Gestione inserzioni di Facebook per creare campagne in Facebook e Instagram.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b1d9b-105">Prerequisiti per la connessione</span><span class="sxs-lookup"><span data-stu-id="b1d9b-105">Prerequisites for connection</span></span>

- <span data-ttu-id="b1d9b-106">Devi disporre di un [**account annunci Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) che includa un [**account aziendale Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="b1d9b-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="b1d9b-107">Devi essere un amministratore sull'[**account annunci Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="b1d9b-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b1d9b-108">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="b1d9b-108">Known limitations</span></span>

- <span data-ttu-id="b1d9b-109">Fino a 10 milioni di profili cliente per esportazione verso Gestore annunci di Facebook.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="b1d9b-110">L'esportazione in Facebook Ads Manager è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="b1d9b-111">Crea o aggiorna segmenti di gruppi di destinatari personalizzati in Facebook solo di tipo *elenco clienti*.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="b1d9b-112">L'esportazione di segmenti con un totale di 10 milione di profili può richiedere fino a 90 minuti.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="b1d9b-113">Configurare la connessione a Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="b1d9b-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="b1d9b-114">Prima che gli utenti possano creare un'esportazione, un amministratore deve configurare la connessione al servizio e consentire ai collaboratori di utilizzare la connessione.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="b1d9b-115">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b1d9b-116">Seleziona **Aggiungi connessione** e scegli **Facebook Ads Manager** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="b1d9b-117">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b1d9b-118">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b1d9b-119">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b1d9b-120">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-120">Choose who can use this connection.</span></span> <span data-ttu-id="b1d9b-121">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b1d9b-122">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b1d9b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b1d9b-123">Esegui l'autenticazione con Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="b1d9b-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="b1d9b-124">Seleziona **Continua con Facebook** per accedere al tuo account annunci Facebook.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="b1d9b-125">Consenti l'autorizzazione **ads_management** dopo l'autenticazione con Facebook.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="b1d9b-126">Seleziona l'**account inserzionista Facebook** che vuoi utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="b1d9b-127">Seleziona un **gruppo di destinatari personalizzato esistente** dall'elenco a discesa o crea un **nuovo gruppo di destinatari personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="b1d9b-128">Per ulteriori informazioni, vedi [**Destinatari in Gestione inserzioni di Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="b1d9b-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="b1d9b-129">Puoi creare o aggiornare segmenti di pubblico personalizzati solo su Facebook del tipo *elenco clienti* con questa esportazione.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="b1d9b-130">In alcuni casi, nell'elenco a discesa, vengono visualizzati segmenti di pubblico personalizzati di diversi tipi.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="b1d9b-131">La selezione di un tipo diverso da *elenco clienti* comporterà un'esportazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="b1d9b-132">Rivedi **Privacy e conformità dei dati** e seleziona **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="b1d9b-133">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b1d9b-134">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="b1d9b-134">Configure an export</span></span>

<span data-ttu-id="b1d9b-135">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b1d9b-136">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b1d9b-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b1d9b-137">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b1d9b-138">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="b1d9b-139">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="b1d9b-140">Se non vedi questo nome di sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="b1d9b-141">Nel **campo Scegli identificatore chiave**, seleziona **E-mail**, **Nome e indirizzo** o **Telefono** per inviare a Gestione inserzioni di Facebook.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="b1d9b-142">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b1d9b-143">Mappa gli attributi corrispondenti dall'entità cliente unificata per l'identificatore chiave selezionato.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="b1d9b-144">Le migliori possibilità di corrispondenza si hanno se selezioni **E-mail** come identificatore chiave.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="b1d9b-145">L'aggiunta di identificatori aggiuntivi può migliorare la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="b1d9b-146">Seleziona **Aggiungi attributo** per mappare più attributi da inviare a Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="b1d9b-147">Gli attributi di Gestione annunci di Facebook sono mapping ai seguenti nomi descrittivi per l'utente: **FN** = **Nome**, **LN** = **Cognome**, **FI** = **Iniziali**, **PHONE** = **Telefono**, **GEN** = **Sesso**, **DOB** = **Data di nascita**, **ST** = **Stato**, **CT** = **Città**, **ZIP** = **Codice postale**, **COUNTRY** = **Paese/Area geografica**</span><span class="sxs-lookup"><span data-stu-id="b1d9b-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="b1d9b-148">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="b1d9b-149">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-149">Select **Save**.</span></span>

<span data-ttu-id="b1d9b-150">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b1d9b-151">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b1d9b-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="b1d9b-152">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b1d9b-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b1d9b-153">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="b1d9b-153">Data privacy and compliance</span></span>

<span data-ttu-id="b1d9b-154">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Gestione inserzioni di Facebook, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b1d9b-155">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Facebook rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b1d9b-156">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b1d9b-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b1d9b-157">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b1d9b-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
