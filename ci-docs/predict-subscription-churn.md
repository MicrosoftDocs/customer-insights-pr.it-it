---
title: Previsione dell'abbandono dell'abbonamento (contiene video)
description: Prevedi se esiste il rischio che un cliente non utilizzi più i prodotti o i servizi relativi all'abbonamento della società.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610241"
---
# <a name="predict-subscription-churn"></a>Previsione dell'abbandono dell'abbonamento

Prevedi se esiste il rischio che un cliente non utilizzi più i prodotti o i servizi relativi all'abbonamento della società. I dati dell'abbonamento includono gli abbonamenti attivi e inattivi per ogni cliente, quindi ci sono più voci per ID cliente.

È necessaria la conoscenza dell'azienda per capire cosa significa l'abbandono per la tua azienda. Supportiamo le definizioni di abbandono basate sul tempo, nel senso che un cliente è considerato come perso dopo un determinato periodo di tempo dalla fine del suo abbonamento.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Prova la previsione di abbandono dell'abbonamento utilizzando dati di esempio: [Guida di esempio per una previsione di abbandono dell'abbonamento](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Prerequisiti

- [Autorizzazioni di collaboratore](permissions.md) come minimo.
- Almeno 10 profili cliente, preferibilmente più di 1.000 clienti univoci.
- Identificatore cliente, un identificatore univoco per abbinare gli abbonamenti ai clienti.
- Dati di abbonamento per almeno il doppio della finestra temporale selezionata. Preferibilmente, da due a tre anni di dati dell'abbonamento. La cronologia degli abbonamenti deve includere:
  - **ID abbonamento**: l'identificatore univoco di un abbonamento.
  - **Data di fine abbonamento**: la data di scadenza dell'abbonamento per il cliente.
  - **Data di inizio abbonamento**: la data in cui inizia l'abbonamento per il cliente.
  - **Data transazione**: la data in cui è avvenuta una modifica dell'abbonamento. Ad esempio, un cliente che acquista o annulla un abbonamento.
  - **È un abbonamento ricorrente**: un campo booleano vero/falso che determina se l'abbonamento verrà rinnovato con lo stesso ID abbonamento senza l'intervento del cliente.
  - **Frequenza ricorrenza (in mesi)**: per gli abbonamenti ricorrenti, è il mese in cui l'abbonamento verrà rinnovato. Ad esempio, un abbonamento annuale che si rinnova automaticamente per un cliente ogni anno per un altro anno ha il valore 12.
  - **Importo abbonamento**: la quantità di valuta che un cliente paga per il rinnovo dell'abbonamento. Può aiutare a identificare modelli per diversi livelli di abbonamento.
- Almeno due record di attività per il 50% dei clienti per i quali desideri calcolare il tasso di abbandono. Le attività del cliente devono includere:
  - **Chiave primaria**: identificatore univoco per un'attività. Ad esempio, una visita al sito Web o un record di utilizzo che mostra che il cliente ha visualizzato un episodio di un programma TV.
  - **Timestamp**: data e ora dell'evento identificato dalla chiave primaria.
  - **Evento**: nome dell'evento che si desidera utilizzare. Ad esempio, un campo chiamato "UserAction" in un servizio di streaming video potrebbe avere il valore di "Visualizzato".
  - **Dettagli:** informazioni dettagliate sull'evento. Ad esempio, un campo chiamato "ShowTitle" in un servizio di streaming video potrebbe avere il valore di un video visto dal cliente.
- Meno del 20% dei valori mancanti nel campo dati dell'entità fornita.

## <a name="create-a-subscription-churn-prediction"></a>Ceare una previsione di abbandono dell'abbonamento

Seleziona **Salva bozza** in qualsiasi momento per salvare la previsione come bozza. La previsione della bozza sarà visibile nella scheda **Previsioni personali**.

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Crea** seleziona **Usa modello** nel riquadro **Modello di abbandono dei clienti**.

1. Seleziona **Abbonamento** per il tipo di abbandono, quindi seleziona **Operazioni preliminari**.

1. Specifica **Assegna un nome al modello** e **Nome entità di output** per distinguerli da altri modelli o entità.

1. Selezionare **Avanti**.

### <a name="define-customer-churn"></a>Definisci abbandono cliente

1. Immetti un valore in **Giorni dalla fine dell'abbonamento** dopo il quale la tua azienda considera il cliente come perso. Questo periodo è in genere collegato ad attività commerciali come offerte o altre attività di marketing che cercano di prevenire la perdita del cliente.

1. Immettere i **Giorni da esaminare nel futuro per prevedere l'abbandono**. Ad esempio, prevedi il rischio di abbandono dei clienti nei prossimi 90 giorni per allinearti agli sforzi di fidelizzazione del marketing. Prevedere il rischio di abbandono per periodi di tempo più o meno lunghi può rendere più difficile risolvere i fattori nel profilo di rischio di abbandono, a seconda dei requisiti aziendali specifici.

1. Selezionare **Avanti**.

### <a name="add-required-data"></a>Aggiungi dati obbligatori

1. Seleziona **Aggiungi dati** per **Cronologia transazioni**.

1. Seleziona il tipo di attività semantica **Subscription** che contiene le informazioni richieste sulla cronologia degli abbonamenti. Se l'attività non è stata impostata, seleziona **qui** e creala.

1. In **Attività**, se gli attributi dell'attività erano stati mappati a livello semantico al momento della creazione dell'attività, scegli gli attributi o l'entità specifici su cui dovranno essere basati i calcoli. Se il mapping semantico non era stato eseguito, seleziona **Modifica** e mappa i tuoi dati.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Aggiungere i dati richiesti per il modello di abbandono dell'abbonamento":::

1. Seleziona **Avanti** e rivedi gli attributi richiesti per questo modello.

1. Seleziona **Salva**.

1. Seleziona **Aggiungi dati** per **Attività dei clienti**.

1. Seleziona il tipo di attività semantica che fornisce le informazioni sull'attività del cliente. Se l'attività non è stata impostata, seleziona **qui** e creala.

1. In **Attività**, se gli attributi dell'attività erano stati mappati a livello semantico al momento della creazione dell'attività, scegli gli attributi o l'entità specifici su cui dovranno essere basati i calcoli. Se il mapping semantico non era stato eseguito, seleziona **Modifica** e mappa i tuoi dati.

1. Seleziona **Avanti** e rivedi gli attributi richiesti per questo modello.

1. Seleziona **Salva**.

1. Aggiungi ulteriori attività oppure seleziona **Avanti**.

### <a name="set-update-schedule"></a>Impostare la pianificazione di aggiornamento

1. Scegli la frequenza con cui ripetere il training del modello. Questa impostazione è importante per aggiornare la precisione delle previsioni a mano a mano che i nuovi dati vengono inseriti in Customer Insights. La maggior parte delle aziende può ripetere il training una volta al mese e ottenere una buona precisione per le loro previsioni.

1. Selezionare **Avanti**.

### <a name="review-and-run-the-model-configuration"></a>Rivedere ed eseguire la configurazione del modello

Il passaggio **Rivedi ed esegui** mostra un riepilogo della configurazione e offre la possibilità di apportare modifiche prima di creare la previsione.

1. Seleziona **Modifica** per una qualsiasi delle fasi per rivedere e apportare modifiche.

1. Se tutti i valori sono configurati correttamente, selezionare **Salva ed esegui** per avviare l'esecuzione del modello. Seleziona **Fatto**. La scheda **Previsioni personali** viene visualizzata durante la creazione della previsione. Il completamento del processo potrebbe richiedere diverse ore a seconda della quantità di dati utilizzati nella previsione.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visualizzare i risultati della previsione

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Previsioni personali** seleziona la previsione che vuoi visualizzare.

Esistono tre sezioni principali di dati nella pagina dei risultati:

- **Prestazioni modello di training**: i voti A, B o C indicano le prestazioni della previsione e possono aiutarti a prendere la decisione di usare i risultati archiviati nell'entità di output.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Immagine della casella delle informazioni sul punteggio del modello con il voto A.":::

  I voti sono determinati in base alle seguenti regole:
  - **A** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è superiore al tasso di abbandono storico medio di almeno il 10%.
  - **A** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è fino al 10% superiore al tasso di abbandono storico medio.
  - **C** quando il modello ha fornito una previsione corretta con un precisione inferiore al 50% delle previsioni totali oppure quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è inferiore al tasso di abbandono storico medio.
  
- **Probabilità di abbandono (numero di clienti)**: Gruppi di clienti basati sul loro rischio previsto di abbandono. Facoltativamente, [crea segmenti di clienti](prediction-based-segment.md) con rischio elevato di abbandono. Tali segmenti aiutano a capire dove dovrebbe posizionare il limite per l'appartenenza al segmento.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Grafico che mostra la distribuzione dei risultati di abbandono, suddivisi in intervalli da 0-100%":::

- **Fattori più influenti:** esistono molti fattori che vengono presi in considerazione durante la creazione della previsione. Ciascuno dei fattori ha la sua importanza calcolata per le previsioni aggregate create da un modello. Usa questi fattori per convalidare i risultati della previsione. Oppure, usa queste informazioni in seguito per [creare segmenti](.//prediction-based-segment.md) che potrebbero contribuire a influenzare il rischio di abbandono per i clienti.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Elenco che mostra i fattori influenti e la loro importanza nella previsione del risultato di abbandono.":::

> [!NOTE]
> Nell'entità di output per questo modello, *ChurnScore* è la probabilità prevista di abbandono e *IsChurn* è un'etichetta binaria basata su *ChurnScore* con soglia di 0,5. Se questa soglia predefinita non funziona per il tuo scenario, [crea un nuovo segmento](segments.md) con la tua soglia preferita. Per visualizzare il punteggio di abbandono, vai a **Dati** > **Entitià** e visualizza la scheda dei dati per l'entità di output definita per questo modello.

[!INCLUDE [footer-include](includes/footer-banner.md)]
