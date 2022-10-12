---
title: Prevedere il valore della durata del cliente (CLV)
description: Prevedi i futuri ricavi potenziali dai clienti attivi.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610379"
---
# <a name="predict-customer-lifetime-value-clv"></a>Prevedere il valore della durata del cliente (CLV)

Prevedi il valore potenziale (ricavi) che i singoli clienti attivi porteranno nella tua attività in un periodo di tempo futuro definito. Questa previsione ti permette di:

- Identificare i clienti di alto valore ed elaborare queste informazioni approfondite.
- Creare segmenti di clienti strategici in base al loro valore potenziale per eseguire campagne personalizzate con vendite, marketing e supporto mirati.
- Guidare lo sviluppo dei prodotti concentrandoti sulle funzionalità che aumentano il valore per il cliente.
- Ottimizzare la strategia di vendita o di marketing e allocare il budget in modo più accurato per la sensibilizzazione dei clienti.
- Riconoscere e premiare i clienti di alto valore attraverso programmi di fidelizzazione o premi.

Determinare cosa significa il CLV per la tua attività. Supportiamo la previsione del CLV basato su transazioni. Il valore previsto di un cliente si basa sulla cronologia delle transazioni commerciali. Prendi in considerazione la creazione di diversi modelli con diverse preferenze di input e confronta i risultati dei modelli per vedere quale scenario di modello si adatta meglio alle tue esigenze aziendali.

> [!TIP]
> Prova la previsione del CLV usando dati di esempio: [Guida di esempio previsione di Customer Lifetime Value (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Prerequisiti

- Almeno autorizzazioni [Collaboratore](permissions.md)
- Almeno 100 clienti univoci, preferibilmente più di 10.000 clienti
- Identificatore cliente: un identificatore univoco per abbinare le transazioni a un singolo cliente
- Almeno un anno di cronologia delle transazioni, preferibilmente due o tre anni. Idealmente, almeno due o tre transazioni per ID cliente, preferibilmente in più date. La cronologia delle transazioni deve includere:
  - **ID transazione**: un identificatore univoco per ogni transazione.
  - **Data transazione**: data o timestamp di ciascuna transazione
  - **Importo della transazione**: valore monetario (ad esempio, ricavi o margine di profitto) di ciascuna transazione
  - **Etichetta assegnata ai resi**: valore booleano vero/falso che indica se la transazione è un reso
  - **ID prodotto**: ID prodotto del prodotto coinvolto nella transazione
- Dati sugli impegni dei clienti:
  - **Chiave primaria**: identificatore univoco per un'attività
  - **Timestamp**: data e ora dell'evento identificato dalla chiave primaria
  - **Evento (nome attività)**: nome dell'evento che desideri usare
  - **Dettagli (importo o valore)**: dettagli sull'impegno del cliente
- Dati aggiuntivi quali:
  - Attività Web: cronologia delle visite al sito Web o cronologia dei messaggi e-mail
  - Attività di fidelizzazione: accumulo di punti fedeltà e cronologia dei riscatti
  - Registro servizio clienti, cronologia delle chiamate di servizio, dei reclami o dei resi
  - Informazioni sul profilo cliente
- Meno del 20% di valori mancanti nei campi obbligatori

> [!NOTE]
> È possibile configurare una sola entità di cronologia delle transazioni. Se sono presenti più entità di acquisto/transazione, puoi combinarle in Power Query prima che inizi l'inserimento dati.

## <a name="create-a-customer-lifetime-value-prediction"></a>Creare una previsione del valore di durata del cliente

Seleziona **Salva bozza** in qualsiasi momento per salvare la previsione come bozza. La previsione della bozza sarà visibile nella scheda **Previsioni personali**.

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Crea** seleziona **Usa modello** nel riquadro **Valore di durata del cliente**.

1. Seleziona **Richiedi una demo**.

1. Specifica **Assegna un nome al modello** e **Nome entità di output** per distinguerli da altri modelli o entità.

1. Seleziona **Avanti**.

### <a name="define-model-preferences"></a>Definire le preferenze del modello

1. Imposta un **Periodo di tempo della previsione** per definire quanto lontano nel futuro si desidera prevedere il CLV. Per impostazione predefinita, l'unità è impostata su mesi.

   > [!TIP]
   > Per prevedere con precisione il CLV per il periodo di tempo impostato, è necessario un periodo di dati storici comparabile. Ad esempio, se vuoi prevedere il CLV per i prossimi 12 mesi, devi disporre di almeno 18-24 mesi di dati storici.

1. Imposta la intervallo di tempo in cui un cliente deve aver avuto almeno una transazione per essere considerato attivo. Il modello prevede il CLV solo per i **Clienti attivi**.
   - **Consenti al modello di calcolare l'intervallo di acquisto (scelta consigliata)**: il modello analizza i dati e determina un periodo di tempo in base agli acquisti storici.
   - **Imposta intervallo manualmente**: il periodo di tempo per la definizione di cliente attivo.

1. Definisci il percentile di **Cliente di valore elevato**.
    - **Calcolo del modello (scelta consigliata)**: il modello usa la regola 80/20. La percentuale di clienti che ha contribuito all'80% delle ricavi cumulative per il tuo business nel periodo storico è considerata clienti di alto valore. In genere, meno del 30-40% dei clienti contribuisce all'80% dei ricavi cumulative. Tuttavia, questo numero potrebbe variare a seconda della tua attività e del tuo settore.
    - **Percentuale dei principali clienti attivi**: il percentile specifico per un cliente di valore elevato. Ad esempio, immetti **25** per definire i clienti di valore elevato come il primo 25% dei futuri clienti paganti.

    Se la tua azienda definisce i clienti di alto valore in un modo diverso, [ci piacerebbe sapere come](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Selezionare **Avanti**.

### <a name="add-required-data"></a>Aggiungi dati obbligatori

1. Seleziona **Aggiungi dati** per **Cronologia transazioni cliente**.

1. Seleziona il tipo di attività semantica, **SalesOrder** o **SalesOrderLine**, che contiene la cronologia delle transazioni. Se l'attività non è stata impostata, seleziona **qui** e creala.

1. In **Attività**, se gli attributi dell'attività erano stati mappati a livello semantico al momento della creazione dell'attività, scegli gli attributi o l'entità specifici su cui dovranno essere basati i calcoli. Se il mapping semantico non era stato eseguito, seleziona **Modifica** e mappa i tuoi dati.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Aggiungere i dati richiesti per il modello CLV":::

1. Seleziona **Avanti** e rivedi gli attributi richiesti per questo modello.

1. Seleziona **Salva**.

1. Aggiungi ulteriori attività oppure seleziona **Avanti**.

### <a name="add-optional-activity-data"></a>Aggiungere dati sugli impegni facoltativi

I dati che riflettono le interazioni chiave dei clienti (come web, servizio clienti e registri eventi) aggiungono contesto ai record delle transazioni. Altri modelli trovati nei dati degli impegni del cliente possono migliorare l'accuratezza delle previsioni.

1. Seleziona **Aggiungi dati** in **Incrementa le informazioni dettagliate sul modello con dati aggiuntivi sul cliente**.

1. Seleziona un tipo di impegno che corrisponda al tipo di impegno del cliente che stai aggiungendo. Se l'attività non è stata impostata, seleziona **qui** e creala.

1. In **Attività**, se gli attributi dell'attività erano stati mappati al momento della creazione dell'attività, scegli gli attributi o l'entità specifici su cui dovranno essere basati i calcoli. Se il mapping non era stato eseguito, seleziona **Modifica** e mappa i tuoi dati.

1. Seleziona **Avanti** e rivedi gli attributi richiesti per questo modello.

1. Seleziona **Salva**.

1. Selezionare **Avanti**.

1. [Aggiungi dati cliente facoltativi](#add-optional-customer-data) oppure seleziona **Avanti** e vai a [Impostare la pianificazione di aggiornamento](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Aggiungere dati sul cliente facoltativi

Seleziona tra 18 attributi del profilo cliente di uso comune da includere come input nel modello. Questi attributi possono portare a risultati del modello più personalizzati, pertinenti e utilizzabili per i casi d'uso aziendali.

Ad esempio: Contoso Coffee vuole prevedere il valore di durata del cliente per presentare ai clienti di alto valore un'offerta personalizzata correlata al lancio della sua nuova macchina per caffè espresso. Contoso usa il modello CLV e aggiunge tutti i 18 attributi del profilo cliente per stabilire quali fattori influenzano i clienti di maggior valore. Contoso determina che la posizione del cliente è il fattore più influente per tali clienti.
Sulla base di queste informazioni, organizza quindi un evento locale per il lancio della macchina per caffè espresso e collabora con i fornitori locali per offerte personalizzate e un'esperienza speciale all'evento. Senza tali informazioni, Contoso potrebbe inviare solo email di marketing generiche e perdere l'opportunità di personalizzare questo segmento locale di clienti di alto valore.

1. Seleziona **Aggiungi dati** in **Incrementa ulteriormente le informazioni dettagliate sul modello con dati aggiuntivi sul cliente**.

1. Per **Entità** scegli **Cliente : CustomerInsights** per selezionare il profilo cliente unificato mappato ai dati degli attributi del cliente. In **ID cliente**, scegli **System.Customer.CustomerId**.

1. Mappa più campi se i dati sono disponibili nei tuoi profili cliente unificati.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Esempio di campi mappati per i dati del profilo cliente.":::

1. Seleziona **Salva**.

1. Selezionare **Avanti**.

### <a name="set-update-schedule"></a>Impostare la pianificazione di aggiornamento

1. Scegli la frequenza con cui ripetere il training del modello in base ai dati più recenti. Questa impostazione è importante per aggiornare l'accuratezza delle previsioni quando nuovi dati vengono inseriti in Customer Insights. La maggior parte delle aziende può ripetere il training una volta al mese e ottenere una buona precisione per le loro previsioni.

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
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Immagine della casella delle informazioni sul punteggio del modello con il voto A.":::

  Customer Insights valuta le prestazioni del modello di intelligenza artificiale rispetto al modello di base in termini di previsione dei clienti a valore elevato.

  I voti sono determinati in base alle seguenti regole:
  - **A** quando il modello ha previsto con precisione almeno il 5% in più di clienti di alto valore rispetto al modello di base.
  - **B** quando il modello ha previsto con precisione tra 0 e 5% in più di clienti di alto valore rispetto al modello di base.
  - **C** quando il modello ha previsto con precisione meno clienti di alto valore rispetto al modello di base.
  
  Seleziona [**Informazioni su questo punteggio**](#learn-about-the-score) per aprire il riquadro **Classificazione modello** che mostra ulteriori dettagli sulle prestazioni del modello di intelligenza artifiicale e sul modello di base. Queste informazioni ti aiuteranno a comprendere meglio le metriche sottostanti delle prestazioni del modello e come è stato derivato il voto finale delle prestazioni del modello. Il modello di base utilizza un approccio non basato sull'intelligenza artificiale per calcolare il valore di durata del cliente basato principalmente sugli acquisti storici effettuati dai clienti.

- **Valore dei clienti per percentile** : i clienti di basso valore e di valore elevato vengono visualizzati in un grafico. Passando il mouse sulle barre nell'istogramma, puoi vedere il numero di clienti in ogni gruppo e il CLV medio di quel gruppo. Facoltativamente, [crea segmenti di clienti](prediction-based-segment.md) in base alle relative previsioni CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Valore dei clienti per percentile per modello CLV":::

- **Fattori più influenti** : Vengono presi in considerazione vari fattori durante la creazione della previsione del CLV in base ai dati di input forniti al modello di intelligenza artificiale. Ciascuno dei fattori ha la sua importanza calcolata per le previsioni aggregate create da un modello. Usa questi fattori per convalidare i risultati della previsione. Questi fattori forniscono anche maggiori informazioni sui fattori più influenti che hanno contribuito a prevedere il CLV per tutti i tuoi clienti.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Fattori più influenti per modello CLV":::

### <a name="learn-about-the-score"></a>Informazioni sul punteggio

La formula standard utilizzata per calcolare il CLV dal modello di base:

 _**CLV per ogni cliente** = Acquisto mensile medio effettuato dal cliente nella finestra di clienti attivi * Numero di mesi nel periodo di previsione del CLV * Tasso di fidelizzazione complessivo di tutti i clienti_

Il modello di intelligenza artificiale viene confrontato con il modello di base sulla base di due metriche delle prestazioni del modello.
  
- **Percentuale di successo nella previsione di clienti di valore elevato**

  Vedi la differenza nel prevedere i clienti di alto valore utilizzando il modello di intelligenza artificiale rispetto al modello di base. Ad esempio, una percentuale di successo dell'84% significa che tra tutti i clienti di alto valore nei dati di training, il modello di intelligenza artificiale è stato in grado di acquisire con precisione l'84%. Quindi confrontiamo questa percentuale di successo con la percentuale di successo del modello di base per riportare la variazione relativa. Questo valore viene utilizzato per assegnare un voto al modello.

- **Metrica di errore**

  Mostra le prestazioni complessive del modello in termini di errore nella previsione dei valori futuri. Usiamo la metrica complessiva Radice dell'errore quadratico medio (RMSE) per valutare questo errore. RMSE è un modo standard per misurare l'errore di un modello nella previsione di dati quantitativi. L'RMSE del modello di intelligenza artificiale viene confrontato con l'RMSE del modello di base e viene riportata la differenza relativa.

Il modello di intelligenza artificiale dà la priorità all'accurata classificazione dei clienti in base al valore che apportano al tuo business. Quindi solo la percentuale di successo della previsione dei clienti di alto valore viene utilizzato per ricavare il voto finale del modello. La metrica RMSE è sensibile ai valori anomali. Negli scenari in cui si dispone di una piccola percentuale di clienti con valori di acquisto straordinariamente elevati, la metrica RMSE complessiva potrebbe non fornire un quadro completo delle prestazioni del modello.

[!INCLUDE [footer-include](includes/footer-banner.md)]
