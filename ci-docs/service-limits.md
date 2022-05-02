---
title: Limiti del servizio in Dynamics 365 Customer Insights
description: Informazioni su limiti e restrizioni.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641767"
---
# <a name="service-limits-in-customer-insights"></a>Limiti del servizio in Customer Insights

In questo articolo vengono descritti i limiti predefiniti del servizio Customer Insights, che sono progettati per assicurare l'affidabilità e la stabilità del servizio. Tutte le richieste di modifiche possono essere effettuate tramite il [forum Idee](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Area  | Limiti  | Note |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, misure e previsioni | 300  | Il numero totale di [segmenti](segments.md), [misure](measures.md) e [previsioni](predictions.md) combinati non può superare 300.  |
| Relazioni | 20 livelli di profondità sulle relazioni nei percorsi delle entità. | Quando si creano [segmenti](segments.md) o [misure](measures.md) utilizzando l'interfaccia del generatore, i percorsi delle entità possono avere fino a 20 hop di relazione tra l'entità di inizio e l'entità di destinazione.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
