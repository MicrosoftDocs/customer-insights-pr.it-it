---
title: Attività iniziali con la funzionalità Informazioni dettagliate sull'interazione
description: Una panoramica delle risorse di assistenza per iniziare rapidamente l'utilizzo.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405363"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Attività iniziali con la funzionalità Informazioni dettagliate sull'interazione di Dynamics 365 Customer Insights (anteprima pubblica)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La funzionalità Informazioni dettagliate sull'interazione ti consente di conoscere e valutare il comportamento dei clienti sul tuo sito Web. Si integra con la funzionalità Audience Insight in modo da poter visualizzare analisi comportamentali in tempo reale complete insieme ai report sul profilo cliente. I collegamenti in questo articolo ti aiutano a configurare e impostare rapidamente il tuo ambiente.

## <a name="step-1-review-prerequisites"></a>Passaggio 1: verificare i prerequisiti

Innanzitutto, devi disporre di un account utente di Microsoft Azure Active Directory attivo. Quindi, leggi i seguenti articoli prima di configurare un'area di lavoro di informazioni dettagliate sulle interazioni.

- Leggi e accetta le [Condizioni d'uso](terms-of-service.md) con Microsoft.  
- Leggi l'articolo [Gestire i cookie e il consenso utente](user-consent-storage.md). Dopo aver esaminato questo articolo, valuta se è necessario aggiornare la notifica del consenso dell'utente. Se in precedenza non avevi cookie "non essenziali", probabilmente dovrai aggiornare i criteri del tuo sito.
- Rivedi il [glossario](glossary.md) per una rapida introduzione ai termini e ai concetti chiave.

## <a name="step-2-explore-engagement-insights"></a>Passaggio 2: esplora Informazioni dettagliate sull'interazione

La prima volta che visiti Informazioni dettagliate sull'interazione, puoi configurare le impostazioni, esaminare i criteri ed esplorare il prodotto.

1. Accedi al [portale della funzionalità Informazioni dettagliate sull'interazione](https://pi.dynamics.com) usando il tuo account utente di Microsoft Azure Active Directory. Può trattarsi del tuo account aziendale o dell'istituto di istruzione.

1. Seleziona la tua area e utilizza la casella di controllo per indicare se desideri acconsentire esplicitamente alla ricezione di aggiornamenti e offerte tramite e-mail.

1. Rivedi le **Condizioni d'uso di Informazioni dettagliate sull'interazione (anteprima)** e l'**Informativa sulla Privacy**, quindi seleziona **Esplora la demo** per accettarli.

1. Esplora il prodotto utilizzando una serie di dati di esempio.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Passaggio 3: configura un'area di lavoro e aggiungi codice al tuo sito Web

Nell'area di lavoro puoi visualizzare l'impegno degli utenti in tempo reale e archiviare e gestire i report. Aggiungi codice al tuo sito Web per iniziare a raccogliere *eventi*, i dati sull'impegno provenienti dagli utenti.

1. [Creare un'area di lavoro](create-workspace.md) e aggiungere membri.

1. [Aggiungi il codice al tuo sito Web](instrument-website.md) o all'[app mobile](developer-resources.md#capture-events-from-mobile-apps) per vedere l'attività degli utenti in arrivo nella tua area di lavoro.

1. Visualizza un [report in tempo reale](view-reports.md) che mostra gli utenti attivi per browser, dispositivo, sistema operativo, posizione e lingua. Puoi anche creare [report personalizzati](custom-reports.md) per creare le tue visualizzazioni.
    
## <a name="step-4-export-data-to-other-channels"></a>Passaggio 4: esporta i dati su altri canali

Puoi creare *eventi affinati* (una visualizzazione virtuale) dei dati di analisi Web. Quindi filtra ed esporta i dati in Azure Data Lake Storage. Puoi inserire i dati esportati come origine dati. Per ulteriori informazioni, vedi [Creare un collegamento tra Informazioni dettagliate sul gruppo di destinatari e Informazioni dettagliate sull'interazione](integrate-audience-insights-engagement-insights.md).

1. [Crea eventi affinati](refined-events.md) per l'esportazione.

1. [Esporta i dati](export-events.md) in Data Lake Storage.

1. Scopri come [eliminare ed esportare i dati degli eventi contenenti informazioni personali](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Passaggio 5: resta connesso

Apprezziamo la tua partecipazione attiva e prevediamo di prendere in considerazione tutti i feedback pertinenti durante lo sviluppo delle versioni future. Condividi il tuo feedback e segnala i problemi tramite uno di questi canali:
- [Community](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Inviare commenti](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Richiesta di supporto](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
