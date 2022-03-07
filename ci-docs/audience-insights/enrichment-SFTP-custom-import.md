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
ms.openlocfilehash: fa1d4ffd9f77e128b5d804e4562e964561f4684f
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618687"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Arricchimento di profili cliente con dati personalizzati (anteprima)

L'importazione personalizzata SFTP (Secure File Transfer Protocol) consente di importare dati che non devono essere sottoposti al processo di unificazione dei dati. È un modo flessibile, sicuro e facile di importare i dati. L'importazione personalizzata SFTP può essere utilizzata in combinazione con l'[esportazione SFTP](export-sftp.md) che consente di esportare i dati del profilo cliente necessari per l'arricchimento. I dati possono quindi essere elaborati e arricchiti e l'importazione personalizzata SFTP può essere utilizzata per riportare i dati arricchiti alla capacità di approfondimento dei destinatari di Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prerequisiti

Per configurare l'importazione personalizzata SFTP, è necessario soddisfare i seguenti prerequisiti:

- Hai il nome del file e la posizione (percorso) del file da importare sull'host SFTP.
- C'è un file *model.json* che specifica [lo schema Common Data Model](/common-data-model/) per i dati da importare. Questo file deve trovarsi nella stessa directory del file da importare.
- Una connessione SFTP è già stata configurata da un amministratore *o* hai le autorizzazioni di [amministratore](permissions.md#administrator). Avrai bisogno delle credenziali dell'utente, dell'URL e del numero di porta per la posizione SFTP da cui desideri importare i dati.


## <a name="configure-the-import"></a>Configurare l'importazione

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Nel **riquadro di importazione personalizzata SFTP**, seleziona **Arricchisci i miei dati** e quindi seleziona **Attività iniziali**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Riquadro Importazione personalizzata SFTP.":::

1. Seleziona una [connessione](connections.md) dall'elenco a discesa. Contatta un amministratore se non è disponibile alcuna connessione. Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione** e scegliendo **Importazione personalizzata con FTP sicuro** dall'elenco a discesa.

1. Seleziona **Connettiti a Importazione personalizzata** per confermare la connessione selezionata.

1.  Seleziona **Avanti** e immetti **Percorso** e **Nome file** del file di dati che desideri importare.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Screenshot durante l'inserimento della posizione dei dati.":::

1. Selezionate **Avanti** e scegliete il set di dati del cliente. Questo può essere o tutti i profili dei clienti o un segmento.

1. Seleziona **Avanti** e fornisci un nome per l'arricchimento e un nome per l'entità di output. 

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurare la connessione per l'importazione personalizzata SFTP 

Devi essere un amministratore per configurare le connessioni. Seleziona **Aggiungi connessione** quando si configura un arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Importazione personalizzata.

1. Immetti un nome per la connessione nella casella **nome visualizzato**.

1. Immetti un nome utente, una password e un URL host validi per il server SFTP su cui risiedono i dati da importare.

1. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione.

1. Una volta completata la verifica, puoi salvare la connessione selezionando **Salva**.

   > [!div class="mx-imgBorder"]
   > ![Pagina di configurazione della connessione di Experian.](media/enrichment-SFTP-connection.png "Pagina di configurazione della connessione di Experian")


## <a name="defining-field-mappings"></a>Definire i mapping dei campi 

La directory che contiene il file da importare nel server SFTP deve contenere anche un file *model.json*. Questo file definisce lo schema da utilizzare per importare i dati. Lo schema deve usare [Common Data Model](/common-data-model/) per specificare la mappatura del campo. Un esempio semplice di un file model.json è simile a quanto segue:

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

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
