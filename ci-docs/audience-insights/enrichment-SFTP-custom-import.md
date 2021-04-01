---
title: Arricchimento con l'importazione personalizzata SFTP
description: Informazioni generali sull'arricchimento con l'importazione personalizzata SFTP.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595860"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="2444a-103">Arricchimento di profili cliente con dati personalizzati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="2444a-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="2444a-104">L'importazione personalizzata SFTP (Secure File Transfer Protocol) consente di importare dati che non devono essere sottoposti al processo di unificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="2444a-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="2444a-105">È un modo flessibile, sicuro e facile di importare i dati.</span><span class="sxs-lookup"><span data-stu-id="2444a-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="2444a-106">L'importazione personalizzata SFTP può essere utilizzata in combinazione con l'[esportazione SFTP](export-sftp.md) che consente di esportare i dati del profilo cliente necessari per l'arricchimento.</span><span class="sxs-lookup"><span data-stu-id="2444a-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="2444a-107">I dati possono quindi essere elaborati e arricchiti e l'importazione personalizzata SFTP può essere utilizzata per reimportare i dati arricchiti nella funzionalità Audience Insight di Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2444a-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2444a-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2444a-108">Prerequisites</span></span>

<span data-ttu-id="2444a-109">Per configurare l'importazione personalizzata SFTP, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="2444a-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2444a-110">Devi disporre delle credenziali utente (nome utente e password) per la posizione SFTP da cui verranno importati i dati.</span><span class="sxs-lookup"><span data-stu-id="2444a-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="2444a-111">Devi disporre dell'URL e del numero di porta (solitamente 22) per l'host STFP.</span><span class="sxs-lookup"><span data-stu-id="2444a-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="2444a-112">Disponi del nome di file e del percorso del file da importare nell'host SFTP.</span><span class="sxs-lookup"><span data-stu-id="2444a-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="2444a-113">È presente un file *model.json* che specifica lo schema per i dati da importare.</span><span class="sxs-lookup"><span data-stu-id="2444a-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="2444a-114">Questo file deve trovarsi nella stessa directory del file da importare.</span><span class="sxs-lookup"><span data-stu-id="2444a-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="2444a-115">Devi disporre di autorizzazioni di [amministratore](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="2444a-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="2444a-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2444a-116">Configuration</span></span>

1. <span data-ttu-id="2444a-117">Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.</span><span class="sxs-lookup"><span data-stu-id="2444a-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="2444a-118">In **Importazione personalizzata SFTP**, seleziona **Arricchisci i miei dati**.</span><span class="sxs-lookup"><span data-stu-id="2444a-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2444a-119">![Riquadro Importazione personalizzata SFTP](media/SFTP_Custom_Import_tile.png "Riquadro Importazione personalizzata SFTP")</span><span class="sxs-lookup"><span data-stu-id="2444a-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="2444a-120">Seleziona **Inizia** e fornisci le credenziali e l'indirizzo per il server SFTP.</span><span class="sxs-lookup"><span data-stu-id="2444a-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="2444a-121">Ad esempio, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="2444a-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="2444a-122">Immetti il nome del file che contiene i dati e il percorso del file sul server SFTP se non si trova nella cartella radice.</span><span class="sxs-lookup"><span data-stu-id="2444a-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="2444a-123">Conferma tutti gli input selezionando **Connetti a importazione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="2444a-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2444a-124">![Flyout della configurazione dell'importazione personalizzata SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Flyout della configurazione dell'importazione personalizzata SFTP")</span><span class="sxs-lookup"><span data-stu-id="2444a-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="2444a-125">Definire i mapping dei campi</span><span class="sxs-lookup"><span data-stu-id="2444a-125">Defining field mappings</span></span> 

<span data-ttu-id="2444a-126">La directory che contiene il file da importare nel server SFTP deve contenere anche un file *model.json*.</span><span class="sxs-lookup"><span data-stu-id="2444a-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="2444a-127">Questo file definisce lo schema da utilizzare per importare i dati.</span><span class="sxs-lookup"><span data-stu-id="2444a-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="2444a-128">Lo schema deve utilizzare [Common Data Model](/common-data-model/) per specificare il mapping dei campi.</span><span class="sxs-lookup"><span data-stu-id="2444a-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="2444a-129">Un esempio semplice di un file model.json è simile a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2444a-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="2444a-130">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="2444a-130">Enrichment results</span></span>

<span data-ttu-id="2444a-131">Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="2444a-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2444a-132">Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2444a-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2444a-133">Il tempo di elaborazione dipenderà dalla dimensione dei dati da importare e dalla connessione al server SFTP.</span><span class="sxs-lookup"><span data-stu-id="2444a-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="2444a-134">Al termine del processo di arricchimento, puoi esaminare i dati di arricchimento personalizzati appena importati sotto **I miei arricchimenti**.</span><span class="sxs-lookup"><span data-stu-id="2444a-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="2444a-135">Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="2444a-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2444a-136">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="2444a-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2444a-137">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2444a-137">Next steps</span></span>

<span data-ttu-id="2444a-138">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="2444a-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2444a-139">Crea [segmenti](segments.md) e [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="2444a-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]