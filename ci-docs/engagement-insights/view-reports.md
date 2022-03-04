---
title: Visualizzare report di dati
description: Utilizza i report disponibili per vedere l'attività in tempo reale sul tuo sito.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 03b0b4bab0d5d9c2ae641c85aac8174ec1668d45
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229745"
---
# <a name="view-reports"></a>Visualizza report

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un report è una raccolta di visualizzazioni di dati, che utilizza i dati raccolti tramite l'SDK, che ti aiuta a misurare e comprendere il comportamento degli utenti. Le informazioni dettagliate sull'interazione di Dynamics 365 Customer Insights includono report predefiniti per progetti Web e mobile.  

## <a name="web-reports"></a>Report Web

Puoi accedere ai report Web in **Individua** nel riquadro di spostamento a sinistra.

:::image type="content" source="media/report-menu.png" alt-text="Spostamento che mostra l'elenco dei report disponibili.":::

### <a name="real-time-usage-report"></a>Report Utilizzo in tempo reale

Il report **Utilizzo in tempo reale** fornisce una panoramica dell'attività corrente sul tuo sito che si aggiorna automaticamente ogni minuto. Usa l'utilizzo in tempo reale per monitorare l'impatto di campagne di marketing, eventi stampa e altri scenari sul traffico del tuo sito.

### <a name="key-metrics-reports"></a>Report Metrica chiave

- **Visualizzazioni di pagina** elenca le visualizzazioni di pagina per le singole pagine insieme al numero di visualizzazioni di pagina totali nell'intervallo di tempo selezionato.

- **Visite** mostra le informazioni sul numero di visite e sulla durata della visita.

- **Visitatori** indica i visitatori univoci nuovi e di ritorno sul tuo sito.

### <a name="content-reports"></a>Report di contenuto

- **Collegamenti** mostra informazioni sul numero e sul tipo di clic.

- **Pagine di uscita** elenca i collegamenti su cui i visitatori hanno fatto clic per uscire dal tuo sito.

### <a name="traffic-sources-reports"></a>Report delle origini del traffico

- **Referrer** elenca i domini e gli URL che hanno indirizzato i visitatori al tuo sito.

- **Codici registrazione** fornisce i dettagli sui codici registrazione nei collegamenti che hanno indirizzato i visitatori al tuo sito.

### <a name="visitor-profiles-reports"></a>Report sui profili dei visitatori

- **Dispositivi** elenca i dispositivi fisici che sono stati utilizzati per accedere al tuo sito.

- **Sistema operativo e browser** fornisce informazioni dettagliate sui sistemi operativi e sui browser in esecuzione durante l'accesso al tuo sito.

- **Posizioni** mostra le informazioni sui visitatori per paese, area geografica e città.

- **Lingue** elenca le visualizzazioni di pagina in base alle lingue preferite del visitatore.

## <a name="mobile-reports"></a>Report per dispositivi mobili

I report per dispositivi mobili sono raggruppati per utilizzo in tempo reale, app e categorie di utenti. Puoi accedere ai report per dispositivi mobili in **Individua** nel riquadro di spostamento a sinistra.   

:::image type="content" source="media/mobile-reports.png" alt-text="Interfaccia utente delle informazioni dettagliate sull'interazione che mostra il rapporto sull'utilizzo in tempo reale in cui viene eseguito il rendering dei dati in grafici ed elenchi.":::   

### <a name="real-time-usage"></a>Utilizzo in tempo reale

**Utilizzo in tempo reale** fornisce una panoramica dell'attività corrente nella tua app mobile che si aggiorna automaticamente ogni minuto. Grazie all'utilizzo in tempo reale monitora il numero di utenti e sessioni attive in quel momento nella tua app e le visualizzazioni dello schermo superiore.

### <a name="app-reports"></a>Report sulle app

- **Visualizzazioni schermata** elenca le visualizzazioni delle schermate dei singoli schermi di un'app e il numero totale di visualizzazioni di schermate in un intervallo di tempo selezionato. Puoi visualizzare le visualizzazioni di schermate per nome dello schermo o per titolo dello schermo.

- **Sessioni** mostra le informazioni sul numero di sessioni e sulla durata della sessione.

- **Frequenza di ritorno** raggruppa i numeri di sessioni in base al numero di giorni trascorsi dall'ultima sessione.

- **Utenti** mostra gli utenti nuovi e di ritorno nella tua app mobile.

- **Eventi** elenca tutti gli eventi raccolti dalla tua app, più il numero totale per ogni evento.

### <a name="user-reports"></a>Report utente

- **Versioni app** elenca le versioni della tua app per dispositivi mobili utilizzate dalla tua base di utenti.

- **Dispositivi e versioni sistema operativo** fornisce informazioni dettagliate su quali dispositivi e sistemi operativi è in esecuzione la tua app per dispositivi mobili.

- **Posizioni** mostra le informazioni sugli utenti dell'app per paese, area geografica e città.

## <a name="filter-by-time-or-date-range"></a>Filtrare per intervallo di tempo o di data

È possibile selezionare il lasso di tempo o l'intervallo di date in un report web o mobile per concentrarsi su un valore o un periodo di tempo. 

- Per selezionare un lasso di tempo, nell'angolo in alto a destra della vista del rapporto, seleziona un valore dall'elenco a discesa del rapporto. Puoi anche scegliere un **intervallo di date fisso**. 

  :::image type="content" source="media/filter-by-time.png" alt-text="Filtra per intervallo di tempo o di data.":::   

- Per la maggior parte dei rapporti, seleziona un valore in un grafico o in un elenco per filtrare il rapporto.

> [!NOTE]
> La selezione dell'intervallo di tempo è disabilitata per un report sull'utilizzo in tempo reale. L'intervallo di tempo per un report sull'utilizzo in tempo reale è "adesso".


[!INCLUDE[footer-include](../includes/footer-banner.md)]
