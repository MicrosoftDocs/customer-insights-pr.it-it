---
title: Funzionalità nuove e future
description: 'Informazioni su nuove funzionalità, miglioramenti e correzioni di bug.'
ms.date: 01/27/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
---

# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novità della funzionalità Informazioni dettagliate sul gruppo di destinatari di Dynamics 365 Customer Insights



Siamo lieti di annunciare i nuovissimi aggiornamenti. Questo articolo riassume le funzionalità con anteprima pubblica, i miglioramenti della disponibilità generale e gli aggiornamenti delle funzionalità. Per vedere i piani delle funzionalità a lungo termine, dai un'occhiata ai [piani di rilascio di Dynamics 365 e Power Platform](/dynamics365/release-plans/).

Gli aggiornamenti vengono implementati in base all'area geografica. Quindi alcune aree geografiche potrebbero vedere le funzionalità prima di altre. Se non diversamente specificato, non è necessario intraprendere alcuna azione e l'app viene aggiornata automaticamente senza tempi di inattività.

> [!TIP]
> Per inviare e votare funzionalità richieste e suggerimenti di prodotto, vai al [portale Ideas dell'applicazione Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="december-2021-updates"></a>Aggiornamenti di dicembre 2021

Gli aggiornamenti di dicembre 2021 includono nuove funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Inoltrare i log di Customer Insights a Monitoraggio di Azure

Customer Insights fornisce un'integrazione diretta con Monitoraggio di Azure. Questa funzionalità include eventi di controllo ed eventi operativi. I log delle risorse di Monitoraggio di Azure consentono di monitorare e inviare i log ad Archiviazione di Azure, Azure Log Analytics o di trasmetterli in streaming su Hub eventi di Azure.

Per altre informazioni, vedi [Inoltro del log in Dynamics 365 Customer Insights con Monitoraggio di Azure (anteprima)](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Arricchire i profili dei clienti con i dati sull'interazione

Usa i dati di Microsoft Office 365 per arricchire i profili del tuo account cliente con approfondimenti sul coinvolgimento attraverso app di Office 365. I dati sull'interazione sono costituiti da e-mail e attività di riunione, che vengono aggregati a livello di account. Ad esempio, il numero di e-mail da un account aziendale o il numero di riunioni con l'account. Non vengono condivisi dati sui singoli utenti. Questo arricchimento è disponibile solo nelle aree: UK, Europa e Nord America.

Per altre informazioni, vedi [Arricchire i profili dei clienti con i dati sull'interazione (anteprima)](enrichment-office.md)

### <a name="advanced-data-unification-features"></a>Funzionalità avanzate di unificazione dei dati

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Abilitare i criteri di risoluzione dei conflitti a livello di singolo attributo

Quando si deduplicano i record dei clienti all'interno di un'entità, potrebbe non essere necessario scegliere un record completo come vincitore. Ora è possibile unire i campi migliori da vari record in base a regole per ogni attributo. Ad esempio, puoi scegliere di conservare il messaggio e-mail più recente E l'indirizzo più completo da record diversi. 

Puoi ora definire regole di unione separate per i singoli attributi durante la deduplicazione e l'unione di record all'interno di una singola entità. In precedenza, veniva consentito di selezionare solo una singola regola di unione (conservando i record in base alla completezza dei dati recenti) e tale regola veniva applicata a livello di record a tutti gli attributi. Non è l'ideale quando alcuni dei dati che desideri conservare si trovano nel record A e altri dati validi nel record B.

Per ulteriori informazioni, vedi [Definire la deduplicazione in un'entità di corrispondenza ](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Regole personalizzate per la corrispondenza

Ci sono momenti in cui è necessario specificare un'eccezione alle regole generali per NON far corrispondere i record. Ciò può accadere quando più individui condividono informazioni sufficienti in modo che il sistema li abbini come un singolo individuo. Ad esempio, gemelli con lo stesso cognome, che vivono nella stessa città e condividono la data di nascita.

Le eccezioni garantiscono che l'unificazione errata dei dati possa essere affrontata nelle regole di unificazione. Puoi aggiungere più eccezioni a una regola.

Per altre informazioni, vedi [Aggiungere eccezioni a una regola](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Fornire ulteriori criteri di risoluzione dei conflitti e abilitare il raggruppamento degli attributi

Questa funzionalità consente di considerare un gruppo di campi come una singola unità. Ad esempio, se i nostri record contengono i campi Indirizzo1, Indirizzo2, Città, Stato e CAP. Probabilmente non vogliamo unire l'indirizzo 2 di un record diverso, pensando che renderebbe i nostri dati più completi.

Ora puoi combinare un gruppo di campi correlati e applicare un unico criterio di unione al gruppo. 

Per altre informazioni, vedi [Combinare un gruppo di campi](merge-entities.md#combine-a-group-of-fields).


## <a name="november-2021-updates"></a>Aggiornamenti di novembre 2021

Gli aggiornamenti di novembre 2021 includono nuove funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="segment-membership-now-available-in-dataverse"></a>L'appartenenza al segmento è ora disponibile in Dataverse

Le informazioni sull'appartenenza al segmento per i profili dei clienti sono ora disponibili in Dataverse insieme ai profili e agli approfondimenti dei clienti. Le app per le azioni di Dynamics 365 e le app basate su modello possono utilizzare questi dati per cercare i dettagli dell'appartenenza al segmento per un determinato cliente.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Le attività supportano i dettagli a livello di contatto per gli account aziendali

Ora puoi configurare, visualizzare e filtrare le attività per i contatti nelle tempistiche delle attività del tuo account aziendale per capire meglio quali contatti dell'account hanno preso parte ad attività specifiche.

## <a name="october-2021-updates"></a>Aggiornamenti di ottobre 2021

Gli aggiornamenti di ottobre 2021 includono nuove funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="b-to-b"></a>B2B

A partire da ottobre 2021, puoi usare gli account aziendali e i relativi contatti in Customer Insights. In precedenza, l'app era principalmente adatta ai singoli consumatori. Diverse aree di funzionalità sono state aggiornate per supportare scenari B2B oltre a un nuovo tipo di ambiente. Per una panoramica sulle funzionalità B2B supportate, vedi [Lavorare con gli account aziendali nelle informazioni dettagliate sul gruppo di destinatari](work-with-business-accounts.md).

Le sezioni seguenti evidenziano alcune delle aree chiave che sono state adattate per supportare gli account aziendali e i singoli consumatori.

#### <a name="export-segments-based-on-business-accounts"></a>Esportare i segmenti in base agli account aziendali

Tutte le esportazioni di segmenti nelle informazioni dettagliate sul gruppo di destinatari sono disponibili nel contesto degli account aziendali. La maggior parte delle esportazioni di segmenti richiede una configurazione aggiuntiva e [informazioni di contatto previste](segment-builder.md#create-a-new-segment) nei segmenti sottostanti per essere valide per gli account aziendali. Per altre informazioni, vedi [Esportare segmenti](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Usare l'esportazione degli annunci LinkedIn con gli account aziendali

L'esportazione degli annunci LinkedIn è ora disponibile per il targeting di contatti e di azienda nel contesto degli account aziendali. Quando si seleziona il targeting di azienda come obiettivo principale dell'esportazione di LinkedIn, è possibile esportare i segmenti creati negli account aziendali senza la necessità di proiettare le informazioni di contatto. Per altre informazioni, vai alla documentazione relativa all'[esportazione degli annunci LinkedIn](export-linkedin-ads.md) e alla differenza tra [targeting di contatto](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) e [targeting di azienda](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Creare misure basate sugli account aziendali e sulla loro gerarchia

Il generatore di misure consente di creare misure correlate agli account aziendali e, facoltativamente, di usare le informazioni sulla gerarchia. Le informazioni sulla gerarchia vengono usate per eseguire il rollup di un calcolo di misura in un account e in tutti i relativi account secondari. Puoi ad esempio creare misure come i ricavi totali per ogni gruppo di account aziendali identificati dalla gerarchia. Per ulteriori informazioni, vedi [Definire e gestire misure](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Creare segmenti basati sugli account aziendali e sulla loro gerarchia

Il generatore di segmenti consente di creare segmenti di account aziendali che includono facoltativamente informazioni di contatto per ciascun account in un segmento. Se hai configurato la gerarchia di account, puoi usare le informazioni sulla gerarchia di account nella creazione dei segmenti. Per altre informazioni, vedi [Creare un nuovo segmento](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Conservare gli account aziendali con informazioni approfondite sulla tendenza di abbandono

Il modello di previsione dell'abbandono dei clienti supporta ora anche gli account aziendali. Puoi valutare il rischio di abbandono non solo per un account, ma anche per una combinazione di un account e una categoria di prodotto o servizio che effettua acquisti da te. Questa aggiunta consente di capire se è più probabile che un account smetta di effettuare acquisti da te in generale o solo per una determinata categoria di beni o servizi. Per aiutarti ulteriormente a usare questo modello di intelligenza artificiale, elenca anche i motivi che rendono probabile l'abbandono da parte di un account. Per altre informazioni, vedere [Previsione dell'abbandono delle transazioni (anteprima)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Visualizzare i contatti di un account aziendale nella vista Clienti

Se gli account aziendali sono mappati ad account correlati, l'app Customer Insights mostra tali contatti correlati come parte della vista dei dettagli del cliente. Per altre informazioni, vedi [Profili cliente](customer-profiles.md).


## <a name="september-2021-updates"></a>Aggiornamenti di settembre 2021

Gli aggiornamenti di settembre 2021 includono nuove funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="activities"></a>Attività

- **Miglioramenti alla timeline** delle attività Abbiamo esteso i filtri per la timeline delle attività sui profili dei clienti. Inoltre, è possibile utilizzare il nuovo pannello dei filtri per filtrare per tipo di attività e per data. Le date possono essere filtrate usando diverse condizioni. Per maggiori informazioni, vedi [Visualizzare le cronologie delle attività sui profili dei clienti](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relazioni

- **Supporto delle relazioni multi** -hop Usate le relazioni multi-hop quando configurate le attività e definite le relazioni tra le entità. Le relazioni multi-hop utilizzano un'entità intermedia per collegare due entità. Quando si configura un'attività, si può usare una relazione multi-hop per collegare l'entità attività a un'entità intermedia e poi a un'entità cliente. È possibile combinare relazioni multi-hop con relazioni multi-path. Per maggiori informazioni, vedere [Relazione multi-hop](relationships.md#multi-hop-relationship).

- **Supporto per le relazioni** multipercorso Usa le relazioni multipercorso quando configuri le attività e definisci le relazioni tra le entità. Le relazioni multipercorso mettono in relazione un'entità sorgente con più di un'entità. Quando si configura un'attività, si può usare una relazione multipercorso per collegare l'entità attività a più di un'entità cliente. È possibile combinare relazioni multi-path con relazioni multi-hop. Per maggiori informazioni, vedere [Relazione multipercorso](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Aggiornamenti di agosto 2021

Gli aggiornamenti di luglio e agosto 2021 includono una nuova funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="extensibility"></a>Estendibilità

- **Esporta segmenti in Klaviyo** Abbiamo esteso le nostre [destinazioni di esportazione affinché includano Klaviyo](export-klaviyo.md). Puoi ora esportare i segmenti per creare campagne, eseguire e-mail marketing e utilizzare gruppi specifici di clienti con Klaviyo. 


## <a name="june-2021-updates"></a>Aggiornamenti di giugno 2021

Gli aggiornamenti di giugno 2021 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="data-ingestion"></a>Inserimento dati

- **Aggiornamenti sui progressi dell'unificazione dei dati migliorati** Ora puoi visualizzare aggiornamenti di stato dinamici più granulari e migliorati sui passaggi del [processo di unificazione dei dati](data-unification.md). Questa funzionalità ti consente di tenere traccia dei progressi dettagliati per comprendere il flusso del processo e agire se uno dei passaggi richiede attenzione.

### <a name="extensibility"></a>Estendibilità

- **Esporta segmenti e altri dati in Salesforce Marketing Cloud** Abbiamo esteso le nostre destinazioni di esportazione affinché includano [Salesforce Marketing Cloud](export-salesforce.md). Ora puoi esportare segmenti e altri tipi di dati in Salesforce Marketing Cloud tramite un'esportazione SFTP con marchio. L'importazione dei dati può essere completamente automatizzata in Salesforce e utilizzata per creare campagne di marketing più efficaci.  
 
- **Esporta segmenti in ActiveCampaign** Abbiamo esteso le nostre destinazioni di esportazione affinché includano [Campagna attiva](export-active-campaign.md). Puoi ora esportare i segmenti per generare campagne, offrire e-mail marketing e utilizzare gruppi specifici di clienti in ActiveCampaign.
 
- **Esporta segmenti in Sendinblue** Abbiamo esteso le nostre destinazioni di esportazione affinché includano [Sendinblue](export-sendinblue.md). Puoi ora esportare i segmenti per generare campagne, offrire e-mail marketing e utilizzare gruppi specifici di clienti con Sendinblue.
 
### <a name="ux-updates"></a>Aggiornamenti UX 

- **Pagina dei clienti nuova e migliorata e pagina dei dettagli del profilo** Abbiamo riprogettato la pagina Clienti e le pagine dei dettagli dei profili per una migliore esperienza utente e prestazioni migliori. Queste modifiche ti consentono di visualizzare, ordinare, cercare e filtrare i clienti. I filtri sono ora rappresentati nell'URL per condividere i risultati della ricerca con altri utenti senza problemi. I risultati della ricerca possono anche essere salvati come segmento.    
  La pagina dei dettagli per i profili dei clienti ora raggruppa i dati in varie sottosezioni come dati demografici, ID e altri attributi dei profili per una migliore leggibilità. Altre sezioni nella pagina dei dettagli dei profili sono ora più interattive. Per esempio, la sezione delle attività ora permette di filtrare e ordinare.


## <a name="may-2021-updates"></a>Aggiornamenti di maggio 2021

Gli aggiornamenti di maggio 2021 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="data-ingestion"></a>Inserimento dati

- **Visualizza o modifica i metadati o la definizione dell'entità quando alleghi i dati ad Azure Data Lake Storage** Ora puoi visualizzare e modificare i metadati o la definizione dell'entità in Informazioni dettagliate sul gruppo di destinatari quando alleghi i dati da una cartella Common Data Model in Azure Data Lake Storage. Questa funzionalità fornisce feedback in tempo reale, convalida del modello e controllo degli errori. Ti consente di modificare facilmente sia model.json che manifest.json.

### <a name="extensibility"></a>Estendibilità

- **Esportazioni di segmenti migliorate, pianificazione personalizzata e duplicazione** Ora puoi [vedere tutte le esportazioni per un segmento specifico](export-destinations.md#view-exports-and-export-details) in un elenco. Questa nuova visualizzazione aiuta a gestire il modo in cui viene utilizzato un segmento specifico e ad adattare quelle esistenti o a creare nuove esportazioni.    
  È possibile [definire pianificazioni di aggiornamenti personalizzate](export-destinations.md#schedule-and-run-exports) per singole esportazioni o più esportazioni contemporaneamente. Fino ad ora, tutte le esportazioni venivano eseguite con ogni aggiornamento del sistema.    
  Per risparmiare tempo invece di creare una nuova esportazione da zero, puoi iniziare con una esistente.

- **Esporta segmenti in Microsoft Advertising** Abbiamo esteso le nostre destinazioni di esportazione per includere Microsoft Advertising. Crea gruppi di destinatari con corrispondenza con il cliente su Microsoft Advertising con i dati del profilo cliente unificati e utilizza questi gruppi di destinatari per le tue campagne pubblicitarie. Per ulteriori informazioni, vedi [Esporta segmenti in Microsoft Advertising](export-microsoft-advertising.md).

- **Esporta segmenti in LinkedIn Ads** Abbiamo esteso i gruppi di destinatari per le esportazioni per includere LinkedIn Ads e consentirti di sbloccare il targeting per contatto e il targeting per azienda tramite LinkedIn esportando i dati del tuo profilo cliente unificato. Per ulteriori informazioni, vedi [Esporta segmenti in LinkedIn Ads](export-linkedin-ads.md).


- **Esporta segmenti in Omnisend** Abbiamo esteso le nostre destinazioni di esportazione per includere Omnisend. Usa i segmenti creati in Informazioni dettagliate sul gruppo di destinatari per generare campagne, offrire e-mail marketing e utilizzare gruppi specifici di clienti con Omnisend. Per ulteriori informazioni, vedi [Esporta segmenti in Omnisend](export-omnisend.md)

### <a name="predictions"></a>Previsioni

- **Report sull'usabilità dei dati di input** Il report sull'usabilità dei dati di input fornisce una visualizzazione consolidata degli errori e degli avvisi che potrebbero essere generati dalle previsioni predefinite. Fornisce inoltre consigli su come migliorare le prestazioni del modello.    
  Il report è disponibile dopo che un modello ha completato il processo di addestramento. Viene creato separatamente per ogni modello, indipendentemente dal fatto che sia stato completato correttamente o meno.
  Attualmente, questa funzione è disponibile solo per il modello Transaction Churn. Per ulteriori informazioni, vedi [Report sull'usabilità dei dati di input](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relazioni

- **Visualizzatore di relazioni** La vista del visualizzatore di relazioni ti consente di vedere tutti le relazioni esistenti tra le entità e la loro cardinalità. Le relazioni sono ora organizzate in gruppi: relazioni create dall'utente, di sistema ed ereditate. Puoi anche esportare una vista come immagine. Per ulteriori informazioni, vedi [Visualizza relazioni](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Aggiornamenti di aprile 2021

Gli aggiornamenti di aprile 2021 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="data-unification"></a>Unificazione dei dati
 
- **Esperienza di unione migliorata per l'unificazione dei dati**    
  
   Ora abbiamo un'esperienza utente migliorata nella configurazione di unione del processo di unificazione dei dati. Le modifiche includono l'ordinamento intuitivo dei campi uniti e le statistiche dettagliate sui campi combinati e singleton.

- **Riordino entità e configurazione di tutti i record di origine nell'entità Cliente**  
      
   È ora possibile riordinare e rimuovere le entità da un piano di conflazione esistente nel processo di unificazione dei dati. Offre la flessibilità per riordinare le entità nel processo di corrispondenza in base alle esigenze aziendali. Inoltre, consentiamo di includere tutti i record non corrispondenti nell'entità finale *Cliente* che consente loro di definire la definizione del set di dati del profilo del cliente.

### <a name="enrichments"></a>Arricchimenti

 - **Nuovo arricchimento: indirizzi avanzati**    
  
   Siamo lieti di introdurre un nuovo arricchimento per migliorare gli indirizzi nei dati dei clienti. Gli indirizzi nei tuoi dati possono essere non strutturati, incompleti o errati. Questa funzione utilizza i modelli di Microsoft per normalizzare e arricchire i tuoi indirizzi nel formato Common Data Model per una migliore precisione e informazioni dettagliate.
 
   Per ulteriori informazioni, vedi [Arricchimento dei profili dei clienti con indirizzi avanzati](enrichment-enhanced-addresses.md).

- **Esperienza di configurazione guidata per gli arricchimenti**    
  
   Abbiamo rivisitato l'esperienza di configurazione per arricchimenti con un'esperienza semplice e guidata. Ora hai un chiaro processo dettagliato per la creazione e la modifica degli arricchimenti.
 
   Inoltre, abbiamo separato la configurazione delle connessioni per gli arricchimenti di terze parti per consentire l'utilizzo della stessa connessione per più arricchimenti. Solo gli amministratori possono configurare nuove connessioni, ma le connessioni create sono disponibili sia per gli amministratori che per i contributori.    

   Per ulteriori informazioni, vedi [Panoramica delle connessioni](connections.md).

- **Più arricchimenti dello stesso tipo**    
  
   Ora consentiamo agli utenti di creare e gestire più arricchimenti dello stesso tipo. Ad esempio, ora puoi creare due arricchimenti di indirizzi separati per arricchire due diversi segmenti di clienti. Si applicano limiti al numero di arricchimenti dello stesso tipo che possono essere creati e variano a seconda del tipo di arricchimento.
  
   Per ulteriori informazioni, vedi [Arricchimento per i profili cliente](enrichment-hub.md).

## <a name="march-2021-updates"></a>Aggiornamenti di marzo 2021

Gli aggiornamenti di marzo 2021 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="activities"></a>Impegni

- **Procedura guidata impegno e tipi semantici**

   Abbiamo migliorato e aggiornato la nostra esperienza di mappatura degli impegni per guidare e semplificare la creazione della mappatura degli impegni. In questa nuova esperienza, gli utenti ottengono un'esperienza guidata per completare ogni fase del processo. Nella fase di mappatura degli impegni, oltre a scegliere tra molti tipi di impegni, l'utente può scegliere di mappare semanticamente i dati per *Sottoscrizione* e/o *SalesOrderLine* agli schemi standard del settore, che possono essere utilizzati per il consumo a valle.   

   Per altre informazioni, vedi [Impegni cliente](activities.md).

### <a name="data-ingestion"></a>Inserimento dati

- **Connettiti alle origini dati locale utilizzando flussi di dati e gateway Power Platform** Siamo lieti di annunciare l'anteprima di flussi di dati e connettività locale Power Platform utilizzando gateway in Customer Insights con un ambiente Power Platform o Dataverse. Qualsiasi nuova origine dati creata in un ambiente Customer Insights con un ambiente Dataverse collegato verrà impostata automaticamente su flussi di dati Power Platform che introducono la connettività dei dati locali e un ricco set di connettori e capacità di trasformazione.

### <a name="extensibility"></a>Estendibilità

- **Esportazioni organizzate in connessioni ed esportazioni** Abbiamo cambiato il nome della pagina **Destinazioni di esportazione** in **Connessioni** e abbiamo aggiunto una pagina separata per le **Esportazioni**. Come parte di questo aggiornamento, trasferiremo le esportazioni esistenti in coppie di una connessione e un'esportazione che utilizza quella connessione. Gli amministratori ora hanno maggiore chiarezza sui dati in uscita nella pagina **Connessioni**. Tutti i ruoli utente hanno accesso alla pagina **Esportazioni**, ma solo gli amministratori possono scegliere di consentire ai collaboratori di modificare esportazioni specifiche con connessioni condivise.     
  Per ulteriori informazioni, vedi [Panoramica delle connessioni](connections.md) e [Panoramica delle esportazioni](export-destinations.md).

- **Esporta segmenti in Campaign Monitor** Abbiamo esteso le nostre destinazioni di esportazione per includere Campaign Monitor. Ora puoi esportare segmenti da Customer Insights agli elenchi di Campaign Monitor e utilizzarli come base per le tue campagne di marketing.    
   Per ulteriori informazioni, vedi [Esportare in Campaign Monitor](export-campaign-monitor.md).

- **Esporta segmenti in Constant Contact** Abbiamo esteso le nostre destinazioni di esportazione per includere Constant Contact. Ora puoi esportare segmenti da Customer Insights agli elenchi di Constant Contact e utilizzarli come base per le tue campagne di marketing.   
   Per ulteriori informazioni, vedi [Esportare in Constant Contact](export-constant-contact.md).

- **Esporta segmenti in RollWorks** Abbiamo esteso le nostre destinazioni di esportazione per includere RollWorks. Ora puoi esportare i segmenti da Customer Insights ai segmenti di destinatari RollWorks e utilizzarli come base per la tua pubblicità B2B.    
   Per ulteriori informazioni, vedi [Esportare in RollWorks](export-rollworks.md).

- **Esporta segmenti in Snapchat** Abbiamo esteso le nostre destinazioni di esportazione per includere Snapchat. Ora puoi esportare segmenti da Customer Insights agli elenchi di Snapchat e utilizzarli come base per le tue pubblicità.     
   Per ulteriori informazioni, vedi [Esportare in Snapchat](export-snapchat.md).

### <a name="predictions"></a>Previsioni

- **Utilizza i filtri di prodotto negli elementi consigliati predittivi di prodotto** Abbiamo aggiunto la possibilità di utilizzare i filtri di prodotto nel nostro modello di elementi consigliati di prodotto. Ora puoi creare un previsione che utilizza solo un sottoinsieme dei tuoi prodotti.    
   Per ulteriori informazioni, vedi [Configurare i filtri di prodotto](predict-product-recommendation.md#configure-product-filters).

- **Crea segmenti dalle previsioni del modello** Abbiamo aggiunto un modo rapido per creare segmenti utilizzando i risultati di un modello previsione. Dalla pagina dei risultati del modello, puoi creare facilmente un nuovo segmento selezionando la nuova opzione **Crea segmento**.    
  Per ulteriori informazioni, vedi [Creare un segmento basato su un modello di previsione](prediction-based-segment.md).

- **Spiegazioni per gli elementi consigliati di prodotti** Abbiamo aggiunto informazioni che spiegano i fattori chiave appresi dal modello IA per generare elementi consigliati di prodotti e il grado in cui tali fattori contribuiscono agli elementi consigliati di prodotti. Queste informazioni vengono aggiunte alla schermata dei risultati del modello.    
   Per ulteriori informazioni, vedi [Esaminare lo stato e i risultati di una previsione](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Aggiornamenti di febbraio 2021

Gli aggiornamenti di febbraio 2021 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

#### <a name="extensibility"></a>Estendibilità

- **Esporta segmenti in AdRoll**

  Abbiamo esteso le nostre destinazioni di esportazione per includere AdRoll. Ora puoi esportare segmenti da Customer Insights a gruppi di destinatari AdRoll e utilizzarli come base per la tua pubblicità. Per ulteriori informazioni, vedi [Connettore per AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmenti
 
- **Duplica un segmento**
  
  Per creare un nuovo segmento basato su uno esistente, ora puoi duplicare un segmento e modificare il segmento duplicato per perfezionarlo ulteriormente. 

- **Aggiungi attributi aggiuntivi a un segmento**

  Ora puoi includere attributi nell'output del segmento, anche se questi attributi non fanno parte del profilo del cliente. Ad esempio, includi gli ID sottoscrizione in un segmento anche se fa parte dell'entità di sottoscrizione che ha una relazione M:1 con l'entità cliente. Finché l'attributo appartiene a un'entità correlata all'entità cliente, puoi includere questi attributi.  

#### <a name="predictions"></a>Previsioni

- **Crea previsioni di raccomandazioni sui prodotti**

  Capire ciò che i clienti sono interessati ad acquistare è uno dei primi passi necessari per migliorare i ricavi aziendali e fidelizzare i clienti attraverso la personalizzazione e il coinvolgimento. Fornire gli elementi consigliati per i prodotti che non sono allineati agli interessi del tuo cliente può creare un senso di disconnessione tra il cliente e la tua attività e, in ultima analisi, limitare i guadagni potenziali complessivi e l'esperienza per un cliente. 

  Utilizzando i tuoi dati, ora puoi creare previsioni per i prodotti che i tuoi clienti probabilmente acquisteranno in futuro. Per ulteriori informazioni, vedi [Previsione di raccomandazioni sui prodotti](predict-product-recommendation.md).

#### <a name="system-administration"></a>Amministrazione di sistema

- **L'ambiente di copia supporta più tipi di origini dati**

  Gli amministratori possono copiare le configurazioni dell'ambiente in un nuovo ambiente nella stessa organizzazione. Questa funzionalità estende la funzionalità dell'ambiente di copia per i casi in cui vengono utilizzate origini dati basate su un data lake Microsoft Dataverse gestito o una cartella Common Data Model.

## <a name="january-2021-updates"></a>Aggiornamenti di gennaio 2021

Gli aggiornamenti di gennaio 2021 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

#### <a name="extensibility"></a>Estendibilità

- **Funzionalità estese e prestazioni migliorate per l'esportazione FTP sicuro** È ora possibile esportare tutte le entità di output da Customer Insights a un host FTP sicuro. In precedenza, l'esportazione era limitata alle entità di segmento. Inoltre, le prestazioni dell'esportazione FTP sicuro consentono più volume di dati in meno tempo, a seconda delle prestazioni dell'host FTP sicuro.    
  Per ulteriori informazioni, vedi [Connettore per FTP sicuro (anteprima)](export-sftp.md).  

#### <a name="segments"></a>Segmenti

- **Segmenti suggeriti in base all'apprendimento automatico per migliorare le metriche** C'è un nuovo modo per individuare e creare segmenti. Il sistema utilizza un modello di intelligenza artificiale per suggerire segmenti che possono aiutare a migliorare un KPI (misura) di cui tieni già traccia. Mostriamo il grado di influenza degli attributi selezionati per una misura o un altro attributo principale. Queste informazioni aiutano a trovare potenziali segmenti che presentano opportunità.    
  Per ulteriori informazioni, vedi [Segmenti suggeriti (anteprima)](suggested-segments.md).

#### <a name="data-unification"></a>Unificazione dei dati

- **Esperienza di corrispondenza migliorata** Nell'area di unificazione dei dati, l'esperienza della corrispondenza è stata aggiornata. Ti consente di configurare e visualizzare le regole di corrispondenza, comprese le statistiche dettagliate per spiegare ulteriormente come funziona la corrispondenza. Sono disponibili opzioni per disabilitare una regola di corrispondenza in modo che non sia più attiva pur mantenendo la configurazione, regole di corrispondenza con trascinamento della selezione e altro ancora.
  Per ulteriori informazioni, vedere [Mettere in corrispondenza le entità](match-entities.md).

- **L'output della deduplicazione dal processo di corrispondenza è disponibile come entità** L'output del processo di deduplicazione dal processo di corrispondenza viene ora scritto in un'entità separata per ulteriori analisi. Questa entità è composta dai campi utilizzati nel processo di deduplicazione e dal record vincitore e dai record alternativi corrispondenti che vengono uniti al record vincitore.
  Per ulteriori informazioni, vedi [Output di deduplicazione come entità](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Amministrazione di sistema

- **Condivisione dei dati con Microsoft Dataverse** Ora puoi condividere l'output di Customer Insights con le applicazioni Microsoft Dataverse usando il Data Lake gestito di Microsoft Dataverse. Dopo aver associato un ambiente Dataverse con Customer Insights, hai la possibilità di abilitare la condivisione dei dati.
  Per ulteriori informazioni, vedere [Gestire ambienti](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]