---
title: Analisi valutazione per il feedback dei clienti
description: Scopri come utilizzare un modello di analisi valutazione sul feedback dei clienti in Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: b06613b00a512a31479f9d30d539a010e17d33ba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231470"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizzare la valutazione nel feedback dei clienti (anteprima)

Al giorno d'oggi i clienti si aspettano prodotti, servizi ed esperienze di alta qualità. Soprattutto i clienti che condividono il loro feedback. È molto difficile per le organizzazioni analizzare un volume crescente di dati senza ridurre la precisione e aumentare il costo del lavoro. Dynamics 365 Customer Insights offre un modello di analisi valutazione per il feedback dei clienti che consente alle organizzazioni di analizzare i propri dati in modo più accurato e a un costo inferiore.

L'analisi valutazione consente di sintetizzare la valutazione dei clienti e identificare gli aspetti aziendali come opportunità di miglioramento. Questa funzione di Customer Insights ti aiuta a capire cosa funziona bene e cosa devi correggere. Concentrati sulle aree aziendali più rilevanti e di impatto per migliorare l'esperienza dei tuoi clienti. In definitiva, può aiutarti a guidare le azioni aziendali che consentono esperienze che si traducono in un'elevata soddisfazione e fidelizzazione dei clienti.

## <a name="overview"></a>Descrizione

La funzione di analisi valutazione genera due informazioni dettagliate derivate per ID cliente. Un punteggio di valutazione (da -5 a 5) e un elenco di aspetti aziendali applicabili (aree di attività) aiutano a comprendere meglio il feedback dei clienti. 

Queste informazioni possono aiutarti a ottenere i seguenti risultati: 
- Ottieni una panoramica delle valutazioni dei clienti per un marchio o un'organizzazione
- Identifica i clienti con una valutazione negativa per concentrare le tue campagne e i tuoi impegni e ottimizzare per un maggiore ritorno  
- Identificare gli aspetti aziendali con i problemi segnalati dai clienti  
- Segmenta i clienti in base alla loro valutazione per eseguire campagne personalizzate con impegni mirati di vendita, marketing e supporto
- Ottimizza le operazioni aziendali affrontando le aree di interesse o le opportunità menzionate dai clienti
- Riconosci gli aspetti aziendali che stanno andando bene e premia i clienti soddisfatti attraverso programmi di fidelizzazione e promozione

Per garantire di poterti fidare dei risultati dei modelli, forniamo informazioni trasparenti su come i modelli prendono le decisioni. Otterrai un elenco di parole che hanno influenzato la decisione dei modelli di assegnare un particolare punteggio di valutazione o un aspetto aziendale ai commenti di feedback.  

Usiamo due **Modelli di elaborazione del linguaggio naturale (NLP)**: il primo assegna a ciascun commento di feedback un punteggio di valutazione. Il secondo modello associa ogni feedback a tutti gli aspetti aziendali applicabili. I modelli sono formati su dati pubblici provenienti da fonti nei settori dei social media, della vendita al dettaglio, della ristorazione, dei prodotti di consumo e dell'auto.    
  
Gli aspetti aziendali predefiniti per il modello da associare ai dati di feedback includono:
-   Gestione account
-   Checkout e pagamento
-   Supporto tecnico
-   Prelievo presso il punto vendita
-   Spedizione e recupero imballaggi
-   Pre-ordine
-   Prezzo
-   Privacy e sicurezza
-   Promozioni e premi
-   Ricevuta e garanzia
-   Annullamento e resi e cambi
-   Accuratezza evasione
-   Qualità app/sito Web

> [!NOTE]
> Attualmente, supportiamo solo l'analisi valutazione sul feedback dei clienti in inglese. Verranno supportate altre lingue in futuro. Se viene caricato un feedback in altre lingue, il modello restituirà comunque i risultati. Tuttavia, questi risultati non saranno accurati. 

## <a name="prerequisites"></a>Prerequisiti

L'analisi valutazione si basa sui dati di feedback che sono passati attraverso il [processo di unificazione dei dati](data-unification.md). Consigliamo vivamente di [configurare le tue entità di dati di feedback come entità di attività di tipo semantico](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (tipo di feedback) in anticipo. 

Per configurare un modello di analisi valutazione, sono necessarie almeno le [autorizzazioni di collaboratore](permissions.md).

Customer Insights può elaborare fino a 10 milioni di record di feedback per una singola esecuzione del modello. Il modello può analizzare i commenti di feedback fino a 128 parole. Se un commento di feedback è più lungo, l'analisi considera solo le prime 128 parole.

### <a name="data-requirements"></a>Requisiti dei dati
  
Sono richiesti i seguenti attributi di dati:
- Unified Customer ID (UCID) per abbinare i record di dati di feedback di testo a un singolo cliente. Questo ID è il risultato del [processo di unificazione dei dati](data-unification.md).
- ID commenti
- Timestamp del feedback
- Testo dei commenti   

> [!TIP]
> L'analisi valutazione richiede il feedback di testo dei tuoi clienti. Attualmente è possibile configurare solo un'entità di feedback. Se sono presenti più entità di feedback, puoi unirle in Power Query prima che inizi l'importazione dei dati.

## <a name="configure-a-sentiment-analysis"></a>Configurazione dell'analisi valutazione 

1. In Customer Insights, vai a **Intelligence** > **Previsioni**.

1. Nel riquadro **Analisi valutazione dei clienti** seleziona **Usa modello**.

1. Nel riquadro **Analisi valutazione dei clienti (anteprima)** seleziona **Inizia**.

1. Nel passaggio **Nome modello** fornisci un **Nome** per la tua analisi. 

1. Fornisci il **Nome entità di output aspetto aziendale** e il **Nome entità di output punteggio valutazione**, quindi seleziona **Avanti**.

1. Nel passaggio **Dati obbligatori** seleziona **Aggiungi dati**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Aggiungi il flusso di dati nel modello di analisi valutazione.":::

1. Nel riquadro **Aggiungi dati** scegli il tipo semantico **Feedback** dall'elenco.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Passaggio di configurazione per selezionare le attività di feedback per l'analisi valutazione.":::

1. Seleziona le attività da utilizzare per l'analisi valutazione e quindi seleziona **Avanti**.
 
1. Mappa gli attributi dei tuoi dati agli attributi del modello. Seleziona **Salva** per applicare le selezioni. 

1. Viene visualizzato lo stato del mapping dei dati. Selezionare **Avanti** per continuare. 

1. Nel passaggio **Rivedi i dettagli del modello** convalida la configurazione della tua analisi valutazione. Puoi tornare a qualsiasi parte della configurazione della previsione. Seleziona **Salva ed esegui** per avviare l'analisi. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Passaggio di revisione per il modello di valutazione che mostra tutti gli elementi configurati.":::

1. Seleziona **Fatto** per uscire dall'esperienza di configurazione. Il completamento del processo potrebbe richiedere diverse ore a seconda della quantità di dati utilizzati. 

## <a name="review-analysis-status"></a>Revisione dello stato dell'analisi

1.  Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.
2.  Seleziona la previsione da rivedere.
- **Nome previsione:** il nome del previsione fornito durante la creazione.
- **Tipo di previsione:** il tipo di modello utilizzato per la previsione.
- **Entità di output:** nome dell'entità per memorizzare l'output della previsione. Vai a **Dati** > **Entità** per trovare l'entità con questo nome.
- **Campo previsione:** questo campo viene popolato solo per alcuni tipi di previsioni e non viene utilizzato nella previsione del valore di durata del cliente.
- **Stato:** lo stato dell'esecuzione della previsione.
  - **In coda:** la previsione attende il completamento di altri processi.
  - **Aggiornamento in corso:** la previsione è attualmente in esecuzione per creare risultati che verranno inseriti nell'entità di output.
  - **Errore:** l'esecuzione della previsione non è riuscita. Esamina i log per maggiori informazioni.
  - **Completata:** la previsione è riuscita. Seleziona Visualizza sotto i puntini di sospensione verticali per esaminare i risultati della previsione.
- **Data di modifica**: la data in cui è stata modificata la configurazione per la previsione.
- **Ultimo aggiornamento**: la data in cui la previsione aggiornata viene restituita nell'entità di output.

## <a name="manage-sentiment-analysis"></a>Gestione dell'analisi valutazione

Puoi ottimizzare, risolvere i problemi, aggiornare o eliminare le previsioni. Esamina un report sull'usabilità dei dati di input per scoprire come rendere un previsione più veloce e affidabile. Per ulteriori informazioni, vedi [Gestisci previsioni](manage-predictions.md).

## <a name="review-analysis-results"></a>Revisione dei risultati dell'analisi
 
1. Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**. 
1. Seleziona il nome della previsione per cui vuoi vedere i risultati. In questo caso, seleziona l'analisi valutazione che desideri rivedere. 

### <a name="summary-tab"></a>Scheda Riepilog

Ci sono quattro sezioni principali di dati all'interno della pagina dei risultati. 

- **Punteggio di valutazione medio**: ti aiuta a comprendere la valutazione generale di tutti i clienti. I punteggi di valutazione sono raggruppati in tre categorie: 
  1.    Negativo (-5 > 2)
  2.    Neutro (-1 > 1)
  3.    Positivo (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Rappresentazione visiva della valutazione generale dei clienti.":::

- **Distribuzione dei clienti per punteggio di valutazione**: i clienti sono classificati in gruppi negativi, neutri e positivi in base ai loro punteggi di valutazione. Passa il mouse sopra le barre dell'istogramma per vedere il numero di clienti e il punteggio medio di valutazione in ciascun gruppo. Questi dati possono aiutarti a [creare segmenti di clienti](segments.md) in base ai loro punteggi di valutazione.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Grafico a barre mostra la valutazione del cliente nei tre gruppi di valutazioni.":::

- **Punteggio medio di valutazione nel tempo**: la valutazione del cliente può cambiare nel tempo. Forniamo le tendenze di valutazione dei tuoi clienti per l'intervallo di tempo dei tuoi dati. Questa visualizzazione può aiutarti a valutare l'effetto di promozioni stagionali, lanci di prodotti o altri interventi a scadenza sulla valutazione dei clienti. Visualizza il grafico selezionando l'anno di interesse dal menu a discesa. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Grafico cronologico con il punteggio di valutazione nel tempo rappresentato da una linea.":::
 
- **Valutazione degli aspetti aziendali**: questa tabella elenca la valutazione media degli aspetti aziendali. Può aiutarti a valutare quali aspetti della tua attività soddisfano già i clienti o gli aspetti che richiedono maggiore attenzione. I record di feedback che non si allineano a nessuno degli aspetti aziendali supportati sono classificati in **Altro**. Per impostazione predefinita la taella è ordinata in ordine alfabetico. È possibile modificare l'ordine selezionando l'intestazione della tabella.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Elenco degli aspetti aziendali con l'associato tipo di valutazione e il numero di clienti che lo menzionano.":::
 
  Seleziona il nome di un aspetto aziendale per visualizzare ulteriori informazioni su come viene identificato dal modello. Ci sono due parti in questo riquadro: 

  - **Parole influenti**: mostra le parole principali che hanno influenzato l'identificazione del modello di intelligenza artificiale di un aspetto aziendale nel feedback dei clienti. 
    **Mostra parole offensive**: consente di includere parole offensive nell'elenco dai dati di feedback dei clienti originali. Per impostazione predefinita, è disattivato.  Il mascheramento delle parole offensive è alimentato da un modello di intelligenza artificiale e potrebbe non rilevare tutte le parole offensive. Continuiamo a ripetere e addestrare il classificatore per ottenere prestazioni ottimali. Se rilevi una parola offensiva che non è stata filtrata come previsto, faccelo sapere. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Elenco di parole influenti con l'interruttore per mostrare o nascondere le parole offensive.":::
 
  - **Esempi di feedback**: mostra i record di feedback effettivi nei tuoi dati. Le parole sono codificate a colori in base alla loro influenza sull'identificazione di un aspetto aziendale. 


### <a name="influential-words-analysis-tab"></a>Scheda Analisi delle parole influenti

Ci sono tre sezioni di informazioni aggiuntive che spiegano come funziona il modello di valutazione.
  
1. **Parole più significative che contribuiscono alla valutazione positiva**: mostra le parole principali che hanno influenzato l'identificazione della valutazione positiva del modello di intelligenza artificiale nel feedback dei clienti.  
2. **Parole più significative che contribuiscono alla valutazione negativa**: mostra le parole principali che hanno influenzato l'identificazione della valutazione negativa del modello di intelligenza artificiale nel feedback dei clienti.  
3. **Esempi di feedback**: mostra i record di feedback effettivi, uno con una valutazione negativa e uno con una valutazione positiva. Le parole nei record di feedback sono evidenziate in base al loro contributo al punteggio di valutazione assegnato. Le parole che contribuiscono a un punteggio di valutazione positivo sono evidenziate in verde. Le parole che contribuiscono a un punteggio negativo sono evidenziate in rosso.
   Seleziona **Vedi altro** per caricare più esempi di feedback che forniscono più informazioni e contesto su come funziona il modello di valutazione.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Esempi di analisi valutazione sul feedback dei clienti.":::
 
**Mostra parole offensive**: consente di includere parole offensive nell'elenco dai dati di feedback dei clienti originali. Per impostazione predefinita, è disattivato.  Il mascheramento delle parole offensive è alimentato da un modello di intelligenza artificiale e potrebbe non rilevare tutte le parole offensive. Continuiamo a ripetere e addestrare il classificatore per ottenere prestazioni ottimali. Se rilevi una parola offensiva che non è stata filtrata come previsto, faccelo sapere. 

## <a name="act-on-analysis-results"></a>Azione sui risultati dell'analisi

Puoi facilmente iniziare a creare nuovi segmenti di clienti dalla pagina dei risultati dell'analisi valutazione selezionando **Crea segmenti** nella parte superiore della pagina dei risultati del modello.

:::image type="content" source="media/create-segment-model.png" alt-text="Barra dei comandi con le opzioni sui modelli di previsione.":::
 
## <a name="potential-bias"></a>Distorsione potenziale

Come con qualsiasi funzione che utilizza l'intelligenza artificiale predittiva, dovresti essere consapevole della potenziale distorsione nei dati che utilizzi per prevedere la valutazione dei clienti. Ad esempio, se raccogli feedback solo digitalmente, potresti perdere il feedback dei clienti che svolgono principalmente affari con te di persona, il che potrebbe influire sull'output della funzione.

Poiché questa funzionalità utilizza mezzi automatizzati per valutare i dati e fare previsioni sulla base di tali dati, ha quindi la capacità di essere utilizzata come metodo di profilatura, come definito dal Regolamento generale sulla protezione dei dati ("GDPR"). L'utilizzo di questa funzionalità per elaborare i dati può essere soggetto al GDPR o ad altre leggi o regolamenti. Sei responsabile di garantire che il tuo utilizzo di Dynamics 365 Customer Insights, inclusa l'analisi valutazione, è conforme a tutte le leggi e ai regolamenti applicabili, comprese le leggi relative alla privacy, ai dati personali, ai dati biometrici, alla protezione dei dati e alla riservatezza delle comunicazioni.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

