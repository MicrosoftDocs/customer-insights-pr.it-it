---
title: Limiti del servizio in Customer Insights
description: Conosci i limiti e le restrizioni nell'ambito del servizio SaaS Customer Insights.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 421e1aa41a54a4b8c34ac27fc7c02e510d2bb588
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387161"
---
# <a name="service-limits-in-customer-insights"></a>Limiti del servizio in Customer Insights

 Customer Insights ha limiti incorporati che sono progettati per assicurare l'affidabilità e la stabilità del servizio. Tutte le richieste di modifiche possono essere effettuate tramite il [forum Idee](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Area  | Limiti  | Note |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, misure e previsioni | 300  | Il numero totale di [segmenti](segments.md), [misure](measures.md) e [previsioni](predictions.md) combinati non può superare 300.  |
| Relazioni | 20 livelli di profondità sulle relazioni nei percorsi delle entità. | Quando si creano [segmenti](segments.md) o [misure](measures.md) utilizzando l'interfaccia del generatore, i percorsi delle entità possono avere fino a 20 hop di relazione tra l'entità di inizio e l'entità di destinazione.  |

## <a name="fair-scheduling-of-jobs"></a>Pianificazione equa dei processi

Customer Insights è un servizio SaaS che usa risorse di Azure condivise. I clienti tendono ad avere carichi di lavoro di intensità variabile e con piani diversi. Per garantire un accesso equo alle risorse sottostanti, ci assicuriamo che i processi di sistema vengano eseguiti in modo equo. Esempi di processi di sistema sono i processi relativi all'unificazione dei dati, agli aggiornamenti dei segmenti o al calcolo delle misure. La pianificazione equa ti protegge dalla messa in coda delle risorse qualora si verifichi è un picco di processi richiesti. Allo stesso tempo, Customer Insights non garantisce che tutti i processi in coda vengano elaborati in parallelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
