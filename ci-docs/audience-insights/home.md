---
title: Home page di Audience Insights
description: Esplora l'app nella home page.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406122"
---
# <a name="create-a-new-environment"></a>Crea un nuovo ambiente

## <a name="create-a-trial-environment"></a>Crea un ambiente di valutazione

Puoi registrarti per una versione di valutazione nella [pagina di iscrizione alla versione di valutazione](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Le versioni di valutazione scadono dopo 30 giorni.

1. Scegli l'opzione **Iscriviti a una versione di prova gratuita** e seleziona **Iscriviti ora**.

1. Fornisci il tuo indirizzo e-mail di lavoro o della scuola, raccontaci qualcosa di te e seleziona **Avanti**.

1. Fornisci un **nome** per il tuo nuovo ambiente. 

1. Selezionare il tipo di versione di valutazione.

1. Scegli l'**area** per il tuo ambiente.

1. Facoltativamente, per gli amministratori di un'organizzazione Dynamics 365: seleziona **Impostazioni avanzate** e fornisci l'URL della tua organizzazione per utilizzare le funzionalità previsione come l'abbandono dei clienti.

1. Seleziona **Crea**. 

Dopo che l'ambiente è stato creato, vedrai l'ambiente **Demo** che ti consente di esplorare l'app con dati fittizi. Puoi modificare i dati di esempio con quelli del tuo settore. Seleziona l'icona **Impostazioni** nell'intestazione e seleziona **Impostazioni demo**. Inoltre, puoi cambiare il tema visivo. 

Puoi [passare all'ambiente](#change-between-environments) creato durante il processo di registrazione per lavorare con i tuoi dati.

## <a name="create-a-new-production-or-sandbox-environment"></a>Crea un nuovo ambiente sandbox o di produzione

Nel tuo ambiente, seleziona l'icona **Impostazioni** nell'intestazione e seleziona **Nuovo ambiente**.

Segui i passaggi come per [creare un ambiente di prova](#create-a-trial-environment). Ottieni un'opzione aggiuntiva quando selezioni **Impostazioni avanzate** per archiviare i dati nel tuo Azure Data Lake. Fornisci il nome e la chiave dell'account per stabilire una connessione al tuo Azure Data Lake. Per impostazione predefinita, i dati vengono archiviati nel data lake gestito di Customer Insights.

> [!IMPORTANT]
> Salvando i dati in Azure Data Lake Storage, accetti che i dati vengano trasferiti e archiviati nella posizione geografica appropriata per tale account di archiviazione di Azure, che può essere diversa da quella in cui sono archiviati i dati in Dynamics 365 Customer Insights. [Altre informazioni nel Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Esplorare la home page

Puoi [accedere all'ambiente Customer Insights](https://home.ci.ai.dynamics.com/) mediante l'URL [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
La **home page** mostra una panoramica della base di clienti e delle metriche chiave per monitorare l'integrità dell'azienda.

> [!div class="mx-imgBorder"] 
> ![Informazioni dettagliate nella home page](media/home-page-insights.png "Informazioni dettagliate nella home page")

Sotto **Segmenti recenti**, sono visualizzati gruppi di clienti in base ad attributi demografici, comportamentali o transazionali che hai definito. [Creazione di segmenti](segments.md) ti aiuta a indirizzare meglio le tue attività aziendali.

**Misure recenti** mostra riquadri con [misure](measures.md). Le misure sono indicatori di prestazioni chiave (KPI) che hai definito. Ad esempio, la probabilità media di abbandono dei clienti o la spesa media online per cliente.

La sezione **Arricchimenti recenti** elenca i risultati delle esecuzioni di arricchimento completate di recente. Gli arricchimenti aggiungono informazioni sulla base di clienti. Ad esempio, comprendendo gli interessi e i marchi con cui hanno affinità. Queste informazioni possono essere sbloccate usando le funzionalità di [arricchimento](enrichment-microsoft-graph.md), dopo aver completato le fasi di [mapping](map-entities.md), [corrispondenza](match-entities.md) e [unione](merge-entities.md).

## <a name="change-between-environments"></a>Passare da un ambiente all'altro

Dopo aver configurato le [origini dati](data-sources.md), è consigliabile passare da un ambiente demo a un ambiente live. L'utilizzo dell'ambiente di produzione ti consente di utilizzare i dati cliente. Seleziona il controllo **Ambiente** nell'angolo superiore destro della pagina per modificare gli ambienti.

> [!div class="mx-imgBorder"] 
> ![Cambia ambiente](media/home-page-environment-switcher.png "Cambia ambiente")

Gli amministratori possono creare e gestire [ambienti multipli](manage-environments.md). Il mantenimento di più di un ambiente può essere utile se, ad esempio, la tua organizzazione opera a livello internazionale e devi separare dati e informazioni dettagliate in diversi modi.

## <a name="next-step"></a>Passaggio successivo

Per vedere le tue informazioni dettagliate sulla home page, dovrai prima [aggiungere le origini dati](data-sources.md) e [unifica](data-unification.md) i tuoi dati per creare profili cliente.
