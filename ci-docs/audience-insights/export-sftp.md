---
title: Esportare dati di Customer Insights in host SFTP
description: Scopri come configurare la connessione a un host SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643508"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="6abe6-103">Connettore per SFTP (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6abe6-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="6abe6-104">Utilizza i tuoi dati cliente in applicazioni di terze parti esportandoli in un host SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="6abe6-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6abe6-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6abe6-105">Prerequisites</span></span>

- <span data-ttu-id="6abe6-106">Disponibilità di un host SFTP e credenziali corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="6abe6-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="6abe6-107">Connessione a SFTP</span><span class="sxs-lookup"><span data-stu-id="6abe6-107">Connect to SFTP</span></span>

1. <span data-ttu-id="6abe6-108">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6abe6-109">In **SFTP**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="6abe6-110">Assegna alla tua destinazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6abe6-111">Fornisci un **Nome utente**, una **Password** e un **Nome host** per il tuo account SFTP.</span><span class="sxs-lookup"><span data-stu-id="6abe6-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="6abe6-112">Esempio: se la cartella radice del server SFTP è /root/folder e desideri che i dati vengano esportati in /root/folder/ci_export_destination_folder, l'host deve essere sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="6abe6-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="6abe6-113">Seleziona **Verifica** per testare la connessione.</span><span class="sxs-lookup"><span data-stu-id="6abe6-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="6abe6-114">Al termine della verifica, scegli se desideri esportare i tuoi dati **compressi** o **decompressi** e seleziona il **delimitatore di campo** per i file esportati.</span><span class="sxs-lookup"><span data-stu-id="6abe6-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="6abe6-115">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6abe6-116">Seleziona **Avanti** per iniziare a configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6abe6-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="6abe6-117">Configurare la connessione</span><span class="sxs-lookup"><span data-stu-id="6abe6-117">Configure the connection</span></span>

1. <span data-ttu-id="6abe6-118">Seleziona gli **attributi del cliente** da esportare.</span><span class="sxs-lookup"><span data-stu-id="6abe6-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="6abe6-119">È possibile esportare uno o più attributi.</span><span class="sxs-lookup"><span data-stu-id="6abe6-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="6abe6-120">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-120">Select **Next**.</span></span>

1. <span data-ttu-id="6abe6-121">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="6abe6-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="6abe6-122">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6abe6-123">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="6abe6-123">Export the data</span></span>

<span data-ttu-id="6abe6-124">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6abe6-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6abe6-125">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6abe6-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6abe6-126">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="6abe6-126">Data privacy and compliance</span></span>

<span data-ttu-id="6abe6-127">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati via SFTP, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="6abe6-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6abe6-128">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che la destinazione di esportazione rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="6abe6-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6abe6-129">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6abe6-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6abe6-130">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6abe6-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
