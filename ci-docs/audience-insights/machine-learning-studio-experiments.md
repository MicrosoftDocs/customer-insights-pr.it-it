---
title: Esperimenti con Machine Learning Studio (versione classica)
description: Utilizza modelli di Machine Learning Studio (versione classica) in Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b979dd177b7c6de1971c02a69748006d041e4d2c3e49a3639dba03212bd7acf9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033728"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Utilizzare modelli basati su Azure Machine Learning Studio (versione classica)

I dati unificati in Dynamics 365 Customer Insights sono una fonte per la creazione di modelli di Machine Learning che possono generare ulteriori informazioni aziendali. Customer Insights si integra con Machine Learning Studio (versione classica) per l'uso di modelli personalizzati. Per vedere come i modelli sviluppati in Azure Machine Learning sono integrati con Customer Insights, vedi [Esperimenti con Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Prerequisiti

- Accesso a Customer Insights
- Abbonamento attivo ad Azure Enterprise
- [Profili cliente unificati](data-unification.md)
- Configurazione dell'[esportazione di entità nell'archivio BLOB di Azure](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Configurare Machine Learning Studio (versione classica)

In un primo passaggio, dobbiamo creare un'area di lavoro e aprire Machine Learning Studio (versione classica).

1. Vai a [https://www.portal.azure.com](https://www.portal.azure.com/) e accedi

1. Seleziona **Crea una risorsa**.

1. Cerca **Area di lavoro di Machine Learning Studio** e seleziona **Crea**.

1. Immetti i dettagli obbligatori per [creare l'area di lavoro](/azure/machine-learning/studio/create-workspace). Scegli il **Piano tariffario del piano di servizi Web** in base alla quantità di dati che intendi importare. Per le migliori prestazioni, seleziona la **Posizione** che è geograficamente più vicina a te.

1. Dopo aver creato la risorsa, verrà visualizzata la dashboard dell'area di lavoro di Machine Learning Studio. Seleziona **Avvia Machine Learning Studio**.

   ![Interfaccia utente di Azure Machine Learning Studio.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Utilizzare Azure Machine Learning Studio

Ora puoi creare un nuovo esperimento o importare un modello di esperimento esistente dalla galleria di esempio. Sono disponibili esperimenti di esempio per tre scenari standard:

- [Previsione sull'abbandono dei clienti](#churn-analysis)

- [Valore di durata del cliente](#customer-lifetime-value-prediction)

- [Suggerimenti di prodotto o migliore azione successiva](#productrecommendation-or-next-best-action)

1. Se crei un nuovo esperimento o utilizzi un modello di esperimento dalla raccolta, devi configurare le proprietà **Importa dati**. Usa l'esperienza guidata o fornisci direttamente i dettagli per accedere all'archivio BLOB di Azure che contiene i tuoi dati.  

   ![Esperimento con Azure Machine Learning Studio.](media/azure-machine-learning-studio-experiment.png)

1. Ora puoi creare una pipeline di elaborazione personalizzata per pulire e preelaborare i dati, estrarre le funzionalità ed eseguire il training di un modello adatto.

1. Testa e ottimizza le prestazioni del modello.

1. Quando sei soddisfatto della qualità di un modello, seleziona **Configura servizio Web** > **Servizio Web predittivo**. Questa opzione importa il modello con training e la pipeline di funzionalità dall'esperimento di training a un servizio predittivo. Il servizio predittivo può prendere un altro set di dati di input con lo schema utilizzato nell'esperimento di training per fare previsioni.

   ![Configurare un servizio Web predittivo.](media/predictive-webservice-control.png)

1. Una volta che l'esperimento del servizio Web predittivo ha esito positivo, è possibile distribuirlo per la pianificazione automatica. Per fare in modo che il servizio Web funzioni con Customer Insights, seleziona **Distribuisci servizio Web** > **Anteprima Distribuisci servizio Web [Nuovo]**. [Scopri di più sulla distribuzione di un servizio Web](/azure/machine-learning/studio/deploy-a-machine-learning-web-service)

   ![Distribuire un servizio Web predittivo.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Modelli di esempio dalla raccolta

Useremo uno scenario fittizio di Contoso Hotel per i modelli in questo articolo. Contoso Hotel raccoglie i seguenti dati:

- Dati CRM costituiti dall'attività di soggiorno in hotel. Il set di dati include informazioni sulle date di soggiorno per ogni cliente registrato. Contiene anche informazioni sulla prenotazione, sui tipi di camera, sui dettagli della spesa e così via. I dati coprono quattro anni, da gennaio 2014 a gennaio 2018.
- Profili cliente degli ospiti dell'hotel. Questi profili contengono informazioni su ogni cliente, inclusi nome, data di nascita, indirizzo postale, sesso e numero di telefono.
- Utilizzo dei servizi offerti dall'hotel, come spa, lavanderia, WiFi o corriere. Queste informazioni vengono registrate per ogni cliente registrato. Tipicamente, l'utilizzo dei servizi è legato al soggiorno. In alcuni casi i servizi possono essere utilizzati dai clienti senza pernottare in hotel.

## <a name="churn-analysis"></a>Analisi dell'abbandono

L'analisi dell'abbandono si applica a diverse aree aziendali. In questo esempio, esamineremo il tasso di abbandono dei servizi, in particolare nel contesto dei servizi alberghieri come descritto sopra. Fornisce un esempio operativo di una pipeline di modelli end-to-end che può essere utilizzata come punto di partenza per qualsiasi altro tipo di modello di abbandono.

### <a name="definition-of-churn"></a>Definizione di abbandono

La definizione di abbandono può variare in base allo scenario. In questo esempio, un ospite che non ha visitato l'hotel nell'ultimo anno dovrebbe essere etichettato come cliente perso.  

Il modello dell'esperimento può essere importato dalla raccolta. Innanzitutto, assicurati di importare i dati per **Attività di soggiorno in hotel**, **Dati dei clienti** e **Dati sull'utilizzo del servizio** dall'archivio BLOB di Azure.

   ![Importare i dati per il modello di abbandono.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Definizione delle funzionalità

Sulla base della definizione di abbandono, identifichiamo prima le funzionalità non elaborate che influenzeranno l'etichetta. Quindi, elaboriamo queste funzionalità non elaborate in funzionalità numeriche che possono essere utilizzate con i modelli di apprendimento automatico. L'integrazione dei dati avviene in Customer Insights di modo che possiamo unire queste tabelle utilizzando l'*ID cliente*.

   ![Unisci i dati importati.](media/join-imported-data.png)

La definizione delle funzionalità per la creazione del modello per l'analisi del tasso di abbandono può rivelarsi complicata. I dati sono una funzione del tempo con la nuova attività alberghiera registrata su base giornaliera. Durante la definizione delle funzionalità, vogliamo generare funzionalità statiche dai dati dinamici. In questo caso, generiamo più funzionalità dall'attività alberghiera con una finestra flessibile di un anno. Espandiamo anche funzionalità di categoria come il tipo di camera o il tipo di prenotazione in funzionalità separate utilizzando la codifica one-hot.  

Elenco finale delle funzionalità:

| **Numero**  | **Original_Column**          | **Funzionalità derivate**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Tipo di stanza                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Tipo di prenotazione                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Categoria di viaggio              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Soldi spesi                | TotalDollarSpent                                                                                                                          |
| 5           | Date di check-in e check-out  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Utilizzo del servizio                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Selezione del modello

Ora dobbiamo scegliere l'algoritmo ottimale da utilizzare. In questo caso, la maggior parte delle funzionalità si basa su funzionalità di categoria. In genere, i modelli basati su albero decisionale funzionano bene. Se sono disponibili solo funzionalità numeriche, le reti neurali potrebbero essere una scelta migliore. Anche la Support Vector Machine (SVM) è un buon candidato in tali situazioni; tuttavia, deve essere perfezionata per ottenere le migliori prestazioni. Scegliamo **Albero decisionale promosso a due classi** come primo modello di scelta seguito da **SVM a due classi** come secondo modello. Azure Machine Learning Studio consente di eseguire test A/B, pertanto è utile iniziare con due modelli anziché uno.

L'immagine seguente mostra la pipeline di training e valutazione del modello da Azure Machine Learning Studio:

![Modello di abbandono in Azure Machine Learning Studio.](media/azure-machine-learning-model.png)

Applichiamo anche una tecnica chiamata **Importanza delle funzionalità di permuta**, un aspetto importante dell'ottimizzazione del modello. I modelli incorporati hanno poche informazioni dettagliate sull'impatto di qualsiasi funzionalità specifica sulla previsione finale. Il calcolatore dell'importanza delle funzionalità utilizza un algoritmo personalizzato per calcolare l'influenza delle singole funzionalità sul risultato per un modello specifico. L'importanza della funzionalità è normalizzata tra +1 e -1. Un'influenza negativa significa che la funzionalità corrispondente ha un'influenza contro-intuitiva sul risultato e dovrebbe essere rimossa dal modello. Un'influenza positiva indica che la funzionalità sta contribuendo notevolmente alla previsione. Questi valori non sono coefficienti di correlazione in quanto sono metriche diverse. Per ulteriori informazioni, vedi [Importanza delle funzionalità di permuta](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

L'intero [esperimento di abbandono è disponibile in Azure AI Gallery](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Previsione della durata della relazione con il cliente

Il calcolo della durata della relazione con il cliente è una delle metriche chiave che un'azienda può utilizzare per valutare e segmentare i propri clienti. Per il settore alberghiero è fondamentale conoscere i propri clienti. Ad esempio, la comprensione dei fattori alla base di clienti ottimali è un'informazione cruciale. Aiuta la direzione dell'hotel a valutare le funzionalità su cui deve concentrarsi e migliorare per soddisfare i propri clienti paganti. Queste decisioni possono avere un impatto diretto sulle vendite e sui guadagni.  

### <a name="definition-of-cltv"></a>Definizione della durata della relazione con il cliente

Per questo esempio, definiamo la durata della relazione con il cliente come l'importo totale in dollari che il cliente dovrebbe spendere nei prossimi 365 giorni. Utilizzeremo i dati degli ultimi tre anni per consentire a tutti i clienti di prevedere questo valore.

### <a name="featurization"></a>Definizione delle funzionalità

In questo caso, la funzionalità sarà molto simile allo scenario di abbandono. Tuttavia, le etichette e i valori previsti sono diversi da quelli definiti sopra.

### <a name="model-selection"></a>Selezione del modello

La previsione della durata della relazione con il cliente è un problema di regressione poiché il valore previsto è una variabile continua a valore positivo. In base alle proprietà della funzionalità, selezioniamo **Regressione dell'albero decisionale proposta** come un algoritmo e **Regressione della rete neurale** come un altro algoritmo per eseguire il training del modello.

## <a name="product-recommendation-or-next-best-action"></a>Suggerimenti di prodotto o migliore azione successiva

I suggerimenti di prodotto in uno scenario di hotel vengono interpretati come servizi di suggerimenti offerti dall'hotel ai clienti. L'obiettivo è scegliere i servizi appropriati per i clienti in modo da massimizzarne l'utilizzo. È simile ai suggerimenti sui film per gli utenti del servizio di streaming video.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definizione dei suggerimenti di prodotto o migliore azione successiva

Definiamo l'obiettivo come la massimizzazione della quantità di denaro speso per l'utilizzo del servizio offrendo i migliori servizi di corrispondenza ai clienti dell'hotel in base al loro interesse.

### <a name="featurization"></a>Definizione delle funzionalità

Come il modello di abbandono, stiamo unendo il ServiceCustomerID dell'hotel con CustomerID al fine di creare suggerimenti in modo coerente per CustomerID.

![Funzionalità del modello di suggerimenti.](media/azure-machine-learning-model-featurization.png)

I dati provengono da tre diverse entità e le funzionalità sono derivate da esse. La definizione delle funzionalità per il problema dei suggerimenti è diversa rispetto agli scenari di abbandono o durata della relazione con il cliente. Il modello di suggerimenti richiede dati di input sotto forma di tre set di funzionalità.

### <a name="model-selection"></a>Selezione del modello

Prevediamo prodotti o servizi utilizzando l'algoritmo chiamato **Train Matchbox Recommender** per eseguire il training del modello di suggerimenti.

![Algoritmo di suggerimenti per il prodotto.](media/azure-machine-learning-model-recommendation-algorithm.png)

Le tre porte di input per il modello **Train Matchbox Recommender** acquisisce i dati sull'utilizzo del servizio di training, la descrizione del cliente (facoltativa) e la descrizione del servizio. Esistono tre modi diversi per assegnare un punteggio al modello. Uno è per la valutazione del modello in cui viene calcolato un punteggio NDCG (Normalized Discounted Cumulative Gain) per classificare gli elementi valutati. In questo esperimento, il punteggio NDCG è 0,97. Le altre due opzioni sono il punteggio del modello sull'intero catalogo di servizi suggeriti o il punteggio solo sugli elementi che gli utenti non hanno utilizzato prima.

Esaminando ulteriormente le distribuzioni dei suggerimenti sull'intero catalogo dei servizi, notiamo che telefono, WiFi e corriere sono i migliori servizi da consigliare. Ciò è coerente con quanto rilevato dalle distribuzioni dei dati di utilizzo del servizio:

![Risultato del modello di suggerimenti.](media/azure-machine-learning-model-output.png)

L'intero [esperimento dei suggerimenti di prodotto è accessibile in Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrare modelli personalizzati

Per utilizzare queste previsioni in Customer Insights, è necessario **esportare** le previsioni insieme agli ID cliente. [Esportali nella stessa posizione dell'archivio BLOB di Azure](/azure/storage/common/storage-import-export-data-from-blobs) in cui esportare i dati di origine. Il servizio Web predittivo può essere pianificato per essere eseguito regolarmente e aggiornare i punteggi.

I dati generati dal modello personalizzato possono essere utilizzati per arricchire ulteriormente i dati cliente. Per ulteriori informazioni, vedi [Modelli personalizzati apprendimento automatico](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]