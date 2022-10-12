---
title: Panoramica delle previsioni
description: Scenari e opzioni di previsione coperti dall'applicazione Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610195"
---
# <a name="predictions-overview"></a>Panoramica delle previsioni

Dynamics 365 Customer Insights viene fornito con una varietà di opzioni che sfruttano l'intelligenza artificiale e l'apprendimento automatico per prevedere i dati.

## <a name="out-of-box-models"></a>Modelli predefiniti

Il modo più semplice per iniziare con la previsione dei dati sono i modelli predefiniti, spesso indicati come modelli predefiniti. Richiedono solo determinati dati e una struttura per generare rapidamente informazioni dettagliate. Sono disponibili i seguenti modelli:

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (B2C)](#tab/b2c)

- [Valore durata cliente](predict-customer-lifetime-value.md): prevede ricavi potenziali di un cliente durante l'intera interazione con un'azienda.
- [Raccomandazione del prodotto](predict-product-recommendation.md): suggerisce set di raccomandazioni predittive sui prodotti in base al comportamento di acquisto e ai clienti con modelli di acquisto simili.
- [Abbandono dell'abbonamento](predict-subscription-churn.md): prevede se un cliente è a rischio perché non utilizza più i prodotti o i servizi in abbonamento della società.
- [Abbandono transazionale](predict-transactional-churn.md): prevede se un singolo cliente non acquisterà più i tuoi prodotti o servizi in un determinato intervallo di tempo.
- [Analisi valutazione](sentiment-analysis.md): analizza la valutazione del feedback dei clienti e identifica gli aspetti aziendali che vengono citati frequentemente.

# <a name="business-accounts-b-to-b"></a>[Account aziendali (B2B)](#tab/b2b)

- [Abbandono transazionale](predict-transactional-churn.md): prevede se un account cliente non acquisterà più i tuoi prodotti o servizi in un determinato intervallo di tempo.

---

> [!TIP]
> Ti consigliamo di aggiornare regolarmente i modelli predefiniti con dati aggiornati per assicurarti che forniscano informazioni precise al caso d'uso aziendale. I dati vengono aggiornati ad hoc quando il sistema acquisisce origini dati nuove o aggiornate. Tuttavia, in questo caso i modelli calcolano nuovamente il punteggio e continuano a utilizzare i dati di training esistenti.
>
> Configura una **pianificazione degli aggiornamenti** impostando la pianificazione del nuovo training del modello durante la configurazione. Vengono eseguiti nuovamente il training del modello e il calcolo del punteggio in base a questa pianificazione, che puoi modificare in qualsiasi momento.

## <a name="azure-machine-learning-integration"></a>Integrazione di Azure Machine Learning

Se un'organizzazione usa già scenari di apprendimento automatico basati su esperimenti di Azure Machine Learning, la funzionalità dei modelli personalizzati in Customer Insights aiuta a collegare i punti. Crea flussi di lavoro che ti aiutino a scegliere i dati da cui desideri generare informazioni dettagliate e mappare i risultati ai profili dei tuoi clienti unificati. Per ulteriori informazioni, vedi [Modelli personalizzati apprendimento automatico](custom-models.md).

## <a name="manage-existing-predictions"></a>Gestire previsioni esistenti

Vai alla pagina **Intelligence** > **Previsioni**. Nella scheda **Previsioni personali** visualizza le previsioni che hai creato, il tipo di previsione, il nome dell'entità di output, lo stato, l'ultima volta che previsione è stata modificata e l'ultima volta che i dati sono stati aggiornati. Puoi ordinare l'elenco delle previsioni per qualsiasi colonna.

Seleziona una previsione per visualizzare le azioni disponibili.

:::image type="content" source="media/predictions.png" alt-text="Pagina Previsioni personali.":::

- **Modifica** la previsione per modificarne le proprietà.
- [**Aggiorna**](#refresh-a-prediction) la previsione per includere i dati più recenti.
- **Visualizza** i dettagli della previsione.
- [**Report usabilità dati di input**](#view-the-input-data-usability-report) per visualizzare errori, avvisi e raccomandazioni.
- **Elimina** la previsione.

### <a name="refresh-a-prediction"></a>Aggiornare una previsione

Le previsioni possono essere aggiornate in base a una pianificazione automatica o manualmente su richiesta. Per aggiornare manualmente tutte le previsioni, seleziona **Aggiorna tutto**. Per aggiornare manualmente una previsione, selezionala e scegli **Aggiorna**. Per [pianificare un aggiornamento automatico](schedule-refresh.md), vai ad **Amministratore** > **Sistema** > **Pianifica**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Visualizza il report sull'usabilità dei dati di input

Il report sull'usabilità dei dati di input fornisce una visualizzazione consolidata degli errori e degli avvisi che potrebbero essere generati dalle previsioni predefinite. Fornisce inoltre consigli su come migliorare le prestazioni del modello.

Il report è disponibile dopo che un modello ha completato il processo di addestramento. Viene creato separatamente per ogni modello, indipendentemente dal fatto che il training sia stato completato correttamente o meno.

Nella scheda **Previsioni personali** seleziona la previsione e scegli **Report usabilità dati di input**. Oppure, dalla visualizzazione dei dettagli di previsione, seleziona **Report usabilità dati di input**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Esempio di un report sull'usabilità dei dati di input che mostra una tabella con errori, avvisi ed elementi consigliati.":::

Il report include:

- **Nome:** nome descrittivo dell'errore, dell'avviso o dell'elemento consigliato.
- **Passaggio:** fase del modello, treno o punteggio, a cui si riferiscono le informazioni.
- **Stato:** gravità delle informazioni (errore, avviso, elemento consigliato).
- **Nome colonna:** colonna in un'entità che deve essere modificata per migliorare le prestazioni del modello.
- **Nome entità:** nome dell'entità che deve essere modificata per migliorare le prestazioni del modello.
- **Dettagli:** dettagli dell'errore, dell'avviso o dell'elemento consigliato.

[!INCLUDE [footer-include](includes/footer-banner.md)]
