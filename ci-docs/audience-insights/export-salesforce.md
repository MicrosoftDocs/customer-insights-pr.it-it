---
title: Esportazione dei dati di Customer Insights in Salesforce Marketing Cloud
description: Scopri come configurare la connessione ed esportare in Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314630"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="ba586-103">Esportazione di segmenti e altri dati in Salesforce Marketing Cloud (anteprima)</span><span class="sxs-lookup"><span data-stu-id="ba586-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="ba586-104">Utilizza i dati dei tuoi clienti in Salesforce Marketing Cloud esportandoli tramite una posizione con FTP sicuro.</span><span class="sxs-lookup"><span data-stu-id="ba586-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ba586-105">Prerequisiti per la connessione</span><span class="sxs-lookup"><span data-stu-id="ba586-105">Prerequisites for connection</span></span>

- <span data-ttu-id="ba586-106">Disponibilità di un host con FTP sicuro e delle corrispondenti credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="ba586-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="ba586-107">Come configurare le posizioni con FTP sicuro per Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="ba586-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="ba586-108">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="ba586-108">Known limitations</span></span>

- <span data-ttu-id="ba586-109">Il tempo di esecuzione di un'esportazione dipende dalle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="ba586-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="ba586-110">Consigliamo due core CPU e 1 GB di memoria come configurazione minima del server.</span><span class="sxs-lookup"><span data-stu-id="ba586-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="ba586-111">L'esportazione di entità con un massimo di 100 milioni di profili cliente può richiedere 90 minuti quando si utilizza la configurazione minima consigliata.</span><span class="sxs-lookup"><span data-stu-id="ba586-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="ba586-112">Configurazione della connessione a Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="ba586-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="ba586-113">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="ba586-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ba586-114">Seleziona **Aggiungi connessione** e scegli **Salesforce Marketing Cloud** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="ba586-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="ba586-115">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="ba586-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ba586-116">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="ba586-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ba586-117">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="ba586-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ba586-118">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="ba586-118">Choose who can use this connection.</span></span> <span data-ttu-id="ba586-119">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="ba586-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ba586-120">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ba586-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ba586-121">Fornisci un **Nome utente**, una **Password** e un **Nome host** e una **Cartella di esportazione** per il tuo account FTP sicuro.</span><span class="sxs-lookup"><span data-stu-id="ba586-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="ba586-122">Seleziona **Verifica** per testare la connessione.</span><span class="sxs-lookup"><span data-stu-id="ba586-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="ba586-123">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="ba586-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ba586-124">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="ba586-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ba586-125">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="ba586-125">Configure an export</span></span>

<span data-ttu-id="ba586-126">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="ba586-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ba586-127">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ba586-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ba586-128">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="ba586-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ba586-129">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="ba586-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ba586-130">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione SFTP.</span><span class="sxs-lookup"><span data-stu-id="ba586-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="ba586-131">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="ba586-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ba586-132">Scegli se desideri esportare i tuoi dati **Compresso** o **Decompresso** e il **delimitatore di campo** per i file esportati.</span><span class="sxs-lookup"><span data-stu-id="ba586-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="ba586-133">Seleziona le entità, ad esempio i segmenti, che vuoi esportare.</span><span class="sxs-lookup"><span data-stu-id="ba586-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ba586-134">Ogni entità selezionata verrà suddivisa in un massimo di cinque file di output quando esportata.</span><span class="sxs-lookup"><span data-stu-id="ba586-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="ba586-135">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ba586-135">Select **Save**.</span></span>

<span data-ttu-id="ba586-136">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="ba586-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ba586-137">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ba586-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ba586-138">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ba586-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="ba586-139">Importazione dei dati di Customer Insights dalla posizione con FTP sicuro in Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="ba586-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="ba586-140">Crea [estensioni dati in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) per importare il file di dati di Customer Insights dalla posizione con FTP sicuro.</span><span class="sxs-lookup"><span data-stu-id="ba586-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="ba586-141">[Importa i dati dalla posizione con FTP sicuro](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) nell'estensione dati Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="ba586-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="ba586-142">Imposta l'automazione per importare i dati nelle estensioni dati.</span><span class="sxs-lookup"><span data-stu-id="ba586-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="ba586-143">Scopri di più riguardo [automazioni di rilascio file e automazioni programmate](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="ba586-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="ba586-144">Definisci un'[automazione di rilascio file](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) o un'[automazione programmata ](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="ba586-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="ba586-145">Ecco un esempio di [un'automazione con FTP sicuro](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="ba586-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ba586-146">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="ba586-146">Data privacy and compliance</span></span>

<span data-ttu-id="ba586-147">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati via SFTP, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="ba586-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ba586-148">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che la destinazione di esportazione rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="ba586-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ba586-149">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ba586-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ba586-150">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ba586-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
