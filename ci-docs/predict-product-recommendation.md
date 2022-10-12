---
title: Prevedere raccomandazioni sui prodotti
description: Prevedi i prodotti che è probabile che un cliente acquisterà o con cui interagirà.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610287"
---
# <a name="predict-product-recommendations"></a>Prevedere raccomandazioni sui prodotti

Il modello di raccomandazione prodotti crea serie di raccomandazioni predittive sui prodotti. Le raccomandazioni si basano sul comportamento di acquisto precedente e sui clienti con modelli di acquisto simili. Questo modello è per i singoli consumatori (B-to-C).

Devi avere una conoscenza aziendale dei diversi tipi di prodotti del tuo business e sapere come i tuoi clienti interagiscono con essi. Supportiamo la raccomandazione di prodotti che sono stati precedentemente acquistati dai tuoi clienti o raccomandazioni per nuovi prodotti.

Gli elementi consigliati sui prodotti possono essere soggette alle leggi e ai regolamenti locali e alle aspettative dei clienti, che il modello non è stato concepito per tenere specificamente in considerazione. Pertanto, **devi rivedere le raccomandazioni prima di fornirle ai clienti** per assicurarti di rispettare le leggi o i regolamenti applicabili e le aspettative dei clienti per ciò che potresti consigliare.

L'output di questo modello fornisce raccomandazioni basati sull'ID del prodotto. Il tuo meccanismo di fornitura deve mappare gli ID prodotto previsti al contenuto appropriato affinché i tuoi clienti tengano conto della localizzazione, del contenuto dell'immagine e di altri contenuti o comportamenti specifici dell'azienda.

> [!TIP]
> Prova la previsione di raccomandazioni sui prodotti usando i dati di esempio: [Guida di esempio per la previsione di raccomandazioni sui prodotti](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Prerequisiti

- Almeno [autorizzazioni collaboratore](permissions.md)
- Almeno 100 clienti univoci, preferibilmente più di 10.000 clienti.
- Identificatore cliente: un identificatore univoco per abbinare le transazioni a un singolo cliente
- Almeno un anno di dati transazionali, preferibilmente da due a tre anni per includere una certa stagionalità. Idealmente, almeno tre transazioni per ID cliente. La cronologia delle transazioni deve includere:
  - **ID transazione**: un identificatore univoco di un acquisto o di una transazione.
  - **Data transazione**: la data dell'acquisto o della transazione.
  - **Valore della transazione:** il valore numerico dell'acquisto o transazione.
  - **ID prodotto univoco:** l'ID del prodotto o del servizio acquistato se i tuoi dati sono a livello di voce singola.
  - **Acquisto o reso**: un valore booleano vero/falso in cui *vero* identifica la transazione come reso. Se i dati di acquisto o di reso non vengono forniti nel modello e il **Valore della transazione** è negativo, ne dedurremo un reso.
- Un'entità di dati del catalogo prodotti da usare come filtro per i prodotti.

> [!NOTE]
> - Il modello richiede la cronologia delle transazioni dei tuoi clienti in cui la transazione è qualsiasi dato che descrive un'interazione utente-prodotto. Ad esempio, l'acquisto di un prodotto, la partecipazione a un corso o la partecipazione a un evento.
> - È possibile configurare una sola entità di cronologia delle transazioni. Se sono presenti più entità di acquisto, puoi combinarle in Power Query prima dell'inserimento dati.
> - Se l'ordine e i dettagli dell'ordine sono entità diverse, uniscili prima di utilizzarli nel modello. Il modello non funziona solo con un ID ordine o un ID ricevuta in un'entità.

## <a name="create-a-product-recommendation-prediction"></a>Creare una previsione di raccomandazioni sui prodotti

Seleziona **Salva bozza** in qualsiasi momento per salvare la previsione come bozza. La previsione della bozza sarà visibile nella scheda **Previsioni personali**.

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Crea** seleziona **Usa modello** nel riquadro **Consigli sui prodotti (anteprima)**.

1. Seleziona **Richiedi una demo**.

1. Specifica **Assegna un nome al modello** e **Nome entità di output** per distinguerli da altri modelli o entità.

1. Selezionare **Avanti**.

### <a name="define-product-recommendation-preferences"></a>Definire le preferenze per le raccomandazioni sui prodotti

1. Imposta il **Numero di prodotti** da consigliare a un cliente. Questo valore dipende da come il metodo di consegna inserisce i dati.

1. Scegli se desideri includere i prodotti che i clienti hanno precedentemente effettuato acquisti nel campo **Ripetizione degli acquisti prevista**.

1. Imposta la **Finestra per guardare indietro** con l'intervallo di tempo che il modello considera prima di consigliare nuovamente il prodotto all'utente. Ad esempio, indica che un cliente acquista un laptop ogni due anni. Il modello esamina la cronologia degli acquisti degli ultimi due anni e, se trova un articolo, questo viene filtrato dagli elementi consigliati.

1. Selezionare **Avanti**.

### <a name="add-purchase-history"></a>Aggiungi cronologia acquisti

1. Seleziona **Aggiungi dati** per **Cronologia transazioni cliente**.

1. Seleziona il tipo di attività semantica, **SalesOrderLine**, che contiene le informazioni richieste sulla cronologia delle transazioni o degli acquisti. Se l'attività non è stata impostata, seleziona **qui** e creala.

1. In **Attività**, se gli attributi dell'attività erano stati mappati a livello semantico al momento della creazione dell'attività, scegli gli attributi o l'entità specifici su cui dovranno essere basati i calcoli. Se il mapping semantico non era stato eseguito, seleziona **Modifica** e mappa i tuoi dati.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Riquadro laterale che mostra la scelta di impegni specifici nel tipo semantico.":::

1. Seleziona **Avanti** e rivedi gli attributi richiesti per questo modello.

1. Seleziona **Salva**.

1. Selezionare **Avanti**.

### <a name="add-product-information-and-filters"></a>Aggiungere filtri e informazioni sui prodotti

A volte, solo alcuni prodotti sono utili o appropriati per il tipo di previsione che crei. Usa i filtri di prodotto per identificare un sottoinsieme di prodotti con caratteristiche specifiche da consigliare ai tuoi clienti. Il modello utilizzerà tutti i prodotti disponibili per apprendere i modelli, ma utilizzerà solo i prodotti che corrispondono al filtro di prodotto nell'output.

1. Aggiungi la tua entità catalogo prodotti che contiene informazioni per ogni prodotto. Mappa le informazioni richieste e seleziona **Salva**.

1. Selezionare **Avanti**.

1. Seleziona **Filtri prodotti**:

   - **Nessun filtro**: Utilizza tutti i prodotti nella previsione di raccomandazione prodotto.

   - **Definisci filtri di prodotti specifici**: Utilizza prodotti specifici nella previsione di raccomandazione prodotto. Nel riquadro **Attributi catalogo prodotti** seleziona gli attributi dalla tua entità catalogo prodotti che desideri includere nel filtro.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Riquadro laterale che mostra l'attributo nell'entità catalogo prodotti da selezionare per i filtri di prodotto.":::

1. Scegli se desideri utilizzare nel filtro di prodotto i connettori **and** oppure **or** per combinare in modo logico la selezione di attributi dal catalogo prodotti.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Configurazione di esempio dei filtri di prodotto combinati con connettori logici AND.":::

1. Selezionare **Avanti**.

### <a name="set-update-schedule"></a>Impostare la pianificazione di aggiornamento

1. Scegli una frequenza per ripetere il training del modello. Questa impostazione è importante per aggiornare l'accuratezza delle previsioni quando nuovi dati vengono inseriti in Customer Insights. La maggior parte delle aziende può ripetere il training una volta al mese e ottenere una buona precisione per le loro previsioni.

1. Selezionare **Avanti**.

### <a name="review-and-run-the-model-configuration"></a>Rivedere ed eseguire la configurazione del modello

Il passaggio **Rivedi ed esegui** mostra un riepilogo della configurazione e offre la possibilità di apportare modifiche prima di creare la previsione.

1. Seleziona **Modifica** per una qualsiasi delle fasi per rivedere e apportare modifiche.

1. Se tutti i valori sono configurati correttamente, selezionare **Salva ed esegui** per avviare l'esecuzione del modello. Seleziona **Fatto**. La scheda **Previsioni personali** viene visualizzata durante la creazione della previsione. Il completamento del processo potrebbe richiedere diverse ore a seconda della quantità di dati utilizzati nella previsione.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visualizzare i risultati della previsione

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Previsioni personali** seleziona la previsione che vuoi visualizzare.

Ci sono cinque sezioni principali di dati all'interno della pagina dei risultati.

- **Prestazioni modello**: i voti A, B o C indicano le prestazioni della previsione e possono aiutarti a prendere la decisione di usare i risultati archiviati nell'entità di output.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Immagine del risultato delle prestazioni del modello con voto A.":::

  I voti sono determinati in base alle seguenti regole:
  - **A** quando la metrica "Successo @ K" è superiore almeno del 10% rispetto alla baseline.
  - **B** quando la metrica "Successo @ K" è superiore dello 0% - 10% rispetto alla baseline.
  - **C** quando la metrica "Successo @ K" è inferiore alla baseline.
  - **Baseline**: il modello prende i prodotti più consigliati in base al conteggio degli acquisti di tutti i clienti + le regole apprese identificate dal modello = una serie di raccomandazioni per i clienti. Le previsioni vengono quindi confrontate con i prodotti di punta, come calcolato dal numero di clienti che hanno acquistato il prodotto. Se un cliente ha almeno un prodotto tra i prodotti consigliati che è stato visto anche nei prodotti più acquistati, viene considerato parte della baseline. Ad esempio, se ci fossero 10 di questi clienti che hanno acquistato un prodotto consigliato su 100 clienti totali, la baseline sarebbe il 10%.
  - **Successo @ K**: le raccomandazioni vengono create per tutti i clienti e confrontate con il set di convalida del periodo delle transazioni. Ad esempio, in un periodo di 12 mesi, il mese 12 potrebbe essere accantonato come set di dati di convalida. Se il modello prevede almeno una cosa che acquisteresti nel mese 12 in base a ciò che ha appreso dagli 11 mesi precedenti, il cliente aumenterebbe la metrica "Successo @ K".

- **Prodotti più consigliati (con conteggio):** I primi cinque prodotti previsti per i tuoi clienti.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Grafico che mostra i primi 5 prodotti più consigliati.":::

- **Fattori raccomandazione chiave:** Il modello utilizza la cronologia delle transazioni dei clienti per fornire consigli sui prodotti. Apprende i modelli basati sugli acquisti passati e trova somiglianze tra clienti e prodotti. Queste somiglianze vengono quindi utilizzate per generare le raccomandazioni sui prodotti.
  Di seguito sono riportati i fattori che potrebbero influenzare una raccomandazione di prodotto generata dal modello.
  - **Transazioni passate** : un prodotto consigliato si basava su modelli di acquisto passati. Ad esempio, il modello può consigliare un *Surface Arc Mouse* se qualcuno ha recentemente acquistato un *Surface Book 3* e una *Penna per Surface*. Il modello ha appreso che storicamente molti clienti avevano acquistato un *Surface Arc Mouse* dopo aver acquistato un *Surface Book 3* e una *Penna per Surface*.
  - **Somiglianza cliente**: Un prodotto consigliato è stato storicamente acquistato da altri clienti che mostrano modelli di acquisto simili. Ad esempio, a John sono state consigliate le *Cuffie Surface 2* perché Jennifer e Brad hanno recentemente acquistato le *Cuffie Surface 2*. Il modello crede che John sia simile a Jennifer e Brad perché storicamente hanno avuto modelli di acquisto simili.
  - **Somiglianza prodotto**: Un prodotto consigliato è simile ad altri prodotti che il cliente aveva acquistato in precedenza. Il modello considera due prodotti simili se acquistati insieme o da clienti simili. Ad esempio, qualcuno riceve una raccomandazione per una *Unità di archiviazione USB* perché in precedenza avevano acquistato un *Adattatore da USB-C a USB* e il modello crede che *Unità di archiviazione USB* sia simile ad *Adattatore da USB-C a USB* in base ai modelli storici di acquisto.

  Ogni raccomandazione sul prodotto è influenzata da uno o più di questi fattori. La percentuale di raccomandazioni in cui ogni fattore di influenza ha svolto un ruolo viene visualizzata in un grafico. Nell'esempio seguente, il 100% delle raccomandazioni è stato influenzato da transazioni passate, il 60% dalla somiglianza del cliente e il 22% dalla somiglianza del prodotto. Passa il mouse sulle barre nel grafico per vedere la percentuale esatta a cui hanno contribuito i fattori di influenza.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Fattori di raccomandazione chiave appresi dal modello per generare raccomandazioni sui prodotti.":::

- **Statistiche dei dati**: una panoramica del numero di transazioni, clienti e prodotti presi in considerazione dal modello. Si basa sui dati di input utilizzati per apprendere i modelli e generare raccomandazioni sui prodotti.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Statistiche dei dati sui dati di input utilizzati dal modello per apprendere i modelli.":::
  
  Il modello usa tutti i dati disponibili per apprendere i modelli. Pertanto, se usi il filtro del prodotto nella configurazione del modello, questa sezione mostra il numero totale di prodotti analizzati dal modello per apprendere i modelli, che potrebbero differire dal numero di prodotti che corrispondono ai criteri di filtro definiti. Il filtro si applica all'output generato dal modello.

- **Elementi consigliati per il prodotto di esempio**: un esempio di raccomandazioni che il modello ritiene probabile possano essere acquistati dal cliente. Se viene aggiunto un catalogo di prodotti, gli ID dei prodotti vengono sostituiti con i nomi dei prodotti.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Elenco che mostra suggerimenti ad alta affidabilità per un gruppo selezionato di singoli clienti.":::

> [!NOTE]
> Nell'entità di output per questo modello, *Punteggio* mostra la misura quantitativa della raccomandazione. Il modello consiglia prodotti con un punteggio più alto rispetto a prodotti con un punteggio inferiore. Per visualizzare il punteggio, vai a **Dati** > **Entitià** e visualizza la scheda dei dati per l'entità di output definita per questo modello.

[!INCLUDE [footer-include](includes/footer-banner.md)]
