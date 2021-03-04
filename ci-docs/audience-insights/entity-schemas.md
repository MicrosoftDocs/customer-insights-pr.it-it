---
title: Schemi delle entità di Customer Insights in Common Data Model
description: Utilizza le entità in Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269289"
---
# <a name="entity-schemas-in-common-data-model"></a>Schemi delle entità in Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) è una specifica dichiarativa e una definizione delle entità standard che rappresentano i concetti e le attività usati comunemente nelle applicazioni aziendali e di produttività. Questo modello viene esteso anche ai dati osservativi e analitici. Common Data Model offre entità aziendali ben definite, modulari ed estendibili, come ad esempio account, business unit, casi, contatti, lead, opportunità e prodotti, nonché le interazioni e le relazioni con fornitori, ruoli di lavoro e clienti, come ad esempio attività e contratti di servizio. Chiunque può creare ed estendere le definizioni di Common Data Model per acquisire altre idee specifiche per l'azienda.

Questo modello di dati condiviso consente alle applicazioni e agli integratori di dati di collaborare più facilmente fornendo una definizione unificata dei dati. Common Data Model include un ricco sistema di metadati con entità, relazioni, gerarchie, tratti standard e altro. Trae origine dalle app di Dynamics 365 ed è open source su GitHub con oltre 260 entità standard. Un vasto sistema di partner interni ed esterni contribuisce al Common Data Model con concetti specifici del settore.

Più sistemi e piattaforme implementano oggi Common Data Model, tra cui i flussi di dati di Power BI e Azure Data Services. È già supportato in Common Data Service, Dynamics 365, Power Apps, Power BI e i futuri servizi dati di Azure, accumulando direttamente nell'ottica della [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Schemi delle entità di Customer Insights

Per ottenere una panoramica a 360 gradi del cliente e rendere disponibili i modelli di Customer Insights in Common Data Model per l'estendibilità, abbiamo pubblicato i seguenti schemi di entità:

| Entità | Descrizione |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Un impegno svolto da un utente che ha un valore osservativo per l'azienda. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Una persona o un'organizzazione che ha eseguito o ha il potenziale per eseguire attività aziendali. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definizione di KPI partizionati per zero o più dimensioni (ad esempio Utenti attivi mensili, spesa totale per cliente, costo di acquisizione medio del cliente) |
|[Segmento ](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definisce un gruppo di membri con tratti comuni. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Membri che partecipano a un determinato segmento. |

Per altre informazioni, vedi la documentazione relativa a [Schemi di entità di Customer Insights nel Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Visualizzare le entità utilizzando l'elenco delle entità di Common Data Model

Puoi visualizzare le entità nell'[elenco delle entità di Common Data Model](https://microsoft.github.io/CDM/). Seleziona il pulsante **Carica da GitHub** e vai a **foundationCommon** > **crmCommon** > **solutions** > **customerInsights** dove troverai l'elenco delle entità di Customer Insights e le relative definizioni.
> [!div class="mx-imgBorder"]
> ![Elenco di entità CDM che mostra l'entità CustomerActivity](media/CDM-entity-navigator.png "Elenco di entità CDM che mostra l'entità CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]