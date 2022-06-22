---
title: Arricchimento con l'importazione personalizzata SFTP
description: Informazioni generali sull'arricchimento con l'importazione personalizzata SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953724"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Arricchimento di profili cliente con dati personalizzati (anteprima)

L'importazione personalizzata SFTP (Secure File Transfer Protocol) consente di importare dati che non devono essere sottoposti al processo di unificazione dei dati. È un modo flessibile, sicuro e facile di importare i dati. L'importazione personalizzata SFTP può essere utilizzata in combinazione con l'[esportazione SFTP](export-sftp.md) che consente di esportare i dati del profilo cliente necessari per l'arricchimento. I dati possono quindi essere elaborati e arricchiti e l'importazione personalizzata SFTP può essere utilizzata per riportare i dati arricchiti in Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prerequisiti

- Il nome del file e la posizione (percorso) del file da importare sull'host SFTP sono noti.

- È disponibile un file *model.json* che specifica lo schema Common Data Model per i dati da importare. Questo file deve trovarsi nella stessa directory del file da importare.

- Una [connessione](connections.md) SFTP è [configurata](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Esempio di schema di file

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurare la connessione per l'importazione personalizzata SFTP

Devi essere un [amministratore](permissions.md#admin) in Customer Insights e disporre delle credenziali utente, dell'URL e del numero di porta per la posizione SFTP da cui desideri importare i dati.

1. Seleziona **Aggiungi connessione** quando configuri un arricchimento o vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Importazione personalizzata.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Pagina della configurazione della connessione di Importazione personalizzata":::

1. Immettere un nome per la connessione.

1. Immetti un nome utente, una password e un URL host validi per il server SFTP su cui risiedono i dati da importare.

1. Rivedi e fornisci il tuo consenso per [Conformità e privacy dei dati](#data-privacy-and-compliance) selezionando **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione e quindi seleziona **Salva**.

### <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati usando Importazione personalizzata, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati su tua istruzione, ma devi garantire che i dati soddisfino qualsiasi obbligo di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

## <a name="configure-the-import"></a>Configurare l'importazione

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** sul riquadro **Importazione personalizzata con SFTP**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Riquadro Importazione personalizzata SFTP.":::

1. Esamina la panoramica e quindi seleziona **Avanti**.

1. Seleziona la connessione. Contatta un amministratore se uno non è disponibile.

1. Seleziona **Set di dati cliente** e scegli il profilo o il segmento che vuoi arricchire. L'entità *Cliente* arricchisce tutti i tuoi profili cliente se un segmento arricchisce solo i profili cliente contenuti in quel segmento.

1. Selezionare **Avanti**.

1. Immetti **Percorso** e **Nome file** del file di dati che desideri importare.

1. Selezionare **Avanti**.

1. Specifica un **Nome** per l'arricchimento e il **Nome entità di output**.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

1. Seleziona **Esegui** per avviare il processo di arricchimento o chiudere per tornare alla pagina **Arricchimenti**.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
