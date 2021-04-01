---
title: Funzionalità nuove e future
description: Informazioni su nuove funzionalità, miglioramenti e correzioni di bug.
ms.date: 03/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 96c0b871eeaaf0976e5c718f37f883f4410977dc
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598437"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novità della funzionalità Audience Insights di Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Siamo lieti di annunciare i nuovissimi aggiornamenti. Questo articolo riassume le funzionalità con anteprima pubblica, i miglioramenti della disponibilità generale e gli aggiornamenti delle funzionalità. Per vedere i piani delle funzionalità a lungo termine, dai un'occhiata ai [piani di rilascio di Dynamics 365 e Power Platform](/dynamics365/release-plans/).

Puoi inoltre guardare il video seguente per saperne di più sulle funzionalità pianificate per gli ultimi sei mesi.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Gli aggiornamenti vengono implementati in base all'area geografica. Quindi alcune aree geografiche potrebbero vedere le funzionalità prima di altre. Se non diversamente specificato, non è necessario intraprendere alcuna azione e l'app viene aggiornata automaticamente senza tempi di inattività.

> [!TIP]
> Per inviare e votare funzionalità richieste e suggerimenti di prodotto, vai al [portale Ideas dell'applicazione Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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

  Gli amministratori possono copiare le configurazioni dell'ambiente in un nuovo ambiente nella stessa organizzazione. Questa funzione estende la funzionalità dell'ambiente di copia per i casi in cui vengono utilizzate le origini dati basate su un data lake Common Data Service o una cartella Common Data Model.

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


## <a name="december-2020-updates"></a>Aggiornamenti di dicembre 2020

Gli aggiornamenti di dicembre 2020 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="new-and-updated-features-in-december-2020"></a>Funzionalità nuove e aggiornate a dicembre 2020

#### <a name="data-enrichment"></a>Arricchimento dei dati

- **Miglioramenti negli arricchimenti con affinità di marchio e interesse**
  
  Abbiamo semplificato i nostri punteggi di affinità per renderli più facili da capire e utilizzare. Ora puoi identificare rapidamente i clienti in base a quanta affinità hanno per un determinato marchio o interesse.

  Inoltre, abbiamo aggiunto nuove opzioni di configurazione per controllare meglio come desideri arricchire i profili dei tuoi clienti. 

  Per ulteriori informazioni, vedi [Arricchire profili cliente con affinità di marchi e interessi](enrichment-microsoft-graph.md).

- **Controlla quali profili arricchire**

  È ora possibile arricchire solo un sottoinsieme dei profili cliente con l'opzione di selezionare un'entità segmento invece dell'entità cliente predefinita. Crea un segmento con i profili cliente che desideri arricchire e selezionalo nella configurazione di arricchimento per il set di dati dei clienti.
  Questa funzionalità è attualmente disponibile solo per gli arricchimenti forniti da Experian e HERE Technologies. Presto abiliteremo questa funzionalità per ulteriori arricchimenti.

  Per ulteriori informazioni, vedere [Arricchisci i profili cliente con i dati demografici di Experian](enrichment-experian.md) o [Arricchimento dei profili cliente con HERE Technologies](enrichment-here.md).

#### <a name="extensibility"></a>Estendibilità

- **Attiva i segmenti tramite Autopilot**

  Esporta segmenti in Autopilot e usali per scopi di marketing. Per ulteriori informazioni, vedi [Connettore per Autopilot (anteprima)](export-autopilot.md).

- **Attiva i segmenti tramite SendGrid**

  Esporta segmenti in SendGrid e usali per scopi di marketing. Per ulteriori informazioni, vedi [Connettore per SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Amministrazione di sistema

- **Esperienza di gestione degli ambienti aggiornata**
  
  Ora puoi creare, modificare, eliminare e reimpostare gli ambienti direttamente dal selettore degli ambienti nell'intestazione dell'app. 
  
  Inoltre, l'ambiente che stai utilizzando verrà bloccato nella parte superiore del pannello dell'ambiente in modo che tu non debba più cercarlo.

  Per ulteriori informazioni, vedere [Gestire ambienti](manage-environments.md).

## <a name="november-2020-updates"></a>Aggiornamenti di novembre 2020

Gli aggiornamenti di novembre 2020 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="new-and-updated-features-in-november-2020"></a>Funzionalità nuove e aggiornate di novembre 2020

#### <a name="data-enrichment"></a>Arricchimento dei dati

- **Importare i dati di arricchimento tramite importazione personalizzata SFTP (Secure File Transfer Protocol)**
  
  L'importazione personalizzata FTP sicuro ti consente di importare dati di arricchimento che non devono essere sottoposti al processo di unificazione dei dati. Leggi gli articoli sull'importazione personalizzata SFTP.

  Per ulteriori informazioni, vedi [Arricchire i profili cliente con i dati personalizzati (anteprima)](enrichment-SFTP-custom-import.md).
 
- **Arricchire i dati cliente con i dati di localizzazione di HERE Technologies**

  Con i servizi di arricchimento dei dati di HERE Technologies, puoi creare una comprensione più precisa della posizione dei tuoi clienti con la normalizzazione degli indirizzi, l'estrazione di latitudine e longitudine e altro ancora. Leggi gli articoli sull'arricchimento con HERE Technologies.

  Per ulteriori informazioni, vedi [Arricchimento dei profili cliente con HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Unificazione dei dati

- **Flessibilità per abilitare il profiling dei dati in entità e campi selezionati dal tuo account di archiviazione**

  Puoi indicare per quali entità e campi di dati di una cartella Common Data Model nell'account di archiviazione di Azure Data Lake desideri abilitare il profiling dei dati come parte del processo di inserimento dati.

  Per ulteriori informazioni, vedi [Connettiti a una cartella Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Estendibilità

- **Attivare i segmenti tramite Google Ads**

  Esporta segmenti dagli elenchi di destinatari di Google Ads e utilizza questi elenchi per fare pubblicità su Google Search, Gmail, YouTube e Rete Display di Google. Leggi gli articoli sull'attivazione dei segmenti tramite Google Ads.

  Per ulteriori informazioni, vedi [Connettore per Google Ads](export-google-ads.md).

- **Attivare i segmenti tramite Marketo**

  Esporta segmenti negli elenchi di destinatari di Marketo e utilizza questi destinatari per l'automazione del marketing. Leggi gli articoli sull'attivazione dei segmenti tramite Marketo. 

  Per ulteriori informazioni, vedi [Connettore per Marketo](export-marketo.md).

- **Attiva i segmenti tramite Google DotDigital**

  Esporta segmenti in DotDigital e usali per scopi di marketing. Leggi gli articoli sull'attivazione dei segmenti tramite DotDigital. 

  Per ulteriori informazioni, vedi [Connettore per DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Previsioni

- **Prevedere l'abbandono transazionale**

  La funzione di previsione dell'abbandono transazionale ti consente, senza l'aiuto di un data scientist, di prevedere la probabilità che un cliente smetta di acquistare prodotti o servizi.  Utilizzando il punteggio di previsione, puoi combinare altre informazioni sui tuoi clienti, come il valore del cliente, per creare segmenti di clienti ad alto rischio di abbandono o di valore elevato. Utilizza questo segmento per rivolgerti direttamente ai clienti attraverso attività di marketing, assistenza ai clienti e altri scenari per ridurre il rischio di abbandono.
 
  Configura la definizione di abbandono come finestra temporale specifica per la tua attività e definisci quando i clienti sono considerati persi. Ad esempio, un negozio di alimentari potrebbe considerare un cliente come perso se questo non ha acquistato nulla negli ultimi 30 giorni.
 
  Durante la creazione della previsione, ti indicheremo quali dati sono necessari e ti guideremo nel mapping dei dati inerenti alla tua attività ai campi necessari per prevedere l'abbandono dei clienti. Puoi inoltre impostare una pianificazione per ripetere il training del modello in base a nuove informazioni nel sistema per adattarlo all'evoluzione della situazione commerciale.
 
  Per ulteriori informazioni, vedi [Previsione di abbandono transazionale (anteprima)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Amministrazione di sistema

- **Reimpostare l'ambiente**

  Reimposta tutto in un ambiente di un'istanza selezionata per ricominciare da zero.

  Per ulteriori informazioni, vedi [Reimpostare un ambiente esistente](manage-environments.md#reset-an-existing-environment).


- **Connettersi all'account di archiviazione di Azure Data Lake usando un'entità servizio**

  Scrivi l'output dei dati e leggi i dati nell'account di archiviazione usando un'entità servizio di Azure. Le connessioni dell'account di archiviazione esistenti possono continuare a usare la chiave dell'account. Offrono anche un'opzione di aggiornamento per utilizzare l'entità servizio in futuro. Le nuove connessioni saranno basate sul metodo di autenticazione dell'entità servizio per l'account di archiviazione.

  Per ulteriori informazioni, vedi [Connettersi a un account di Azure Data Lake Storage Gen2 con un'entità servizio di Azure per Audience Insights](connect-service-principal.md).

## <a name="october-2020-updates"></a>Aggiornamenti di ottobre 2020

Gli aggiornamenti di ottobre 2020 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="new-and-updated-features-in-october-2020"></a>Funzionalità nuove e aggiornate di ottobre 2020

#### <a name="extensibility"></a>Estendibilità

- **Esportare in MailChimp**

Esporta segmenti negli elenchi di destinatari esistenti di Mailchimp per fornire un'esperienza di posta elettronica personalizzata ai tuoi clienti.

Per ulteriori informazioni, vedi [Connettore per Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Arricchimento dei dati

- **Deduplicare i record di origine in un'entità di corrispondenza**

Specifica le regole di deduplicazione nelle entità utilizzate nel processo di corrispondenza per identificare i record duplicati. Uniscili in un unico record e collega tutti i record di origine a questo record unito. Il record deduplicato verrà quindi utilizzato nel processo di corrispondenza tra entità.

Per ulteriori informazioni, vedi [Definire la deduplicazione in un'entità di corrispondenza ](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Amministrazione di sistema

- **Orchestrazione: nuova opzione di aggiornamento in Unione**

Fino a ieri, quando eseguivi il processo di unione, il sistema eseguiva tutti i processi downstream che dipendono dall'unione e dai processi successivi. Ora puoi verificare l'output del processo di unione (l'entità cliente unificata) prima di utilizzarlo nell'elaborazione downstream come i segmenti o le misure.
Nella pagina Unione, ora puoi scegliere di eseguire solo il passaggio di unione e solo questo processo. Per aggiornare anche tutti i processi downstream, puoi scegliere di eseguire i processi di unione e downstream. 

## <a name="september-2020-updates"></a>Aggiornamenti di settembre 2020

Gli aggiornamenti di settembre 2020 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="new-and-updated-features-in-september-2020"></a>Funzionalità nuove e aggiornate a settembre 2020

#### <a name="activities"></a>Impegni

- **Previsione intelligente della semantica degli attributi**

Questa nuova funzionalità prevede i tipi semantici di attributi di input che vengono passati al processo di unificazione dei dati. Utilizza modelli apprendimento automatico che migliorano la precisione e fanno risparmiare tempo.

#### <a name="enrichments"></a>Arricchimenti

- **Arricchimento demografico di Experian**

L'arricchimento demografico di Experian è ora disponibile in anteprima. Experian è un leader globale nei servizi di marketing e reporting del credito al consumo e alle imprese. Con [Servizi di arricchimento dei dati di Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), puoi acquisire una conoscenza più approfondita dei tuoi clienti arricchendo i tuoi profili cliente con dati demografici come le dimensioni del nucleo familiare, il reddito e altro ancora.

Per utilizzare questa funzione, è necessario disporre di un abbonamento Experian attivo.

Per ulteriori informazioni, vedi [Arricchire i profili cliente con i dati demografici di Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Amministrazione di sistema

- **Riquadro dettagli dell'attività**

Il riquadro dei dettagli dell'attività consente di visualizzare i dettagli sulle attività eseguite dal sistema. È un modo pratico per identificare i problemi della configurazione e trovare soluzioni.
Esamina i messaggi di errore per vedere come affrontare potenziali problemi.
 
- **Elaborazione delle informazioni aggiunta a più pagine**

Questo miglioramento aggiunge informazioni sullo stato delle tue entità nelle pagine **Entità** e **Clienti**.
 
Inoltre, puoi trovare dettagli sull'avanzamento dei processi, insieme ai dettagli sulle attività, in entrambe queste pagine.

- **Miglioramenti alla pagina di stato del sistema**

Abbiamo migliorato la struttura della tabella dei dettagli dello stato su **Sistema** > **Stato** durante la revisione delle esportazioni di dati.
 
Inoltre, gli errori nella colonna **Dettagli** ora sono più dettagliati e utilizzabili. 
 
- **Annulla ripristino del lavoro allo stato precedente**

Quando annulli un'attività, ad esempio, nel processo di corrispondenza, tornerà allo stato più recente. Ad esempio, se il processo di corrispondenza è stato completato ieri e lo annulli oggi, tornerà allo stato di ieri.


## <a name="august-2020-updates"></a>Aggiornamenti di agosto 2020

Gli aggiornamenti di agosto 2020 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="new-and-updated-features-in-august-2020"></a>Funzionalità nuove e aggiornate ad agosto 2020

#### <a name="data-unification"></a>Unificazione dei dati

- **Esperienza migliorata per la fase della mappa durante l'unificazione dei dati**

  L'esperienza della fase di mappa nel processo di unificazione dei dati consente di selezionare entità, attributi e definire la semantica in modo più semplice.

  Le modifiche includono:
  
  - meno interazioni richieste per aggiungere entità e campi
  - capacità di ricerca migliorate sulla pagina della mappa
  - identificazione visiva e facile del tipo di campo suggerito

#### <a name="enrichment"></a>Arricchimento

- **Arricchimento delle affinità di interesse disponibile in più mercati**

  Stiamo estendendo la disponibilità dell'arricchimento delle affinità di interesse oltre gli Stati Uniti ad altri cinque mercati: Canada, Australia, Regno Unito, Francia e Germania. Con questa estensione, puoi arricchire i tuoi dati cliente con più interessi applicabili a questi mercati. Inoltre arricchiremo i profili cliente che si trovano in questi mercati utilizzando i dati proprietari locali di Microsoft Graph.
  Per ulteriori informazioni, vedi [Arricchire i profili cliente con affinità di marchi e interessi](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Aggiornamenti di luglio 2020

Gli aggiornamenti di luglio 2020 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="new-and-updated-features-in-july-2020"></a>Funzionalità nuove e aggiornate a luglio 2020

#### <a name="extensibility"></a>Estendibilità

- **Trigger di Power Automate per il processo di unificazione completato**

  Abbiamo esteso i trigger per Power Automate in modo da consentire la creazione di una notifica o un'azione quando viene completato un aggiornamento del processo di unificazione (mappa, corrispondenza, unione).    
  Per ulteriori informazioni, vedi [Connettore Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Arricchimento

- **Arricchimento delle affinità di marchio disponibile in più mercati**

  Stiamo estendendo la disponibilità dell'arricchimento delle affinità di marchio oltre gli Stati Uniti ad altri cinque mercati: Canada, Australia, Regno Unito, Francia e Germania. Con questa estensione, puoi arricchire i dati cliente con marchi locali in questi mercati. Inoltre arricchiremo i profili cliente che si trovano in questi mercati utilizzando i dati proprietari locali di Microsoft Graph.
  Per ulteriori informazioni, vedi [Arricchire i profili cliente con affinità di marchi e interessi](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Aggiornamenti di giugno 2020

Gli aggiornamenti di giugno 2020 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="new-and-updated-features-in-june-2020"></a>Funzionalità nuove e aggiornate a giugno 2020

#### <a name="enrichment"></a>Arricchimento

- **Arricchimento con i dati aziendali di Leadspace**
  
  Definisci i campi nei profili cliente unificati utilizzati per cercare i relativi dati aziendali da Leadspace. Dopo aver eseguito il processo di arricchimento, i profili B2B vengono arricchiti con più attributi tra cui dimensioni, posizione, settore dell'azienda e altro.    
  Questa collaborazione consente di migliorare la qualità dei tuoi dati con input da servizi di terze parti. Per utilizzare questo arricchimento avrai bisogno di una licenza di Leadspace per accedere ai relativi dati aziendali B2B. Il sistema utilizzerà quella licenza per arricchire continuamente i dati.    
  Per ulteriori informazioni, vedi [Arricchimento dei profili aziendali con Leadspace](enrichment-leadspace.md).

- **Pagina dell'hub di arricchimento**

  Tutti gli arricchimenti di dati disponibili dei provider di arricchimento di terze parti e del produttore vengono configurati nella stessa posizione. La configurazione dell'arricchimento dei dati è un'esperienza semplice gestita da un'unica posizione.    
  Per ulteriori informazioni, vedi [Arricchimento per i profili cliente](enrichment-hub.md).

- **Separare l'arricchimento delle affinità di marchi e interessi**

  Le affinità di marchi e interessi sono ora disponibili come due arricchimenti indipendenti. Gli arricchimenti separati ti offrono la flessibilità di configurarli e gestirli individualmente, a seconda dei requisiti o delle esigenze aziendali.    
  Per ulteriori informazioni, vedi [Arricchire i profili cliente con affinità di marchi e interessi](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Estendibilità

- **URL selezionabili per impegni unificati nel componente aggiuntivo Scheda cliente di Dynamics 365**

  Gli impegni unificati nel componente aggiuntivo Scheda cliente ora mostrano URL selezionabili se tali URL sono stati definiti durante la configurazione degli impegni.    
  Per altre informazioni, vedi [Componente aggiuntivo Scheda cliente](customer-card-add-in.md).

- **Affinità di marchio e interessi disponibili nel componente aggiuntivo Scheda cliente di Dynamics 365**

  Un nuovo controllo sul componente aggiuntivo Scheda cliente Dynamics 365 consente di mostrare gli arricchimenti di marchio e interessi sui tuoi contatti nelle app di interazione con i clienti in Dynamics 365.    
  Per altre informazioni, vedi [Componente aggiuntivo Scheda cliente](customer-card-add-in.md).

- **Più trigger Power Automate**

  Abbiamo esteso i trigger per Power Automate e aggiunto i seguenti trigger:
  - Ottenere una notifica o eseguire un'azione al termine di un aggiornamento completo automatizzato (origini dati, unificazione, segmenti, misure, esportazioni)
  - Definisci una soglia per una misura aziendale. Ad esempio, puoi creare una notifica che viene inviata al superamento della soglia definita. Inoltre, il trigger introduce informazioni che consentono di creare flussi di lavoro più complessi in Power Automate.    
  Per ulteriori informazioni, vedi [Connettore Power Automate](export-power-automate.md)

- **Esportare in Gestione inserzioni di Facebook**
  
  Questa funzionalità ti consente di esportare segmenti in Gestione inserzioni di Facebook. I segmenti vengono esportati come elenchi di destinatari personalizzati per utilizzare profili cliente unificati nelle campagne di marketing e nelle inserzioni di Facebook. Gli elenchi di destinatari personalizzati sono anche utilizzabili per creare campagne su Instagram tramite Gestione inserzioni di Facebook.    
  Per ulteriori informazioni, vedi [Connettore per Gestione inserzioni di Facebook](export-facebook.md).

#### <a name="predictions"></a>Previsioni

- **Previsione sull'annullamento degli abbonamenti**

  Segui un'esperienza guidata per creare previsioni di abbandono in aree di abbonamento come servizi cloud, iscrizioni dei clienti e altri settori. 

  La funzionalità di previsione di abbandono degli abbonamenti consente di prevedere la probabilità che un cliente interrompa l'utilizzo di prodotti o servizi basati su abbonamento senza coinvolgere un data scientist. Utilizzando il punteggio di previsione, è possibile combinare altre informazioni sui clienti per creare segmenti ad alto rischio di abbandono. Con questo segmento, puoi rivolgerti direttamente ai clienti tramite marketing, assistenza ai clienti e in altri scenari per ridurre il rischio di abbandono di clienti specifici per migliorare i ricavi e ridurre i costi.

  All'interno dell'esperienza, puoi configurare la definizione di abbandono come una finestra basata sul tempo specifica per la tua azienda. Ad esempio, una società di streaming video che ha un processo di abbonamento mensile potrebbe considerare che un cliente ha abbandonato dopo 15 giorni dalla scadenza del suo abbonamento.

  Mentre prosegui con la previsione, ti guideremo per individuare i dati necessari e ti consentiremo di eseguire il mapping dei dati sulla tua azienda ai campi richiesti per prevedere l'abbandono per i clienti. Man mano che le informazioni aziendali cambiano, puoi anche impostare una pianificazione per ripetere il training in base alle nuove informazioni nel sistema e rispondere all'evoluzione delle circostanze aziendali.    
  Per ulteriori informazioni, vedi [Previsione di abbandono degli abbonamenti (anteprima)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmenti

- **Trova clienti simili**
  
  Trova clienti simili nella tua base clienti tramite l'intelligenza artificiale. Un modello di apprendimento automatico a classificazione binaria assegna un punteggio di somiglianza ai clienti nel segmento espanso. Il punteggio si basa sulla somiglianza con i clienti nel segmento di origine. A seconda del punteggio di somiglianza, i profili cliente vengono aggiunti a un segmento appena creato.

  A volte indicato come modellazione sosia nel marketing digitale, utilizza un modello di intelligenza artificiale per aiutare a trovare clienti simili a un altro segmento di clienti prendendo in considerazione più attributi. Non solo consente di scegliere gli attributi, ma anche di specificare il numero massimo di clienti che dovrebbero essere inclusi in questo nuovo segmento. Il modello di intelligenza artificiale calcolerà quindi i punteggi di somiglianza per ciascun cliente in base agli attributi selezionati e troverà i clienti con il punteggio di somiglianza medio più elevato. Il segmento risultante includerà i clienti che appaiono simili al cliente nel segmento originale.    
  Per ulteriori informazioni, vedi [Clienti simili](find-similar-customer-segments.md).

- **Sovrapposizione e fattori di differenziazione dei segmenti**

  La sovrapposizione dei segmenti ti consente di vedere quanti e quali clienti sono comuni a due o più segmenti. Ad esempio, il modo in cui un segmento di clienti con spese di livello elevato si sovrappone a un segmento di clienti con alti livelli di soddisfazione o il modo in cui un segmento di clienti che abbandonano si sovrappone a un segmento di clienti con bassi livelli di soddisfazione. Inoltre, puoi analizzare come cambia la sovrapposizione in base a un attributo aggiuntivo di tua scelta.

  I fattori di differenziazione dei segmenti rivelano cosa differenzia un segmento dal resto dei clienti o da un altro segmento. Devi semplicemente identificare un segmento e il sistema identificherà gli attributi e le misure del profilo che distinguono il segmento sotto forma di un elenco classificato di fattori di differenziazione, dal più forte al più debole.    
  Per ulteriori informazioni, vedi [Informazioni dettagliate sui segmenti (anteprima)](segment-insights.md).

- **Durata del segmento**
  
  Definisci una pianificazione per attivare o disattivare un segmento.    
  Per ulteriori informazioni, vedi [Gestire i segmenti esistenti](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Aggiornamenti di maggio 2020

Gli aggiornamenti di maggio 2020 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="new-and-updated-features-in-may-2020"></a>Funzionalità nuove e aggiornate a maggio 2020

#### <a name="data-ingestion"></a>Inserimento dati

- **Inserimento dati in tempo reale: visualizzazioni cronologiche**

  Quando usi la nostra API per importare aggiornamenti in tempo reale, puoi visualizzare fino a 30 giorni di cronologia aggregata per questi aggiornamenti. Hai accesso agli aggregati di tutte le chiamate API riuscite o non riuscite, inclusi i risultati, il sistema di origine e altri metadati utili.    
  Per altre informazioni, vedi [Inserimento dati in tempo reale](real-time-data-ingestion.md).

- **Inserimento dati in tempo reale: aggiornamenti del profilo**

  Questa estensione dell'inserimento dati in tempo reale consente di visualizzare, in pochi secondi, le modifiche a specifici campi del profilo utente.    
  Oltre alla funzionalità in tempo reale per gli impegni, il sistema supporta gli aggiornamenti a bassa latenza dei campi del profilo. Gli aggiornamenti in tempo reale per i campi del profilo hanno un tempo di scadenza e pertanto non sostituiscono gli aggiornamenti pianificati.    
  Per altre informazioni, vedi [Inserimento dati in tempo reale](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Estendibilità

- **Sequenza temporale e paginazione aggiornate sul componente aggiuntivo Scheda cliente**

  La sequenza temporale del componente aggiuntivo Scheda cliente corrisponde alla sequenza temporale degli impegni. La paginazione della sequenza temporale è migliorata, mostrando fino a 50 impegni contemporaneamente. Consente inoltre di caricare più impegni nella sequenza temporale.    
  Per altre informazioni, vedi [Componente aggiuntivo Scheda cliente](customer-card-add-in.md).

- **Trigger di Power Automate per le modifiche di segmento**

  Trigger per definire da cosa Power Automate può creare un flusso. Il trigger appena aggiunto consente di definire una soglia per un segmento. Ad esempio, puoi creare una notifica che viene inviata al superamento della soglia definita.    
  Per ulteriori informazioni, vedi [Connettore Power Automate](export-power-automate.md).

- **Supporto multi-tenant per modelli personalizzati**

  Configura i flussi di lavoro per i modelli personalizzati con un servizio Web di un diverso tenant di Azure Machine Learning. Puoi accedere al tenant di Azure Machine Learning durante la creazione di un nuovo flusso di lavoro per modelli personalizzati. Questa funzionalità è un'aggiunta alla capacità esistente di integrazione con il tuo servizio Web Azure Machine Learning personalizzato.    
  Per ulteriori informazioni, vedi [Modelli personalizzati apprendimento automatico](custom-models.md).

#### <a name="segments"></a>Segmenti

- **Automazione del percorso di entità**

  Quando si crea un segmento, gli utenti devono definire il percorso dell'entità. Questa capacità fa un primo passo per automatizzare la definizione del percorso dell'entità in modo da poterti concentrare sui criteri di segmentazione che hai in mente.    
  Se l'entità per cui vuoi segmentare i clienti è direttamente correlata all'entità cliente unificato, non è più necessario definire il percorso dell'entità. Tuttavia, se esiste più di un percorso di entità possibile, è comunque necessario definirlo manualmente.

- **Azioni su più segmenti**
  
  Gli utenti possono selezionare più segmenti e intraprendere azioni, come aggiornare i segmenti, con un solo clic.    

- **Aggiornare i segmenti**

  Gli utenti possono aggiornare un singolo segmento o selezionare solo i segmenti che desiderano aggiornare.    

  
- **Miglioramenti ai segmenti composti**

  Gli utenti possono creare, modificare ed eliminare segmenti basati su altri segmenti. Ad esempio, un segmento costruito su un altro segmento che è stato costruito su un terzo segmento.    

- **Pagina elenco di segmenti**

  Il nuovo design della pagina dei segmenti utilizza un formato elenco che consente di visualizzare più segmenti contemporaneamente. Viene aggiunto un campo di ricerca per trovare rapidamente i segmenti. Gli utenti possono ora applicare azioni come il download o l'eliminazione su più segmenti contemporaneamente. Viene introdotta una nuova esperienza di tendenza per identificare rapidamente le modifiche significative sui segmenti.    
  Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).

#### <a name="system-administration"></a>Amministrazione di sistema

- **Customer Insights disponibile in Microsoft Dynamics 365 Online Government**

  Con un numero sempre maggiore di canali per le interazioni, i dati dei cittadini sono sparsi su una miriade di sistemi che comportano dati in silos e una visione frammentata delle informazioni sulle interazioni dei cittadini. Senza una visione completa delle interazioni di ciascun cittadino attraverso i canali, è impossibile per i governi modernizzarsi su larga scala. Microsoft si impegna a supportare le esigenze tecnologiche del governo per stare al passo con le aspettative dei cittadini per esperienze coerenti e reattive.    
  Con la prima ondata di rilascio del 2020, Dynamics 365 Customer Insights sarà disponibile per Government Community Cloud (GCC), un ambiente creato per soddisfare le esigenze di conformità più elevate delle agenzie governative degli Stati Uniti. Le agenzie ottengono una visione unificata dei cittadini e utilizzano un'intelligenza artificiale predefinita per ricavare informazioni dettagliate che migliorano le interazioni, potenziano i dipendenti e trasformano le comunità, riducendo al contempo la complessità dell'IT e rispettando gli standard di conformità e sicurezza degli Stati Uniti. Dynamics 365 Government soddisfa i severi requisiti del programma US Federal Risk and Authorization Management Program (FedRAMP) che consente alle agenzie federali degli Stati Uniti di beneficiare dei risparmi sui costi e della rigorosa sicurezza di Microsoft Cloud.

## <a name="april-2020-updates"></a>Aggiornamenti di aprile 2020

Gli aggiornamenti di aprile 2020 includono diverse funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="new-and-updated-features-in-april-2020"></a>Funzionalità nuove e aggiornate ad aprile 2020

#### <a name="activities"></a>Impegni

- **Mappare l'entità impegno sul tipo di impegno standard**
  
  La configurazione e l'archiviazione dell'impegno sono attualmente basate su una progettazione statica per essere incluse in una sequenza temporale. Il significato semantico degli impegni, che ha il potenziale per più casi d'uso nei modelli di intelligenza artificiale, al momento non è pienamente utilizzato. Abbiamo in programma di rendere la sequenza temporale degli impegni più dinamica, in base al tipo di impegno e alla migliore comprensione semantica degli impegni. Questa funzione ha lo scopo di identificare il tipo di impegno come definito nel Common Data Model per qualsiasi impegno inserito.
  Per altre informazioni, vedi [Impegni cliente](activities.md).

#### <a name="data-ingestion"></a>Inserimento dati

- **Inserimento dati in tempo reale: impegni**
  
  L'inserimento dati in tempo reale fornisce immediatamente dei dati per il consumo, fino a quando il successivo aggiornamento pianificato non estrae questi dati dall'origine dati.    
  Per altre informazioni, vedi [Inserimento dati in tempo reale](real-time-data-ingestion.md).

- **Miglioramenti alla preparazione dei dati**
  
  Scopri di più sui dati inseriti in un'entità. Con il riepilogo dei dati, puoi comprendere le caratteristiche di qualità dei dati che possono essere utili per intraprendere le azioni appropriate.    
  Per ulteriori informazioni, vedi [Esplorare i dati di entità](entities.md#exploring-a-specific-entitys-data).

- **Inserimento di dati analitici da Dynamics 365 con Common Data Service**
  
  Common Data Service consente di creare origini dati. I clienti di Dynamics 365 esistenti possono importare entità analitiche da Common Data Service in Customer Insights. Una singola origine dati può utilizzare contemporaneamente lo stesso lake gestito da Common Data Service in un ambiente Customer Insights.    
  Per ulteriori informazioni, vedi [Connessione ai dati in un data lake gestito da Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Estendibilità

- **Esportare in LiveRamp**

  Attiva i tuoi dati in LiveRamp® per connetterti con oltre 500 piattaforme su ecosistemi digitali, social e TV. Utilizza i tuoi dati in LiveRamp per il targeting, l'eliminazione e la personalizzazione delle campagne pubblicitarie.    
  Per ulteriori informazioni, vedi [Connettore LiveRamp&reg;](export-liveramp.md).

- **Componente aggiuntivo Customer Insights Teams**
  
  Il bot offre funzionalità di ricerca per profili cliente unificati. Mostrerà una scheda con un massimo di 15 campi dal profilo cliente risultante. Più corrispondenze restituiscono un elenco di risultati in cui è possibile selezionare un profilo.    
  Per ulteriori informazioni, vedi [Bot di Teams per Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Misure

- **Pagina elenco di misure**
  
  I miglioramenti alla pagina delle misure includono il supporto per le azioni su una singola misura e su più misure contemporaneamente. Inoltre, troverai un campo di ricerca per trovare e tracciare rapidamente le misure.    
  Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).

- **Miglioramenti alle misure composte**
  
  Gli utenti possono creare, modificare ed eliminare misure basate su altre misure. Ad esempio, una misura costruita su un'altra misura che è stata costruita su una terza misura.

#### <a name="segments"></a>Segmenti

- **Un altro operatore**
  
  L'operatore In-set consente la segmentazione per i clienti in base a diversi possibili valori di stringa. Prima di questo operatore, era necessario costruire tali segmenti con più condizioni OR. L'operatore In-set ti consente di farlo con una sola condizione.    
  Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).

#### <a name="system-administration"></a>Amministrazione di sistema

- **Copiare le impostazioni di configurazione in un nuovo ambiente**
  
  Copia la tua configurazione da un ambiente a un altro. Durante la creazione di un nuovo ambiente, puoi selezionare un ambiente esistente da cui vuoi copiare la configurazione. Attualmente supportiamo per la copia origini dati, unificazione dei dati, relazioni, misure e segmenti. Le credenziali e i dati effettivi dell'origine dati non vengono copiati.    
  Per ulteriori informazioni, vedere [Gestire ambienti](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]