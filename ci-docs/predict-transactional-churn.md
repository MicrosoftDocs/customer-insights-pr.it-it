---
title: Previsione dell'abbandono delle transazioni (video)
description: Determina se esiste il rischio che un cliente non acquisti più i tuoi prodotti o servizi.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610517"
---
# <a name="predict-transaction-churn"></a>Prevedere l'abbandono delle transazioni

La previsione di abbandono transazionale ti consente di prevedere se un cliente non acquisterà più i tuoi prodotti o servizi in un determinato intervallo di tempo.

È necessaria la conoscenza dell'azienda per capire cosa significa l'abbandono per la tua azienda. Supportiamo definizioni di abbandono basate sul tempo, ovvero un cliente è considerato come perso dopo un periodo sena acquisti.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Per gli ambienti basati su conti commerciali, possiamo prevedere l'abbandono transazionale per un conto e anche una combinazione di conto e un altro livello di informazioni come la categoria del prodotto. Ad esempio, aggiungere una dimensione può aiutare a determinare quanto è probabile che l'account "Contoso" smetta di comprare la categoria di prodotti "cancelleria per ufficio". Inoltre, per gli account aziendali, possiamo anche usare l'AI per generare un elenco di potenziali motivi per cui un account è probabile che si trasformi per una categoria di informazioni di livello secondario.

> [!TIP]
> Prova la previsione di abbandono della transazione utilizzando i dati di esempio: [Guida di esempio sulla previsione dell'abbandono delle transazioni](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Prerequisiti

- [Autorizzazioni di collaboratore](permissions.md) come minimo.
- Almeno 10 profili cliente, preferibilmente più di 1.000 clienti univoci.
- Identificatore cliente, un identificatore univoco per abbinare le transazioni ai clienti.
- Dati delle transazioni per almeno il doppio della finestra temporale selezionata, ad esempio da due a tre anni di cronologia delle transazioni. Idealmente, almeno due transazioni per cliente. La cronologia delle transazioni deve includere:
  - **ID transazione**: un identificatore univoco di un acquisto o di una transazione.
  - **Data transazione**: la data dell'acquisto o della transazione.
  - **Valore della transazione**: l'importo in valuta o in valore numerico della transazione.
  - **ID prodotto univoco:** l'ID del prodotto o del servizio acquistato se i tuoi dati sono a livello di voce singola.
  - **Specifica se la transazione è stata un reso**: un campo vero/falso che identifica se la transazione era un reso o meno. Se il **Valore della transazione** è negativo, se ne può dedurre che si trattava di un reso.
- Dati attività cliente
  - Identificatore cliente, un identificatore univoco per associare le attività ai clienti.
  - **Chiave primaria**: identificatore univoco per un'attività. Ad esempio, una visita al sito Web o un record di utilizzo che mostra che il cliente ha provato un campione del prodotto.
  - **Timestamp**: data e ora dell'evento identificato dalla chiave primaria.
  - **Evento**: nome dell'evento che si desidera utilizzare. Ad esempio, un campo denominato "UserAction" in un negozio di alimentari potrebbe essere un coupon utilizzato dal cliente.
  - **Dettagli:** informazioni dettagliate sull'evento. Ad esempio, un campo denominato "CouponValue" in un negozio di alimentari potrebbe essere il valore monetario del coupon.
- Meno del 20% dei valori mancanti nel campo dati dell'entità fornita

Per gli account aziendali (B-to-B), aggiungi i dati dei clienti allineati con attributi più statici per garantire che il modello funzioni al meglio:
- **CustomerID**: un identificatore univoco per un cliente.
- **Data di creazione**: la data in cui il cliente è stato aggiunto inizialmente.
- **Stato o provincia**: l'ubicazione dello stato o della provincia di un cliente.
- **Paese**: il Paese di un cliente.
- **Settore**: il tipo di settore di un cliente. Per esempio, un campo denominato "Settore" in un torrefattore di caffè potrebbe indicare se il cliente era un dettagliante.
- **Classificazione**: la categorizzazione di un cliente per il tuo business. Per esempio, un campo chiamato "ValueSegment" in una torrefazione di caffè potrebbe essere il livello di cliente basato sulla dimensione del cliente.

> [!NOTE]
> Per un'azienda con un'elevata frequenza di acquisto da parte dei clienti (ogni poche settimane) si consiglia di selezionare una finestra di previsione e una definizione di abbandono più brevi. Per una bassa frequenza di acquisto (ogni pochi mesi o una volta all'anno), scegli una finestra di previsione e una definizione di abbandono più lunghe.

## <a name="create-a-transaction-churn-prediction"></a>Creare una previsione di abbandono delle transazioni

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Crea** seleziona **Usa modello** nel riquadro **Modello di abbandono dei clienti**.

1. Seleziona **Transazione** per il tipo di abbandono, quindi seleziona **Operazioni preliminari**.

1. Specifica **Assegna un nome al modello** e **Nome entità di output** per distinguerli da altri modelli o entità.

1. Selezionare **Avanti**.

### <a name="define-customer-churn"></a>Definisci abbandono cliente

Seleziona **Salva bozza** in qualsiasi momento per salvare la previsione come bozza. La previsione della bozza sarà visibile nella scheda **Previsioni personali**.

1. Imposta la **finestra Previsione**. Ad esempio, prevedi il rischio di abbandono dei clienti nei prossimi 90 giorni per allinearti agli sforzi di fidelizzazione del marketing. La previsione del rischio di abbandono per un periodo di tempo più o meno lungo può rendere più difficile prendere in considerazione i fattori nel profilo di rischio di abbandono, ma dipende dalle esigenze aziendali specifiche.

1. Immetti il numero di giorni per definire l'abbandono nel campo **Definizione abbandono**. Ad esempio, se un cliente non ha effettuato acquisti negli ultimi 30 giorni, potrebbe essere considerato come perso per la tua attività.

1. Selezionare **Avanti**.

### <a name="add-purchase-history"></a>Aggiungi cronologia acquisti

1. Seleziona **Aggiungi dati** per **Cronologia transazioni cliente**.

1. Seleziona il tipo di attività semantica, **SalesOrder** o **SalesOrderLine**, che contiene le informazioni sulla cronologia delle transazioni. Se l'attività non è stata impostata, seleziona **qui** e creala.

1. In **Attività**, se gli attributi dell'attività erano stati mappati a livello semantico al momento della creazione dell'attività, scegli gli attributi o l'entità specifici su cui dovranno essere basati i calcoli. Se il mapping semantico non era stato eseguito, seleziona **Modifica** e mappa i tuoi dati.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Riquadro laterale che mostra la scelta di impegni specifici nel tipo semantico.":::

1. Seleziona **Avanti** e rivedi gli attributi richiesti per questo modello.

1. Seleziona **Salva**.

1. Aggiungi ulteriori attività oppure seleziona **Avanti**.

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Aggiungere altri dati (opzionale)

1. Seleziona **Aggiungi dati** per **Attività dei clienti**.

1. Seleziona il tipo di attività semantica che contiene i dati che vuoi usare. Se l'attività non è stata impostata, seleziona **qui** e creala.

1. In **Attività**, se gli attributi dell'attività erano stati mappati a livello semantico al momento della creazione dell'attività, scegli gli attributi o l'entità specifici su cui dovranno essere basati i calcoli. Se il mapping semantico non era stato eseguito, seleziona **Modifica** e mappa i tuoi dati.

1. Seleziona **Avanti** e rivedi gli attributi richiesti per questo modello.

1. Seleziona **Salva**.

1. Selezionare **Avanti**.

# <a name="business-accounts-b-to-b"></a>[Account aziendali (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Seleziona il livello di predizione

La maggior parte delle previsioni sono create a livello del cliente. In alcune situazioni, questo potrebbe non essere abbastanza granulare per soddisfare le vostre esigenze aziendali. Usa questa caratteristica per prevedere l'abbandono per un ramo di un cliente, ad esempio, piuttosto che per il cliente nel suo complesso.

1. Seleziona **Seleziona l'entità per un livello secondario**. Se l'opzione non è disponibile, assicurati di aver completato la sezione precedente.

1. Espandi le entità da cui vuoi scegliere il livello secondario, o usa la casella del filtro di ricerca per filtrare le opzioni selezionate.

1. Scegli l'attributo da usare come livello secondario, quindi seleziona **Aggiungi**.

1. Selezionare **Avanti**.

> [!NOTE]
> Le entità disponibili in questa sezione sono mostrate perché hanno una relazione con l'entità che hai scelto nella sezione precedente. Se non vedi l'entità che vuoi aggiungere, assicurati che abbia una relazione valida presente in **Relationships**. Solo le relazioni one-to-one e many-to-one sono valide per questa configurazione.

### <a name="add-additional-data-optional"></a>Aggiungere altri dati (opzionale)

1. Seleziona **Aggiungi dati** per **Attività dei clienti**.

1. Seleziona il tipo di attività semantica che contiene i dati che vuoi usare. Se l'attività non è stata impostata, seleziona **qui** e creala.

1. In **Attività**, se gli attributi dell'attività erano stati mappati a livello semantico al momento della creazione dell'attività, scegli gli attributi o l'entità specifici su cui dovranno essere basati i calcoli. Se il mapping semantico non era stato eseguito, seleziona **Modifica** e mappa i tuoi dati.

1. Seleziona **Avanti** e rivedi gli attributi richiesti per questo modello.

1. Seleziona **Salva**.

1. Selezionare **Avanti**.

1. Opzionalmente, seleziona **Aggiungi dati** per i **dati dei clienti**.

1. Mappate gli attributi semantici ai campi dei vostri dati cliente come identificati. I dati nei campi utilizzati non dovrebbero cambiare spesso per garantire le migliori prestazioni del modello. Per esempio, selezionando un campo per "Classificazione" che cambiava ogni mese, si avrebbe solo l'ultimo valore usato nella predizione, anche se storicamente lo stesso valore potrebbe non essere applicato al cliente quando si costruiscono i modelli di predizione.

1. Selezionare **Avanti**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Fornisci un elenco facoltativo di account benchmark

Aggiungi una lista dei tuoi clienti aziendali e degli account che vuoi usare come punti di riferimento. I [dettagli per questi account di riferimento](#view-prediction-results) includono il loro punteggio di abbandono e le caratteristiche più influenti che hanno influenzato la loro previsione di abbandono.

1. Seleziona **+ Aggiungi clienti**.

1. Scegliere i clienti che fungono da punto di riferimento.

1. Selezionare **Avanti**.

---

### <a name="set-update-schedule"></a>Impostare la pianificazione di aggiornamento

1. Per il passaggio **Aggiornamenti dei dati** scegli una frequenza per ripetere il training del modello. Questa impostazione è importante per aggiornare l'accuratezza delle previsioni quando nuovi dati vengono inseriti in Customer Insights. La maggior parte delle aziende può ripetere il training una volta al mese e ottenere una buona precisione per le loro previsioni.

1. Selezionare **Avanti**.

### <a name="review-and-run-the-model-configuration"></a>Rivedere ed eseguire la configurazione del modello

Il passaggio **Rivedi ed esegui** mostra un riepilogo della configurazione e offre la possibilità di apportare modifiche prima di creare la previsione.

1. Seleziona **Modifica** per una qualsiasi delle fasi per rivedere e apportare modifiche.

1. Se tutti i valori sono configurati correttamente, selezionare **Salva ed esegui** per avviare l'esecuzione del modello. Seleziona **Fatto**. La scheda **Previsioni personali** viene visualizzata durante la creazione della previsione. Il completamento del processo potrebbe richiedere diverse ore a seconda della quantità di dati utilizzati nella previsione.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visualizzare i risultati della previsione

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Previsioni personali** seleziona la previsione che vuoi visualizzare.

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (B2C)](#tab/b2c)

Esistono tre sezioni principali di dati nella pagina dei risultati:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Account aziendali (B2B)](#tab/b2b)

Esistono tre sezioni principali di dati nella pagina dei risultati:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Una pagina di informazioni **Analisi delle caratteristiche influenti** contiene quattro sezioni di dati:

- Nel riquadro di destra, seleziona un elemento dai **Clienti principali** o dai **Clienti benchmark**. Entrambe le liste sono ordinate per valore decrescente del punteggio di abbandono, sia che il punteggio sia solo per il cliente o un punteggio combinato per i clienti e un livello secondario come la categoria del prodotto. L'elemento selezionato determina il contenuto di questa pagina.

  - **Clienti principali**: elenco di 10 clienti che sono a più alto rischio di abbandono e a più basso rischio di abbandono in base ai loro punteggi di abbandono.
  - **Clienti di riferimento**: Elenco di un massimo di 10 clienti che sono stati selezionati durante la configurazione del modello.

- **Punteggio di abbandono**: mostra il punteggio di abbandono per l'elemento selezionato nel pannello di destra.

- **Distribuzione dei rischi di abbandono**: mostra la distribuzione dei rischi di abbandono tra i clienti e il percentile in cui si trova il cliente selezionato.

- **Caratteristiche principali che aumentano e diminuiscono i rischi di abbandono**: per l'elemento selezionato nel riquadro di destra, sono elencate le cinque caratteristiche principali che hanno aumentato e diminuito i rischi di abbandono. Per ogni caratteristica influente, mostra il valore della caratteristica per quell'elemento e la sua influenza sul punteggio di abbandono. Viene anche mostrato il valore medio di ogni caratteristica nei segmenti di clienti a bassa, media e alta rotazione. Aiuta a contestualizzare meglio i valori delle caratteristiche più influenti per l'elemento selezionato e a confrontarlo con i segmenti di clienti a bassa, media e alta rotazione.

  - Basso: conti o combinazioni di conti e livello secondario con un punteggio di abbandono compreso tra 0 e 0,33.
  - Medio: conti o combinazioni di conti e livelli secondari con un punteggio di abbandono compreso tra 0,33 e 0,66.
  - Alto: conti o combinazioni di conti e livelli secondari con un punteggio di abbandono superiore a 0,66.

  Quando si prevede l'abbandono a livello di account, tutti gli account sono considerati nel derivare i valori medi delle caratteristiche per i segmenti di abbandono. Per le previsioni di abbandono a livello secondario per ogni conto, la derivazione dei segmenti di abbandono dipende dal livello secondario dell'elemento selezionato nel pannello laterale. Ad esempio, se un articolo ha un livello secondario di categoria di prodotto (forniture per ufficio), allora solo gli articoli che hanno forniture per ufficio come categoria di prodotto vengono presi in considerazione quando si ricavano i valori medi delle caratteristiche per i segmenti di abbandono. Questa logica viene applicata per assicurare un confronto equo dei valori delle caratteristiche dell'articolo con i valori medi dei segmenti a bassa, media e alta rotazione.

  In alcuni casi, il valore medio dei segmenti di abbandono basso, medio o alto è vuoto o non disponibile perché non ci sono articoli che appartengono ai segmenti di abbandono corrispondenti in base alla definizione di cui sopra.

  L'interpretazione della media nelle colonne con valori bassi, medi o alti è diversa per le caratteristiche di categoria come paese o settore. Poiché la nozione del valore di caratteristica "medio" non si applica alle caratteristiche di categoria, i valori in queste colonne sono la proporzione di clienti nei segmenti di abbandono basso, medio o alto che hanno lo stesso valore della caratteristica di categoria rispetto all'articolo selezionato nel pannello laterale.

---

 > [!NOTE]
 > Nell'entità di output per questo modello, *ChurnScore* mostra la probabilità prevista di abbandono e *IsChurn* è un'etichetta binaria basata su *ChurnScore* con soglia di 0,5. Se questa soglia predefinita non funziona per il tuo scenario, [crea un nuovo segmento](segments.md#create-a-segment) con la tua soglia preferita. Non tutti i clienti sono necessariamente clienti attivi. Alcuni di loro potrebbero non aver avuto alcun impegno per molto tempo e sono già considerati come abbandonati, in base alla tua definizione di abbandono. Prevedere il rischio di abbandono per i clienti che hanno già abbandonato non è utile perché non sono il pubblico di interesse.
>
> Per visualizzare il punteggio di abbandono, vai a **Dati** > **Entitià** e visualizza la scheda dei dati per l'entità di output definita per questo modello.

[!INCLUDE [footer-include](includes/footer-banner.md)]
