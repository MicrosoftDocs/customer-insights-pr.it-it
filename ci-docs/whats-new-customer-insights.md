---
title: Novità di Dynamics 365 Customer Insights
description: Informazioni su nuove funzionalità, miglioramenti e correzioni di bug.
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 4b5b95d1774d22827b3c08c2b6ccbb7858f1b04b
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054023"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novità di Dynamics 365 Customer Insights

Siamo lieti di annunciare i nuovissimi aggiornamenti. Questo articolo riassume le funzionalità con anteprima pubblica, i miglioramenti della disponibilità generale e gli aggiornamenti delle funzionalità. Per vedere i piani delle funzionalità a lungo termine, dai un'occhiata ai [piani di rilascio di Dynamics 365 e Power Platform](/dynamics365/release-plans/).

Gli aggiornamenti vengono implementati in base all'area geografica. Quindi alcune aree geografiche potrebbero vedere le funzionalità prima di altre. Se non diversamente specificato, non è necessario intraprendere alcuna azione e l'app viene aggiornata automaticamente senza tempi di inattività.

> [!TIP]
> Per inviare e votare funzionalità richieste e suggerimenti di prodotto, vai al [portale Ideas dell'applicazione Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2022-updates"></a>Aggiornamenti di maggio 2022

Gli aggiornamenti di maggio 2022 includono nuove funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="updated-data-unification-experience"></a>Esperienza di unificazione dei dati aggiornata

 L'unificazione dei dati ti consente di unificare origini dati un tempo disparate in un unico set di dati principali che fornisce una vista unificata di tali dati. I dati possono essere unificati in una singola entità o in più entità. In primo luogo, [seleziona entità e campi di origine](map-entities.md), [rimuovi record duplicati](remove-duplicates.md), specifica regole per le [condizioni corrispondenti](match-entities.md) e definisci quali [campi includere nei profili cliente unificati](merge-entities.md).

Per altre informazioni, vedi [Panoramica dell'unificazione dei dati](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Home page aggiornata in Customer Insights

La pagina **Home** ti guida nel processo di configurazione delle funzioni chiave e fornisce una panoramica di segmenti, misure e dati di arricchimento. Abbiamo aggiornato l'esperienza per fornire immediatamente informazioni più pertinenti.

Per altre informazioni, vedi [Scopri Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Tenere traccia dell'utilizzo di un segmento

Puoi ora [tenere traccia dell'utilizzo di un segmento](segments.md#track-usage-of-a-segment) nelle app basate sull'organizzazione Dataverse connessa a Customer Insights. Per i [Segmenti di Customer Insights utilizzati nei percorsi del cliente di Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), il sistema ti informa sull'utilizzo di quel segmento.

### <a name="export-to-criteo"></a>Esportazione in Criteo

Criteo è una piattaforma online che aiuta gli utenti a gestire il digital advertising. Puoi esportare segmenti di profili cliente unificati per generare campagne, fornire e-mail marketing e utilizzare gruppi specifici di clienti con Criteo.

Per altre informazioni, vedi [Esportazione di segmenti in Criteo (anteprima)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Struttura della documentazione migliorata per la creazione dell'ambiente

Abbiamo aggiornato i documenti della Guida relativi alla creazione e alla gestione degli ambienti in Customer Insights. Gli articoli sono ora raggruppati nel nodo Ambienti nel sommario. Gli articoli di cui è stata modificata la struttura forniscono maggiori indicazioni sui diversi modi per configurare gli ambienti e ottenere una struttura più chiara. Se hai commenti da condividere, informaci tramite i controlli presenti verso la fine degli articoli della Guida.

Per altre informazioni, vedi [Come creare un nuovo ambiente](create-environment.md).

## <a name="april-2022-updates"></a>Aggiornamenti di aprile 2022

Gli aggiornamenti di aprile 2022 includono nuove funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="dun--bradstreet-enrichment-preview"></a>Arricchimento Dun & Bradstreet (anteprima)

Dun & Bradstreet fornisce dati commerciali, analisi e informazioni dettagliate per le aziende. Consente ai clienti con profili cliente unificati per le aziende di arricchire i propri dati. Gli arricchimenti includono attributi quali il numero DUNS, le dimensioni, l'ubicazione e il settore di attività della società e altro ancora.

Per ulteriori informazioni, vedi [Arricchimento dei profili aziendali con Dun & Bradstreet (anteprima)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definisci il tipo di misura durante la creazione di una nuova misura

Ora puoi distinguere tra misure per profili individuali e misure per l'intera azienda. Mentre le misure aziendali vengono visualizzate nella home page di Customer Insights, quelle dei clienti sono esposte nelle viste dettagliate relative.

Per ulteriori informazioni, vedi [Usare il generatore di misure per creare misure da zero](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Consolidamento della documentazione di Customer Insights

Abbiamo rivisitato i nostri articoli di documentazione e rimosso le menzioni delle funzionalità sulle informazioni dettagliate sul coinvolgimento e sui destinatari. Nel seguito, faremo riferimento in modo coerente al nome del prodotto Customer Insights quando descriviamo le funzionalità principali dell'applicazione. Questa modifica porta anche a una significativa ristrutturazione del sommario, della struttura degli URL e dei percorsi dei file nel repository della documentazione sottostante. Tutti i tuoi segnalibri o link esistenti continuano a funzionare e reindirizzano agli URL aggiornati.

Se vuoi comunicarci come percepisci il cambiamento o se individui qualcosa che non funziona come previsto, [invia il feedback per questa pagina](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Aggiornamenti di marzo 2022

Gli aggiornamenti di marzo 2022 includono nuove funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="liveramp-abilitec-enrichment-preview"></a>Arricchimento LiveRamp AbiliTec (anteprima)

LiveRamp fornisce la risoluzione delle identità offline e il consolidamento dei dati dei clienti. Puoi mappare gli identificatori personali nei dati dei clienti sul grafico dell'identità AbiliTec e ricevere ID AbiliTec. Puoi quindi utilizzare questi ID per una migliore unificazione dei dati dei clienti.

Per altre informazioni, vedi [Arricchire i profili dei clienti con i dati di identità di LiveRamp (Anteprima)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organizza segmenti e misure con tag e filtri

Se l'organizzazione gestisce molti segmenti o misure, la ricerca dell'elemento giusto a volte può sembrare difficile. Questa nuova funzionalità consente di organizzare gli elenchi utilizzando tag e colonne. Aiuta a trovare i dati in modo rapido e semplice e a personalizzare le visualizzazioni.

Per altre informazioni, vedi [Utilizzare tag e colonne](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Abilita la condivisione dei dati con Dataverse quando utilizzi l'account di archiviazione

Se l'ambiente utilizza Azure Data Lake Storage per archiviare i dati di Customer Insights, per l'abilitazione della condivisione dei dati con Microsoft Dataverse è necessaria una configurazione aggiuntiva.
In precedenza, potevi abilitare la condivisione dei dati con Dataverse solo quando i dati erano archiviati nel nostro data lake gestito.

Per altre informazioni, vedi [Abilitare la condivisione dati con Dataverse nella propria istanza di Azure Data Lake Storage (anteprima)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nuove destinazioni di esportazione: Iterable e Braze

Continuiamo a espandere il nostro ecosistema di destinazioni di esportazione con nuove connessioni. Ora puoi esportare segmenti in Iterable e Braze per utilizzarne i servizi di attivazione.

Per altre informazioni, vedi [Esportare segmenti in Iterable (anteprima)](export-iterable.md) ed [Esportare segmenti in Braze (anteprima)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Miglioramenti all'esportazione in Marketo e Google Ads

La modifica delle API nei servizi connessi comporta aggiornamenti per l'esecuzione affidabile e regolare dei connettori. Abbiamo rilasciato alcuni aggiornamenti per le esportazioni verso i servizi Marketo e Google Ads:

- Google Ads: la nuova versione del connettore di esportazione di Google Ads semplifica l'esperienza di autenticazione e ora consente di creare automaticamente nuovi segmenti di pubblico di Google Ads. 
- Marketo: la nuova versione del connettore di esportazione Marketo fornisce supporto per l'ID Marketo, consentendoti di evitare la duplicazione dei dati, aggiornare i record esistenti e creare nuovi record in Marketo. 

## <a name="february-2022-updates"></a>Aggiornamenti di febbraio 2022

Gli aggiornamenti di febbraio 2022 includono nuove funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="general-availability-for-prediction-models"></a>Disponibilità generale per i modelli di previsione

I modelli di previsione predefiniti, inclusi **abbandono degli abbonamenti**, **abbandono transazionale**, e **durata del cliente (CLV)** diventano generalmente disponibili come parte di Customer Insights. 

Per ulteriori informazioni, vedere [Panoramica delle previsioni](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nuova origine dati: integrazione con Azure Synapse Analytics (Anteprima)

Azure Synapse Analytics è un servizio di analisi aziendale che accelera il tempo per ottenere informazioni dettagliate tra i data warehouse e i sistemi di big data.

Le organizzazioni che utilizzano già Azure Synapse Analytics possono importare tali dati in Customer Insights. 

Per altre informazioni, vedi [Connessione a un'origine dati Azure Synapse (anteprima)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Arricchimento LiveRamp (anteprima)

LiveRamp fornisce la risoluzione delle identità offline e il consolidamento dei dati dei clienti. Puoi mappare gli identificatori personali nei dati dei clienti sul grafico dell'identità AbiliTec e ricevere ID AbiliTec. Puoi quindi utilizzare questi ID per una migliore unificazione dei dati dei clienti.

Per altre informazioni, vedi [Arricchire i profili dei clienti con i dati di identità di LiveRamp (Anteprima)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Arricchimento per le origini dati (anteprima)

Usa i dati provenienti da origini come Microsoft e altri partner per arricchire i dati dei tuoi clienti prima dell'unificazione dei dati. Gli arricchimenti per le origini dati aiutano a produrre una maggiore completezza e qualità dei dati che possono aiutare a ottenere risultati migliori una volta unificati.

Per altre informazioni, vedi [Arricchimento per le origini dati (anteprima)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Cambia proprietario dell'ambiente

Sebbene diversi utenti possano disporre delle autorizzazioni di amministratore in Customer Insights, solo un utente è il proprietario di un ambiente. Un'esperienza migliorata ti consente di cambiare proprietario di un ambiente e rivendicare la proprietà se un ex proprietario che ha lasciato l'organizzazione. 

Per ulteriori informazioni, vedi [Cambiare il proprietario di un ambiente](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Il processo di preparazione dei dati elenca il motivo del danneggiamento dei record danneggiati

La preparazione dei dati ora mostra il motivo del danneggiamento per tutti i campi con dati danneggiati. Le informazioni sono fornite a livello di record individuale per una facile identificazione. 

Per altre informazioni, vedi [Origini dati danneggiate](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Fine dell'anteprima per le funzionalità di creazione di report nella funzionalità di informazioni dettagliate sul coinvolgimento

L'anteprima della capacità delle informazioni dettagliate sul coinvolgimento di Dynamics 365 Customer Insights è terminata il 15 febbraio 2022.  
Questa modifica significa che l'esperienza di prova di Customer Insights non include più la possibilità di creare funnel né altre funzionalità di reporting.

Ti invitiamo ad esplorare e valutare le tante altre caratteristiche di [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), la piattaforma dati dei clienti Microsoft (CDP).    
 
Per un periodo di transizione, i partecipanti all'anteprima hanno ancora accesso ad alcune capacità e funzionalità di anteprima:

- Ottieni il codice per strumentare un sito Web o un'app mobile 
- Visualizza gli eventi e le proprietà degli eventi 
- Migliora i profili unificati con eventi inseriti e perfezionati per beneficiare di tutto il valore dei dati dei clienti
  
Durante il periodo di transizione, gli eventi acquisiti vengono comunque trasmessi in streaming al Data Lake connesso. Una volta disattivata questa funzionalità, la condivisione dei dati verrà interrotta e nessun nuovo evento verrà inviato all'archiviazione connessa.
Contatta direttamente il team dell'account Microsoft in caso di domande sulla fine dell'anteprima delle funzionalità. Il team del tuo account ti terrà aggiornato sui prossimi lanci. 

## <a name="january-2022-updates"></a>Aggiornamenti di gennaio 2022

Gli aggiornamenti di gennaio 2022 includono nuove funzionalità, aggiornamenti delle prestazioni e correzioni di bug.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analisi valutazione per il feedback dei clienti

Customer Insights fornisce una nuova funzionalità basata sull'intelligenza artificiale per sintetizzare la valutazione dei clienti e identificare aspetti aziendali specifici come opportunità per miglioramenti mirati. Analizzando il feedback scritto dai tuoi clienti, puoi ottenere informazioni dettagliate accurate a basso costo. L'analisi della valutazione basata su modelli di elaborazione del linguaggio naturale (NLP) che generano due informazioni dettagliate derivate per ogni ID cliente. Un punteggio di valutazione (da –5 a 5) e un elenco di aspetti aziendali applicabili. 

Per ulteriori informazioni, vedi [Analizzare la valutazione del feedback dei clienti (Anteprima)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]