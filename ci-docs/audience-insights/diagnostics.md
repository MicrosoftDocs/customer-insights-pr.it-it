---
title: Controllo di Dynamics 365 Customer Insights con Monitoraggio di Azure
description: Informazioni su come inviare log a Monitoraggio di Microsoft Azure.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 2e0801c2b6af591e48a7df485a8523903c07617c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354413"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Inoltro del log in Dynamics 365 Customer Insights con Monitoraggio di Azure (anteprima)

Dynamics 365 Customer Insights fornisce un'integrazione diretta con Monitoraggio di Azure. I log delle risorse di Monitoraggio di Azure consentono di monitorare e inviare i log ad [Archiviazione di Azure](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) o di trasmetterli in streaming su [Hub eventi di Azure](https://azure.microsoft.com/services/event-hubs/).

Customer Insights invia i seguenti registri eventi:

- **Eventi di controllo**
  - **APIEvent**: abilita il rilevamento delle modifiche effettuato tramite l'interfaccia utente di Dynamics 365 Customer Insights.
- **Eventi operativi**
  - **WorkflowEvent**: il flusso di lavoro consente di impostare [Origini dati](data-sources.md), [unificare](data-unification.md), [arricchire](enrichment-hub.md) e infine [esportare](export-destinations.md) dati in altri sistemi. Tutti questi passaggi possono essere eseguiti individualmente (ad esempio attivare una singola esportazione) o orchestrati (ad esempio l'aggiornamento dei dati da origini dati che attivano il processo di unificazione che comporterà ulteriori arricchimenti e una volta terminato esporterà i dati in un altro sistema). Per maggiori dettagli vedi lo [Schema WorkflowEvent](#workflow-event-schema).
  - **APIEvent**: tutte le chiamate API all'istanza del cliente a Dynamics 365 Customer Insights. Per maggiori dettagli vedi lo [Schema APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Configurare le impostazioni di diagnostica

### <a name="prerequisites"></a>Prerequisiti

Per configurare la diagnostica in Customer Insights, devono essere soddisfatti i seguenti prerequisiti:

- Hai un [abbonamento di Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) attivo.
- Hai diritti di [amministratore](permissions.md#administrator) in Customer Insights.
- Hai il ruolo **Collaboratore** e **Amministratore accessi utente** nella risorsa di destinazione in Azure. La risorsa può essere un account di archiviazione di Azure, un hub eventi di Azure o un'area di lavoro Log Analytics di Azure. Per ulteriori informazioni, vedi [Aggiungere o rimuovere le assegnazioni dei ruoli di Azure tramite il portale di Azure](/azure/role-based-access-control/role-assignments-portal).
- [Requisiti della destinazione](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) per Archiviazione di Azure, Hub eventi di Azure o Log Analytics di Azure soddisfatti.
- Hai almeno il ruolo **Lettore** nel gruppo di risorse a cui appartiene la risorsa.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configurare la diagnostica con Monitoraggio di Azure

1. In Customer Insights, seleziona **Sistema** > **Diagnostica** per vedere le destinazioni di diagnostica configurate per questa istanza.

1. Seleziona **Aggiungi destinazione**.

   > [!div class="mx-imgBorder"]
   > ![Connessione diagnostica](media/diagnostics-pane.png "Connessione diagnostica")

1. Fornire un nome nel campo **Nome per la destinazione della diagnostica**.

1. Scegli il **Tenant** della sottoscrizione di Azure con la risorsa di destinazione e seleziona **Accedi**.

1. Seleziona il **Tipo di risorsa** (Account di archiviazione, Hub eventi o analisi dei log).

1. Seleziona la **sottoscrizione** per la risorsa di destinazione.

1. Seleziona il **gruppo risorse** per la risorsa di destinazione.

1. Seleziona **Risorsa**.

1. Conferma l'affermazione **Conformità e privacy dei dati**.

1. Seleziona **Connetti al sistema** per connettersi alla risorsa di destinazione. I log iniziano ad apparire nella destinazione dopo 15 minuti, se l'API è in uso e genera eventi.

### <a name="remove-a-destination"></a>Rimuovi una destinazione

1. Vai a **Sistema** > **Diagnostica**.

1. Seleziona la destinazione di diagnostica dall'elenco.

1. Nella colonna **Azioni**, seleziona l'icona **Elimina**.

1. Confermare l'eliminazione per interrompere l'inoltro del registro. La risorsa nella sottoscrizione di Azure non verrà eliminata. È possibile selezionare il collegamento nella colonna **Azioni** per aprire il portale di Azure per la risorsa selezionata ed eliminarla lì.

## <a name="log-categories-and-event-schemas"></a>Categorie di log e schemi di eventi

Attualmente gli [eventi API](apis.md) e gli eventi del flusso di lavoro sono supportati e si applicano alle categorie e agli schemi seguenti.
Lo schema del registro segue lo [schema comune di Monitoraggio di Azure](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Categorie

Customer Insights fornisce due categorie:

- **Eventi di controllo**: [eventi API](#api-event-schema) per tenere traccia delle modifiche alla configurazione del servizio. Le operazioni `POST|PUT|DELETE|PATCH` rientrano in questa categoria.
- **Eventi operativi**: [eventi API](#api-event-schema) o [eventi del flusso di lavoro](#workflow-event-schema) generati durante l'utilizzo del servizio.  Per esempio, le richieste `GET` o gli eventi di esecuzione di un flusso di lavoro.

## <a name="configuration-on-the-destination-resource"></a>Configurazione sulla risorsa di destinazione

In base alla scelta del tipo di risorsa, verranno applicati automaticamente i seguenti passaggi:

### <a name="storage-account"></a>Storage account

L'entità servizio di Customer Insights ottiene l'autorizzazione **Collaboratore account di archiviazione** sulla risorsa selezionata e crea due contenitori nello spazio dei nomi selezionato:

- `insight-logs-audit` contenente **eventi di controllo**
- `insight-logs-operational` contenente **eventi operativi**

### <a name="event-hub"></a>Hub eventi

L'entità servizio di Customer Insights ottiene l'autorizzazione **Proprietario dati hub eventi di Azure** sulla risorsa selezionata e creerà due hub eventi nello spazio dei nomi selezionato:

- `insight-logs-audit` contenente **eventi di controllo**
- `insight-logs-operational` contenente **eventi operativi**

### <a name="log-analytics"></a>Log Analytics

L'entità servizio di Customer Insights ottiene l'autorizzazione **Collaboratore analisi dei log** sulla risorsa. I log saranno disponibili in **Log** > **Tabelle** > **Gestione registri** nell'area di lavoro di Log Analytics selezionata. Espandi la soluzione **Gestione registri** e individua le tabelle `CIEventsAudit` e `CIEventsOperational`.

- `CIEventsAudit` contenente **eventi di controllo**
- `CIEventsOperational` contenente **eventi operativi**

Nella finestra **Query**, espandi la soluzione **Controllo** e individua le query di esempio fornite cercando `CIEvents`.

## <a name="event-schemas"></a>Schemi di eventi

Gli eventi API e gli eventi del flusso di lavoro hanno una struttura comune e dettagli in cui differiscono, vedi [schema dell'evento API](#api-event-schema) o [schema degli eventi del flusso di lavoro](#workflow-event-schema).

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
| `identity`        | String    | Facoltativa          | Oggetto JSON che descrive l'identità dell'utente o dell'applicazione che ha eseguito l'operazione.       | Vedi la sezione [Identità](#identity-schema).     |  |
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
|                 |

#### <a name="workflow-properties-schema"></a>Schema di proprietà di un flusso di lavoro

Gli eventi fi flusso di lavoro hanno le seguenti proprietà.

| Campo              | Workflow | Attività | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Sì      | Sì  | Sempre `WorkflowEvent`, contrassegnando l'evento di flusso di lavoro.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Sì      | Sì  | Identificatore dell'esecuzione del flusso di lavoro. Tutti gli eventi del flusso di lavoro e delle attività all'interno dell'esecuzione del flusso di lavoro hanno lo stesso `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Sì      | Sì  | Identificatore dell'operazione, vedi [Tipi di operazione].(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Sì      | No   | Solo flusso di lavoro. Numero di attività attivate dal flusso di lavoro.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Sì      | No   | (Facoltativo). Solo eventi flusso di lavoro. L'[objectId dell'utente](/azure/marketplace/find-tenant-object-id#find-user-object-id) Azure Active Directory che ha attivato il flusso di lavoro, vedi anche `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Sì      | No   | aggiornamento `full` o `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Sì      | No   | `OnDemand` oppure `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Sì      | No   | `Running` oppure `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Sì      | Sì  | Timestamp UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Sì      | Sì  | Timestamp UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Sì      | Sì  | Timestamp UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Sì      | Sì  | `instanceId` di Customer Insights                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Sì  | - Per OperationType = `Export`, l'identificatore è il guid della configurazione di esportazione. <br> - Per OperationType = `Enrichment`, è il guid dell'arricchimento <br> - Per OperationType `Measures` e `Segmentation`, l'identificatore è il nome dell'entità. |
| `properties.friendlyName`                    | No       | Sì  | Nome descrittivo dell'esportazione o dell'entità che viene elaborata.                                                                                                                                                                                           |
| `properties.error`                           | No       | Sì  | (Facoltativo). Messaggio di errore con maggiori dettagli.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Sì  | (Facoltativo). Per OperationType solo `Export`. Identifica il tipo di esportazione. Per altre informazioni, vedi [panoramica delle destinazioni di esportazione](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Sì  | (Facoltativo). Per OperationType solo `Export`. Contiene un elenco di entità configurate nell'esportazione.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Sì  | (Facoltativo). Per OperationType solo `Export`. Messaggio dettagliato per l'esportazione.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Sì  | (Facoltativo). Per OperationType solo `Segmentation`. Indica il numero totale di membri del segmento.                                                                                                                                                    |
