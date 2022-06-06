---
title: Esempi OData per le API Dynamics 365 Customer Insights
description: Esempi comunemente usati di Open Data Protocol (OData) per eseguire query sulle API Customer Insights al fine di esaminare i dati.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cdadd72bfe4272d8d83d923baaa6fd40d008473b
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808466"
---
# <a name="odata-query-examples"></a>Esempi di query OData

OData (Open Data Protocol) è un protocollo di accesso ai dati basato su protocolli di base come HTTP. Utilizza metodologie comunemente accettate come REST per il Web. Esistono vari tipi di librerie e strumenti che consentono di utilizzare i servizi OData.

Questo articolo elenca alcune query di esempio eseguite di frequente per aiutarti a creare le implementazioni basate su [API Customer Insights](apis.md).

È necessario modificare gli esempi di query perché funzionino negli ambienti di destinazione: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` dove {instanceId} è il GUID dell'ambiente Customer Insights su cui eseguire le query. L'[operazione ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) consente di trovare gli elementi {InstanceId} a cui hai accesso.
- {CID}: GUID di un record cliente unificato. Esempio: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: identificatore della chiave primaria di un record cliente in un origine dati. Esempio: `CNTID_1002`
- {DSname}: stringa con il nome dell'entità di un origine dati che viene inserito in Customer Insights. Esempio: `Website_contacts`.
- {SegmentName}: stringa con il nome dell'entità di output di un segmento in Customer Insights. Esempio: `Male_under_40`.

## <a name="customer"></a>Cliente

La tabella seguente contiene una serie di query di esempio per l'entità *Cliente*.

|Tipo di query |Esempio  | Nota  |
|---------|---------|---------|
|ID cliente singolo     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Chiave alternativa    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Le chiavi alternative persistono nell'entità cliente unificata       |
|Seleziona   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Tra    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Chiave alternativa + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Ricerca  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Restituisce i primi 10 risultati per una stringa di ricerca      |
|Appartenenza al segmento  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Restituisce un numero predefinito di righe dall'entità di segmentazione.      |

## <a name="unified-activity"></a>Impegno unificato

La tabella seguente contiene una serie di query di esempio per l'entità *UnifiedActivity*.

|Tipo di query |Esempio  | Nota  |
|---------|---------|---------|
|Impegno di CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Elenca gli impegni di un profilo cliente specifico |
|Intervallo di tempo impegni    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Impegni di un profilo cliente in un intervallo di tempo       |
|Tipo di impegno    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Impegno per nome visualizzato     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Ordinamento impegni    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Ordina gli impegni in modo crescente o decrescente       |
|Impegno esteso dall'appartenenza al segmento  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Altri esempi

La tabella seguente contiene una serie di query di esempio per altre entità.

|Tipo di query |Esempio  | Nota  |
|---------|---------|---------|
|Misure di CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Marchi arricchiti di CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Interessi arricchiti di CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Clausola In + Espandi     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Query OData non supportate

Le seguenti query non sono supportate da Customer Insights:

- `$filter` sulle entità di origine inserite. Puoi eseguire query $filter solo sulle entità di sistema create da Customer Insights.
- `$expand` da una query `$search`. Esempio: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` da `$select` se è selezionato solo un sottoinsieme di attributi. Esempio: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- Marchio arricchito o affinità di interesse `$expand` per un determinato cliente. Esempio: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Query sulle entità di output del modello di previsione tramite chiave alternativa. Esempio: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
