---
title: Schemi delle entità di Customer Insights in Common Data Model
description: Utilizza le entità in Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2cdbe11a1c0cc5d65434fb2ae3a3f38c18f31cf4
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046521"
---
# <a name="entity-schemas-in-common-data-model"></a>Schemi delle entità in Common Data Model



[Common Data Model](/common-data-model/) è una specifica dichiarativa e una definizione delle entità standard che rappresentano i concetti e le attività usati comunemente nelle applicazioni aziendali e di produttività. Questo modello viene esteso anche ai dati osservativi e analitici. Common Data Model offre entità aziendali ben definite, modulari ed estendibili, come ad esempio account, business unit, casi, contatti, lead, opportunità e prodotti, nonché le interazioni e le relazioni con fornitori, ruoli di lavoro e clienti, come ad esempio attività e contratti di servizio. Chiunque può creare ed estendere le definizioni di Common Data Model per acquisire altre idee specifiche per l'azienda.

Questo modello di dati condiviso consente alle applicazioni e agli integratori di dati di collaborare più facilmente fornendo una definizione unificata dei dati. Common Data Model include un ricco sistema di metadati con entità, relazioni, gerarchie, tratti standard e altro. Trae origine dalle app di Dynamics 365 ed è open source su GitHub con oltre 260 entità standard. Un vasto sistema di partner interni ed esterni contribuisce al Common Data Model con concetti specifici del settore.

Più sistemi e piattaforme implementano oggi il Common Data Model, tra cui i flussi di dati Power BI e Azure Data Services. È già supportato in Microsoft Dataverse, Dynamics 365, Power Apps, Power BI e i prossimi servizi dati di Azure, accumulando direttamente valore verso l'[Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Schemi delle entità di Customer Insights

Per ottenere una panoramica a 360 gradi del cliente e rendere disponibili i modelli di Customer Insights in Common Data Model per l'estendibilità, abbiamo pubblicato i seguenti schemi di entità:

| Entità | Descrizione |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Un impegno svolto da un utente che ha un valore osservativo per l'azienda. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Una persona o un'organizzazione che ha eseguito o ha il potenziale per eseguire attività aziendali. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definizione di KPI partizionati per zero o più dimensioni (ad esempio Utenti attivi mensili, spesa totale per cliente, costo di acquisizione medio del cliente) |
|[Segmento ](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definisce un gruppo di membri con tratti comuni. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Membri che partecipano a un determinato segmento. |

Per altre informazioni, vedi la documentazione relativa a [Schemi di entità di Customer Insights nel Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Visualizzare le entità utilizzando l'elenco delle entità di Common Data Model

Puoi visualizzare le entità nell'[elenco delle entità di Common Data Model](https://microsoft.github.io/CDM/). Seleziona un'entità nella sezione Application Insights per ottenere l'elenco delle entità di Customer Insights e le relative definizioni.
> [!div class="mx-imgBorder"]
> ![Elenco di entità CDM che mostra l'entità CustomerActivity.](media/CDM-entity-navigator.png "Elenco di entità CDM che mostra l'entità CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]
