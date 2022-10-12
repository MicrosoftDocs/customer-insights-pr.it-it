---
title: Connessione ai dati in un Data Lake gestito di Microsoft Dataverse
description: Importa dati da un data lake Microsoft Dataverse gestito.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609800"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Connessione ai dati in un Data Lake gestito di Microsoft Dataverse

Gli utenti di Microsoft Dataverse possono connettersi rapidamente alle entità analitiche in un data lake gestito da Microsoft Dataverse. Solo un'origine dati di un ambiente può utilizzare contemporaneamente lo stesso data lake gestito di Dataverse.

> [!NOTE]
> Devi essere un amministratore nell'organizzazione Dataverse per procedere e visualizzare l'elenco delle entità disponibili nel lake gestito.

## <a name="prerequisites"></a>Prerequisiti

- I dati archiviati nei servizi online come Azure Data Lake Storage possono essere archiviati in una posizione diversa rispetto a quella in cui i dati vengono elaborati o archiviati in Dynamics 365 Customer Insights.Importando o connettendoti a dati archiviati nei servizi online, accetti che i dati possano essere trasferiti e archiviati con Dynamics 365 Customer Insights. [Altre informazioni sono disponibili nel Microsoft Trust Center.](https://www.microsoft.com/trust-center).

- Sono visibili solo entità Dataverse con il [rilevamento modifiche](/power-platform/admin/enable-change-tracking-control-data-synchronization) abilitato. Queste entità possono essere esportate in un data lake gestito da Dataverse e utilizzato in Customer Insights. Le tabelle predefinite di Dataverse hanno il rilevamento modifiche abilitato per impostazione predefinita. Devi attivare il rilevamento modifiche per le tabelle personalizzate. Per verificare se una tabella di Dataverse è abilitata per il rilevamento modifiche, vai a [Power Apps](https://make.powerapps.com) > **Dati** > **Tabelle**. Trova la tabella desiderata e selezionala. Vai a **Impostazioni** > **Opzioni avanzate** ed esamina l'impostazione **Rilevamento modifiche**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Connettersi a un data lake gestito Dataverse

1. Vai a **Dati** > **Origini dati**.

1. Seleziona **Aggiungi origine dati**.

1. Seleziona **Microsoft Dataverse**.

1. Immetti un **Nome** per l'origine dati e una **Descrizione** opzionale.

1. Fornisci l'**Indirizzo del server** per l'organizzazione Dataverse e seleziona **Accedi**.

1. Seleziona le tabelle che desideri inserire come entità in Customer Insights dall'elenco disponibile.

   > [!NOTE]
   > Se alcune tabelle sono già selezionate, potrebbero essere utilizzate da altre applicazioni Dynamics 365 (come Dynamics 365 Sales Insights o Customer Service Insights). Non è possibile modificare la selezione. Queste tabelle saranno disponibili come entità una volta creata l'origine dati.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Finestra di dialogo che mostra un elenco di entità nell'ambiente Dataverse.":::

1. Salva la tua selezione per iniziare a sincronizzare le tabelle selezionate da Dataverse. Troverai la connessione appena aggiunta nella pagina **Origine dati**. Verrà messo in coda per l'aggiornamento e visualizzerà il conteggio delle entità su 0 fino a quando tutte le tabelle selezionate non saranno sincronizzate.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Il caricamento dei dati può richiedere tempo. Al termine dell'aggiornamento, i dati inseriti possono essere esaminati nella pagina [**Entità**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Modificare l'origine dati di un data lake gestito Dataverse

Modifichi la selezione dell'entità solo dopo aver creato l'origine dati. Ad esempio, se sono state aggiunte ulteriori entità a Dataverse e vuoi importare anche quelle.
Per connettersi a un altro data lake Dataverse, [crea una nuova origine dati](#connect-to-a-dataverse-managed-lake).

1. Vai a **Dati** > **Origini dati**.

1. Accanto all'origine dati che desideri aggiornare, seleziona **Modifica**.

1. Seleziona le entità aggiuntive dall'elenco disponibile di entità.

1. Fai clic su **Salva** per applicare le modifiche e tornare alla pagina **Origine dati**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Motivi comuni per errori di inserimento o dati danneggiati

I seguenti controlli vengono eseguiti sui dati importati per esporre i record danneggiati:

- Il valore di un campo non corrisponde al tipo di dati della sua colonna.
- I campi contengono caratteri che fanno sì che le colonne non corrispondano allo schema previsto. Ad esempio: virgolette formattate in modo errato, virgolette senza caratteri di escape o caratteri di nuova riga.
- Se sono presenti colonne datetime/date/datetimeoffset, il loro formato deve essere specificato nel modello se non segue il formato ISO standard.

### <a name="schema-or-data-type-mismatch"></a>Mancata corrispondenza dello schema o del tipo di dati

Se i dati non sono conformi allo schema, i record vengono classificati come danneggiati. Correggere i dati di origine o lo schema e reinserire i dati.

### <a name="datetime-fields-in-the-wrong-format"></a>Formato errato dei campi datetime

I campi datetime nell'entità non sono nei formati ISO o en-US Il formato datetime predefinito in Customer Insights è il formato en-US. Tutti i campi datetime in un'entità devono essere nello stesso formato. Customer Insights supporta altri formati, a condizione che le annotazioni o i tratti vengano creati a livello di origine o di entità nel modello o nel file manifest.json. Ad esempio: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  In un manifest.json, il formato datetime può essere specificato a livello di entità o di attributo. A livello di entità, usa "exhibitsTraits" nell'entità in *.manifest.cdm.json per definire il formato datetime. A livello di attributo, usa "appliedTraits" nell'attributo in entityname.cdm.json.

**Manifest.json a livello di entità**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json a livello di entità**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
