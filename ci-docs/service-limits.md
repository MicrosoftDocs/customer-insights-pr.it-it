---
title: Limiti del servizio in Dynamics 365 Customer Insights
description: Informazioni su limiti e restrizioni.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483679"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limiti del servizio nelle funzionalità Customer Insights

In questo articolo vengono descritti i limiti predefiniti del servizio Customer Insights, che sono progettati per assicurare l'affidabilità e la stabilità del servizio. Tutte le richieste di modifiche possono essere effettuate tramite il [forum Idee](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Informazioni dettagliate gruppo di destinatari

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Limiti del servizio nella funzionalità Informazioni dettagliate sul gruppo di destinatari di Dynamics 365 Customer Insights

| Area  | Limiti  | Note |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti e misure | 100 segmenti o misure. | Il numero totale di [segmenti](audience-insights/segments.md) e [misure](audience-insights/measures.md) attivi combinato non può essere superiore a 100.  |
| Relazioni | 20 livelli di profondità sulle relazioni nei percorsi delle entità. | Quando si creano [segmenti](audience-insights/segments.md) o [misure](audience-insights/measures.md) utilizzando l'interfaccia del generatore, i percorsi delle entità possono avere fino a 20 hop di relazione tra l'entità di inizio e l'entità di destinazione.  |


## <a name="engagement-insights"></a>Informazioni dettagliate sull'interazione

### <a name="workspace-and-event-quotas"></a>Quote di spazio di lavoro ed eventi

Le informazioni dettagliate sull'interazione sono un'applicazione altamente scalabile in grado di supportare milioni di eventi al secondo. Durante l'anteprima pubblica, gli eventi hanno una soglia di volume. Esiste anche un limite al numero di aree di lavoro in un'organizzazione.

### <a name="engagement-insights-limits"></a>Limiti delle informazioni dettagliate sull'interazione

- Volume massimo di eventi per area di lavoro = 100 eventi al secondo

- Numero massimo di aree di lavoro per organizzazione = 100

Quando gli eventi superano la soglia, è possibile che si verifichi la perdita di dati nei report basati su tali eventi. Puoi [contattare il supporto](https://go.microsoft.com/fwlink/?linkid=2145734) per richiedere un aumento del volume prima di superare i limiti. Lavoreremo con te per determinare la tua necessità di aumentare il volume e supportare la tua richiesta.


[!INCLUDE[footer-include](includes/footer-banner.md)]