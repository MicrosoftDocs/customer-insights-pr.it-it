---
title: Analizzare la valutazione del feedback dei clienti (anteprima)
description: Scopri come utilizzare un modello di analisi valutazione sul feedback dei clienti in Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610471"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizzare la valutazione nel feedback dei clienti (anteprima)

L'analisi valutazione consente di sintetizzare la valutazione dei clienti e identificare gli aspetti aziendali come opportunità di miglioramento. Questa funzione di Customer Insights ti aiuta a capire cosa funziona bene e cosa devi correggere. Può aiutarti a guidare le azioni aziendali che consentono esperienze che si traducono in un'elevata soddisfazione e fidelizzazione dei clienti.

## <a name="overview"></a>Descrizione

La funzione di analisi valutazione genera due informazioni dettagliate derivate per ID cliente. Un punteggio di valutazione (da -5 a 5) e un elenco di aspetti aziendali applicabili (aree di attività) aiutano a comprendere meglio il feedback dei clienti.

Questa analisi presenta diversi vantaggi:
- Ottieni una panoramica delle valutazioni dei clienti per un marchio o un'organizzazione
- Identifica i clienti con una valutazione negativa per concentrare le tue campagne e i tuoi impegni e ottimizzare per un maggiore ritorno  
- Identificare gli aspetti aziendali con i problemi segnalati dai clienti  
- Segmenta i clienti in base alla loro valutazione per eseguire campagne personalizzate con impegni mirati di vendita, marketing e supporto
- Ottimizza le operazioni aziendali affrontando le aree di interesse o le opportunità menzionate dai clienti
- Riconosci gli aspetti aziendali che stanno andando bene e premia i clienti soddisfatti attraverso programmi di fidelizzazione e promozione

Il modello fornisce un elenco di parole che hanno influenzato la decisione dei modelli di assegnare un particolare punteggio di valutazione o un aspetto aziendale ai commenti di feedback.  

Usiamo due **Modelli di elaborazione del linguaggio naturale (NLP)**: il primo assegna a ciascun commento di feedback un punteggio di valutazione. Il secondo modello associa ogni feedback a tutti gli aspetti aziendali applicabili. I modelli sono formati su dati pubblici provenienti da fonti nei settori dei social media, della vendita al dettaglio, della ristorazione, dei prodotti di consumo e dell'auto.
  
Gli aspetti aziendali predefiniti per il modello da associare ai dati di feedback includono:
- Gestione account
- Checkout e pagamento
- Supporto tecnico
- Prelievo presso il punto vendita
- Spedizione e recupero imballaggi
- Pre-ordine
- Prezzo
- Privacy e sicurezza
- Promozioni e premi
- Ricevuta e garanzia
- Annullamento e resi e cambi
- Accuratezza evasione
- Qualità app/sito Web

> [!NOTE]
> Attualmente, supportiamo solo l'analisi valutazione sul feedback dei clienti in inglese. Verranno supportate altre lingue in futuro. Se viene caricato un feedback in altre lingue, il modello restituirà comunque i risultati. Tuttavia, questi risultati non saranno accurati.

## <a name="prerequisites"></a>Prerequisiti

- Almeno [autorizzazioni collaboratore](permissions.md)
- Dati di feedback del testo [unificato](data-unification.md). Consigliamo vivamente di [configurare le tue entità di dati di feedback come entità di attività di tipo semantico](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (tipo di feedback).
- Unified Customer ID (UCID) dall'unificazione dei dati per abbinare i record di dati di feedback di testo a un singolo cliente.
- ID commenti
- Timestamp del feedback
- Testo dei commenti

Customer Insights può elaborare fino a 10 milioni di record di feedback per una singola esecuzione del modello. Il modello può analizzare i commenti di feedback fino a 128 parole. Se un commento di feedback è più lungo, l'analisi considera solo le prime 128 parole.

> [!NOTE]
> È possibile configurare solo un'entità di feedback. Se sono presenti più entità di feedback, uniscile in Power Query prima dell'inserimento dati.

## <a name="configure-a-sentiment-analysis"></a>Configurazione dell'analisi valutazione

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Crea** seleziona **Usa modello** nel riquadro **Analisi della valutazione del cliente (anteprima)**.

1. Seleziona **Richiedi una demo**.

1. Assegna un **Nome** all'analisi e fornici il **Nome entità di output aspetto aziendale** e il **Nome entità di output punteggio valutazione**.

1. Selezionare **Avanti**.

1. Seleziona **Aggiungi dati** per **Feedback cliente**.

1. Seleziona il tipo di attività semantica **Feedback** che contiene i dati di feedback. Se l'attività non è stata impostata, seleziona **qui** e creala.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Passaggio di configurazione per selezionare le attività di feedback per l'analisi valutazione.":::

1. Seleziona le attività da utilizzare per l'analisi valutazione e quindi seleziona **Avanti**.

1. Mappa gli attributi dei tuoi dati agli attributi del modello. 

1. Seleziona **Salva**.

1. Selezionare **Avanti**. Il passaggio **Rivedi ed esegui** mostra un riepilogo della configurazione e offre la possibilità di apportare modifiche prima di creare l'analisi.

1. Seleziona **Modifica** per una qualsiasi delle fasi per rivedere e apportare modifiche.

1. Se tutti i valori sono configurati correttamente, selezionare **Salva ed esegui** per avviare l'esecuzione del modello. Seleziona **Fatto**. La scheda **Previsioni personali** viene visualizzata durante la creazione della previsione. Il completamento del processo potrebbe richiedere diverse ore a seconda della quantità di dati utilizzati nella previsione.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Visualizzare i risultati dell'analisi

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Previsioni personali** seleziona la previsione che vuoi visualizzare.

Esistono due schede di risultati.

### <a name="sumary-tab"></a>Scheda Riepilogo

Ci sono quattro sezioni principali di dati all'interno della pagina dei risultati.

- **Punteggio di valutazione medio**: il punteggio di valutazione ti aiuta a comprendere la valutazione generale di tutti i clienti.
  - **Negativo** (-5 > 2)
  - **Neutro** (-1 > 1)
  - **Positivo** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Rappresentazione visiva della valutazione generale dei clienti.":::

- **Distribuzione dei clienti per punteggio di valutazione**: i clienti sono classificati in gruppi negativi, neutri e positivi in base ai loro punteggi di valutazione. Passa il mouse sopra le barre dell'istogramma per vedere il numero di clienti e il punteggio medio di valutazione in ciascun gruppo. Questi dati possono aiutarti a [creare segmenti di clienti](prediction-based-segment.md) in base ai loro punteggi di valutazione.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Grafico a barre mostra la valutazione del cliente nei tre gruppi di valutazioni.":::

- **Punteggio medio di valutazione nel tempo**: la valutazione del cliente può cambiare nel tempo. Forniamo le tendenze di valutazione dei tuoi clienti per l'intervallo di tempo dei tuoi dati. Questa visualizzazione ti aiuta a valutare l'effetto di promozioni stagionali, lanci di prodotti o altri interventi a scadenza sulla valutazione dei clienti. Visualizza il grafico selezionando l'anno di interesse dal menu a discesa.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Grafico cronologico con il punteggio di valutazione nel tempo rappresentato da una linea.":::

- **Valutazione degli aspetti aziendali** : la valutazione media degli aspetti aziendali ti aiuta a valutare quali aspetti della tua attività soddisfano già i clienti o richiedono maggiore attenzione. I record di feedback che non si allineano a nessuno degli aspetti aziendali supportati sono classificati in **Altro**. Ordina i dati selezionando una colonna qualsiasi.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Elenco degli aspetti aziendali con l'associato tipo di valutazione e il numero di clienti che lo menzionano.":::

  Seleziona il nome di un aspetto aziendale per visualizzare come questo viene identificato dal modello:

  - **Parole influenti**: le parole principali che hanno influenzato l'identificazione del modello di intelligenza artificiale di un aspetto aziendale nel feedback dei clienti.
    **Mostra parole offensive**: consente di includere parole offensive nell'elenco dai dati di feedback dei clienti originali. Per impostazione predefinita, è disattivato.  Il mascheramento delle parole offensive è alimentato da un modello di intelligenza artificiale e potrebbe non rilevare tutte le parole offensive. Se rilevi una parola offensiva che non è stata filtrata come previsto, faccelo sapere.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Elenco di parole influenti con l'interruttore per mostrare o nascondere le parole offensive.":::

  - **Esempi di feedback**: i record di feedback effettivi nei tuoi dati. Le parole sono codificate a colori in base alla loro influenza sull'identificazione di un aspetto aziendale.

### <a name="influential-words-analysis-tab"></a>Scheda Analisi delle parole influenti

Ci sono tre sezioni di informazioni aggiuntive che spiegano come funziona il modello di valutazione.
  
- **Parole più significative che contribuiscono alla valutazione positiva**:le parole principali che hanno influenzato l'identificazione della valutazione positiva del modello di intelligenza artificiale nel feedback dei clienti.  

- **Parole più significative che contribuiscono alla valutazione negativa**: le parole principali che hanno influenzato l'identificazione della valutazione negativa del modello di intelligenza artificiale nel feedback dei clienti.

- **Esempi di feedback**: i record di feedback effettivi, uno con una valutazione negativa e uno con una valutazione positiva. Le parole nei record di feedback sono evidenziate in base al loro contributo al punteggio di valutazione assegnato. Le parole che contribuiscono a un punteggio di valutazione positivo sono evidenziate in verde. Le parole che contribuiscono a un punteggio negativo sono evidenziate in rosso.
   Seleziona **Visualizza altro** per caricare altri esempi di feedback.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Esempi di analisi valutazione sul feedback dei clienti.":::

**Mostra parole offensive**: consente di includere parole offensive nell'elenco dai dati di feedback dei clienti originali. Per impostazione predefinita, è disattivato.  Il mascheramento delle parole offensive è alimentato da un modello di intelligenza artificiale e potrebbe non rilevare tutte le parole offensive. Se rilevi una parola offensiva che non è stata filtrata come previsto, faccelo sapere.

## <a name="act-on-analysis-results"></a>Azione sui risultati dell'analisi

Per creare nuovi segmenti di clienti dai risultati dell'analisi valutazione, seleziona **Crea segmenti** nella parte superiore della pagina dei risultati del modello.

## <a name="potential-bias"></a>Distorsione potenziale

Come con qualsiasi funzionalità che utilizza l'intelligenza artificiale predittiva, devi essere consapevole della potenziale distorsione nei dati che utilizzi per prevedere la valutazione dei clienti. Ad esempio, se raccogli feedback solo digitalmente, potresti perdere il feedback dei clienti che svolgono principalmente affari con te di persona, il che potrebbe influire sull'output della funzione.

Poiché questa funzionalità utilizza mezzi automatizzati per valutare i dati e fare previsioni sulla base di tali dati, ha quindi la capacità di essere utilizzata come metodo di profilatura, come definito dal Regolamento generale sulla protezione dei dati ("GDPR"). L'utilizzo di questa funzionalità per elaborare i dati può essere soggetto al GDPR o ad altre leggi o regolamenti. Sei responsabile di garantire che il tuo utilizzo di Dynamics 365 Customer Insights, inclusa l'analisi valutazione, è conforme a tutte le leggi e ai regolamenti applicabili, comprese le leggi relative alla privacy, ai dati personali, ai dati biometrici, alla protezione dei dati e alla riservatezza delle comunicazioni.

[!INCLUDE [footer-include](includes/footer-banner.md)]

