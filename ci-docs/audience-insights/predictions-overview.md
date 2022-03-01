---
title: Panoramica sugli scenari di previsione supportati
description: Scenari e opzioni di previsione coperti dall'applicazione Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 57c61895d636273fc90a0ac5a942fd0c9abf583c687ae20621949554e581cdf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036014"
---
# <a name="predictions-overview"></a>Panoramica delle previsioni

Dynamics 365 Customer Insights viene fornito con una varietà di opzioni che sfruttano l'intelligenza artificiale e l'apprendimento automatico per prevedere i dati. 

## <a name="out-of-box-models"></a>Modelli predefiniti

Il modo più semplice per iniziare con la previsione dei dati sono i modelli predefiniti, spesso indicati come modelli predefiniti. Richiedono solo determinati dati e una struttura per generare rapidamente informazioni dettagliate. Attualmente sono disponibili i seguenti modelli: 
- [Valore durata cliente](predict-customer-lifetime-value.md): prevede ricavi potenziali di un cliente durante l'intera interazione con un'azienda. 
- [Raccomandazione del prodotto](predict-product-recommendation.md): suggerisce set di raccomandazioni predittive sui prodotti in base al comportamento di acquisto e ai clienti con modelli di acquisto simili.
- [Abbandono dell'abbonamento](predict-subscription-churn.md): prevede se un cliente è a rischio perché non utilizza più i prodotti o i servizi in abbonamento della società.
- [Abbandono transazionale](predict-transactional-churn.md): prevede se un cliente non acquisterà più i tuoi prodotti o servizi in un determinato intervallo di tempo.

## <a name="azure-machine-learning-integration"></a>Integrazione di Azure Machine Learning

Se un'organizzazione usa già scenari di apprendimento automatico basati su esperimenti di Azure Machine Learning, la funzionalità dei modelli personalizzati in Customer Insights aiuta a collegare i punti. Crea flussi di lavoro che ti aiutino a scegliere i dati da cui desideri generare informazioni dettagliate e mappare i risultati ai profili dei tuoi clienti unificati. Per ulteriori informazioni, vedi [Modelli personalizzati apprendimento automatico](custom-models.md).

## <a name="ai-builder-prediction"></a>Previsione AI Builder

A volte, i set di dati sono incompleti e mancano alcuni valori. Customer Insights può aiutare a prevedere i valori mancanti per l'entità e i segmenti Customer. Per ulteriori informazioni, vedi [Completa i tuoi dati parziali con le previsioni](predictions.md).
