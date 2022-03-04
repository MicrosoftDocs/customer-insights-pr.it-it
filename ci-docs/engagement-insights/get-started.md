---
title: Attività iniziali con la funzionalità Informazioni dettagliate sull'interazione
description: Una panoramica delle risorse di assistenza per iniziare rapidamente l'utilizzo.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225603"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Attività iniziali con la funzionalità Informazioni dettagliate sull'interazione di Dynamics 365 Customer Insights (anteprima pubblica)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La funzionalità Informazioni dettagliate sull'interazione ti consente di conoscere e valutare il comportamento dei clienti sul tuo sito Web. Si integra con la funzionalità Audience Insight in modo da poter visualizzare analisi comportamentali in tempo reale complete insieme ai report sul profilo cliente. I collegamenti in questo articolo ti aiutano a configurare e impostare rapidamente il tuo ambiente.

## <a name="step-1-review-prerequisites"></a>Passaggio 1: verificare i prerequisiti

Innanzitutto, devi disporre di un account utente di Microsoft Azure Active Directory (AAD) attivo. Quindi, leggi i seguenti articoli prima di configurare un'area di lavoro di informazioni dettagliate sulle interazioni.

- Leggi e accetta le [Condizioni d'uso](terms-of-service.md) con Microsoft.  
- Leggi l'articolo [Gestire i cookie e il consenso utente](user-consent-storage.md). Successivamente, valuta se è necessario aggiornare la notifica del consenso dell'utente. Se in precedenza non avevi cookie "non essenziali", probabilmente dovrai aggiornare i criteri del tuo sito.
- Rivedi il [glossario](glossary.md) per una rapida introduzione ai termini e ai concetti chiave.

## <a name="step-2-explore-engagement-insights"></a>Passaggio 2: esplora Informazioni dettagliate sull'interazione

La prima volta che visiti le informazioni dettagliate sull'interazione, puoi configurare le impostazioni, esaminare i criteri ed esplorare la funzionalità.

1. Accedi al [portale della funzionalità relativa alle informazioni dettagliate sull'interazione](https://home.ci.ai.dynamics.com/app/engagement-insights) usando il tuo account utente (scolastico o aziendale) di Microsoft AAD.

1. Seleziona la tua area geografica e seleziona la casella se desideri acconsentire esplicitamente alla ricezione di aggiornamenti e offerte via e-mail.

1. Rivedere le **condizioni d'uso** e la **dichiarazione sulla privacy** di engagement insights (anteprima), e poi selezionare **Esplora la demo** per accettare queste impostazioni.

1. Esplora il prodotto utilizzando una serie di dati di esempio.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Passo 3: Impostare uno spazio di lavoro e creare rapporti

In un'area di lavoro è possibile visualizzare l'attività dell'utente in tempo reale e archiviare e gestire i report. Aggiungi codice al tuo sito Web per iniziare a raccogliere *eventi*, i dati sull'impegno provenienti dagli utenti.

1. [Creare un'area di lavoro](create-workspace.md) e aggiungere membri.

1. Aggiungi del codice al tuo [sito web](instrument-website.md) o alla tua [app mobile](developer-resources.md#capture-events-from-mobile-apps) per vedere l'attività degli utenti che arrivano nel tuo spazio di lavoro.

1. Visualizza un [report in tempo reale](view-reports.md) che mostra gli utenti attivi per browser, dispositivo, sistema operativo, posizione e lingua. Puoi anche creare [report personalizzati](custom-reports.md) per creare le tue visualizzazioni.

1. Crea [dimensioni](dimensions.md) per ordinare i visitatori in base ai nuovi utenti e a quelli che ritornano, [metriche](metrics.md) per aiutare a capire meglio il comportamento degli utenti e [segmenti](segments.md) per identificare sottoinsiemi di visitatori basati su caratteristiche o interazioni del sito.
    
## <a name="step-4-export-data-to-other-channels"></a>Passaggio 4: esporta i dati su altri canali

Puoi creare *eventi affinati* (una visualizzazione virtuale) dei dati di analisi Web. Quindi filtra ed esporta i dati in Azure Data Lake Storage. Puoi inserire i dati esportati come origine dati.

1. [Crea eventi affinati](refined-events.md) per l'esportazione.

1. [Esportare i dati](export-events.md) in Azure Data Lake Storage.

1. [Crea un collegamento tra informazioni dettagliate sul gruppo di destinatari e informazioni dettagliate sull'interazione](integrate-audience-insights-engagement-insights.md) per condividere i dati tra le due funzionalità.

1. [Riconoscere gli eventi web da utenti precedentemente autenticati](unknown-to-known.md) con la funzione **da sconosciuto a conosciuto** .

1. Scopri come [eliminare ed esportare i dati degli eventi contenenti informazioni personali](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Passo 5: Creare e gestire rapporti sul funnel

Un report del grafico a imbuto raccoglie informazioni sui passaggi che si verificano durante un percorso del cliente tramite il tuo sito Web o la tua app mobile. Oltre a creare rapporti di profilo out-of-box e rapporti personalizzati, è possibile creare un rapporto funnel per identificare i percorsi che i tuoi clienti prendono prima di fare un acquisto. 

1. [Creare un rapporto sul funnel](funnel-reports.md) per informare le decisioni e identificare le aree di ottimizzazione e di miglioramento dei processi.

1. Crea rapporti cross-channel funnel, una volta che hai strumentato la tua app mobile con l'engagement insights [Android SDK](get-started-android.md) o [iOS SDK](get-started-ios.md).

1. Utilizza gli [approfondimenti dell'imbuto](funnel-reports.md#funnel-insights) per ottenere una visione più profonda del comportamento dei clienti sui passi del tuo rapporto sull'imbuto.
 
## <a name="step-6-stay-connected"></a>Passaggio 6: resta connesso

Ti ringraziamo per la tua partecipazione e prendiamo in considerazione tutti i feedback pertinenti nello sviluppo di versioni future. Condividi il tuo feedback e segnala i problemi tramite uno di questi canali:
- [Community](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Inviare commenti](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Richiesta di supporto](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
