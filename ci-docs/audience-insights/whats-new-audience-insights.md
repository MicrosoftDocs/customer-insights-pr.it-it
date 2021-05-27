---
title: Funzionalità nuove e future
description: Informazioni su nuove funzionalità, miglioramenti e correzioni di bug.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988925"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novità della funzionalità Audience Insights di Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Siamo lieti di annunciare i nuovissimi aggiornamenti. Questo articolo riassume le funzionalità con anteprima pubblica, i miglioramenti della disponibilità generale e gli aggiornamenti delle funzionalità. Per vedere i piani delle funzionalità a lungo termine, dai un'occhiata ai [piani di rilascio di Dynamics 365 e Power Platform](/dynamics365/release-plans/).

Gli aggiornamenti vengono implementati in base all'area geografica. Quindi alcune aree geografiche potrebbero vedere le funzionalità prima di altre. Se non diversamente specificato, non è necessario intraprendere alcuna azione e l'app viene aggiornata automaticamente senza tempi di inattività.

> [!TIP]
> Per inviare e votare funzionalità richieste e suggerimenti di prodotto, vai al [portale Ideas dell'applicazione Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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

- **Esporta segmenti in RollWorks** Abbiamo esteso le nostre destinazioni di esportazione per includere RollWorks. Ora puoi esportare segmenti da Customer Insights agli elenchi di RollWorks e utilizzarli come base per le tue pubblicità B2B.    
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




[!INCLUDE[footer-include](../includes/footer-banner.md)]