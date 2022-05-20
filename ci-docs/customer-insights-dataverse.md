---
title: Dati di Customer Insights in Microsoft Dataverse
description: Utilizza le entità di Customer Insights come tabelle in Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741370"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Utilizzare i dati di Customer Insights in Microsoft Dataverse

Customer Insights offre la possibilità di rendere disponibili entità di output in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Questa integrazione consente una facile condivisione dei dati e sviluppo personalizzato con un approccio a uso limitato di codice/senza codice. Le [entità di output](#output-entities) sono disponibili come tabelle in un ambiente Dataverse. È possibile utilizzare i dati per qualsiasi altra applicazione basata su tabelle Dataverse. Queste tabelle consentono scenari come flussi di lavoro automatizzati tramite Power Automate o di creare app con Power Apps. L'implementazione corrente supporta principalmente le ricerche con cui è possibile recuperare i dati dalle entità Customer Insights disponibili per un determinato ID cliente.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Allega un ambiente Dataverse a Customer Insights

**Organizzazione esistente**

Gli amministratori possono configurare Customer Insights per [usare un ambiente Dataverse esistente](create-environment.md) quando creano un ambiente Customer Insights. Fornendo l'URL all'ambiente Dataverse, si collega il nuovo ambiente Customer Insights. Gli ambiente Customer Insights e Dataverse devono essere ospitati nella stessa area. 

Se non si desidera usare un ambiente Dataverse esistente, il sistema crea un nuovo ambiente per i dati di Customer Insights nel tenant in uso. 

> [!NOTE]
> Se le tue organizzazioni già utilizzano Dataverse nel tenant, è importante ricordare che [la creazione dell'ambiente Dataverse è controllata da un amministratore](/power-platform/admin/control-environment-creation). Ad esempio, se stai configurando un nuovo ambiente Customer Insights con il tuo account aziendale e l'amministratore ha disabilitato la creazione di ambienti di prova Dataverse per tutti tranne gli amministratori, non puoi creare un nuovo ambiente di prova.
> 
> Gli ambienti Dataverse di prova creati in Customer Insights dispongono di 3 GB di spazio di archiviazione che non verranno conteggiati ai fini della capacità complessiva a disposizione del tenant. Gli abbonamenti a pagamento ottengono il diritto a Dataverse di 15 GB per il database e 20 GB per l'archiviazione dei file.

**Nuova organizzazione**

Se crei una nuova organizzazione durante la configurazione di Customer Insights, il sistema crea automaticamente un nuovo ambiente Dataverse per l'organizzazione.

## <a name="output-entities"></a>Entità di output

Alcune entità di output di Customer Insights sono disponibili come tabelle in Dataverse. Le sezioni seguenti descrivono lo schema previsto di queste tabelle.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Arricchimento](#enrichment)
- [Previsione](#prediction)
- [Appartenenza al segmento](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Questa tabella contiene il profilo cliente unificato di Customer Insights. Lo schema per un profilo cliente unificato dipende dalle entità e dagli attributi utilizzati nel processo di unificazione dei dati. Uno schema del profilo del cliente di solito contiene un sottoinsieme degli attributi dalla [Definizione del Common Data Model di CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

La tabella AlternateKey contiene le chiavi delle entità che hanno partecipato al processo di unificazione.

|Column  |Digita  |Description  |
|---------|---------|---------|
|DataSourceName    |Stringa         | Nome origine dati. Ad esempio: `datasource5`        |
|EntityName        | String        | Nome dell'entità in Customer Insights. Ad esempio: `contact1`        |
|AlternateValue    |String         |ID alternativo mappato all'ID cliente. Esempio: `cntid_1078`         |
|KeyRing           | Testo su più righe        | Valore JSON  </br> Esempio: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|Customerid         | Stringa        | ID del profilo cliente unificato.         |
|AlternateKeyId     | GUID         |  GUID deterministico AlternateKey basato su msdynci_identifier       |
|msdynci_identifier |   Stringa      |   `DataSourceName|EntityName|AlternateValue`  </br> Esempio: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Questa tabella contiene le attività degli utenti disponibili in Customer Insights.

| Column            | Digita        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Customerid        | Stringa      | ID profilo cliente                                                                      |
| ActivityId        | Stringa      | ID interno dell'attività del cliente (chiave primaria)                                       |
| SourceEntityName  | Stringa      | Nome dell'entità di origine                                                                |
| SourceActivityId  | Stringa      | Chiave primaria dall'entità di origine                                                       |
| ActivityType      | Stringa      | Tipo di attività semantica o nome dell'attività personalizzata                                        |
| ActivityTimeStamp | DATETIME    | Timestamp impegno                                                                      |
| Posizione             | Stringa      | Titolo o nome dell'impegno                                                               |
| Description       | Stringa      | Descrizione impegno                                                                     |
| URL               | Stringa      | Collegamento a un URL esterno specifico per l'impegno                                         |
| SemanticData      | Stringa JSON | Include un elenco di coppie chiave-valore per campi di mappatura semantica specifici per il tipo di attività |
| RangeIndex        | Stringa      | Timestamp Unix utilizzato per ordinare la sequenza temporale dell'attività e le query sull'intervallo effettivo |
| mydynci_unifiedactivityid   | GUID | ID interno dell'attività del cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Questa tabella contiene i dati di output delle misure basate sugli attributi del cliente.

| Column             | Digita             | Description                 |
|--------------------|------------------|-----------------------------|
| Customerid         | Stringa           | ID profilo cliente        |
| Misure           | Stringa JSON      | Include un elenco di coppie di valori chiave per il nome della misura e i valori per il cliente specificato | 
| msdynci_identifier | Stringa           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profilo cliente |


### <a name="enrichment"></a>Arricchimento

Questa tabella contiene l'output del processo di arricchimento.

| Column               | Digita             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| Customerid           | Stringa           | ID profilo cliente                                 |
| EnrichmentProvider   | Stringa           | Nome del provider per l'arricchimento                                  |
| EnrichmentType       | Stringa           | Tipo di arricchimento                                      |
| Valori               | Stringa JSON      | Elenco degli attributi prodotti dal processo di arricchimento |
| msdynci_enrichmentid | GUID             | GUID deterministico generato da msdynci_identifier |
| msdynci_identifier   | Stringa           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Previsione

Questa tabella contiene l'output delle previsioni del modello.

| Column               | Digita        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| Customerid           | Stringa      | ID profilo cliente                                  |
| ModelProvider        | Stringa      | Nome del provider del modello                                      |
| Modello                | Stringa      | Nome modello                                                |
| Valori               | Stringa JSON | Elenco degli attributi prodotti dal modello |
| msdynci_predictionid | GUID        | GUID deterministico generato da msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Appartenenza al segmento

Questa tabella contiene le informazioni sull'appartenenza al segmento dei profili cliente.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| Customerid        | String       | ID profilo cliente        |
| SegmentProvider      | String       | App che pubblica i segmenti.      |
| SegmentMembershipType | String       | Tipo di cliente di questo record di appartenenza al segmento. Supporta più tipi come Cliente, Contatto o Account. Impostazione predefinita: cliente  |
| Segmenti       | Stringa JSON  | Elenco dei segmenti univoci di cui il profilo cliente è membro      |
| msdynci_identifier  | String   | Identificatore univoco del record di appartenenza al segmento. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID deterministico generato da `msdynci_identifier`          |
