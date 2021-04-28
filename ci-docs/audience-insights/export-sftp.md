---
title: Esportare dati di Customer Insights in host SFTP
description: Scopri come configurare la connessione ed esportare in una posizione SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760424"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="cea32-103">Esportare elenchi di segmenti e altri dati su SFTP (anteprima)</span><span class="sxs-lookup"><span data-stu-id="cea32-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="cea32-104">Utilizza i dati dei tuoi clienti in applicazioni di terze parti esportandoli in una posizione SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="cea32-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="cea32-105">Prerequisiti per la connessione</span><span class="sxs-lookup"><span data-stu-id="cea32-105">Prerequisites for connection</span></span>

- <span data-ttu-id="cea32-106">Disponibilità di un host FTP sicuro e credenziali corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="cea32-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cea32-107">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="cea32-107">Known limitations</span></span>

- <span data-ttu-id="cea32-108">Il tempo di esecuzione di un'esportazione dipende dalle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="cea32-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="cea32-109">Consigliamo due core CPU e 1 GB di memoria come configurazione minima del server.</span><span class="sxs-lookup"><span data-stu-id="cea32-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="cea32-110">L'esportazione di entità con un massimo di 100 milioni di profili cliente può richiedere 90 minuti se si utilizza la configurazione minima consigliata di due core CPU e 1 GB di memoria.</span><span class="sxs-lookup"><span data-stu-id="cea32-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="cea32-111">Configurare la connessione a SFTP</span><span class="sxs-lookup"><span data-stu-id="cea32-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="cea32-112">Vai ad **Amministratore** > **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="cea32-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cea32-113">Seleziona **Aggiungi connessione** e scegli **SFTP** per configurare la connessione.</span><span class="sxs-lookup"><span data-stu-id="cea32-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="cea32-114">Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="cea32-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cea32-115">Il nome e il tipo di connessione descrivono la connessione.</span><span class="sxs-lookup"><span data-stu-id="cea32-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cea32-116">Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.</span><span class="sxs-lookup"><span data-stu-id="cea32-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cea32-117">Scegli chi può utilizzare questa connessione.</span><span class="sxs-lookup"><span data-stu-id="cea32-117">Choose who can use this connection.</span></span> <span data-ttu-id="cea32-118">Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori.</span><span class="sxs-lookup"><span data-stu-id="cea32-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="cea32-119">Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cea32-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="cea32-120">Fornisci un **Nome utente**, una **Password** e un **Nome host** e una **Cartella di esportazione** per il tuo account FTP sicuro.</span><span class="sxs-lookup"><span data-stu-id="cea32-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="cea32-121">Seleziona **Verifica** per testare la connessione.</span><span class="sxs-lookup"><span data-stu-id="cea32-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="cea32-122">Scegli se desideri esportare i tuoi dati **Compresso** o **Decompresso** e il **delimitatore di campo** per i file esportati.</span><span class="sxs-lookup"><span data-stu-id="cea32-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="cea32-123">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="cea32-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cea32-124">Seleziona **Salva** per completare la connessione.</span><span class="sxs-lookup"><span data-stu-id="cea32-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="cea32-125">Configurare un'esportazione</span><span class="sxs-lookup"><span data-stu-id="cea32-125">Configure an export</span></span>

<span data-ttu-id="cea32-126">Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="cea32-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cea32-127">Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cea32-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cea32-128">Vai a **Dati** > **Esportazioni**.</span><span class="sxs-lookup"><span data-stu-id="cea32-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cea32-129">Per creare una nuova esportazione seleziona **Aggiungi destinazione**.</span><span class="sxs-lookup"><span data-stu-id="cea32-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="cea32-130">Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione SFTP.</span><span class="sxs-lookup"><span data-stu-id="cea32-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="cea32-131">Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="cea32-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="cea32-132">Seleziona le entità, ad esempio i segmenti, che vuoi esportare.</span><span class="sxs-lookup"><span data-stu-id="cea32-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cea32-133">Ogni entità selezionata verrà suddivisa in un massimo di cinque file di output quando esportata.</span><span class="sxs-lookup"><span data-stu-id="cea32-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="cea32-134">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cea32-134">Select **Save**.</span></span>

<span data-ttu-id="cea32-135">Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="cea32-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="cea32-136">L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cea32-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cea32-137">Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cea32-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cea32-138">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="cea32-138">Data privacy and compliance</span></span>

<span data-ttu-id="cea32-139">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati via SFTP, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="cea32-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cea32-140">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che la destinazione di esportazione rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="cea32-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="cea32-141">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cea32-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cea32-142">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cea32-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
