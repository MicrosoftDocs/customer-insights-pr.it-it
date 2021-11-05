---
title: Previsione del churn delle transazioni
description: Determina se esiste il rischio che un cliente non acquisti più i tuoi prodotti o servizi.
ms.date: 10/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 9fa6a044989d523e1068aff24266cfb475632736
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673050"
---
# <a name="transaction-churn-prediction-preview"></a>Previsione del churn delle transazioni (anteprima)

La previsione di abbandono transazionale ti consente di prevedere se un cliente non acquisterà più i tuoi prodotti o servizi in un determinato intervallo di tempo. Puoi creare nuove previsioni di abbandono in **Intelligenza** > **Previsioni**. Seleziona **Le mie previsioni** per visualizzare altre previsioni che hai creato. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Per gli ambienti basati su conti commerciali, possiamo prevedere il churn transazionale per un conto e anche una combinazione di conto e un altro livello di informazioni come la categoria del prodotto. Aggiungere una dimensione può aiutare a scoprire quanto è probabile che l'account "Contoso" smetta di comprare la categoria di prodotti "cancelleria per ufficio" Inoltre, per gli account aziendali, possiamo anche usare l'AI per generare un elenco di potenziali motivi per cui un account è probabile che si trasformi per una categoria di informazioni di livello secondario.

> [!TIP]
> Provate il tutorial per una previsione del churn delle transazioni utilizzando dati di esempio: [Previsione di churn delle transazioni (anteprima) guida di esempio](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Prerequisiti

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.
- Conoscenza dell'azienda per capire cosa significa abbandono per la tua azienda. Supportiamo definizioni di abbandono basate sul tempo, ovvero un cliente è considerato come perso dopo un periodo sena acquisti.
- Dati su transazioni/acquisti e la relativa cronologia:
    - Identificatori di transazione per distinguere acquisti/transazioni.
    - Identificatori di cliente per abbinare le transazioni ai clienti.
    - Date dell'evento di transazione, che definiscono le date in cui è avvenuta la transazione.
    - Lo schema dei dati semantici per acquisti/transazioni richiede le seguenti informazioni:
        - **ID transazione**: Un identificatore unico di un acquisto o di una transazione.
        - **Data della transazione**: La data dell'acquisto o della transazione.
        - **Valore della transazione**: L'importo in valuta/valore numerico della transazione/articolo.
        - (Opzionale) **ID unico del prodotto**: L'ID del prodotto o del servizio acquistato se i tuoi dati sono a livello di voce.
        - (Opzionale) **Se questa transazione era un ritorno**: Un campo vero/falso che identifica se la transazione era un ritorno o no. Se il **Valore della transazione** è negativo, useremo queste informazioni per dedurre un reso.
- (Facoltativo) Dati sugli impegni del cliente:
    - Identificatori di impegni per distinguere gli impegni dello stesso tipo.
    - Identificativi del cliente per mappare gli impegni ai clienti.
    - Informazioni sull'impegno contenenti il nome e la data dell'impegno.
    - Lo schema di dati semantici per gli impegni dei clienti include:
        - **Chiave primaria:** l'identificatore univoco per un impegno. Ad esempio, una visita al sito Web o un record di utilizzo che mostra che il cliente ha provato un campione del prodotto.
        - **Timestamp:** la data e l'ora dell'evento identificato dalla chiave primaria.
        - **Evento:** il nome dell'evento che si desidera utilizzare. Ad esempio, un campo denominato "UserAction" in un negozio di alimentari potrebbe essere un coupon utilizzato dal cliente.
        - **Dettagli:** informazioni dettagliate sull'evento. Ad esempio, un campo denominato "CouponValue" in un negozio di alimentari potrebbe essere il valore monetario del coupon.

# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.
- Conoscenza dell'azienda per capire cosa significa abbandono per la tua azienda. Supportiamo definizioni di abbandono basate sul tempo, ovvero un cliente è considerato come perso dopo un periodo sena acquisti.
- Dati su transazioni/acquisti e la relativa cronologia:
    - Identificatori di transazione per distinguere acquisti/transazioni.
    - Identificatori di cliente per abbinare le transazioni ai clienti.
    - Date dell'evento di transazione, che definiscono le date in cui è avvenuta la transazione.
    - Lo schema dei dati semantici per acquisti/transazioni richiede le seguenti informazioni:
        - **ID transazione**: Un identificatore unico di un acquisto o di una transazione.
        - **Data della transazione**: La data dell'acquisto o della transazione.
        - **Valore della transazione**: L'importo in valuta/valore numerico della transazione/articolo.
        - (Opzionale) **ID unico del prodotto**: L'ID del prodotto o del servizio acquistato se i tuoi dati sono a livello di voce.
        - (Opzionale) **Se questa transazione era un ritorno**: Un campo vero/falso che identifica se la transazione era un ritorno o no. Se il **Valore della transazione** è negativo, useremo queste informazioni per dedurre un reso.
- (Facoltativo) Dati sugli impegni del cliente:
    - Identificatori di impegni per distinguere gli impegni dello stesso tipo.
    - Identificativi del cliente per mappare gli impegni ai clienti.
    - Informazioni sull'impegno contenenti il nome e la data dell'impegno.
    - Lo schema di dati semantici per gli impegni dei clienti include:
        - **Chiave primaria:** l'identificatore univoco per un impegno. Ad esempio, una visita al sito Web o un record di utilizzo che mostra che il cliente ha provato un campione del prodotto.
        - **Timestamp:** la data e l'ora dell'evento identificato dalla chiave primaria.
        - **Evento:** il nome dell'evento che si desidera utilizzare. Ad esempio, un campo denominato "UserAction" in un negozio di alimentari potrebbe essere un coupon utilizzato dal cliente.
        - **Dettagli:** informazioni dettagliate sull'evento. Ad esempio, un campo denominato "CouponValue" in un negozio di alimentari potrebbe essere il valore monetario del coupon.
- (Opzionale) Dati sui tuoi clienti:
    - Questi dati dovrebbero allinearsi rispetto ad attributi più statici per garantire che il modello funzioni al meglio.
    - Lo schema di dati semantici per i dati dei clienti include:
        - **CustomerID:** Un identificatore unico per un cliente.
        - **Data di creazione:** La data in cui il cliente è stato aggiunto inizialmente.
        - **Stato o provincia:** L'ubicazione dello stato o della provincia di un cliente.
        - **Paese:** Il paese di un cliente.
        - **Industria:** Il tipo di industria di un cliente. Per esempio, un campo chiamato "Industria" in un torrefattore di caffè potrebbe indicare se il cliente era al dettaglio.
        - **Classificazione:** La categorizzazione di un cliente per il tuo business. Per esempio, un campo chiamato "ValueSegment" in una torrefazione di caffè potrebbe essere il livello di cliente basato sulla dimensione del cliente.

---

- Caratteristiche dei dati consigliate:
    - Dati storici sufficienti: dati di transazione per almeno il doppio della finestra temporale selezionata. Preferibilmente, due o tre anni di cronologia delle transazioni. 
    - Acquisti multipli per cliente: idealmente almeno due transazioni per cliente.
    - Numero di clienti: almeno 10 profili cliente, preferibilmente più di 1.000 clienti univoci. Il modello non riesce con meno di 10 clienti e dati storici insufficienti.
    - Completezza dei dati: meno del 20% dei valori mancanti nel campo dati dell'entità fornita.

> [!NOTE]
> Per un'azienda con un'elevata frequenza di acquisto da parte dei clienti (ogni poche settimane) si consiglia di selezionare una finestra di previsione e una definizione di abbandono più brevi. Per una bassa frequenza di acquisto (ogni pochi mesi o una volta all'anno), scegli una finestra di previsione e una definizione di abbandono più lunghe.

## <a name="create-a-transaction-churn-prediction"></a>Creare una previsione del churn delle transazioni

1. In Customer Insights, vai a **Intelligence** > **Previsioni**.

1. Seleziona il riquadro **Modello di abbandono dei cliente (anteprima)** e seleziona **Utilizza questo modello**.

1. Nel riquadro del **modello di rotazione dei clienti** , scegliete **Transazione** e selezionate **Inizia**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Schermata con l'opzione di transazione selezionata nel riquadro del modello di rotazione dei clienti.":::

### <a name="name-model"></a>Assegna nome a modello

1. Specifica un nome per il modello per distinguerlo dagli altri modelli.

1. Specifica un nome per l'entità di output utilizzando solo lettere e numeri, senza spazi. Questo è il nome che verrà utilizzato dall'entità modello. 

1. Seleziona **Avanti**.

### <a name="define-customer-churn"></a>Definisci abbandono cliente

1. Imposta un periodo in giorni per la previsione dell'abbandono nel campo **Identifica i clienti che potrebbero abbandonare nei prossimi/nelle prossime**. Ad esempio, prevedi il rischio di abbandono dei clienti nei prossimi 90 giorni per allinearti agli sforzi di fidelizzazione del marketing. La previsione del rischio di abbandono per un periodo di tempo più o meno lungo può rendere più difficile prendere in considerazione i fattori nel profilo di rischio di abbandono, ma dipende dalle esigenze aziendali specifiche.
   >[!TIP]
   > Puoi selezionare **Salva e chiudi** in qualsiasi momento per salvare la previsione come bozza. La previsione della bozza è disponibile nella scheda **Le mie previsioni** per continuare.

1. Immetti il numero di giorni per definire l'abbandono nel campo **Un cliente ha abbandonato se non ha effettuato alcun acquisto per**. Ad esempio, se un cliente non ha effettuato acquisti negli ultimi 30 giorni, potrebbe essere considerato come perso per la tua attività. 

1. Selezionare **Avanti** per continuare.

### <a name="add-required-data"></a>Aggiungi dati obbligatori

1. Seleziona **Aggiungi dati** e scegli il tipo di impegno nel riquadro laterale che contiene la transazione richiesta o le informazioni sulla cronologia degli acquisti.

1. In **Scegli impegni** seleziona gli impegni specifici dall'impegno selezionato su cui desideri che il calcolo si concentri.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Riquadro laterale che mostra la scelta di impegni specifici nel tipo semantico.":::

1. Se non hai ancora mappato l'attività su un tipo semantico, seleziona **Modifica** per farlo. Si apre l'esperienza guidata per mappare gli impegni semantici. Mappa i tuoi dati ai campi corrispondenti nel tipo di impegno selezionato.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Pagina di impostazione del tipo di impegno.":::

1. Dopo aver mappato l'impegno sul tipo semantico corrispondente, seleziona **Avanti** per procedere

1. Mappa gli attributi semantici ai campi necessari per eseguire il modello. Se i campi sottostanti non sono popolati, configurare la relazione tra l'entità storia degli acquisti e l'entità *Cliente* .

1. Selezionare **Avanti**.

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Aggiungere altri dati (opzionale)

Configura la relazione dall'entità degli impegni cliente all'entità *Cliente*.

1. Seleziona il campo che identifica il cliente nella tabella degli impegni del cliente. Può essere correlato direttamente all'ID cliente primario dell'entità *Cliente*.

1. Selezionate l'entità che è la vostra entità *Cliente* principale.

1. Immetti un nome che descrive la relazione.

#### <a name="customer-activities"></a>Impegni cliente

1. Facoltativamente, seleziona **Aggiungi dati** in **Impegni cliente**.

1. Seleziona il tipo di attività semantica che contiene i dati che vorresti utilizzare, poi seleziona una o più attività nella sezione **Attività** .

1. Seleziona un tipo di impegno corrispondente al tipo di impegno del cliente che stai configurando. Seleziona **Creare nuovo** e scegli un tipo di impegno disponibile o creane uno.

1. Selezionate **Avanti** e poi **Salva**.

1. Se hai altri impegni dei clienti che desideri includere, ripeti i passaggi precedenti.

# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

### <a name="select-prediction-level"></a>Seleziona il livello di predizione

La maggior parte delle previsioni sono create a livello del cliente. In alcune situazioni, questo potrebbe non essere abbastanza granulare per soddisfare le vostre esigenze aziendali. È possibile utilizzare questa funzione per prevedere il churn per un ramo di un cliente, ad esempio, piuttosto che per il cliente nel suo complesso.

1. Per creare una previsione ad un livello più granulare del cliente, seleziona **Seleziona entità per un livello secondario**. Se l'opzione non è disponibile, assicurati di aver completato la sezione precedente.

1. Espandi le entità da cui vuoi scegliere il livello secondario, o usa la casella del filtro di ricerca per filtrare le opzioni selezionate.

1. Scegli l'attributo da usare come livello secondario, quindi seleziona **Aggiungi**.

1. Selezionare **Avanti**.

> [!NOTE]
> Le entità disponibili in questa sezione sono mostrate perché hanno una relazione con l'entità che hai scelto nella sezione precedente. Se non vedi l'entità che vuoi aggiungere, assicurati che abbia una relazione valida presente in **Relationships**. Solo le relazioni one-to-one e many-to-one sono valide per questa configurazione.

### <a name="add-additional-data-optional"></a>Aggiungere altri dati (opzionale)

Configura la relazione dall'entità degli impegni cliente all'entità *Cliente*.

1. Seleziona il campo che identifica il cliente nella tabella degli impegni del cliente. Può essere correlato direttamente all'ID cliente primario dell'entità *Cliente*.

1. Selezionate l'entità che è la vostra entità *Cliente* principale.

1. Immetti un nome che descrive la relazione.

#### <a name="customer-activities"></a>Impegni cliente

1. Facoltativamente, seleziona **Aggiungi dati** in **Impegni cliente**.

1. Seleziona il tipo di attività semantica che contiene i dati che vorresti utilizzare, poi seleziona una o più attività nella sezione **Attività** .

1. Seleziona un tipo di impegno corrispondente al tipo di impegno del cliente che stai configurando. Seleziona **Creare nuovo** e scegli un tipo di impegno disponibile o creane uno.

1. Selezionate **Avanti** e poi **Salva**.

1. Se hai altri impegni dei clienti che desideri includere, ripeti i passaggi precedenti.

#### <a name="customers-data"></a>Dati dei clienti

1. Opzionalmente, seleziona **Aggiungi dati** per i **dati dei clienti**.

1. Mappate gli attributi semantici ai campi dei vostri dati cliente come identificati. I dati nei campi utilizzati non dovrebbero cambiare spesso per garantire le migliori prestazioni del modello. Per esempio, selezionando un campo per "Classificazione" che cambiava ogni mese, si avrebbe solo l'ultimo valore usato nella predizione, anche se storicamente lo stesso valore potrebbe non essere applicato al cliente quando si costruiscono i modelli di predizione.

1. Selezionare **Avanti**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Fornisci un elenco facoltativo di account benchmark

Aggiungi una lista dei tuoi clienti aziendali e degli account che vuoi usare come punti di riferimento. Otterrai i [dettagli per questi account di riferimento](#review-a-prediction-status-and-results) , compreso il loro punteggio di churn e le caratteristiche più influenti che hanno influenzato la loro previsione di churn.

1. Seleziona **+ Aggiungi clienti**.

1. Scegliere i clienti che fungono da punto di riferimento.

1. Selezionare **Avanti** per continuare.

---

### <a name="set-schedule-and-review-configuration"></a>Impostazione della pianificazione e revisione della configurazione

1. Imposta una frequenza per ripetere il training del modello. Questa impostazione è importante per aggiornare la precisione delle previsioni a mano a mano che vengono inseriti nuovi dati. La maggior parte delle aziende può ripetere il training una volta al mese e ottenere una buona precisione per le loro previsioni.

1. Seleziona **Avanti**.

1. Esamina la configurazione della previsione. Puoi tornare ai passaggi precedenti selezionando **Modifica** sotto il valore mostrato. Oppure puoi selezionare un passaggio di configurazione dall'indicatore di avanzamento.

1. Se tutti i valori sono configurati correttamente, seleziona **Salva ed esegui** per iniziare il processo di previsione. Nella scheda **Le mie previsioni**, puoi vedere lo stato delle tue previsioni. Il completamento del processo potrebbe richiedere diverse ore a seconda della quantità di dati utilizzati nella previsione.

## <a name="review-a-prediction-status-and-results"></a>Rivedere lo stato e i risultati di una previsione

1. Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.

1. Seleziona la previsione da rivedere.
   - **Nome previsione:** il nome del previsione fornito durante la creazione.
   - **Tipo di previsione:** il tipo di modello utilizzato per la previsione
   - **Entità di output:** nome dell'entità per memorizzare l'output della previsione. Puoi trovare un'entità con questo nome su **Dati** > **Entità**.
     Nell'entità di output, *ChurnScore* è la probabilità prevista di abbandono e *IsChurn* è un'etichetta binaria basata su *ChurnScore* con soglia di 0,5. La soglia predefinita potrebbe non funzionare per il tuo scenario. [Crea un nuovo segmento](segments.md#create-a-new-segment) con la tua soglia preferita.
     Non tutti i clienti sono necessariamente clienti attivi. Alcuni di loro potrebbero non aver avuto alcun impegno per molto tempo e sono già considerati come abbandonati, in base alla tua definizione di abbandono. Prevedere il rischio di abbandono per i clienti che hanno già abbandonato non è utile perché non sono il pubblico di interesse.
   - **Campo previsto**: Questo campo è popolato solo per alcuni tipi di previsioni, e non è usato nella previsione di churn.
   - **Stato:** lo stato dell'esecuzione della previsione.
        - **In coda**: La previsione è in attesa di altri processi da eseguire.
        - **Rinfrescante**: La predizione è attualmente in esecuzione per produrre risultati che confluiranno nell'entità di uscita.
        - **Errore:** l'esecuzione della previsione non è riuscita. [Esamina i log](manage-predictions.md#troubleshoot-a-failed-prediction) per maggiori informazioni.
        - **Completata:** la previsione è riuscita. Seleziona **Visualizza** sotto i puntini di sospensione verticali per rivedere la previsione
   - **Data di modifica**: la data in cui è stata modificata la configurazione per la previsione.
   - **Ultimo aggiornamento:** la data in cui sono stati aggiornati i risultati della previsione nell'entità di output.

1. Seleziona i puntini di sospensione verticali accanto alla previsione per cui desideri esaminare i risultati e seleziona **Visualizza**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Controllo Visualizza per visualizzare i risultati di un previsione.":::

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

1. Esistono tre sezioni principali di dati nella pagina dei risultati:
   - **Prestazioni del modello di addestramento**: A, B o C sono punteggi possibili. Questo punteggio indica la performance della predizione e può aiutarvi a prendere la decisione di utilizzare i risultati memorizzati nell'entità di output. I punteggi sono determinati in base alle seguenti regole: 
        - **A** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è superiore al tasso di riferimento di almeno il 10%.
            
        - **B** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è fino al 10% superiore al tasso di riferimento.
            
        - **C** quando il modello ha previsto con precisione meno del 50% delle previsioni totali o quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è inferiore al tasso di riferimento.
               
        - **Baseline** prende l'input della finestra temporale di previsione per il modello (per esempio, un anno), e il modello crea diverse frazioni di tempo dividendolo per 2 fino a raggiungere un mese o meno. Utilizza queste frazioni per creare una regola aziendale per i clienti che non hanno effettuato acquisti durante tale periodo di tempo. Questi clienti vengono considerati come persi. La regola di business basata sul tempo con la più alta capacità di prevedere chi può abbandonare viene scelta come modello di riferimento.
            
    - **Probabilità di abbandono (numero di clienti)**: Gruppi di clienti basati sul loro rischio previsto di abbandono. Questi dati possono aiutarti in un secondo momento se desideri creare un segmento di clienti con elevato rischio di abbandono. Tali segmenti aiutano a capire dove dovrebbe posizionare il limite per l'appartenenza al segmento.
       
    - I **fattori più influenti**: Ci sono molti fattori che vengono presi in considerazione quando si crea la tua previsione. Ciascuno dei fattori ha la sua importanza calcolata per le previsioni aggregate create da un modello. Potete usare questi fattori per aiutare a convalidare i vostri risultati di previsione, o potete usare queste informazioni in seguito per [creare segmenti](segments.md) che potrebbero aiutare a influenzare il rischio di abbandono dei clienti.


# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

1. Esistono tre sezioni principali di dati nella pagina dei risultati:
   - **Prestazioni del modello di addestramento**: A, B o C sono punteggi possibili. Questo punteggio indica la performance della predizione e può aiutarvi a prendere la decisione di utilizzare i risultati memorizzati nell'entità di output. I punteggi sono determinati in base alle seguenti regole: 
        - **A** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è superiore al tasso di riferimento di almeno il 10%.
            
        - **B** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è fino al 10% superiore al tasso di riferimento.
            
        - **C** quando il modello ha previsto con precisione meno del 50% delle previsioni totali o quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è inferiore al tasso di riferimento.
               
        - **Baseline** prende l'input della finestra temporale di previsione per il modello (per esempio, un anno), e il modello crea diverse frazioni di tempo dividendolo per 2 fino a raggiungere un mese o meno. Utilizza queste frazioni per creare una regola aziendale per i clienti che non hanno effettuato acquisti durante tale periodo di tempo. Questi clienti vengono considerati come persi. La regola di business basata sul tempo con la più alta capacità di prevedere chi può abbandonare viene scelta come modello di riferimento.
            
    - **Probabilità di abbandono (numero di clienti)**: Gruppi di clienti basati sul loro rischio previsto di abbandono. Questi dati possono aiutarti in un secondo momento se desideri creare un segmento di clienti con elevato rischio di abbandono. Tali segmenti aiutano a capire dove dovrebbe posizionare il limite per l'appartenenza al segmento.
       
    - I **fattori più influenti**: Ci sono molti fattori che vengono presi in considerazione quando si crea la tua previsione. Ciascuno dei fattori ha la sua importanza calcolata per le previsioni aggregate create da un modello. Potete usare questi fattori per aiutare a convalidare i vostri risultati di previsione, o potete usare queste informazioni in seguito per [creare segmenti](segments.md) che potrebbero aiutare a influenzare il rischio di abbandono dei clienti.


1. Per gli account aziendali, troverai una pagina di informazioni sull' **analisi delle caratteristiche influenti** . Contiene quattro sezioni di dati:

    - L'elemento selezionato nel pannello di destra determina il contenuto di questa pagina. Seleziona un elemento dai **clienti Top** o dai **clienti Benchmark**. Entrambe le liste sono ordinate per valore decrescente del punteggio di churn, sia che il punteggio sia solo per il cliente o un punteggio combinato per i clienti e un livello secondario come la categoria del prodotto.
        
        - I **migliori clienti**: Elenco di 10 clienti che sono a più alto rischio di abbandono e a più basso rischio di abbandono in base ai loro punteggi di abbandono. 
        - **Clienti di riferimento**: Elenco di un massimo di 10 clienti che sono stati selezionati durante la configurazione del modello.
 
    - **Punteggio di churn:** Mostra il punteggio di churn per l'elemento selezionato nel pannello di destra.
    
    - **Distribuzione del rischio di churn:** Mostra la distribuzione del rischio di churn tra i clienti e il percentile in cui si trova il cliente selezionato. 
    
    - **Caratteristiche principali che aumentano e diminuiscono il rischio di churn:** Per l'elemento selezionato nel riquadro di destra, sono elencate le cinque caratteristiche principali che hanno aumentato e diminuito il rischio di churn. Per ogni caratteristica influente, trovate il valore della caratteristica per quell'elemento e la sua influenza sul punteggio di churn. Viene anche mostrato il valore medio di ogni caratteristica nei segmenti di clienti a bassa, media e alta rotazione. Aiuta a contestualizzare meglio i valori delle caratteristiche più influenti per l'elemento selezionato e a confrontarlo con i segmenti di clienti a bassa, media e alta rotazione.

       - Basso: conti o combinazioni di conti e livello secondario con un punteggio di churn tra 0 e 0,33
       - Medio: conti o combinazioni di conti e livelli secondari con un punteggio di churn tra 0,33 e 0,66
       - Alto: conti o combinazioni di conti e livelli secondari con un punteggio di churn superiore a 0,66
    
       Quando si prevede il churn a livello di account, tutti gli account sono considerati nel derivare i valori medi delle caratteristiche per i segmenti di churn. Per le previsioni di abbandono a livello secondario per ogni conto, la derivazione dei segmenti di abbandono dipende dal livello secondario dell'elemento selezionato nel pannello laterale. Per esempio, se un articolo ha un livello secondario di categoria di prodotto = forniture per ufficio, allora solo gli articoli che hanno forniture per ufficio come categoria di prodotto sono considerati quando si ricavano i valori medi delle caratteristiche per i segmenti di churn. Questa logica viene applicata per assicurare un confronto equo dei valori delle caratteristiche dell'articolo con i valori medi dei segmenti a bassa, media e alta rotazione.

       In alcuni casi, il valore medio dei segmenti di churn basso, medio o alto è vuoto o non disponibile perché non ci sono articoli che appartengono ai segmenti di churn corrispondenti in base alla definizione di cui sopra.
       
       > [!NOTE]
       > L'interpretazione della media nelle colonne con valori bassi, medi o alti è diversa per le caratteristiche di categoria come paese o settore. Poiché la nozione del valore di caratteristica "medio" non si applica alle caratteristiche di categoria, i valori in queste colonne sono la proporzione di clienti nei segmenti di abbandono basso, medio o alto che hanno lo stesso valore della caratteristica di categoria rispetto all'articolo selezionato nel pannello laterale.

---

## <a name="manage-predictions"></a>Gestisci previsioni

È possibile ottimizzare, risolvere i problemi, aggiornare o eliminare le previsioni. Esamina un report sull'usabilità dei dati di input per scoprire come rendere un previsione più veloce e affidabile. Per maggiori informazioni, vai a [Gestire le previsioni](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
