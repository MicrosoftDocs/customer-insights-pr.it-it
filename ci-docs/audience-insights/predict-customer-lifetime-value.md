---
title: Previsione della durata del cliente (CLV)
description: Prevedi i futuri ricavi potenziali dai clienti attivi.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 740d6a5a749e156414b0e80193334051b7f2632fe4d1f4291d74b99250f35bc2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035374"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Previsione del valore di durata del cliente (CLV) (anteprima)

Prevedi il valore potenziale (ricavi) che i singoli clienti attivi porteranno nella tua attività in un periodo di tempo futuro definito. Questa funzionalità può aiutarti a raggiungere vari obiettivi: 
- Identificare i clienti di alto valore ed elaborare queste informazioni
- Creare segmenti di clienti strategici in base al loro valore potenziale per eseguire campagne personalizzate con vendite, marketing e supporto mirati
- Guidare lo sviluppo dei prodotti concentrandoti sulle funzionalità che aumentano il valore per il cliente
- Ottimizzare la strategia di vendita o di marketing e allocare il budget in modo più accurato per la sensibilizzazione dei clienti
- Riconoscere e premiare i clienti di alto valore attraverso programmi di fidelizzazione o premi 

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, rifletti su cosa significa il CLV per la tua azienda. Attualmente, supportiamo la previsione del CLV basato su transazioni. Il valore previsto di un cliente si basa sulla cronologia delle transazioni commerciali. Per creare la previsione, è necessario avere almeno autorizzazioni di [collaboratore](permissions.md).

Poiché la configurazione e l'esecuzione di un modello CLV non richiede molto tempo, prendi in considerazione la creazione di diversi modelli con diverse preferenze di input e confronta i risultati dei modelli per vedere quale scenario di modello si adatta meglio alle tue esigenze aziendali.

###  <a name="data-requirements"></a>Requisiti dei dati

I seguenti dati sono obbligatori e, se contrassegnati come facoltativi, consigliati per aumentare le prestazioni del modello. Più dati può elaborare il modello, più accurato sarà il previsione. Pertanto, ti invitiamo a inserire più dati sugli impegni dei clienti, se disponibili.

- Identificatore cliente: identificatore univoco per abbinare le transazioni a un singolo cliente

- Cronologia delle transazioni: registro delle transazioni storiche con il seguente schema dei dati semantici
    - **ID transazione**: un identificatore univoco per ogni transazione.
    - **Data della transazione**: data, preferibilmente un timestamp di ciascuna transazione
    - **Importo della transazione**: valore monetario (ad esempio, ricavi o margine di profitto) di ciascuna transazione
    - **Etichetta assegnata ai resi** (opzionale): valore booleano che indica se la transazione è un reso 
    - **ID prodotto** (opzionale): ID prodotto del prodotto coinvolto nella transazione

- Dati aggiuntivi (facoltativi), ad esempio
    - Attività Web: cronologia delle visite al sito Web, cronologia delle e-mail
    - Attività di fidelizzazione: accumulo di punti fedeltà e cronologia dei riscatti
    - Registro servizio clienti, cronologia delle chiamate di servizio, dei reclami o dei resi
- Dati sugli impegni del cliente (facoltativo):
    - Identificatori di impegni per distinguere gli impegni dello stesso tipo.
    - Identificatori cliente per mappare gli impegni ai clienti.
    - Informazioni sull'impegno contenenti il nome e la data dell'impegno.
    - Lo schema dei dati semantici per gli impegni include: 
        - **Chiave primaria**: l'identificatore univoco per un impegno
        - **Timestamp**: la data e l'ora dell'evento identificato dalla chiave primaria
        - **Evento (nome impegno)** il nome dell'evento che desideri utilizzare
        - **Dettagli (importo o valore)**: dettagli sull'impegno del cliente

- Caratteristiche dei dati consigliate:
    - Dati storici sufficienti: almeno un anno di dati transazionali. Preferibilmente da due a tre anni di dati transazionali per prevedere il CLV per un anno.
    - Acquisti multipli per cliente: idealmente, almeno due o tre transazioni per ID cliente, preferibilmente in più date.
    - Numero di clienti: almeno 100 clienti univoci, preferibilmente più di 10.000 clienti. Il modello non riesce con meno di 100 clienti e dati storici insufficienti
    - Completezza dei dati: meno del 20% di valori mancanti nei campi obbligatori nei dati di input   

> [!NOTE]
> - Il modello richiede la cronologia delle transazioni dei tuoi clienti. Al momento è possibile configurare solo un'entità della cronologia delle transazioni. Se sono presenti più entità di acquisto/transazione, uniscile in Power Query prima dell'inserimento dei dati.
> - Per ulteriori dati sull'impegno del cliente (facoltativo), puoi aggiungere tutte le entità di impegno del cliente che desideri venga in considerazione dal modello.

## <a name="create-a-customer-lifetime-value-prediction"></a>Creare una previsione del valore di durata del cliente

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Intelligenza** > **Previsioni**.

1. Seleziona il riquadro **Valore di durata del cliente** e seleziona **Utilizza modello**. 

1. Nel riquadro **Valore durata cliente (anteprima)** seleziona **Inizia**.

1. Specifica **Assegna un nome al modello** e **Nome entità di output** per distinguerli da altri modelli o entità.

1. Seleziona **Avanti**.

### <a name="define-model-preferences"></a>Definire le preferenze del modello

1. Imposta un **Periodo di tempo della previsione** per definire quanto lontano nel futuro si desidera prevedere il CLV.    
   Per impostazione predefinita, l'unità è impostata su mesi. Puoi cambiarla in anni per prevedere più lontano nel futuro.

   > [!TIP]
   > Per prevedere con precisione il CLV per il periodo di tempo impostato, è necessario un periodo di dati storici comparabile. Ad esempio, se si desidera prevedere il CLV per i prossimi 12 mesi, si consiglia di disporre di almeno 18-24 mesi di dati storici.

1. Specifica cosa significa **Clienti attivi** per il tuo business. Imposta la intervallo di tempo in cui un cliente deve aver avuto almeno una transazione per essere considerato attivo. Il modello prevede il CLV solo per i clienti attivi. 
   - **Consenti al modello di calcolare l'intervallo di acquisto (scelta consigliata)** : Il modello analizza i dati e determina un periodo di tempo in base agli acquisti storici.
   - **Imposta intervallo manualmente** : Se hai una definizione commerciale specifica di un cliente attivo, scegli questa opzione e imposta il periodo di tempo di conseguenza.

1. Definisci il percentile di **Cliente di valore elevato** per consentire al modello di fornire risultati che si adattano alla tua definizione commerciale.
    - **Calcolo modello (scelta consigliata)** : Il modello analizza i tuoi dati e determina quale potrebbe essere un cliente di alto valore per la tua azienda in base alla cronologia delle transazioni dei tuoi clienti. Il modello utilizza una regola euristica (ispirata alla legge 80/20 o principio di Pareto) per trovare la percentuale di clienti di alto valore. La percentuale di clienti che ha contribuito all'80% delle ricavi cumulative per il tuo business nel periodo storico è considerata clienti di alto valore. In genere, meno del 30-40% dei clienti contribuisce all'80% dei ricavi cumulative. Tuttavia, questo numero potrebbe variare a seconda della tua attività e del tuo settore.    
    - **Percentuale dei principali clienti attivi** : Definisci i clienti di alto valore per la tua attività come percentile dei principali clienti paganti attivi. Ad esempio, puoi utilizzare questa opzione per definire i clienti di alto valore come il primo 20% dei futuri clienti paganti.

    Se la tua azienda definisce i clienti di alto valore in un modo diverso, [ci piacerebbe sapere come](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Selezionare **Avanti** per procedere al passaggio successivo.

### <a name="add-required-data"></a>Aggiungi dati obbligatori

1. Nel passaggio **Dati obbligatori** seleziona **Aggiungi dati** in **Cronologia transazioni cliente** e scegli l'entità che fornisce le informazioni sulla cronologia delle transazioni come descritto nei [prerequisiti](#prerequisites).

1. Esegui il mapping dei campi semantici agli attributi nell'entità della cronologia degli acquisti e seleziona **Avanti**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Immagine del passaggio di configurazione per mappare gli attributi dei dati per i dati obbligatori.":::
 
1. Se i campi seguenti non sono popolati, configura la relazione tra l'entità della cronologia degli acquisti e l'entità *Cliente* e seleziona **Salva**.
    1. Seleziona l'entità della cronologia acquisti.
    1. Seleziona il campo che identifica un cliente nell'entità della cronologia degli acquisti. Deve essere correlato all'ID cliente primario dell'entità Cliente.
    1. Seleziona l'entità corrispondente all'entità cliente primario.
    1. Immetti un nome che descrive la relazione.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Immagine del passaggio di configurazione per definire la relazione con l'entità cliente.":::

1. Seleziona **Avanti**.

### <a name="add-optional-data"></a>Aggiungi dati facoltativi

I dati che riflettono le interazioni chiave dei clienti (come web, servizio clienti e registri eventi) aggiungono contesto ai record delle transazioni. Altri modelli trovati nei dati degli impegni del cliente possono migliorare l'accuratezza delle previsioni. 

1. Nel passaggio **Dati aggiuntivi (facoltativi)** seleziona **Aggiungi dati**. Scegli l'entità degli impegni cliente che fornisce le informazioni sugli impegni del cliente come descritto nei [prerequisiti](#prerequisites).

1. Esegui il mapping dei campi semantici agli attributi nell'entità degli impegni del cliente e seleziona **Avanti**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Immagine del passaggio di configurazione per mappare i campi per i dati aggiuntivi.":::

1. Seleziona un tipo di impegno che corrisponda al tipo di impegno del cliente che stai aggiungendo. Scegli tra i tipi di impegno esistenti o aggiungi un nuovo tipo di impegno.

1. Configura la relazione dall'entità degli impegni cliente all'entità *Cliente*.
    
    1. Seleziona il campo che identifica il cliente nella tabella degli impegni del cliente. Può essere correlato direttamente all'ID cliente primario dell'entità *Cliente*.
    1. Seleziona l'entità *Cliente* che corrisponde all'entità *Cliente* primaria.
    1. Immetti un nome che descrive la relazione.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Immagine del passaggio nel flusso di configurazione per aggiungere dati aggiuntivi e configurare l'impegno con esempi compilati.":::

1. Seleziona **Salva**.    
    Aggiungi altri dati se ci sono altre impegni del cliente che desideri includere.

1. Seleziona **Avanti**.

### <a name="set-update-schedule"></a>Impostare la pianificazione di aggiornamento

1. Nel passaggio **Pianificazione aggiornamento dati** scegli la frequenza con cui ripetere il training del modello in base ai dati più recenti. Questa impostazione è importante per aggiornare la precisione delle previsioni a mano a mano che i nuovi dati vengono inseriti in Informazioni dettagliate sul gruppo di destinatari. La maggior parte delle aziende può ripetere il training una volta al mese e ottenere una buona precisione per le loro previsioni.

1. Seleziona **Avanti**.

### <a name="review-and-run-the-model-configuration"></a>Rivedere ed eseguire la configurazione del modello

1. Nel passaggio **Rivedi i dettagli del modello** convalida la configurazione della previsione. Puoi tornare a qualsiasi parte della configurazione di previsione selezionando **Modifica** sotto il valore mostrato. È inoltre possibile selezionare un passaggio di configurazione dall'indicatore di avanzamento.

1. Se tutti i valori sono configurati correttamente, selezionare **Salva ed esegui** per avviare l'esecuzione del modello. Nella scheda **Le mie previsioni** puoi vedere lo stato del processo di previsione. Il completamento del processo potrebbe richiedere diverse ore a seconda della quantità di dati utilizzati nella previsione.

## <a name="review-prediction-status-and-results"></a>Controllare lo stato e i risultati della previsione

### <a name="review-prediction-status"></a>Controllare lo stato della previsione

1.  Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.
2.  Seleziona la previsione da rivedere.

- **Nome previsione:** il nome del previsione fornito durante la creazione.
- **Tipo di previsione:** il tipo di modello utilizzato per la previsione
- **Entità di output:** nome dell'entità per memorizzare l'output della previsione. Vai a **Dati** > **Entità** per trovare l'entità con questo nome.
- **Campo previsione:** questo campo viene popolato solo per alcuni tipi di previsioni e non viene utilizzato nella previsione del valore di durata del cliente.
- **Stato:** lo stato dell'esecuzione della previsione.
    - **In coda:** la previsione attende il completamento di altri processi.
    - **Aggiornamento in corso:** la previsione è attualmente in esecuzione per creare risultati che verranno inseriti nell'entità di output.
    - **Errore:** l'esecuzione della previsione non è riuscita. [Esamina i log](manage-predictions.md#troubleshoot-a-failed-prediction) per maggiori informazioni.
    - **Completata:** la previsione è riuscita. Seleziona **Visualizza** sotto i puntini di sospensione verticali per esaminare i risultati della previsione.
- **Data di modifica**: la data in cui è stata modificata la configurazione per la previsione.
- **Ultimo aggiornamento:** la data in cui sono stati aggiornati i risultati della previsione nell'entità di output.

### <a name="review-prediction-results"></a>Controllare i risultati della previsione

1. Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.

1. Seleziona il previsione di cui desideri esaminare i risultati.

Esistono tre sezioni principali di dati nella pagina dei risultati:

- **Prestazioni modello di training**: A, B o C sono i gradi possibili. Questo grado indica le prestazioni della previsione e può aiutarti a prendere la decisione di utilizzare i risultati archiviati nell'entità di output. Seleziona **Informazioni su questo punteggio** per comprendere meglio le metriche sottostanti delle prestazioni del modello e come è stato derivato il grado finale delle prestazioni del modello.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Immagine della casella delle informazioni sul punteggio del modello con il grado A.":::

  Utilizzando la definizione di clienti di alto valore fornita durante la configurazione della previsione, il sistema valuta come il modello di intelligenza artificiale si è comportato nel prevedere i clienti di alto valore rispetto a un modello di base.    

  I gradi sono determinati in base alle seguenti regole:
  - **A** quando il modello ha previsto con precisione almeno il 5% in più di clienti di alto valore rispetto al modello di base.
  - **B** quando il modello ha previsto con precisione tra 0 e 5% in più di clienti di alto valore rispetto al modello di base.
  - **C** quando il modello ha previsto con precisione meno clienti di alto valore rispetto al modello di base.

  Il riquadro **Classificazione modello** mostra ulteriori dettagli sulle prestazioni del modello di intelligenza artificiale e sul modello di base. Il modello di base utilizza un approccio non basato sull'intelligenza artificiale per calcolare il valore di durata del cliente basato principalmente sugli acquisti storici effettuati dai clienti.     
  La formula standard utilizzata per calcolare il CLV dal modello di base:    

  _**CLV per ogni cliente** = Acquisto mensile medio effettuato dal cliente nella finestra di clienti attivi * Numero di mesi nel periodo di previsione del CLV * Tasso di fidelizzazione complessivo di tutti i clienti_

  Il modello di intelligenza artificiale viene confrontato con il modello di base sulla base di due metriche delle prestazioni del modello.
  
  - **Percentuale di successo nella previsione di clienti di valore elevato**

    Vedi la differenza nel prevedere i clienti di alto valore utilizzando il modello di intelligenza artificiale rispetto al modello di base. Ad esempio, una percentuale di successo dell'84% significa che tra tutti i clienti di alto valore nei dati di training, il modello di intelligenza artificiale è stato in grado di acquisire con precisione l'84%. Quindi confrontiamo questa percentuale di successo con la percentuale di successo del modello di base per riportare la variazione relativa. Questo valore viene utilizzato per assegnare un grado al modello.

  - **Metrica di errore**
    
    Un'altra metrica consente di rivedere le prestazioni complessive del modello in termini di errore nella previsione dei valori futuri. Usiamo la metrica complessiva Radice dell'errore quadratico medio (RMSE) per valutare questo errore. RMSE è un modo standard per misurare l'errore di un modello nella previsione di dati quantitativi. L'RMSE del modello di intelligenza artificiale viene confrontato con l'RMSE del modello di base e viene riportata la differenza relativa.

  Il modello di intelligenza artificiale dà la priorità all'accurata classificazione dei clienti in base al valore che apportano al tuo business. Quindi solo la percentuale di successo della previsione dei clienti di alto valore viene utilizzato per ricavare il grado finale del modello. La metrica RMSE è sensibile ai valori anomali. Negli scenari in cui si dispone di una piccola percentuale di clienti con valori di acquisto straordinariamente elevati, la metrica RMSE complessiva potrebbe non fornire un quadro completo delle prestazioni del modello.   

- **Valore dei clienti per percentile** : Utilizzando la tua definizione di clienti di alto valore, i clienti vengono raggruppati in basso valore e alto valore, in base alle previsioni del loro CLV, e mostrati in un grafico. Passando il mouse sulle barre nell'istogramma, puoi vedere il numero di clienti in ogni gruppo e il CLV medio di quel gruppo. Questi dati possono essere d'aiuto se desideri [creare segmenti di clienti](segments.md) in base alle relative previsioni di CLV.

- **Fattori più influenti** : Vengono presi in considerazione vari fattori durante la creazione della previsione del CLV in base ai dati di input forniti al modello di intelligenza artificiale. Ciascuno dei fattori ha la sua importanza calcolata per le previsioni aggregate create da un modello. Puoi utilizzare questi fattori per convalidare i risultati della previsione. Questi fattori forniscono anche maggiori informazioni sui fattori più influenti che hanno contribuito a prevedere il CLV per tutti i tuoi clienti.

## <a name="manage-predictions"></a>Gestisci previsioni

È possibile ottimizzare, risolvere i problemi, aggiornare o eliminare le previsioni. Esamina un report sull'usabilità dei dati di input per scoprire come rendere un previsione più veloce e affidabile. Per ulteriori informazioni, vedi [Gestisci previsioni](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
