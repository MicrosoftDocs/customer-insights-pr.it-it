---
title: Funzionalità nuove e future
description: Informazioni su nuove funzionalità, miglioramenti e correzioni di bug.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647249"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novità di Dynamics 365 Customer Insights

Siamo lieti di annunciare i nuovissimi aggiornamenti. Questo articolo riassume le funzionalità con anteprima pubblica, i miglioramenti della disponibilità generale e gli aggiornamenti delle funzionalità. Per vedere i piani delle funzionalità a lungo termine, dai un'occhiata ai [piani di rilascio di Dynamics 365 e Power Platform](/dynamics365/release-plans/).

Gli aggiornamenti vengono implementati in base all'area geografica. Quindi alcune aree geografiche potrebbero vedere le funzionalità prima di altre. Se non diversamente specificato, non è necessario intraprendere alcuna azione e l'app viene aggiornata automaticamente senza tempi di inattività.

> [!TIP]
> Per inviare e votare funzionalità richieste e suggerimenti di prodotto, vai al [portale Ideas dell'applicazione Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


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

Per altre informazioni, vedi [Abilitare la condivisione dati con Dataverse nella propria istanza di Azure Data Lake Storage (anteprima)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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