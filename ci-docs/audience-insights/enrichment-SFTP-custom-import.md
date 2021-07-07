---
title: Arricchimento con l'importazione personalizzata SFTP
description: Informazioni generali sull'arricchimento con l'importazione personalizzata SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304655"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="3f577-103">Arricchimento di profili cliente con dati personalizzati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="3f577-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="3f577-104">L'importazione personalizzata SFTP (Secure File Transfer Protocol) consente di importare dati che non devono essere sottoposti al processo di unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3f577-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="3f577-105">È un modo flessibile, sicuro e facile di importare i dati.</span><span class="sxs-lookup"><span data-stu-id="3f577-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="3f577-106">L'importazione personalizzata SFTP può essere utilizzata in combinazione con l'[esportazione SFTP](export-sftp.md) che consente di esportare i dati del profilo cliente necessari per l'arricchimento.</span><span class="sxs-lookup"><span data-stu-id="3f577-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="3f577-107">I dati possono quindi essere elaborati e arricchiti e l'importazione personalizzata SFTP può essere utilizzata per riportare i dati arricchiti alla capacità di approfondimento dei destinatari di Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3f577-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f577-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3f577-108">Prerequisites</span></span>

<span data-ttu-id="3f577-109">Per configurare l'importazione personalizzata SFTP, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="3f577-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3f577-110">Hai il nome del file e la posizione (percorso) del file da importare sull'host SFTP.</span><span class="sxs-lookup"><span data-stu-id="3f577-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="3f577-111">C'è un file *model.json* che specifica [lo schema Common Data Model](/common-data-model/) per i dati da importare.</span><span class="sxs-lookup"><span data-stu-id="3f577-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="3f577-112">Questo file deve trovarsi nella stessa directory del file da importare.</span><span class="sxs-lookup"><span data-stu-id="3f577-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="3f577-113">Una connessione SFTP è già stata configurata da un amministratore *o* hai le autorizzazioni di [amministratore](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="3f577-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="3f577-114">Avrai bisogno delle credenziali dell'utente, dell'URL e del numero di porta per la posizione SFTP da cui desideri importare i dati.</span><span class="sxs-lookup"><span data-stu-id="3f577-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="3f577-115">Configurare l'importazione</span><span class="sxs-lookup"><span data-stu-id="3f577-115">Configure the import</span></span>

1. <span data-ttu-id="3f577-116">Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.</span><span class="sxs-lookup"><span data-stu-id="3f577-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="3f577-117">Nel **riquadro di importazione personalizzata SFTP**, seleziona **Arricchisci i miei dati** e quindi seleziona **Attività iniziali**.</span><span class="sxs-lookup"><span data-stu-id="3f577-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Riquadro Importazione personalizzata SFTP.":::

1. <span data-ttu-id="3f577-119">Seleziona una [connessione](connections.md) dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3f577-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="3f577-120">Contatta un amministratore se non è disponibile alcuna connessione.</span><span class="sxs-lookup"><span data-stu-id="3f577-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="3f577-121">Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione** e scegliendo **Importazione personalizzata con FTP sicuro** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3f577-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="3f577-122">Seleziona **Connettiti a Importazione personalizzata** per confermare la connessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="3f577-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="3f577-123">Seleziona **Avanti** e immetti **Percorso** e **Nome file** del file di dati che desideri importare.</span><span class="sxs-lookup"><span data-stu-id="3f577-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Screenshot durante l'inserimento della posizione dei dati.":::

1. <span data-ttu-id="3f577-125">Seleziona **Avanti** e fornisci un nome per l'arricchimento e un nome per l'entità di output.</span><span class="sxs-lookup"><span data-stu-id="3f577-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="3f577-126">Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.</span><span class="sxs-lookup"><span data-stu-id="3f577-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="3f577-127">Configurare la connessione per l'importazione personalizzata SFTP</span><span class="sxs-lookup"><span data-stu-id="3f577-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="3f577-128">Devi essere un amministratore per configurare le connessioni.</span><span class="sxs-lookup"><span data-stu-id="3f577-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="3f577-129">Seleziona **Aggiungi connessione** quando si configura un arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Importazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3f577-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="3f577-130">Immetti un nome per la connessione nella casella **nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="3f577-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="3f577-131">Immetti un nome utente, una password e un URL host validi per il server SFTP su cui risiedono i dati da importare.</span><span class="sxs-lookup"><span data-stu-id="3f577-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="3f577-132">Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="3f577-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="3f577-133">Seleziona **Verifica** per convalidare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="3f577-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="3f577-134">Una volta completata la verifica, puoi salvare la connessione selezionando **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3f577-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3f577-135">![Pagina di configurazione della connessione di Experian](media/enrichment-SFTP-connection.png "Pagina di configurazione della connessione di Experian")</span><span class="sxs-lookup"><span data-stu-id="3f577-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="3f577-136">Definire i mapping dei campi</span><span class="sxs-lookup"><span data-stu-id="3f577-136">Defining field mappings</span></span> 

<span data-ttu-id="3f577-137">La directory che contiene il file da importare nel server SFTP deve contenere anche un file *model.json*.</span><span class="sxs-lookup"><span data-stu-id="3f577-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="3f577-138">Questo file definisce lo schema da utilizzare per importare i dati.</span><span class="sxs-lookup"><span data-stu-id="3f577-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="3f577-139">Lo schema deve usare [Common Data Model](/common-data-model/) per specificare la mappatura del campo.</span><span class="sxs-lookup"><span data-stu-id="3f577-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="3f577-140">Un esempio semplice di un file model.json è simile a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3f577-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="3f577-141">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="3f577-141">Enrichment results</span></span>

<span data-ttu-id="3f577-142">Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="3f577-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3f577-143">Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3f577-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3f577-144">Il tempo di elaborazione dipenderà dalla dimensione dei dati da importare e dalla connessione al server SFTP.</span><span class="sxs-lookup"><span data-stu-id="3f577-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="3f577-145">Al termine del processo di arricchimento, puoi esaminare i dati di arricchimento personalizzati appena importati sotto **I miei arricchimenti**.</span><span class="sxs-lookup"><span data-stu-id="3f577-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="3f577-146">Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="3f577-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3f577-147">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="3f577-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3f577-148">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3f577-148">Next steps</span></span>

<span data-ttu-id="3f577-149">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="3f577-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3f577-150">Crea [segmenti](segments.md) e [misure](measures.md) e persino [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="3f577-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
