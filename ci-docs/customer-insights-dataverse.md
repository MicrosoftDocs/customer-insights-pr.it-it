---
title: Utilizzare i dati di Customer Insights in Microsoft Dataverse
description: Scopri come collegare Customer Insights e Microsoft Dataverse e comprendi le entità di output che vengono esportate in Dataverse.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153409"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Utilizzare i dati di Customer Insights in Microsoft Dataverse

Customer Insights offre la possibilità di rendere disponibili le entità di output come [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Questa integrazione consente una facile condivisione dei dati e sviluppo personalizzato con un approccio a uso limitato di codice/senza codice. Le [entità di output](#output-entities) sono disponibili come tabelle in un ambiente Dataverse. È possibile utilizzare i dati per qualsiasi altra applicazione basata su tabelle Dataverse. Queste tabelle consentono scenari come flussi di lavoro automatizzati tramite Power Automate o di creare app con Power Apps.

La connessione al tuo ambiente Dataverse ti consente anche di [inserire i dati dalle origini dati locali utilizzando flussi di dati e gateway Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Prerequisiti

- Gli ambiente Customer Insights e Dataverse devono essere ospitati nella stessa area.
- Devi avere un ruolo globale amministratore nell'ambiente Dataverse. Verifica che questo [ambiente Dataverse sia associato](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinati gruppi di sicurezza e assicurati di essere aggiunto a tali gruppi.
- Nessun altro ambiente Customer Insights è già associato all'ambiente Dataverse che vuoi connettere. Scopri come [rimuovere una connessione esistente in un ambiente Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Un ambiente Microsoft Dataverse può connettersi solo a un singolo account di archiviazione. Si applica solo se si configura l'ambiente per [usare il tuo Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Diritto per capacità di archiviazione di Dataverse

Un abbonamento a Customer Insights ti dà diritto di disporre di capacità extra oltre alla [capacità di archiviazione di Dataverse](/power-platform/admin/capacity-storage) esistente della tua organizzazione. La capacità aggiunta dipende dal numero di profili utilizzati dall'abbonamento.

**Esempio:**

Supponiamo che hai a disposizione 15 GB di spazio di archiviazione per database e 20 GB di spazio di archiviazione per file ogni 100.000 profili cliente. Se l'abbonamento include 300.000 profili cliente, la capacità di archiviazione totale sarebbe di 45 GB (3 x 15 GB) di spazio di archiviazione per database e 60 GB di spazio di archiviazione per file (3 x 20 GB). Allo stesso modo, se hai un abbonamento B2B con 30.000 account, la tua capacità di archiviazione totale sarebbe di 45 GB (3 x 15 GB) di spazio di archiviazione per database e 60 GB di spazio archiviazione per file (3 x 20 GB).

La capacità del registro non è incrementale e fissa per la tua organizzazione.

Per ulteriori informazioni sui diritti per capacità di archiviazione, vedi [Guida alle licenze di Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Connessione di un ambiente Dataverse a Customer Insights

Il passaggio **Microsoft Dataverse** ti consente di connettere Customer Insights con il tuo ambiente Dataverse mentre [crei un ambiente Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="condivisione dei dati con Microsoft Dataverse abilitata automaticamente per nuovi ambienti.":::

Gli amministratori possono configurare Customer Insights per connettere un ambiente Dataverse esistente. Fornendo l'URL all'ambiente Dataverse, si esegue la connessione al nuovo ambiente Customer Insights. Dopo aver stabilito la connessione tra Customer Insights e Dataverse, non modificare il nome dell'organizzazione per l'ambiente Dataverse. Il nome dell'organizzazione è utilizzato nell'URL Dataverse e un nome modificato interrompe la connessione con Customer Insights.

Se non si desidera usare un ambiente Dataverse esistente, il sistema crea un nuovo ambiente per i dati di Customer Insights nel tenant in uso. [Gli amministratori Power Platform possono controllare chi può creare gli ambienti](/power-platform/admin/control-environment-creation). Quando stai configurando un nuovo ambiente Customer Insights e l'amministratore ha disabilitato la creazione di ambienti Dataverse per tutti tranne gli amministratori, potresti non essere in grado di creare un nuovo ambiente.

**Abilita la condivisione dei dati** con Dataverse selezionando la casella di controllo della condivisione dei dati.

Se stai usando il tuo account Data Lake Storage, hai anche bisogno dell'**Identificatore delle autorizzazioni**. Per ulteriori informazioni su come ottenere l'identificatore di autorizzazione, consulta la sezione seguente.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Abilitare la condivisione dei dati con Dataverse dalla tua istanza di Azure Data Lake Storage (anteprima)

L'abilitazione della condivisione dei dati con Microsoft Dataverse quando il tuo ambiente [usa l'account Azure Data Lake Storage](own-data-lake-storage.md) necessita di una configurazione extra. L'utente che configura l'ambiente Customer Insights deve avere almeno le autorizzazioni **Lettore dati del BLOB di archiviazione** per il contenitore *CustomerInsights* nell'account Azure Data Lake Storage.

1. Crea due gruppi di sicurezza nella tua sottoscrizione di Azure: un gruppo di sicurezza **Lettore** e un gruppo di sicurezza **Contributore** e impostare il servizio Microsoft Dataverse come proprietario per entrambi i gruppi di sicurezza.
2. Gestisci l'elenco di controllo di accesso nel contenitore CustomerInsights nell'account di archiviazione tramite questi gruppi di sicurezza. Aggiungi il servizio Microsoft Dataverse e qualsiasi applicazione aziendale basata su Dataverse, come Dynamics 365 Marketing al gruppo di sicurezza **Lettore** con autorizzazione di **sola lettura**. Aggiungi *solo* l'applicazione Customers Insights al gruppo di sicurezza **Contributore** per garantire entrambe le autorizzazioni di **lettura e scrittura** per scrivere profili e analisi.

### <a name="limitations"></a>Limiti

Ci sono due limitazioni durante l'utilizzo Dataverse con il tuo account Azure Data Lake Storage:

- C'è un mapping uno-a-uno tra un'organizzazione Dataverse e un account Azure Data Lake Storage. Una volta che un'organizzazione Dataverse è connessa a un account di archiviazione, non può connettersi a un altro account di archiviazione. Questa limitazione impedisce a Dataverse di popolare più account di archiviazione.
- La condivisione dei dati non funzionerà se è necessaria una configurazione del collegamento privato di Azure per accedere all'account di Azure Data Lake Storage perché è protetto da un firewall. Dataverse attualmente non supporta la connessione a endpoint privati tramite collegamento privato.

### <a name="set-up-powershell"></a>Configurare PowerShell

Per eseguire gli script di PowerShell, devi prima configurare PowerShell di conseguenza.

1. Installa l'ultima versione di [Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2).
   1. Nel PC, seleziona il tasto WINDOWS della tastiera e cerca **Windows PowerShell** e seleziona **Esegui come amministratore**.
   1. Nella finestra di PowerShell che si apre, immetti `Install-Module AzureAD`.
2. Importa tre moduli.
    1. Nella finestra di PowerShell, immetti `Install-Module -Name Az.Accounts` e segui la procedura.
    1. Ripeti i passaggi per `Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Passaggi di configurazione

1. Scarica i due script di PowerShell che devi eseguire dai [repository GitHub](https://github.com/trin-msft/byol) dei tecnici.
    1. `CreateSecurityGroups.ps1`
       - Per eseguire lo script di PowerShell, devi disporre delle autorizzazioni di *amministratore di tenant*.
       - Questo script di PowerShell crea due gruppi di sicurezza nella sottoscrizione di Azure. Un gruppo di sicurezza è per il gruppo Lettore, l'altro è per il gruppo Contributore, mentre il servizio Microsoft Dataverse verrà reso proprietario di entrambi i gruppi di sicurezza.
       - Esegui questo script di PowerShell in Windows PowerShell fornendo l'ID della sottoscrizione di Azure contenente la tua istanza di Azure Data Lake Storage. Aprire lo script di PowerShell in un editor per esaminare informazioni aggiuntive e la logica implementata.
       - Salva entrambi i valori dell'ID dei gruppi di sicurezza generati dallo script perché li useremo nello script `ByolSetup.ps1`.

        > [!NOTE]
        > La creazione dei gruppi di sicurezza può essere disabilitata sul tenant. In tal caso, sarebbe necessaria una configurazione manuale e l'amministratore di Azure AD dovrebbe [abilitare la creazione di gruppi di sicurezza](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Per eseguire lo script, hai bisogno dell'autorizzazione *Proprietario dati BLOB di archiviazione* a livello di account di archiviazione/contenitore. In caso contrario, lo script ne creerà uno per te. L'assegnazione del ruolo può essere rimossa manualmente dopo aver eseguito correttamente lo script.
        - Questo script di PowerShell aggiunge il controllo degli accessi in base al ruolo richiesto per il servizio Microsoft Dataverse e per eventuali applicazioni aziendali basate su Dataverse. Aggiorna inoltre l'elenco di controllo di accesso nel contenitore CustomerInsights per i gruppi di sicurezza creati con lo script `CreateSecurityGroups.ps1`. Il gruppo Contributore avrà l'autorizzazione *rwx*, mentre il gruppo Lettore avrà solo l'autorizzazione *r-x*.
        - Esegui questo script di PowerShell in Windows PowerShell fornendo l'ID della sottoscrizione di Azure contenente la tua istanza di Azure Data Lake Storage, il nome dell'account di archiviazione, il nome del gruppo di risorse e i valori dell'ID del gruppo di sicurezza Lettore e Contributore. Aprire lo script di PowerShell in un editor per esaminare informazioni aggiuntive e la logica implementata.
        - Copia la stringa di output dopo aver eseguito correttamente lo script. La stringa di output è simile a questa: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Immetti la stringa di output copiata da quella precedente nel campo **Identificatore autorizzazioni** del passaggio di configurazione ambiente per Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opzioni di configurazione per abilitare la condivisione dei dati da Azure Data Lake Storage con Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Rimuovere una connessione esistente in un ambiente Dataverse

Quando ci si connette a un ambiente Dataverse, il messaggio di errore **Questa organizzazione CDS è già collegata a un'altra istanza di Customer Insights** indica che l'ambiente Dataverse è già utilizzato in un ambiente Customer Insights. Puoi rimuovere la connessione esistente come amministratore globale nell'ambiente Dataverse. Possono essere necessarie un paio d'ore per popolare le modifiche.

1. Passa a [Power Apps](https://make.powerapps.com).
1. Seleziona l'ambiente nel selettore di ambienti.
1. Vai a **Soluzioni**
1. Disinstalla o elimina la soluzione denominata **Componente aggiuntivo scheda cliente di Dynamics 365 Customer Insights (anteprima)**.

OPPURE

1. Apri il tuo ambiente Dataverse.
1. Vai a **Impostazioni avanzate** > **Soluzioni**.
1. Disinstalla la soluzione **CustomerInsightsCustomerCard**.

Se la rimozione della connessione non riesce a causa delle dipendenze, è necessario rimuovere anche le dipendenze. Per ulteriori informazioni, vedi [Rimozione delle dipendenze](/power-platform/alm/removing-dependencies).

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
| SemanticData      | Stringa JSON | Include un elenco di coppie chiave-valore per campi di mapping semantico specifici per il tipo di attività |
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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
