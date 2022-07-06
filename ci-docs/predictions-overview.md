---
title: Panoramica delle previsioni
description: Scenari e opzioni di previsione coperti dall'applicazione Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: a87af80fa713a1ac70493345c0c920e416692b0f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081696"
---
# <a name="predictions-overview"></a>Panoramica delle previsioni

Dynamics 365 Customer Insights viene fornito con una varietà di opzioni che sfruttano l'intelligenza artificiale e l'apprendimento automatico per prevedere i dati. 

## <a name="out-of-box-models"></a>Modelli predefiniti

Il modo più semplice per iniziare con la previsione dei dati sono i modelli predefiniti, spesso indicati come modelli predefiniti. Richiedono solo determinati dati e una struttura per generare rapidamente informazioni dettagliate. Attualmente sono disponibili i seguenti modelli: 

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

- [Valore durata cliente](predict-customer-lifetime-value.md): prevede ricavi potenziali di un cliente durante l'intera interazione con un'azienda.
- [Raccomandazione del prodotto](predict-product-recommendation.md): suggerisce set di raccomandazioni predittive sui prodotti in base al comportamento di acquisto e ai clienti con modelli di acquisto simili.
- [Abbandono dell'abbonamento](predict-subscription-churn.md): prevede se un cliente è a rischio perché non utilizza più i prodotti o i servizi in abbonamento della società.
- [Abbandono transazionale](predict-transactional-churn.md): prevede se un cliente non acquisterà più i tuoi prodotti o servizi in un determinato intervallo di tempo.
- [Analisi valutazione](sentiment-analysis.md): analizza la valutazione del feedback dei clienti e identifica gli aspetti aziendali che vengono citati frequentemente.

# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

- [Abbandono transazionale](predict-transactional-churn.md): prevede se un cliente non acquisterà più i tuoi prodotti o servizi in un determinato intervallo di tempo.

---

> [!TIP]
> Ti consigliamo di aggiornare regolarmente i modelli predefiniti con dati aggiornati per assicurarti che forniscano informazioni precise al caso d'uso aziendale. I dati vengono aggiornati ad hoc quando il sistema acquisisce origini dati nuove o aggiornate. Tuttavia, in questo caso i modelli calcolano nuovamente il punteggio e continuano a utilizzare i dati di training esistenti.
> 
> È possibile configurare un **Programma di aggiornamento** impostando il programma di nuovo training del modello nell'esperienza di configurazione. Vengono eseguiti nuovamente il training del modello e il calcolo del punteggio in base a questo programma, che puoi modificare in qualsiasi momento.


## <a name="azure-machine-learning-integration"></a>Integrazione di Azure Machine Learning

Se un'organizzazione usa già scenari di apprendimento automatico basati su esperimenti di Azure Machine Learning, la funzionalità dei modelli personalizzati in Customer Insights aiuta a collegare i punti. Crea flussi di lavoro che ti aiutino a scegliere i dati da cui desideri generare informazioni dettagliate e mappare i risultati ai profili dei tuoi clienti unificati. Per ulteriori informazioni, vedi [Modelli personalizzati apprendimento automatico](custom-models.md).

## <a name="ai-builder-prediction"></a>Previsione AI Builder

A volte, i set di dati sono incompleti e mancano alcuni valori. Customer Insights può aiutare a prevedere i valori mancanti per l'entità e i segmenti Customer. Per ulteriori informazioni, vedi [Completa i tuoi dati parziali con le previsioni](predictions.md).
