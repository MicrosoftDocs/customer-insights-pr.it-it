---
title: Ottimizzazione dei dati aziendali
description: Arricchisci e normalizza i dati aziendali con i modelli Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953954"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Arricchimento dei profili aziendali con dati aziendali ottimizzati

Usa i modelli Microsoft e i dati aziendali compilati per correggere, integrare e standardizzare i profili aziendali. Useremo il [formato Common Data Model](/common-data-model/schema/core/applicationcommon/account) per una migliore precisione e informazioni dettagliate.

Puoi anche [migliorare i dati aziendali sulle origini dati](data-sources-enrichment.md) per migliorare l'accuratezza della corrispondenza nel processo di unificazione dei dati.

Per le società pubbliche negli Stati Uniti sono disponibili informazioni come ricavi, titoli azionari, settore e altro ancora.  

## <a name="how-we-enhance-company-data"></a>Come ottimizziamo i dati aziendali

Il nostro modello prevede un processo in due fasi per l'ottimizzazione del profilo aziendale. Innanzitutto, normalizza il nome dell'azienda. Ad esempio, *Microsoft Corp* sarà corretto e standardizzato in *Microsoft Corporation*. Cerca di trovare una corrispondenza nei dati aziendali compilati da Microsoft. Se viene trovata una corrispondenza, arricchiamo il profilo aziendale con le informazioni dei nostri dati aziendali compilati, incluso il nome dell'azienda.

### <a name="example"></a>Esempio

Le informazioni aziendali potrebbero non seguire un formato standard e contenere errori di ortografia. Il modello cerca di risolvere questi problemi e creare informazioni coerenti.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Limiti

Il modello non:

- Conferma l'identità dell'azienda. Non verifichiamo se l'input è un'organizzazione esistente né che un'azienda utilizza l'output come nome standard.
- Copri nel complesso le aziende a livello globale. I dati aziendali compilati di Microsoft hanno una copertura globale, ma offrono la maggior parte della copertura in Australia, Canada, Regno Unito e Stati Uniti.
- Standardizza gli indirizzi aziendali a livello globale. Attualmente è supportata la standardizzazione degli indirizzi nei paesi o nelle aree geografiche seguenti: Australia, Canada, Francia, Germania, Italia, Giappone, Regno Unito e Stati Uniti.
- Garantisci l'accuratezza o l'aggiornamento dei dati. Poiché le informazioni aziendali cambiano spesso, non possiamo garantire che i dati aziendali ottimizzati forniti siano sempre esatti o aggiornati.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** sul riquadro **Dati aziendali ottimizzati**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Riquadro di arricchimento nell'hub di arricchimento per i dati aziendali.":::

1. Esamina la panoramica e quindi seleziona **Avanti**.

1. Seleziona **Set di dati cliente** e scegli il profilo o il segmento che vuoi arricchire. L'entità *Cliente* arricchisce tutti i tuoi profili cliente se un segmento arricchisce solo i profili cliente contenuti in quel segmento.

1. Seleziona il tipo di campi dei tuoi profili aziendali da usare per la corrispondenza con i dati aziendali compilati di Microsoft. Questa selezione influenzerà i campi di mapping a cui hai accesso nel passaggio successivo.

1. Selezionare **Avanti**.

1. Mappa i tuoi campi società ai dati società di Microsoft. Per una maggiore accuratezza di corrispondenza, aggiungi più campi.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Fase di mapping dei dati durante la configurazione di un miglioramento aziendale.":::

1. Seleziona **Avanti** per completare il mapping del campo.

1. Fornisci un **nome** per l'arricchimento e l' **entità di output**.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

1. Seleziona **Esegui** per avviare il processo di arricchimento o chiudere per tornare alla pagina **Arricchimenti**.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Scheda panoramica

Il riquadro **Panoramica modifiche clienti** mostra i dettagli sulla copertura dell'arricchimento

- **Società elaborate e modificate**: il numero di profili società che sono stati arricchiti.
- **Società elaborate e non modificate**: il numero di profili società che sono stati riconosciuti ma non modificati. In genere si verifica quando i dati di input sono validi e non possono essere migliorati dall'arricchimento.
- **Società non elaborate e non modificate**: il numero di profili società che non sono stati riconosciuti. Solitamente si verifica per dati di input non validi o non supportati dall'arricchimento.

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
