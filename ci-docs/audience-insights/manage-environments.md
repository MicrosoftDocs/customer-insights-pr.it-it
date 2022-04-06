---
title: Creare e gestire ambienti
description: Scopri come iscriverti al servizio e come gestire gli ambienti.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
  - ci-system-about
  - customerInsights
---

# <a name="manage-environments"></a>Gestisci ambienti

## <a name="switch-environments"></a>Cambiare ambiente

Seleziona il controllo **Ambiente** nell'angolo superiore destro della pagina per modificare gli ambienti.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Screenshot del comando per cambiare ambiente.":::

Gli amministratori possono [creare](create-environment.md) e gestire ambienti.

## <a name="edit-an-existing-environment"></a>Modificare un ambiente esistente

Puoi modificare alcuni dei dettagli degli ambienti esistenti.

1.  Seleziona il selettore **Ambiente** nell'intestazione dell'app.

2.  Seleziona l'icona **Modifica**.

3. Nella casella **Modifica ambiente** , puoi aggiornare le impostazioni dell'ambiente.

Per maggiori informazioni sulle impostazioni dell'ambiente, vedi [Creare un nuovo ambiente](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Connessione a Microsoft Dataverse
   
Il passo **Microsoft Dataverse** permette di collegare Customer Insights con il vostro ambiente Dataverse. 

Fornisci l'ambiente Microsoft Dataverse per condividere dati (profili e informazioni dettagliate) con applicazioni aziendali basate su Dataverse, come Dynamics 365 Marketing o applicazioni basate su modello in Power Apps.

Per utilizzare i [modelli di predizione out-of-box](predictions-overview.md#out-of-box-models), configurare la condivisione dei dati con Dataverse. Oppure puoi abilitare l'ingestione dei dati da fonti di dati on-premises, fornendo l'URL dell'ambiente Microsoft Dataverse che la tua organizzazione amministra.

Se si abilita la condivisione dati con Microsoft Dataverse selezionando la casella di controllo relativa, si attiverà un unico aggiornamento completo delle origini dati e di tutti gli altri processi.

> [!IMPORTANT]
> 1. Customer Insights e Dataverse devono trovarsi nella stessa regione per consentire la condivisione dei dati.
> 1. Devi avere un ruolo globale amministratore nell'ambiente Dataverse. Verifica che questo [ambiente Dataverse sia associato](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinati gruppi di sicurezza e assicurati di essere aggiunto a tali gruppi.
> 1. Nessun ambiente Customer Insights esistente è già associato a questo ambiente Dataverse. Scopri come [rimuovere una connessione esistente in un ambiente Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Opzioni di configurazione per abilitare la condivisione dei dati con Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Abilitare la condivisione dei dati con Dataverse dalla tua istanza di Azure Data Lake Storage (anteprima)

Se il tuo ambiente è configurato per utilizzare la tua istanza di Azure Data Lake Storage per archiviare i dati di Customer Insights, l'abilitazione della condivisione dei dati con Microsoft Dataverse necessita di una configurazione aggiuntiva.

1. Crea due gruppi di sicurezza nella tua sottoscrizione di Azure: un gruppo di sicurezza **Lettore** e un gruppo di sicurezza **Contributore** e impostare il servizio Microsoft Dataverse come proprietario per entrambi i gruppi di sicurezza.
2. Gestisci l'elenco di controllo di accesso nel contenitore CustomerInsights nell'account di archiviazione tramite questi gruppi di sicurezza. Aggiungi il servizio Microsoft Dataverse e qualsiasi applicazione aziendale basata su Dataverse, come Dynamics 365 Marketing al gruppo di sicurezza **Lettore** con autorizzazione di **sola lettura**. Aggiungi *solo* l'applicazione Customers Insights al gruppo di sicurezza **Contributore** per garantire entrambe le autorizzazioni di **lettura e scrittura** per scrivere profili e analisi.
   
#### <a name="prerequisites"></a>Prerequisiti

Per eseguire gli script di PowerShell, è necessario che siano importati i tre moduli seguenti. 

1. Installa l'ultima versione di [Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2).
   1. Nel PC, seleziona il tasto WINDOWS della tastiera e cerca **Windows PowerShell** e seleziona **Esegui come amministratore**.
   1. Nella finestra di PowerShell che si apre, immetti `Install-Module AzureAD`.
2. Importa tre moduli.
    1. Nella finestra di PowerShell, immetti `Install-Module -Name Az.Accounts` e segui la procedura. 
    1. Ripeti i passaggi per `Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Passaggi di configurazione

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
        - Copia la stringa di output dopo aver eseguito correttamente lo script. La stringa di output è simile a questa: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Immetti la stringa di output copiata da quella precedente nel campo **Identificatore autorizzazioni** del passaggio di configurazione ambiente per Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opzioni di configurazione per abilitare la condivisione dei dati da Azure Data Lake Storage con Microsoft Dataverse.":::

Customer Insights non supporta i seguenti scenari di condivisione dei dati:
- Se abiliti la condivisione dei dati con Dataverse, non sarai in grado di [creare valori previsti o mancanti in un'entità](predictions.md).
- Se abiliti la condivisione dei dati con Dataverse, non sarai in grado di visualizzare i report PowerBI Embedded facoltativi nel tuo ambiente Customer Insights.

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

## <a name="copy-the-environment-configuration"></a>Copia la configurazione dell'ambiente

In qualità di amministratore, puoi scegliere di copiare la configurazione da un ambiente esistente quando ne crei uno nuovo. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Screenshot delle opzioni di impostazione nelle impostazioni dell'ambiente.":::

Vedrai un elenco di tutti gli ambienti disponibili nella tua organizzazione da cui puoi copiare i dati.

Le impostazioni di configurazione seguenti vengono copiate:

- Origini dati inserite/importate
- Configurazione di unificazione dei dati (mapping, corrispondenza, unione)
- Segmenti
- Misure
- Relazioni
- Impegni
- Indice di ricerca e filtro
- Destinazioni di esportazione
- Aggiornamento pianificato
- Arricchimenti
- Gestione modelli
- Assegnazioni di ruolo

## <a name="set-up-a-copied-environment"></a>Impostazione di un ambiente copiato

Quando si copia la configurazione dell'ambiente, i seguenti dati *non* sono copiati:

- Profili cliente.
- Credenziali origine dati. Dovrai fornire le credenziali per ogni origine dati e aggiornare manualmente le origini dati.
- Origini dati dalla cartella Common Data Model e dal data lake gestito di Dataverse. Dovrai creare tali origini dati manualmente con lo stesso nome dell'ambiente di origine.
- Segreti di connessione utilizzati per le esportazioni e gli arricchimenti. Devi riautenticare le connessioni e poi riattivare gli arricchimenti e le esportazioni. 

Quando copi un ambiente, vedrai un messaggio di conferma che il nuovo ambiente è stato creato. Seleziona **Vai a origini dati** per visualizzare l'elenco delle origini dati.

Tutte le origini dati mostreranno uno stato **Credenziali obbligatorie**. Modifica le origini dati e inserisci le credenziali per aggiornarle.

:::image type="content" source="media/data-sources-copied.png" alt-text="Elenco delle origini dati che sono state copiate e richiedono l'autenticazione.":::

Dopo aver aggiornato le origini dati, vai a **Dati** > **Unifica**. Qui troverai le impostazioni dall'ambiente di origine. Modificale in base alle necessità o seleziona **Esegui** per avviare il processo di unificazione dei dati e creare l'entità cliente unificata.

Quando l'unificazione dei dati è completa, vai a **Misure** e **Segmenti** per aggiornarli.

Prima di riattivare esportazioni e arricchimenti, vai a **Amministratore** > **Connessioni** per riautenticare le connessioni nel nuovo ambiente.

## <a name="change-the-owner-of-an-environment"></a>Cambiare il proprietario di un ambiente

Sebbene diversi utenti possano disporre delle autorizzazioni di amministratore in Customer Insights, solo un utente è il proprietario di un ambiente. Per impostazione predefinita, è l'amministratore che crea inizialmente un ambiente. In qualità di amministratore di un ambiente, puoi assegnare la proprietà a un altro utente con autorizzazioni di amministratore.

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona l'icona **Modifica**.

1. Nella casella **Modifica ambiente** vai al passaggio **Informazioni di base**.

1. Nel campo **Cambia proprietario dell'ambiente** scegli il nuovo proprietario dell'ambiente.  

1. Seleziona **Verifica e termina** e poi **Aggiorna** per applicare le modifiche. 

## <a name="claim-ownership-of-an-environment"></a>Rivendicare la proprietà di un ambiente

Se il proprietario di un ambiente lascia l'organizzazione o il suo account utente viene eliminato, l'ambiente non avrà alcun proprietario. Un utente con autorizzazioni di amministratore può rivendicare la proprietà e diventare il nuovo proprietario. Può continuare a essere il proprietario dell'ambiente o [passare la proprietà a un altro amministratore](#change-the-owner-of-an-environment). 

Per rivendicare la proprietà, seleziona il pulsante **Diventa proprietario** visualizzato nella parte superiore di ogni pagina di Customer Insights quando il proprietario originale lascia l'organizzazione.

## <a name="reset-an-existing-environment"></a>Reimpostare un ambiente esistente

In qualità di proprietario di un ambiente, puoi reimpostare un ambiente su uno stato vuoto se desideri eliminare tutte le configurazioni e rimuovere i dati inseriti.

1.  Seleziona il selettore **Ambiente** nell'intestazione dell'app. 

2.  Seleziona l'ambiente che desideri reimpostare, quindi i puntini di sospensione (**...**). 

3. Scegli l'opzione **Reimposta**. 

4.  Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Reimposta**.

## <a name="delete-an-existing-environment"></a>Eliminare un ambiente esistente

In qualità di proprietario di un ambiente, puoi eliminare un ambiente che amministri.

1.  Seleziona il selettore **Ambiente** nell'intestazione dell'app.

2.  Seleziona l'ambiente che desideri reimpostare, quindi i puntini di sospensione (**...**). 

3. Scegli l'opzione **Elimina**. 

4.  Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Elimina**.

> [!NOTE]
> L'eliminazione di un ambiente non rimuove l'associazione a un ambiente Dataverse. Scopri come [rimuovere una connessione esistente a un ambiente Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
