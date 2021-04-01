---
title: Home page di Audience Insights
description: Esplora l'app nella home page.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597240"
---
# <a name="create-a-new-environment"></a>Crea un nuovo ambiente

## <a name="create-a-trial-environment"></a>Crea un ambiente di valutazione

Puoi registrarti per una versione di valutazione nella [pagina di iscrizione alla versione di valutazione](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Le versioni di valutazione scadono dopo 30 giorni.

1. Scegli l'opzione **Iscriviti a una versione di prova gratuita** e seleziona **Iscriviti ora**.

1. Fornisci il tuo indirizzo e-mail di lavoro o della scuola, raccontaci qualcosa di te e seleziona **Avanti**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Finestra di dialogo per iscriversi a una versione di valutazione":::

1. Fornisci un **nome** per il tuo nuovo ambiente. 

1. Selezionare il tipo di versione di valutazione.

1. Scegli l'**area** per il tuo ambiente.

1. Facoltativamente, per gli amministratori di un'organizzazione Dynamics 365: seleziona **Impostazioni avanzate** e fornisci l'URL della tua organizzazione per utilizzare le funzionalità previsione come l'abbandono dei clienti.

1. Seleziona **Crea**. 

Dopo che l'ambiente è stato creato, vedrai l'ambiente **Demo** che ti consente di esplorare l'app con dati fittizi. Puoi modificare i dati di esempio con quelli del tuo settore. Seleziona l'icona **Impostazioni** nell'intestazione e seleziona **Impostazioni demo**. Inoltre, puoi cambiare il tema visivo. 

Puoi [passare all'ambiente](#switch-environments) creato durante il processo di registrazione per lavorare con i tuoi dati.

## <a name="create-a-new-production-or-sandbox-environment"></a>Crea un nuovo ambiente sandbox o di produzione

Nel tuo ambiente, seleziona il selettore **Ambienti** nell'intestazione dell'app e seleziona **Nuovo**.

Segui i passaggi come per [creare un ambiente di prova](#create-a-trial-environment). Per impostazione predefinita, i dati vengono archiviati nel data lake gestito di Customer Insights. Ottieni un'opzione aggiuntiva quando selezioni **Impostazioni avanzate** per archiviare i dati nel tuo Azure Data Lake. Fornisci il nome e la chiave dell'account per stabilire una connessione al tuo Azure Data Lake. 

> [!IMPORTANT]
> Salvando i dati in Azure Data Lake Storage, accetti che i dati vengano trasferiti e archiviati nella posizione geografica appropriata per tale account di archiviazione di Azure, che può essere diversa da quella in cui sono archiviati i dati in Dynamics 365 Customer Insights. [Altre informazioni nel Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Esplorare la home page

Puoi [accedere a Audience Insights da Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) con il seguente URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
La **home page** mostra una panoramica di segmenti, misure e dati di arricchimento (se configurati) dopo aver completato le fasi [mapping](map-entities.md), [corrispondenza](match-entities.md), e [unione](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Informazioni dettagliate nella home page](media/home-page-insights.png "Informazioni dettagliate nella home page")

Sotto **Segmenti recenti**, sono visualizzati gruppi di clienti in base ad attributi demografici, comportamentali o transazionali che hai definito. [La creazione di segmenti](segments.md) ti aiuta a raggruppare la tua base di clienti e ad indirizzare meglio le tue attività commerciali.

**Misure recenti** mostra i riquadri con [gli indicatori di prestazioni chiave](measures.md) che hai definito. Ad esempio, la probabilità media di abbandono di un cliente o la spesa media online per cliente.

La sezione **Arricchimenti recenti** elenca i risultati delle esecuzioni di arricchimento completate di recente. Gli [arricchimenti](enrichment-hub.md) aggiungono informazioni sulla base di clienti. Ad esempio, comprendendo gli interessi e i marchi con cui hanno affinità.

## <a name="switch-environments"></a>Cambiare ambiente

Seleziona il controllo **Ambiente** nell'angolo superiore destro della pagina per modificare gli ambienti.

> [!div class="mx-imgBorder"] 
> ![Cambia ambiente](media/home-page-environment-switcher.png "Cambia ambiente")

Gli amministratori possono creare e gestire [ambienti multipli](manage-environments.md). Il mantenimento di più di un ambiente può essere utile se, ad esempio, la tua organizzazione opera a livello internazionale e devi separare dati e informazioni dettagliate in diversi modi.

## <a name="next-step"></a>Passaggio successivo

Per vedere le tue informazioni dettagliate sulla home page, dovrai prima [aggiungere le origini dati](data-sources.md) e [unifica](data-unification.md) i tuoi dati per creare profili cliente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]