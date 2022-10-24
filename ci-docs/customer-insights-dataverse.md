---
title: Utilizzare i dati di Customer Insights in Microsoft Dataverse
description: Scopri come collegare Customer Insights e Microsoft Dataverse e comprendi le entità di output che vengono esportate in Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671256"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Utilizzare i dati di Customer Insights in Microsoft Dataverse

Customer Insights offre la possibilità di rendere disponibili entità di output in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Questa integrazione consente una facile condivisione dei dati e sviluppo personalizzato con un approccio a uso limitato di codice/senza codice. Le [entità di output](#output-entities) sono disponibili come tabelle in un ambiente Dataverse. È possibile utilizzare i dati per qualsiasi altra applicazione basata su tabelle Dataverse. Queste tabelle consentono scenari come flussi di lavoro automatizzati tramite Power Automate o di creare app con Power Apps.

La connessione al tuo ambiente Dataverse ti consente anche di [inserire i dati dalle origini dati locali utilizzando flussi di dati e gateway Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Prerequisiti

- Gli ambiente Customer Insights e Dataverse devono essere ospitati nella stessa area.
- Deve essere configurato un ruolo di amministratore globale nell'ambiente Dataverse. Verifica che questo [ambiente Dataverse sia associato](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinati gruppi di sicurezza e assicurati di essere aggiunto a tali gruppi.
- Nessun altro ambiente Customer Insights è già associato all'ambiente Dataverse che vuoi connettere. Scopri come [rimuovere una connessione esistente in un ambiente Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Un ambiente Microsoft Dataverse connesso a un singolo account di archiviazione se si configura l'ambiente su [Usa il tuo Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Diritto per capacità di archiviazione di Dataverse

Un abbonamento a Customer Insights ti dà diritto di disporre di capacità extra oltre alla [capacità di archiviazione di Dataverse](/power-platform/admin/capacity-storage) esistente della tua organizzazione. La capacità aggiunta dipende dal numero di profili utilizzati dall'abbonamento.

**Esempio:**

Supponiamo che hai a disposizione 15 GB di spazio di archiviazione per database e 20 GB di spazio di archiviazione per file ogni 100.000 profili cliente. Se l'abbonamento include 300.000 profili cliente, la capacità di archiviazione totale è di 45 GB (3 x 15 GB) per l'archiviazione del database e 60 GB per l'archiviazione di file (3 x 20 GB). Allo stesso modo, se disponi di un abbonamento B2B con 30.000 account, la capacità di archiviazione totale è di 45 GB (3 x 15 GB) per l'archiviazione di database e di 60 GB per l'archiviazione di file (3 x 20 GB).

La capacità del registro non è incrementale e fissa per la tua organizzazione.

Per ulteriori informazioni sui diritti per capacità di archiviazione, vedi [Guida alle licenze di Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Connessione di un ambiente Dataverse a Customer Insights

Il passaggio **Microsoft Dataverse** ti consente di connettere Customer Insights con il tuo ambiente Dataverse mentre [crei un ambiente Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="condivisione dei dati con Microsoft Dataverse abilitata automaticamente per nuovi ambienti.":::

1. Fornisci l'URL al tuo ambiente Dataverse o lascia vuoto per averne uno creato per te.

   > [!NOTE]
   > Dopo aver stabilito la connessione tra Customer Insights e Dataverse, non modificare il nome dell'organizzazione per l'ambiente Dataverse. Il nome dell'organizzazione è utilizzato nell'URL Dataverse e un nome modificato interrompe la connessione con Customer Insights.

   [Gli amministratori di Power Platform possono controllare chi può creare nuovi ambienti Dataverse](/power-platform/admin/control-environment-creation). Se stai cercando di configurare un nuovo ambiente Customer Insights e non riesci, l'amministratore potrebbe aver disabilitato la creazione di ambienti Dataverse per tutti tranne gli amministratori.

1. Se stai usando il tuo account Data Lake Storage:
   1. Seleziona **Abilita la condivisione dei dati** con Dataverse.
   1. Immetti l'**Identificatore autorizzazioni**. Per ottenere l'identificatore delle autorizzazioni, [abilita la condivisione dei dati con Dataverse dal tuo Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Abilitare la condivisione dei dati con Dataverse dalla tua istanza di Azure Data Lake Storage (anteprima)

Nel [tuo account Azure Data Lake Storage](own-data-lake-storage.md), verifica che l'utente che sta configurando l'ambiente Customer Insights disponga almeno delle autorizzazioni **Lettore dati BLOB di archiviazione** nel container `customerinsights` nell'account di archiviazione.

> [!NOTE]
> La condivisione dei dati è applicabile solo se utilizzi il tuo account Azure Data Lake Storage. Questa impostazione non è disponibile se l'ambiente Customer Insights utilizza l'archiviazione Dataverse predefinita.

### <a name="limitations"></a>Limiti

- C'è solo un mapping uno-a-uno tra un'organizzazione Dataverse e un account Azure Data Lake Storage. Una volta che un'organizzazione Dataverse è connessa a un account di archiviazione, non può connettersi a un altro account di archiviazione. Questa limitazione impedisce a Dataverse di popolare più account di archiviazione.
- La condivisione dei dati non funzionerà se è necessaria una configurazione del collegamento privato di Azure per accedere all'account di Azure Data Lake Storage perché è protetto da un firewall. Dataverse attualmente non supporta la connessione a endpoint privati tramite collegamento privato.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Configura i gruppi di sicurezza da Azure Data Lake Storage

1. Crea due gruppi di sicurezza nella tua sottoscrizione di Azure: un gruppo di sicurezza **Lettore** e un gruppo di sicurezza **Contributore** e impostare il servizio Microsoft Dataverse come proprietario per entrambi i gruppi di sicurezza.

1. Gestisci l'elenco di controllo di accesso nel contenitore `customerinsights` nell'account di archiviazione tramite questi gruppi di sicurezza.
   1. Aggiungi il servizio Microsoft Dataverse e qualsiasi applicazione aziendale basata su Dataverse, come Dynamics 365 Marketing al gruppo di sicurezza **Lettore** con autorizzazione di **sola lettura**.
   1. Aggiungi *solo* l'applicazione Customers Insights al gruppo di sicurezza **Contributore** per garantire entrambe le autorizzazioni di **lettura e scrittura** per scrivere profili e analisi.

### <a name="set-up-powershell"></a>Configurare PowerShell

Configura PowerShell per eseguire gli script di PowerShell.

1. Installa l'ultima versione di [Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2).
   1. Nel PC, seleziona il tasto WINDOWS della tastiera e cerca **Windows PowerShell** e seleziona **Esegui come amministratore**.
   1. Nella finestra di PowerShell che si apre, immetti `Install-Module AzureAD`.

1. Importa tre moduli.
   1. Nella finestra di PowerShell, immetti `Install-Module -Name Az.Accounts` e segui la procedura.
   1. Ripeti i passaggi per `Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Esegui gli script di PowerShell e ottieni l'identificatore dell'autorizzazione

1. Scarica i due script di PowerShell che devi eseguire dai [repository GitHub](https://github.com/trin-msft/byol) dei tecnici.
   - `CreateSecurityGroups.ps1`: sono necessarie le autorizzazioni di amministratore del tenant.
   - `ByolSetup.ps1`: richiede le autorizzazioni di proprietario dei dati del BLOB di archiviazione a livello di account di archiviazione o del contenitore. Questo script creerà l'autorizzazione per te. L'assegnazione del ruolo può essere rimossa manualmente dopo aver eseguito correttamente lo script.

1. Esegui `CreateSecurityGroups.ps1` in Windows PowerShell fornendo l'ID della sottoscrizione di Azure contenente la tua istanza di Azure Data Lake Storage. Apri lo script di PowerShell in un editor per esaminare informazioni aggiuntive e la logica implementata.

   Questo script crea due gruppi di sicurezza nella sottoscrizione di Azure: uno per il gruppo Lettore e un altro per il gruppo Collaboratore. Il servizio di Microsoft Dataverse è il proprietario di entrambi questi gruppi di sicurezza.

1. Salva entrambi i valori dell'ID dei gruppi di sicurezza generati dallo script perché li useremo nello script `ByolSetup.ps1`.

   > [!NOTE]
   > La creazione dei gruppi di sicurezza può essere disabilitata sul tenant. In tal caso, sarebbe necessaria una configurazione manuale e l'amministratore di Azure AD dovrebbe [abilitare la creazione di gruppi di sicurezza](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Esegui `ByolSetup.ps1` in Windows PowerShell fornendo l'ID della sottoscrizione di Azure contenente la tua istanza di Azure Data Lake Storage, il nome dell'account di archiviazione, il nome del gruppo di risorse e i valori dell'ID del gruppo di sicurezza Lettore e Contributore. Apri lo script di PowerShell in un editor per esaminare informazioni aggiuntive e la logica implementata.

   Questo script aggiunge il controllo degli accessi in base al ruolo richiesto per il servizio Microsoft Dataverse e per eventuali applicazioni aziendali basate su Dataverse. Aggiorna inoltre l'elenco di controllo di accesso nel contenitore `customerinsights` per i gruppi di sicurezza creati con lo script `CreateSecurityGroups.ps1`. Il gruppo Collaboratore avrà l'autorizzazione *rwx*, mentre il gruppo Lettore avrà solo l'autorizzazione *r-x*.

1. Copia la stringa di output simile a questa: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Immetti la stringa di output copiata nel campo **Identificatore autorizzazioni** del passaggio di configurazione ambiente per Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opzioni di configurazione per abilitare la condivisione dei dati da Azure Data Lake Storage con Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Rimuovere una connessione esistente in un ambiente Dataverse

Quando ci si connette a un ambiente Dataverse, il messaggio di errore **Questa organizzazione CDS è già collegata a un'altra istanza di Customer Insights** indica che l'ambiente Dataverse è già utilizzato in un ambiente Customer Insights. Puoi rimuovere la connessione esistente come amministratore globale nell'ambiente Dataverse. Possono essere necessarie un paio d'ore per popolare le modifiche.

1. Passa a [Power Apps](https://make.powerapps.com).
1. Seleziona l'ambiente nel selettore di ambienti.
1. Andare a **Soluzioni**.
1. Disinstalla o elimina la soluzione denominata **Componente aggiuntivo scheda cliente di Dynamics 365 Customer Insights (anteprima)**.

OPPURE

1. Apri il tuo ambiente Dataverse.
1. Vai a **Impostazioni avanzate** > **Soluzioni**.
1. Disinstalla la soluzione **CustomerInsightsCustomerCard**.

Se la rimozione della connessione non riesce a causa delle dipendenze, è necessario rimuovere anche le dipendenze. Per ulteriori informazioni, vedi [Rimozione delle dipendenze](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entità di output

Alcune entità di output di Customer Insights sono disponibili come tabelle in Dataverse. Le sezioni seguenti descrivono lo schema previsto di queste tabelle.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Arricchimento](#enrichment)
- [Previsione](#prediction)
- [Appartenenza al segmento](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Questa tabella contiene il profilo cliente unificato di Customer Insights. Lo schema per un profilo cliente unificato dipende dalle entità e dagli attributi utilizzati nel processo di unificazione dei dati. Uno schema del profilo del cliente di solito contiene un sottoinsieme degli attributi dalla [Definizione del Common Data Model di CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Per lo scenario B2B, il profilo del cliente contiene account unificati e lo schema in genere contiene un sottoinsieme degli attributi dalla [Definizione di Common Data Model dell'account](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

Un ContactProfile contiene informazioni unificate su un contatto. I contatti sono [individui mappati su un account](data-unification-contacts.md) in uno scenario B2B.

| Column                       | Type                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  BirthDate            | Data/Ora       |  Data di nascita del contatto               |
|  City                 | Testo |  Città dell'indirizzo del contatto               |
|  ContactId            | Testo |  ID del profilo del contatto               |
|  ContactProfileId     | Identificatore univoco   |  GUID per il contatto               |
|  CountryOrRegion      | Testo |  Paese/area geografica dell'indirizzo del contatto               |
|  Customerid           | Testo |  ID dell'account su cui il contatto è mappato               |
|  EntityName           | Testo |  Entità da cui provengono i dati                |
|  FirstName            | Testo |  Nome del contatto               |
|  Sesso               | Testo |  Sesso del contatto               |
|  ID.                   | Testo |  GUID deterministico basato su `Identifier`               |
|  Identificatore           | Testo |  ID interno del profilo del contatto: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Testo |  Posizione del contatto               |
|  LastName             | Testo |  Cognome del contatto               |
|  PostalCode           | Testo |  Codice ZIP dell'indirizzo del contatto               |
|  PrimaryEmail         | Testo |  Indirizzo e-mail del contatto               |
|  PrimaryPhone         | Testo |  Numero di telefono del contatto               |
|  StateOrProvince      | Testo |  Stato o provincia dell'indirizzo del contatto               |
|  StreetAddress        | Testo |  Via dell'indirizzo del contatto               |

### <a name="alternatekey"></a>AlternateKey

La tabella AlternateKey contiene le chiavi delle entità che hanno partecipato al processo di unificazione.

|Column  |Type  |Description  |
|---------|---------|---------|
|DataSourceName    |Testo         | Nome origine dati. Ad esempio: `datasource5`        |
|EntityName        | Testo        | Nome dell'entità in Customer Insights. Ad esempio: `contact1`        |
|AlternateValue    |Testo         |ID alternativo mappato all'ID cliente. Esempio: `cntid_1078`         |
|KeyRing           | Testo        | Valore JSON  </br> Esempio: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|Customerid         | Testo        | ID del profilo cliente unificato.         |
|AlternateKeyId     | Identificatore univoco        |  AlternateKey deterministico basato su `Identifier`      |
|Identificatore |   Testo      |   `DataSourceName|EntityName|AlternateValue`  </br> Esempio: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Questa tabella contiene le attività degli utenti disponibili in Customer Insights.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Customerid        | Testo      | ID profilo cliente                                                                      |
| ActivityId        | Testo      | ID interno dell'attività del cliente (chiave primaria)                                       |
| SourceEntityName  | Testo      | Nome dell'entità di origine                                                                |
| SourceActivityId  | Testo      | Chiave primaria dall'entità di origine                                                       |
| ActivityType      | Testo      | Tipo di attività semantica o nome dell'attività personalizzata                                        |
| ActivityTimeStamp | Data/Ora    | Timestamp impegno                                                                      |
| Title             | Testo      | Titolo o nome dell'impegno                                                               |
| Description       | Testo      | Descrizione impegno                                                                     |
| URL               | Testo      | Collegamento a un URL esterno specifico per l'impegno                                         |
| SemanticData      | Testo | Include un elenco di coppie chiave-valore per campi di mapping semantico specifici per il tipo di attività |
| RangeIndex        | Testo      | Timestamp Unix utilizzato per ordinare la sequenza temporale dell'attività e le query sull'intervallo effettivo |
| UnifiedActivityId   | Identificatore univoco | ID interno dell'attività del cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Questa tabella contiene i dati di output delle misure basate sugli attributi del cliente.

| Column             | Type             | Description                 |
|--------------------|------------------|-----------------------------|
| Customerid         | Testo           | ID profilo cliente        |
| Misure           | Testo      | Include un elenco di coppie di valori chiave per il nome della misura e i valori per il cliente specificato |
| Identificatore | Testo           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Identificatore univoco     | ID profilo cliente |

### <a name="enrichment"></a>Arricchimento

Questa tabella contiene l'output del processo di arricchimento.

| Column               | Type             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| Customerid           | Testo           | ID profilo cliente                                 |
| EnrichmentProvider   | Testo           | Nome del provider per l'arricchimento                                  |
| EnrichmentType       | Testo           | Tipo di arricchimento                                      |
| Valori               | Testo      | Elenco degli attributi prodotti dal processo di arricchimento |
| EnrichmentId | Identificatore univoco            | GUID deterministico generato da `Identifier` |
| Identificatore   | Testo           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Stima

Questa tabella contiene l'output delle previsioni del modello.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| Customerid           | Testo      | ID profilo cliente                                  |
| ModelProvider        | Testo      | Nome del provider del modello                                      |
| Modello                | Testo      | Nome modello                                                |
| Valori               | Testo | Elenco degli attributi prodotti dal modello |
| PredictionId | Identificatore univoco       | GUID deterministico generato da `Identifier` |
| Identificatore   | Testo      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Appartenenza al segmento

Questa tabella contiene le informazioni sull'appartenenza al segmento dei profili cliente.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| Customerid        | Testo       | ID profilo cliente        |
| SegmentProvider      | Testo       | App che pubblica i segmenti.      |
| SegmentMembershipType | Testo       | Tipo di cliente per questo record di appartenenza al segmento. Supporta più tipi come Cliente, Contatto o Account. Impostazione predefinita: cliente  |
| Segments       | Testo  | Elenco dei segmenti univoci di cui il profilo cliente è membro      |
| Identificatore  | Testo   | Identificatore univoco del record di appartenenza al segmento. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Identificatore univoco      | GUID deterministico generato da `Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
