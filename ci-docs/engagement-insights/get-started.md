---
title: Attività iniziali con la funzionalità Informazioni dettagliate sull'interazione
description: Una panoramica delle risorse di assistenza per iniziare rapidamente l'utilizzo.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494599"
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

1. Rivedi le **condizioni per l'utilizzo delle informazioni dettagliate sull'interazione (anteprima)** e l'**Informativa sulla privacy**, quindi seleziona **Esplora la demo** per accettare queste impostazioni.

1. Esplora il prodotto utilizzando una serie di dati di esempio.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Passaggio 3: configura un'area di lavoro e aggiungi codice al tuo sito Web

In un'area di lavoro è possibile visualizzare l'attività dell'utente in tempo reale e archiviare e gestire i report. Aggiungi codice al tuo sito Web per iniziare a raccogliere *eventi*, i dati sull'impegno provenienti dagli utenti.

1. [Creare un'area di lavoro](create-workspace.md) e aggiungere membri.

1. [Aggiungi il codice al tuo sito Web](instrument-website.md) o all'[app mobile](developer-resources.md#capture-events-from-mobile-apps) per vedere l'attività degli utenti in arrivo nella tua area di lavoro.

1. Visualizza un [report in tempo reale](view-reports.md) che mostra gli utenti attivi per browser, dispositivo, sistema operativo, posizione e lingua. Puoi anche creare [report personalizzati](custom-reports.md) per creare le tue visualizzazioni.
    
## <a name="step-4-export-data-to-other-channels"></a>Passaggio 4: esporta i dati su altri canali

Puoi creare *eventi affinati* (una visualizzazione virtuale) dei dati di analisi Web. Quindi filtra ed esporta i dati in Azure Data Lake Storage. Puoi inserire i dati esportati come origine dati. Per ulteriori informazioni, vedi [Creare un collegamento tra Informazioni dettagliate sul gruppo di destinatari e Informazioni dettagliate sull'interazione](integrate-audience-insights-engagement-insights.md).

1. [Crea eventi affinati](refined-events.md) per l'esportazione.

1. [Esporta i dati](export-events.md) in Data Lake Storage.

1. [Crea un collegamento tra informazioni dettagliate sul gruppo di destinatari e informazioni dettagliate sull'interazione](integrate-audience-insights-engagement-insights.md) per condividere i dati tra le due funzionalità.

1. Scopri come [eliminare ed esportare i dati degli eventi contenenti informazioni personali](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Passaggio 5: resta connesso

Ti ringraziamo per la tua partecipazione e prendiamo in considerazione tutti i feedback pertinenti nello sviluppo di versioni future. Condividi il tuo feedback e segnala i problemi tramite uno di questi canali:
- [Community](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Inviare commenti](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Richiesta di supporto](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
