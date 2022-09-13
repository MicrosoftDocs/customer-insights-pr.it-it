---
title: Inserimento dati in tempo reale (anteprima)
description: Informazioni generali sulle funzionalità in tempo reale in Customer Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: dd433b57e8695891a08d6f7fdb8c87befd2e1cfa
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396066"
---
# <a name="real-time-data-ingestion-preview"></a>Inserimento dati in tempo reale (anteprima)

La funzionalità quasi in tempo reale consente di visualizzare, in pochi secondi, le interazioni più recenti che i tuoi clienti hanno effettuato con i tuoi prodotti o servizi.

Gli [aggiornamenti pianificati](schedule-refresh.md) includono un gran numero di record e diverse operazioni complesse. Innanzitutto, i dati vengono estratti dall'origine dati. Successivamente, i dati vengono unificati e quindi arricchiti con ulteriori informazioni. Ogni esecuzione di questo processo può richiedere da minuti a ore.

La funzionalità in tempo reale fornisce dei dati immediatamente per il consumo, fino a quando il successivo aggiornamento pianificato non estrae questi dati dall'origine dati.

Gli aggiornamenti in tempo reale hanno un tempo di scadenza dopo il quale non sovrascrivono più il valore dall'origine dati:

- Gli aggiornamenti del profilo verranno conservati per quattro ore
- Gli impegni verranno conservati per 30 giorni

Questi valori sono parametri di chiamata API che puoi modificare. Mirano a garantire che i dati di origine rimangano l'origine reale. Se desideri includere più a lungo aggiornamenti in tempo reale, devi aggiungerli a un'origine dati di modo che vengano estratti durante l'aggiornamento pianificato successivo.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Aggiornamento in tempo reale dei campi del profilo cliente unificato

I profili aggiornati verranno visualizzati nella visualizzazione della scheda cliente o in qualsiasi altra visualizzazione nel giro di pochi secondi.

Poiché le operazioni in tempo reale avvengono dopo che è avvenuta l'unificazione dei dati, si applicano solo ai profili cliente unificati. Di conseguenza, le modifiche al profilo in tempo reale non aggiorneranno misure, appartenenza al segmento o arricchimenti.

### <a name="limitations"></a>Limitazioni

- I profili cliente possono essere aggiornati, ma non creati o eliminati.
- L'esportazione di aggiornamenti in tempo reale su sistemi esterni, ad esempio Power BI, non è possibile al momento.

## <a name="real-time-creation-of-activities"></a>Creazione di impegni in tempo reale

L'API in tempo reale ti consente di pubblicare un nuovo impegno dal sistema di origine (un singolo record di origine) in un profilo cliente unificato. Il nuovo impegno sarà disponibile come impegno unificato nella sequenza temporale del profilo cliente unificato entro pochi secondi. Puoi visualizzare la sequenza temporale nella visualizzazione della scheda cliente o in qualsiasi altra integrazione della sequenza temporale configurata.

> [!NOTE]
>
> - Gli impegni sono immutabili. Non cambiano una volta creati.
> - Attualmente, i segmenti e le misure non verranno aggiornati in base al nuovo impegno.
> - Gli impegni aggiunti solo tramite l'API in tempo reale non fanno parte delle esportazioni e non verranno visualizzati in PowerBI.

Esistono due modi per connettersi all'API in tempo reale:

- [indirettamente](#connect-via-the-dynamics-365-customer-insights-connector), tramite il [connettore Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [direttamente](#connect-directly-to-the-real-time-api), con il codice

I seguenti prerequisiti si applicano a entrambi:

- Un ambiente di Customer Insights
- Profili cliente unificati
- Impegni configurati ed eseguiti
- Autorizzazioni come contributore o amministratore per autenticare il tuo account

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Connettersi tramite il connettore Dynamics 365 Customer Insights

L'API in tempo reale può inserire dati da un connettore Power Platform dedicato, il [connettore di Dynamics 365 Customer Insights](/connectors/customerinsights/), senza la necessità di scrivere e distribuire alcun codice.    
Il connettore può eseguire le stesse azioni in tempo reale dell'API. È necessaria una licenza valida per i connettori premium. Per altre informazioni, vedi [Domande frequenti sulle licenze di Power Apps e Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps e/o Power Automate](/connectors/)
- [App per la logica](/azure/connectors/apis-list) di Azure

Per dettagli sulla creazione di flussi, vedi la [documentazione di Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Connettersi direttamente all'API in tempo reale

Puoi utilizzare le funzionalità in tempo reale creando una pipeline e connettendoti direttamente all'API in tempo reale.    
Puoi pubblicare un impegno nel formato del tuo sistema di origine o nel formato UnifiedActivity. Ottieni il formato effettuando una chiamata API a /api/instances/{instanceId}/manage/entities/UnifiedActivity.

I dettagli di questa API, inclusi parametri e risposte, sono disponibili nella sezione **EntityData** del [Riferimento API di Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Per ulteriori informazioni, vedi [Utilizzare le API di Customer Insights](apis.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
