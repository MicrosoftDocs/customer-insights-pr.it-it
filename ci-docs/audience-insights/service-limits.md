---
title: Limiti del servizio
description: Informazioni su limiti e restrizioni.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034869"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Limiti del servizio nella funzionalità Informazioni dettagliate sul gruppo di destinatari di Dynamics 365 Customer Insights

In questo articolo vengono descritti i limiti predefiniti del servizio Customer Insights, che sono progettati per assicurare l'affidabilità e la stabilità del servizio. Tutte le richieste di modifiche possono essere effettuate tramite il [forum Idee](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Area  | Limiti  | Note |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti e misure | 100 segmenti o misure. | Il numero totale di [segmenti](segments.md) e [misure](measures.md) attivi combinato non può essere superiore a 100.  |
| Relazioni | 20 livelli di profondità sulle relazioni nei percorsi delle entità. | Quando si creano [segmenti](segments.md) o [misure](measures.md) utilizzando l'interfaccia del generatore, i percorsi delle entità possono avere fino a 20 hop di relazione tra l'entità di inizio e l'entità di destinazione.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]