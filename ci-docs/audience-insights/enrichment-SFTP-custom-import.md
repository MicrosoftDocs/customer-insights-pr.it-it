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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Arricchimento di profili cliente con dati personalizzati (anteprima)

L'importazione personalizzata SFTP (Secure File Transfer Protocol) consente di importare dati che non devono essere sottoposti al processo di unificazione dei dati. È un modo flessibile, sicuro e facile di importare i dati. L'importazione personalizzata SFTP può essere utilizzata in combinazione con l'[esportazione SFTP](export-sftp.md) che consente di esportare i dati del profilo cliente necessari per l'arricchimento. I dati possono quindi essere elaborati e arricchiti e l'importazione personalizzata SFTP può essere utilizzata per reimportare i dati arricchiti nella funzionalità Audience Insight di Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prerequisiti

Per configurare l'importazione personalizzata SFTP, è necessario soddisfare i seguenti prerequisiti:

- Devi disporre delle credenziali utente (nome utente e password) per la posizione SFTP da cui verranno importati i dati.
- Devi disporre dell'URL e del numero di porta (solitamente 22) per l'host STFP.
- Disponi del nome di file e del percorso del file da importare nell'host SFTP.
- È presente un file *model.json* che specifica lo schema per i dati da importare. Questo file deve trovarsi nella stessa directory del file da importare.
- Devi disporre di autorizzazioni di [amministratore](permissions.md#administrator).

## <a name="configuration"></a>Configurazione

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. In **Importazione personalizzata SFTP**, seleziona **Arricchisci i miei dati**.

   > [!div class="mx-imgBorder"]
   > ![Riquadro Importazione personalizzata SFTP](media/SFTP_Custom_Import_tile.png "Riquadro Importazione personalizzata SFTP")

1. Seleziona **Inizia** e fornisci le credenziali e l'indirizzo per il server SFTP. Ad esempio, sftp://mysftpserver.com:22.

1. Immetti il nome del file che contiene i dati e il percorso del file sul server SFTP se non si trova nella cartella radice.

1. Conferma tutti gli input selezionando **Connetti a importazione personalizzata**.

   > [!div class="mx-imgBorder"]
   > ![Flyout della configurazione dell'importazione personalizzata SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Flyout della configurazione dell'importazione personalizzata SFTP")

## <a name="defining-field-mappings"></a>Definire i mapping dei campi 

La directory che contiene il file da importare nel server SFTP deve contenere anche un file *model.json*. Questo file definisce lo schema da utilizzare per importare i dati. Lo schema deve utilizzare [Common Data Model](/common-data-model/) per specificare il mapping dei campi. Un esempio semplice di un file model.json è simile a quanto segue:

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

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipenderà dalla dimensione dei dati da importare e dalla connessione al server SFTP.

Al termine del processo di arricchimento, puoi esaminare i dati di arricchimento personalizzati appena importati sotto **I miei arricchimenti**. Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Crea [segmenti](segments.md) e [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.




[!INCLUDE[footer-include](../includes/footer-banner.md)]