---
title: Esportare dati di Customer Insights in host SFTP
description: Scopri come configurare la connessione a un host SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598390"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="8fb23-103">Connettore per SFTP (anteprima)</span><span class="sxs-lookup"><span data-stu-id="8fb23-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="8fb23-104">Utilizza i tuoi dati cliente in applicazioni di terze parti esportandoli in un host SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="8fb23-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8fb23-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8fb23-105">Prerequisites</span></span>

- <span data-ttu-id="8fb23-106">Disponibilità di un host FTP sicuro e credenziali corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8fb23-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="8fb23-107">Connetti a SFTP</span><span class="sxs-lookup"><span data-stu-id="8fb23-107">Connect to SFTP</span></span>

1. <span data-ttu-id="8fb23-108">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="8fb23-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8fb23-109">In **SFTP**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="8fb23-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="8fb23-110">Assegna alla tua destinazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="8fb23-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8fb23-111">Fornisci un **Nome utente**, una **Password** e un **Nome host** e una **Cartella di esportazione** per il tuo account FTP sicuro.</span><span class="sxs-lookup"><span data-stu-id="8fb23-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="8fb23-112">Seleziona **Verifica** per testare la connessione.</span><span class="sxs-lookup"><span data-stu-id="8fb23-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="8fb23-113">Dopo aver verificato con successo, scegli se desideri esportare i tuoi dati in formato **Compresso** o **Decompresso** e seleziona il **delimitatore di campo** per i file esportati.</span><span class="sxs-lookup"><span data-stu-id="8fb23-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="8fb23-114">Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.</span><span class="sxs-lookup"><span data-stu-id="8fb23-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8fb23-115">Seleziona **Avanti** per iniziare a configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="8fb23-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="8fb23-116">Configurare l'esportazione</span><span class="sxs-lookup"><span data-stu-id="8fb23-116">Configure the export</span></span>

1. <span data-ttu-id="8fb23-117">Seleziona le entità, ad esempio i segmenti, che vuoi esportare.</span><span class="sxs-lookup"><span data-stu-id="8fb23-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8fb23-118">Ogni entità selezionata sarà fino a cinque file di output quando esportata.</span><span class="sxs-lookup"><span data-stu-id="8fb23-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="8fb23-119">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8fb23-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8fb23-120">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="8fb23-120">Export the data</span></span>

<span data-ttu-id="8fb23-121">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8fb23-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8fb23-122">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8fb23-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8fb23-123">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="8fb23-123">Known limitations</span></span>

- <span data-ttu-id="8fb23-124">Il tempo di esecuzione di un'esportazione dipende dalle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="8fb23-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="8fb23-125">Consigliamo due core CPU e 1 GB di memoria come configurazione minima del server.</span><span class="sxs-lookup"><span data-stu-id="8fb23-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="8fb23-126">L'esportazione di entità con un massimo di 100 milioni di profili cliente può richiedere 90 minuti se si utilizza la configurazione minima consigliata di due core CPU e 1 GB di memoria.</span><span class="sxs-lookup"><span data-stu-id="8fb23-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8fb23-127">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="8fb23-127">Data privacy and compliance</span></span>

<span data-ttu-id="8fb23-128">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati via SFTP, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="8fb23-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8fb23-129">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che la destinazione di esportazione rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="8fb23-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8fb23-130">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8fb23-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8fb23-131">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8fb23-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]