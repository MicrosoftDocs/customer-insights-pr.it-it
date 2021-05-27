---
title: Esportare dati di Customer Insights in DotDigital
description: Scopri come configurare la connessione ed esportare in DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976851"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="a04f8-103">Esportare elenchi di segmenti in DotDigital (anteprima)</span><span class="sxs-lookup"><span data-stu-id="a04f8-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="a04f8-104">Esporta segmenti di profili cliente unificati nelle rubriche di DotDigital e usali per campagne, messaggi e-mail di marketing e per costruire segmenti di clientela con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a04f8-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a04f8-105">Prerequisiti per una connessione</span><span class="sxs-lookup"><span data-stu-id="a04f8-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a04f8-106">Devi disporre di un [account DotDigital](https://dotdigital.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="a04f8-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a04f8-107">In DotDigital sono presenti rubriche e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="a04f8-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="a04f8-108">L'ID è presente nell'URL quando selezioni e apri una rubrica.</span><span class="sxs-lookup"><span data-stu-id="a04f8-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="a04f8-109">Per ulteriori informazioni, vedi [Rubriche di DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="a04f8-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="a04f8-110">Disponi di [segmenti configurati](segments.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="a04f8-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a04f8-111">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="a04f8-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a04f8-112">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="a04f8-112">Known limitations</span></span>

- <span data-ttu-id="a04f8-113">Fino a 1 milione di profili per esportazione in DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a04f8-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="a04f8-114">L'esportazione in DotDigital è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="a04f8-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="a04f8-115">L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 3 ore a causa delle limitazioni sul lato provider.</span><span class="sxs-lookup"><span data-stu-id="a04f8-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="a04f8-116">Il numero di profili che puoi esportare in DotDigital dipende ed è limitato dal tuo contratto con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a04f8-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="a04f8-117">Configurare la connessione a DotDigital</span><span class="sxs-lookup"><span data-stu-id="a04f8-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="a04f8-118">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="a04f8-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a04f8-119">Seleziona **Aggiungi connessione** e scegli **DotDigital** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="a04f8-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="a04f8-120">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="a04f8-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a04f8-121">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="a04f8-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a04f8-122">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="a04f8-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a04f8-123">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="a04f8-123">Choose who can use this connection.</span></span> <span data-ttu-id="a04f8-124">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="a04f8-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a04f8-125">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a04f8-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a04f8-126">Immetti il **nome utente e la password di DogDigital**.</span><span class="sxs-lookup"><span data-stu-id="a04f8-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="a04f8-127">Immetti l'**[ID rubrica DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="a04f8-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="a04f8-128">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="a04f8-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a04f8-129">Seleziona **Connetti** per inizializzare la connessione a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a04f8-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="a04f8-130">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a04f8-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a04f8-131">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="a04f8-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="a04f8-132">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="a04f8-132">Configure an export</span></span>

<span data-ttu-id="a04f8-133">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="a04f8-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a04f8-134">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a04f8-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a04f8-135">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="a04f8-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a04f8-136">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="a04f8-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a04f8-137">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a04f8-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="a04f8-138">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="a04f8-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="a04f8-139">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="a04f8-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a04f8-140">Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**, **Nome completo**, **Sesso** e **Codice postale**.</span><span class="sxs-lookup"><span data-stu-id="a04f8-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="a04f8-141">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="a04f8-141">Select the segments you want to export.</span></span> <span data-ttu-id="a04f8-142">Puoi esportare in totale fino a 1 milione di profili cliente in DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a04f8-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="a04f8-143">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a04f8-143">Select **Save**.</span></span>

<span data-ttu-id="a04f8-144">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="a04f8-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a04f8-145">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a04f8-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a04f8-146">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a04f8-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="a04f8-147">I tuoi segmenti sono ora visualizzati sotto [Rubriche DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) in DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a04f8-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a04f8-148">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="a04f8-148">Data privacy and compliance</span></span>

<span data-ttu-id="a04f8-149">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a DotDigital, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="a04f8-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a04f8-150">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che DotDigital rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="a04f8-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a04f8-151">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a04f8-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a04f8-152">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a04f8-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
