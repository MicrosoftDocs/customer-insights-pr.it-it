---
title: Ottimizzazione dei dati aziendali
description: Arricchisci e normalizza i dati aziendali con i modelli Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 693e2f410a77cbf2e87ff0132ce963aab7e8e3e4
ms.sourcegitcommit: 4c9db6c124d7244e7e8bb2f8bfdc697523781c31
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2022
ms.locfileid: "8010914"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Arricchimento dei profili aziendali con dati aziendali ottimizzati

Usa i modelli Microsoft e i dati aziendali compilati per correggere, integrare e standardizzare i profili aziendali. Useremo il [formato Common Data Model](/common-data-model/schema/core/applicationcommon/account) per una migliore precisione e informazioni dettagliate.

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

Esistono alcune limitazioni con i dati ottimizzati. Gli elementi nell'elenco di seguito non sono supportati dal modello.

1.  Conferma l'identità dell'azienda. Non verifichiamo se l'input è un'organizzazione esistente né che un'azienda utilizza l'output come nome standard.
2.  Copri nel complesso le aziende a livello globale. I dati aziendali compilati di Microsoft hanno una copertura globale, ma offrono la maggior parte della copertura in Australia, Canada, Regno Unito e Stati Uniti.
3.  Standardizza gli indirizzi aziendali a livello globale. Attualmente è supportata la standardizzazione degli indirizzi nei paesi o nelle aree geografiche seguenti: Australia, Canada, Francia, Germania, Italia, Giappone, Regno Unito e Stati Uniti.
4.  Garantisci l'accuratezza o l'aggiornamento dei dati. Poiché le informazioni aziendali cambiano spesso, non possiamo garantire che i dati aziendali ottimizzati forniti siano sempre esatti o aggiornati.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento**.

1. Seleziona **Arricchisci i miei dati** sul riquadro **Dati aziendali ottimizzati**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Riquadro di arricchimento nell'hub di arricchimento per i dati aziendali.":::

1. Seleziona il **set di dati del cliente** e scegli l'entità contenente gli indirizzi che vuoi arricchire. Puoi selezionare l'entità *Cliente* per arricchire gli indirizzi in tutti i profili dei clienti o selezionare un'entità segmento per arricchire gli indirizzi solo nei profili dei clienti contenuti in quel segmento.

1. Seleziona il tipo di campi dei tuoi profili aziendali da usare per la corrispondenza con i dati aziendali compilati di Microsoft. Questa selezione influenzerà i campi di mapping a cui hai accesso nel passaggio successivo.

1.  Mappa i campi aziendali dalla tua entità cliente unificata. Maggiore è il numero di identificatori chiave e campi mappati, maggiore è la probabilità di ottenere corrispondenze migliori.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Fase di mapping dei dati durante la configurazione di un miglioramento aziendale.":::

1. Seleziona **Avanti** per completare il mapping del campo.

1. Fornisci un nome per l'arricchimento e l'entità di output.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipende dalle dimensioni dei dati del cliente.

Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**. Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi vedere un esempio dei dati arricchiti nel riquadro **Anteprima clienti arricchita**. Seleziona **Visualizza altro** e seleziona la scheda **Dati** per accedere a una visualizzazione dettagliata di ciascun profilo arricchito.

### <a name="overview-card"></a>Scheda panoramica

La scheda panoramica mostra i dettagli sulla copertura dell'arricchimento. 

* **Società elaborate e modificate**: il numero di profili società che sono stati arricchiti.

* **Società elaborate e non modificate**: il numero di profili società che sono stati riconosciuti ma non modificati. In genere si verifica quando i dati di input sono validi e non possono essere migliorati dall'arricchimento.

* **Società non elaborate e non modificate**: il numero di profili società che sono stati riconosciuti ma non riconosciuti. Solitamente si verifica per dati di input non validi o non supportati dall'arricchimento.

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
