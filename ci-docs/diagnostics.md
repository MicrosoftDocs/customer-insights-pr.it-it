---
title: Esportare log di diagnostica (anteprima)
description: Informazioni su come inviare log a Monitoraggio di Microsoft Azure.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245930"
---
# <a name="export-diagnostic-logs-preview"></a>Esportare log di diagnostica (anteprima)

Inoltra i log di Customer Insights a Monitoraggio di Azure. I log delle risorse di Monitoraggio di Azure consentono di monitorare e inviare i log ad [Archiviazione di Azure](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) o di trasmetterli in streaming su [Hub eventi di Azure](https://azure.microsoft.com/services/event-hubs/).

Customer Insights invia i seguenti registri eventi:

- **Eventi di controllo**
  - **APIEvent**: abilita il rilevamento delle modifiche tramite l'interfaccia utente di Dynamics 365 Customer Insights.
- **Eventi operativi**
  - **WorkflowEvent**: consente di impostare [origini dati](data-sources.md), [unificare](data-unification.md), [arricchire](enrichment-hub.md) ed [esportare](export-destinations.md) dati in altri sistemi. Questi passaggi possono essere eseguiti individualmente (ad esempio attivare una singola esportazione). Possono anche essere eseguiti in modo orchestrato (ad esempio l'aggiornamento dei dati dalle origini dati che attivano il processo di unificazione, il quale inserirà gli arricchimenti e, una volta terminato, esporterà i dati in un altro sistema). Per altre informazioni, vedi [Schema WorkflowEvent](#workflow-event-schema).
  - **APIEvent**: invia tutte le chiamate API dell'istanza del cliente a Dynamics 365 Customer Insights. Per altre informazioni, vedi [Schema APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Configurare le impostazioni di diagnostica

### <a name="prerequisites"></a>Prerequisiti

- Una [sottoscrizione di Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) attiva.
- Autorizzazioni di [amministratore](permissions.md#admin) in Customer Insights.
- [Ruolo Collaboratore e Amministratore accessi utente](/azure/role-based-access-control/role-assignments-portal) nella risorsa di destinazione in Azure. La risorsa può essere un account Azure Data Lake Storage, un hub eventi di Azure o un'area di lavoro Log Analytics di Azure. Questa autorizzazione è necessaria durante la configurazione delle impostazioni diagnostiche in Customer Insights, ma può essere modificata dopo la configurazione.
- [Requisiti della destinazione](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) per Archiviazione di Azure, Hub eventi di Azure o Log Analytics di Azure soddisfatti.
- Almeno il ruolo **Lettore** nel gruppo di risorse a cui appartiene la risorsa.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configurare la diagnostica con Monitoraggio di Azure

1. In Customer Insights, vai ad **Amministratore** > **Sistema** e seleziona la scheda **Diagnostica**.

1. Seleziona **Aggiungi destinazione**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Connessione diagnostica.":::

1. Fornire un nome nel campo **Nome per la destinazione della diagnostica**.

1. Seleziona il **tipo di risorsa** (Account di archiviazione, hub eventi o analisi dei log).

1. Esegui una seleziona in **Sottoscrizione**, **Gruppo di risorse** e **Risorsa** per la risorsa di destinazione. Vedi [Configurazione sulla risorsa di destinazione](#configuration-on-the-destination-resource) per l'autorizzazione e le informazioni sui log.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti al sistema** per connettersi alla risorsa di destinazione. I log iniziano ad apparire nella destinazione dopo 15 minuti, se l'API è in uso e genera eventi.

## <a name="configuration-on-the-destination-resource"></a>Configurazione sulla risorsa di destinazione

In base alla scelta del tipo di risorsa, vengono eseguite automaticamente le seguenti modifiche:

### <a name="storage-account"></a>Storage account

L'entità servizio di Customer Insights ottiene l'autorizzazione **Collaboratore account di archiviazione** sulla risorsa selezionata e crea due contenitori nello spazio dei nomi selezionato:

- `insight-logs-audit` contenente **eventi di controllo**
- `insight-logs-operational` contenente **eventi operativi**

### <a name="event-hub"></a>Hub eventi

L'entità servizio di Customer Insights ottiene l'autorizzazione **Proprietario dati hub eventi di Azure** per la risorsa e crea due hub eventi nello spazio dei nomi selezionato:

- `insight-logs-audit` contenente **eventi di controllo**
- `insight-logs-operational` contenente **eventi operativi**

### <a name="log-analytics"></a>Log Analytics

L'entità servizio di Customer Insights ottiene l'autorizzazione **Collaboratore analisi dei log** sulla risorsa. I log saranno disponibili in **Log** > **Tabelle** > **Gestione registri di controllo** nell'area di lavoro di Log Analytics selezionata. Espandi la soluzione **Gestione registri di controllo** e individua le tabelle `CIEventsAudit` e `CIEventsOperational`.

- `CIEventsAudit` contenente **eventi di controllo**
- `CIEventsOperational` contenente **eventi operativi**

Nella finestra **Query**, espandi la soluzione **Controllo** e individua le query di esempio fornite cercando `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Rimuovere una destinazione della diagnostica

1. Vai ad **Amministratore** > **Sistema** e seleziona la scheda **Diagnostica**.

1. Seleziona la destinazione di diagnostica dall'elenco.

   > [!TIP]
   > La rimozione della destinazione interrompe l'inoltro del log, ma non elimina la risorsa nella sottoscrizione di Azure. Per eliminare la risorsa in Azure, seleziona il collegamento nella colonna **Azioni** per aprire il portale di Azure per la risorsa selezionata ed eliminarla lì. Quindi elimina la destinazione di diagnostica.

1. Nella colonna **Azioni**, seleziona l'icona **Elimina**.

1. Conferma l'eliminazione per rimuovere la destinazione e interrompere l'inoltro del log.

## <a name="log-categories-and-event-schemas"></a>Categorie di log e schemi di eventi

Attualmente gli [eventi API](apis.md) e gli eventi del flusso di lavoro sono supportati e si applicano alle categorie e agli schemi seguenti.
Lo schema del log segue lo [schema comune di Monitoraggio di Azure](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Categorie

Customer Insights fornisce due categorie:

- **Eventi di controllo**: [eventi API](#api-event-schema) per tenere traccia delle modifiche alla configurazione del servizio. Le operazioni `POST|PUT|DELETE|PATCH` rientrano in questa categoria.
- **Eventi operativi**: [eventi API](#api-event-schema) o [eventi del flusso di lavoro](#workflow-event-schema) generati durante l'utilizzo del servizio.  Per esempio, le richieste `GET` o gli eventi di esecuzione di un flusso di lavoro.

## <a name="event-schemas"></a>Schemi di eventi

Gli eventi API e gli eventi del flusso di lavoro hanno una struttura comune, ma con alcune differenze. Per ulteriori informazioni, vedi [Schema di eventi API](#api-event-schema) o [Schema di eventi flusso di lavoro](#workflow-event-schema).

### <a name="api-event-schema"></a>Schema eventi API

| Campo             | Tipo di dati  | Obbligatorio/facoltativo | Description       | Esempio        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Timestamp: | Richiesto          | Timestamp dell'evento (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Richiesto          | ResourceId dell'istanza che ha emesso l'evento         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Richiesto          | Nome dell'operazione rappresentata da questo evento.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Richiesto          | Categoria del log dell'evento. `Operational` o `Audit`. Tutte le richieste POST/PUT/PATCH/DELETE HTTP sono contrassegnate con `Audit`, tutto il resto con `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Richiesto          | Stato dell'evento. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Facoltativa          | Stato dei risultati dell'evento. Se l'operazione corrisponde a una chiamata API REST, è il codice di stato HTTP.        | `200`             |
| `durationMs`      | Lungo      | Facoltativa          | Durata dell'operazione in millisecondi.     | `133`     |
| `callerIpAddress` | String    | Facoltativa          | Indirizzo IP del chiamante, se l'operazione corrisponde a una chiamata API proveniente da un indirizzo IP pubblicamente disponibile.                                                 | `144.318.99.233`         |
| `identity`        | String    | Facoltativa          | Oggetto JSON che descrive l'identità dell'utente o dell'applicazione che ha eseguito l'operazione.       | Vedi la sezione [Identità](#identity-schema).     |  
| `properties`      | String    | Facoltativa          | Oggetto JSON con più proprietà per la particolare categoria di eventi.      | Vedi la sezione [Proprietà](#api-properties-schema).    |
| `level`           | String    | Richiesto          | Livello di sicurezza dell'evento.    | `Informational`, `Warning`, `Error` o `Critical`.           |
| `uri`             | String    | Facoltativa          | URI di richiesta assoluta.    |               |

#### <a name="identity-schema"></a>Schema dell'identità

L'oggetto JSON `identity` ha la seguente struttura

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Campo                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Ruolo assegnato per l'utente o l'app. Per ulteriori informazioni, vedi [autorizzazioni utente](permissions.md).                                     |
| `Authorization.RequiredRoles` | Ruoli richiesti per eseguire l'operazione. Il ruolo `Admin` può eseguire tutte le operazioni.                                                    |
| `Claims`                      | Affermazioni dell'utente o dell'app del token JSON Web (JWT). Le proprietà della richiesta variano in base all'organizzazione e alla configurazione Azure Active Directory. |

#### <a name="api-properties-schema"></a>Schema delle proprietà dell'API

Gli [eventi API](apis.md) hanno le seguenti proprietà.

| Campo                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Sempre `ApiEvent`, contrassegnando l'evento di log come evento API.                                                                 |
| `properties.userAgent`       | Agente del browser che invia la richiesta o `unknown`.                                                                        |
| `properties.method`          | Metodo HTTP: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Percorso relativo della richiesta.                                                                                          |
| `properties.origin`          | URI che indica da dove proviene un recupero o `unknown`.                                                                  |
| `properties.operationStatus` | `Success` per codice stato HTTP < 400 <br> `ClientError` per codice stato HTTP < 500 <br> `Error` per stato HTTP >= 500 |
| `properties.tenantId`        | ID organizzazione                                                                                                        |
| `properties.tenantName`      | Il nome dell'organizzazione.                                                                                              |
| `properties.callerObjectId`  | ObjectId Azure Active Directory del chiamante.                                                                         |
| `properties.instanceId`      | `instanceId` di Customer Insights                                                                                         |

### <a name="workflow-event-schema"></a>Schema di eventi flusso di lavoro

Il flusso di lavoro contiene più passaggi. [Acquisisci origini dati](data-sources.md), [unifica](data-unification.md), [arricchisci](enrichment-hub.md) ed [esporta](export-destinations.md) dati. Tutti questi passaggi possono essere eseguiti individualmente o orchestrati con i seguenti processi.

#### <a name="operation-types"></a>Tipi di operazione

| OperationType     | Raggruppa                                     |
| ----------------- | ----------------------------------------- |
| Inserimento         | [Origini dati](data-sources.md)           |
| DataPreparation   | [Origini dati](data-sources.md)           |
| Mapping               | [Unificazione dei dati](data-unification.md)   |
| Match             | [Unificazione dei dati](data-unification.md)   |
| Unire             | [Unificazione dei dati](data-unification.md)   |
| ProfileStore      | [Profili cliente](customer-profiles.md) |
| Ricerca            | [Profili cliente](customer-profiles.md) |
| Impegno          | [Impegni](activities.md)                  |
| AttributeMeasures | [Segmenti e misure](segments.md)      |
| EntityMeasures    | [Segmenti e misure](segments.md)      |
| Misure          | [Segmenti e misure](segments.md)      |
| Segmentazione      | [Segmenti e misure](segments.md)      |
| Arricchimento        | [Arricchimento](enrichment-hub.md)                                          |
| Intelligenza      | [Previsioni](predictions-overview.md)                                          |
| AiBuilder         | [Previsioni](predictions-overview.md)                                          |
| Informazioni dettagliate          | [Previsioni](predictions-overview.md)                                          |
| Export            | [Esportazioni](export-destinations.md)                                          |
| ModelManagement   | [Previsioni](custom-models.md)                                           |
| Relationship      | [Unificazione dei dati](relationships.md)                                           |

#### <a name="field-description"></a>Descrizione campo

| Campo           | Tipo di dati  | Obbligatorio/facoltativo | Description                                                                                                                                                   | Esempio                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Timestamp: | Richiesto          | Timestamp dell'evento (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Richiesto          | ResourceId dell'istanza che ha emesso l'evento.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Richiesto          | Nome dell'operazione rappresentata da questo evento. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Vedi [Tipi di operazioni](#operation-types) per riferimento. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Richiesto          | Categoria del log dell'evento. Sempre `Operational` per eventi di flusso di lavoro                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Richiesto          | Stato dell'evento. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Lungo      | Facoltativa          | Durata dell'operazione in millisecondi.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Facoltativa          | Oggetto JSON con più proprietà per la particolare categoria di eventi.                                                                                        | Vedi sottosezione [Proprietà del flusso di lavoro](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Richiesto          | Livello di sicurezza dell'evento.                                                                                                                                  | `Informational`, `Warning` o `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Schema di proprietà di un flusso di lavoro

Gli eventi fi flusso di lavoro hanno le seguenti proprietà.

| Campo              | Workflow | Attività | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Sì      | Sì  | Sempre `WorkflowEvent`, contrassegnando l'evento di flusso di lavoro.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Sì      | Sì  | Identificatore dell'esecuzione del flusso di lavoro. Tutti gli eventi del flusso di lavoro e delle attività all'interno dell'esecuzione del flusso di lavoro hanno lo stesso `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Sì      | Sì  | Identificatore dell'operazione, vedi [Tipi di operazione](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Sì      | No   | Solo flusso di lavoro. Numero di attività attivate dal flusso di lavoro.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Sì      | No   | (Facoltativo). Solo eventi flusso di lavoro. L'[objectId dell'utente](/azure/marketplace/find-tenant-object-id#find-user-object-id) Azure Active Directory che ha attivato il flusso di lavoro, vedi anche `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Sì      | No   | aggiornamento `full` o `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Sì      | No   | `OnDemand` oppure `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Sì      | No   | `Running` oppure `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Sì      | Sì  | Timestamp UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Sì      | Sì  | Timestamp UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Sì      | Sì  | Timestamp UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Sì      | Sì  | `instanceId` di Customer Insights                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Sì  | - Per OperationType = `Export`, l'identificatore è il guid della configurazione di esportazione. <br> - Per OperationType = `Enrichment`, è il guid dell'arricchimento <br> - Per OperationType `Measures` e `Segmentation`, l'identificatore è il nome dell'entità. |
| `properties.friendlyName`                    | No       | Sì  | Nome descrittivo dell'esportazione o dell'entità che viene elaborata.                                                                                                                                                                                           |
| `properties.error`                           | No       | Sì  | (Facoltativo). Messaggio di errore con maggiori dettagli.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Sì  | (Facoltativo). Per OperationType solo `Export`. Identifica il tipo di esportazione. Per altre informazioni, vedi [panoramica delle destinazioni di esportazione](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Sì  | (Facoltativo). Per OperationType solo `Export`. Contiene un elenco di entità configurate nell'esportazione.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Sì  | (Facoltativo). Per OperationType solo `Export`. Messaggio dettagliato per l'esportazione.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Sì  | (Facoltativo). Per OperationType solo `Segmentation`. Indica il numero totale di membri del segmento.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
