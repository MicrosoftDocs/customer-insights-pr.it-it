---
title: Previsione di raccomandazioni sui prodotti
description: Prevedi i prodotti che è probabile che un cliente acquisterà o con cui interagirà.
ms.date: 05/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 9b3e60c49d294d031f43ef0594cb69707bb64019
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762737"
---
# <a name="product-recommendation-prediction"></a>Previsione di raccomandazioni sui prodotti

Il modello di raccomandazione prodotti crea serie di raccomandazioni predittive sui prodotti. Le raccomandazioni si basano sul comportamento di acquisto precedente e sui clienti con modelli di acquisto simili. È possibile creare nuove previsioni di raccomandazioni sui prodotti nella pagina **Intelligenza** > **Previsioni**. Seleziona **Le mie previsioni** per visualizzare altre previsioni che hai creato.

Gli elementi consigliati sui prodotti possono essere soggette alle leggi e ai regolamenti locali e alle aspettative dei clienti, che il modello non è stato concepito per tenere specificamente in considerazione.  Come utente di questa capacità predittiva, **è necessario rivedere gli elementi consigliati prima di consegnarli ai clienti** per assicurarti di rispettare le leggi o i regolamenti applicabili e le aspettative dei clienti per ciò che potresti consigliare.

Inoltre, l'output di questo modello fornirà raccomandazioni basati sull'ID del prodotto. Il tuo meccanismo di consegna dovrà mappare gli ID prodotto previsti al contenuto appropriato affinché i tuoi clienti tengano conto della localizzazione, del contenuto dell'immagine e di altri contenuti o comportamenti specifici dell'azienda.

## <a name="sample-guide"></a>Guida di esempio

Se sei interessato a provare questa funzionalità ma non hai i dati per completare i requisiti di seguito, puoi [creare un'implementazione di esempio](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Prerequisiti

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.

- Conoscenza dell'attività aziendale per comprendere i diversi tipi di prodotti del tuo business e come i tuoi clienti interagiscono con essi. Supportiamo la raccomandazione di prodotti che sono stati precedentemente acquistati dai tuoi clienti o raccomandazioni per nuovi prodotti.

- L'ambiente deve essere configurato per il gruppo di destinatari primario **singoli consumatori**.

- Dati su transazioni, acquisti e la relativa cronologia:
  - Identificatori di transazione per distinguere acquisti o transazioni.
  - Identificatori cliente per mappare le transazioni ai clienti.
  - Date dell'evento di transazione che specificano le date in cui è avvenuta la transazione.
  - Informazioni sull'ID del prodotto per la transazione.
  - (Facoltativo) Un'entità di dati del catalogo prodotti per utilizzare un filtro prodotto.
  - (Facoltativo) Se una transazione è un reso o meno.
  - Lo schema dei dati semantici richiede le seguenti informazioni:
    - **ID transazione:** un identificatore univoco di un acquisto o di una transazione.
    - **Data transazione:** la data dell'acquisto o della transazione.
    - **Valore della transazione:** il valore numerico dell'acquisto o transazione.
    - **ID prodotto univoco:** l'ID del prodotto o del servizio acquistato se i tuoi dati sono a livello di voce singola.
    - (Opzionale) **Acquisto o reso:** Un campo booleano in cui il valore *vero* identifica che una transazione era un reso. Se i dati di acquisto o di reso non vengono forniti nel modello e il **Valore della transazione** è negativo, useremo queste informazioni anche per dedurre un reso.
- Caratteristiche dei dati consigliate:
  - Dati storici sufficienti: almeno un anno di dati transazionali, preferibilmente da due a tre anni per includere una certa stagionalità.
  - Acquisti multipli per cliente: tre o più transazioni per ID cliente
  - Numero di clienti: almeno 100 clienti, preferibilmente più di 10.000 clienti. Il modello non riesce con meno di 100 clienti.

> [!NOTE]
>
> - Il modello richiede la cronologia delle transazioni dei tuoi clienti. La definizione di una transazione è abbastanza flessibile. Tutti i dati che descrivono un'interazione utente-prodotto possono funzionare come input. Ad esempio, l'acquisto di un prodotto, la partecipazione a un corso o la partecipazione a un evento.
> - Al momento è possibile configurare solo un'entità della cronologia delle transazioni. Se sono presenti più entità di acquisto, puoi unirle in Power Query prima dell'importazione dei dati.
> - Se l'ordine e i dettagli dell'ordine sono entità diverse, uniscili prima di utilizzarli nel modello. Il modello non funziona solo con un ID ordine o un ID ricevuta in un'entità.

## <a name="create-a-product-recommendation-prediction"></a>Creare una previsione di raccomandazioni sui prodotti

1. In Customer Insights, vai a **Intelligence** > **Previsioni**.

1. Seleziona il riquadro **Modello di consigli sui prodotti** e seleziona **Usa questo modello**.
   > [!div class="mx-imgBorder"]
   > ![Riquadro Modello di raccomandazione prodotto con il pulsante Utilizza questo modello.](media/product-recommendation-usethismodel.PNG "Riquadro Modello di raccomandazione prodotto con il pulsante Utilizza questo modello")

1. Rivedi le informazioni sui requisiti del modello. Se disponi dei dati obbligatori, seleziona **Inizia**.

### <a name="name-model"></a>Assegna nome a modello

1. Specifica un nome per il modello per distinguerlo dagli altri modelli.

1. Immettere un nome per l'entità di output utilizzando solo lettere e numeri, senza spazi. Questo è il nome che verrà utilizzato dall'entità modello. Quindi seleziona **Avanti**.

### <a name="define-product-recommendation-configuration"></a>Definire la configurazione delle raccomandazioni sui prodotti

1. Imposta il **Numero di prodotti** che vuoi consigliare a un cliente. Questo valore dipende da come il metodo di consegna inserisce i dati. Se puoi consigliare tre prodotti, imposta questo valore di conseguenza.

   >[!TIP]
   > Puoi selezionare **Salva la bozza** in qualsiasi momento per salvare la previsione come bozza. Troverai la bozza di previsione nella scheda **Le mie previsioni**.

1. Scegli se desideri includere i prodotti che i clienti hanno acquistato di recente nel campo **Ripetizione degli acquisti prevista**.

1. Imposta la **Finestra per guardare indietro**. Questa impostazione specifica il intervallo di tempo che il modello considera prima di consigliare nuovamente il prodotto all'utente. Ad esempio, indica che un cliente acquista un laptop ogni due anni. Questa finestra esaminerà la cronologia degli acquisti degli ultimi due anni e, se trova un articolo, l'elemento verrà filtrato dagli elementi consigliati.

1. Selezionare **Avanti**.

### <a name="add-required-data"></a>Aggiungi dati obbligatori

1. Seleziona **Aggiungi dati** e scegli il tipo di impegno nel riquadro laterale che contiene la transazione richiesta o le informazioni sulla cronologia degli acquisti.

1. In **Scegli impegni** seleziona gli impegni specifici dall'impegno selezionato su cui desideri che il calcolo si concentri.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Riquadro laterale che mostra la scelta di impegni specifici nel tipo semantico.":::

1. Se non hai ancora mappato l'attività su un tipo semantico, seleziona **Modifica** per farlo. Si apre l'esperienza guidata per mappare gli impegni semantici. Mappa i tuoi dati ai campi corrispondenti nel tipo di impegno selezionato.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Pagina di impostazione del tipo di impegno.":::

1. Dopo aver mappato l'impegno sul tipo semantico corrispondente, seleziona **Avanti** per procedere.

1. Mappa gli attributi semantici ai campi necessari per eseguire il modello.

1. Seleziona **Salva**.

1. Selezionare **Avanti**.

### <a name="configure-product-filters"></a>Configurare filtri di prodotto

A volte, solo alcuni prodotti sono utili o appropriati per il tipo di previsione che crei. I filtri di prodotto ti consentono di identificare un sottoinsieme di prodotti con caratteristiche specifiche da consigliare ai tuoi clienti. Il modello utilizzerà tutti i prodotti disponibili per apprendere i modelli, ma utilizzerà solo i prodotti che corrispondono al filtro di prodotto nell'output.

1. Nel passaggio **Aggiungi informazioni sul prodotto**, aggiungi il tuo catalogo prodotti con le informazioni per ogni prodotto. Mappa le informazioni richieste e seleziona **Avanti**.

1. Nel passaggio **Filtri di prodotto** scegli tra le seguenti opzioni.

   - **Nessun filtro**: Utilizza tutti i prodotti nella previsione di raccomandazione prodotto.

   - **Definisci filtri di prodotti specifici**: Utilizza prodotti specifici nella previsione di raccomandazione prodotto.

1. Seleziona **Avanti**.

1. Se scegli di definire un filtro prodotto, devi definirlo ora. Nel riquadro **Attributi catalogo prodotti** seleziona gli attributi dalla tua *Entità catalogo prodotti* che desideri includere nel filtro.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Riquadro laterale che mostra l'attributo nell'entità catalogo prodotti da selezionare per i filtri di prodotto.":::

1. Scegli se desideri utilizzare nel filtro di prodotto i connettori **and** oppure **or** per combinare in modo logico la selezione di attributi dal catalogo prodotti.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Configurazione di esempio dei filtri di prodotto combinati con connettori logici AND.":::

1. Seleziona **Avanti**.

### <a name="set-update-schedule-and-review-configuration"></a>Impostare la pianificazione degli aggiornamenti e rivedere la configurazione

1. Imposta una frequenza per ripetere il training del modello. Questa impostazione è importante per aggiornare l'accuratezza delle previsioni quando nuovi dati vengono importati in Customer Insights. La maggior parte delle aziende può ripetere il training una volta al mese e ottenere una buona precisione per le loro previsioni.

1. Seleziona **Avanti**.

1. Rivedi la configurazione. Puoi tornare a qualsiasi parte della configurazione di previsione selezionando **Modifica** sotto il valore mostrato. Oppure puoi selezionare un passaggio di configurazione dall'indicatore di avanzamento.

1. Se tutti i valori sono configurati correttamente, seleziona **Salva ed esegui** per iniziare il processo di previsione. Nella scheda **Le mie previsioni**, puoi vedere lo stato delle tue previsioni. Il completamento del processo potrebbe richiedere diverse ore a seconda della quantità di dati utilizzati nella previsione.

## <a name="review-a-prediction-status-and-results"></a>Rivedere lo stato e i risultati di una previsione

1. Vai alla scheda **Le mie previsioni** su **Intelligenza** > **Previsioni**.
   > [!div class="mx-imgBorder"]
   > ![Visualizzazione della pagina Le mie previsioni.](media/product-recommendation-mypredictions.PNG "Visualizzazione della pagina Le mie previsioni")

1. Seleziona la previsione da rivedere.
   - **Nome della previsione:** il nome della previsione specificato durante la creazione.
   - **Tipo di previsione:** il tipo di modello utilizzato per la previsione
   - **Entità di output:** nome dell'entità per memorizzare l'output della previsione. Puoi trovare un'entità con questo nome su **Dati** > **Entità**.
      *Punteggio* nell'entità di output è una misura quantitativa della raccomandazione. Il modello consiglia prodotti con un punteggio più alto rispetto a prodotti con un punteggio inferiore.
   - **Campo previsto:** Questo campo viene compilato solo per alcuni tipi di previsioni e non viene utilizzato nella previsione di raccomandazione sul prodotto.
   - **Stato:** lo stato corrente dell'esecuzione della previsione.
        - **In coda:** la previsione è attualmente in attesa dell'esecuzione di altri processi.
        - **In aggiornamento:** la previsione sta attualmente eseguendo la fase di "valutazione" dell'elaborazione per produrre risultati che confluiranno nell'entità di output.
        - **Non riuscita:** la previsione non è stata completata. Seleziona **Registri** per altri dettagli.
        - **Completata:** la previsione è stata completata. Seleziona **Visualizza** sotto i puntini di sospensione verticali per rivedere la previsione
   - **Modificata:** la data in cui è stata modificata la configurazione per la previsione.
   - **Ultimo aggiornamento:** la data in cui sono stati aggiornati i risultati della previsione risulta nell'entità di output.

1. Seleziona i puntini di sospensione verticali accanto alla previsione per cui desideri esaminare i risultati e seleziona **Visualizza**.
   > [!div class="mx-imgBorder"]
   > ![Visualizzazione delle opzioni nel menu dei puntini di sospensione veriticali per una previsione che include modifica, aggiornamento, visualizzazione, registri ed eliminazione.](media/product-recommendation-verticalellipses.PNG "Visualizzazione delle opzioni nel menu dei puntini di sospensione veriticali per una previsione che include modifica, aggiornamento, visualizzazione, registri ed eliminazione")

1. Ci sono cinque sezioni principali di dati all'interno della pagina dei risultati:
    1. **Prestazioni del modello di training:** A, B o C sono possibili punteggi. Questo punteggio indica le prestazioni della previsione e può aiutarti a prendere la decisione di utilizzare i risultati archiviati nell'entità di output.
        - I punteggi sono determinati in base alle seguenti regole:
            - **A** Il modello verrà considerato di qualità **A** se la metrica "Successo @ K" è almeno il 10% in più rispetto alla baseline. 
            - **B** Il modello verrà considerato di qualità **B** se la metrica "Successo @ K" è tra 0% e 10% in più rispetto alla baseline.
            - **C** Il modello verrà considerato di qualità **C** se la metrica "Successo @ K" è inferiore rispetto alla baseline.

               > [!div class="mx-imgBorder"]
               > ![Visualizzazione del risultato delle prestazioni del modello.](media/product-recommendation-modelperformance.PNG "Visualizzazione del risultato delle prestazioni del modello")
            - **Linea di base**: il modello prende i prodotti più consigliati in base al conteggio degli acquisti di tutti i clienti e utilizza le regole apprese identificate dal modello per creare una serie di raccomandazioni per i clienti. Le previsioni vengono quindi confrontate con i prodotti di punta, come calcolato dal numero di clienti che hanno acquistato il prodotto. Se un cliente ha almeno un prodotto tra i prodotti consigliati che è stato visto anche nei prodotti più acquistati, viene considerato parte della baseline. Se ci fossero 10 di questi clienti che hanno acquistato un prodotto consigliato su 100 clienti totali, la baseline sarebbe 10%.
            - **Successo @ K**: utilizzando un set di convalida di periodo di tempo delle transazioni, le raccomandazioni vengono create per tutti i clienti e confrontate con il set di convalida delle transazioni. Ad esempio, in un periodo di 12 mesi, il mese 12 potrebbe essere accantonato come set di dati di convalida. Se il modello prevede almeno una cosa che acquisteresti nel mese 12 in base a ciò che ha appreso dagli 11 mesi precedenti, il cliente aumenterebbe la metrica "Successo @ K".

    1. **Prodotti più consigliati (con conteggio):** I primi cinque prodotti previsti per i tuoi clienti.
       > [!div class="mx-imgBorder"]
       > ![Grafico che mostra i primi 5 prodotti più consigliati.](media/product-recommendation-topproducts.PNG "Grafico che mostra i primi 5 prodotti più consigliati")

    1. **Fattori raccomandazione chiave:** Il modello utilizza la cronologia delle transazioni dei clienti per fornire consigli sui prodotti. Apprende i modelli basati sugli acquisti passati e trova somiglianze tra clienti e prodotti. Queste somiglianze vengono quindi utilizzate per generare le raccomandazioni sui prodotti.
    Di seguito sono riportati i fattori che potrebbero influenzare una raccomandazione di prodotto generata dal modello.
        - **Transazioni passate**: I modelli di acquisto in passato venivano utilizzati dal modello per generare raccomandazioni sui prodotti. Ad esempio, il modello può consigliare un *Surface Arc Mouse* se qualcuno ha recentemente acquistato un *Surface Book 3* e una *Penna per Surface*. Il modello ha appreso che storicamente molti clienti avevano acquistato un *Surface Arc Mouse* dopo aver acquistato un *Surface Book 3* e una *Penna per Surface*.
        - **Somiglianza cliente**: Un prodotto consigliato è stato storicamente acquistato da altri clienti che mostrano modelli di acquisto simili. Ad esempio, a John sono state consigliate le *Cuffie Surface 2* perché Jennifer e Brad hanno recentemente acquistato le *Cuffie Surface 2*. Il modello crede che John sia simile a Jennifer e Brad perché storicamente hanno avuto modelli di acquisto simili.
        - **Somiglianza prodotto**: Un prodotto consigliato è simile ad altri prodotti che il cliente aveva acquistato in precedenza. Il modello considera due prodotti simili se acquistati insieme o da clienti simili. Ad esempio, qualcuno riceve una raccomandazione per una *Unità di archiviazione USB* perché in precedenza avevano acquistato un *Adattatore da USB-C a USB* e il modello crede che *Unità di archiviazione USB* sia simile ad *Adattatore da USB-C a USB* in base ai modelli storici di acquisto.

        Ogni raccomandazione sul prodotto è influenzata da uno o più di questi fattori. La percentuale di raccomandazioni in cui ogni fattore di influenza ha svolto un ruolo viene visualizzata in un grafico. Nell'esempio seguente, il 100% delle raccomandazioni è stato influenzato da transazioni passate, il 60% dalla somiglianza del cliente e il 22% dalla somiglianza del prodotto. Passa il mouse sulle barre nel grafico per vedere la percentuale esatta a cui hanno contribuito i fattori di influenza.

        > [!div class="mx-imgBorder"]
        > ![Fattori raccomandazione chiave.](media/product-recommendation-keyrecommendationfactors.png "Fattori di raccomandazione chiave appresi dal modello per generare raccomandazioni sui prodotti")

   1. **Statistiche dei dati**: Forniscono una panoramica del numero di transazioni, clienti e prodotti presi in considerazione dal modello. Si basa sui dati di input utilizzati per apprendere i modelli e generare raccomandazioni sui prodotti.

      > [!div class="mx-imgBorder"]
      > ![Statistiche dati.](media/product-recommendation-datastatistics.png "Statistiche dei dati sui dati inout utilizzati dal modello per apprendere i modelli")

      Questa sezione mostra le statistiche sui punti dati che sono stati utilizzati dal modello per apprendere i modelli e generare consigli sui prodotti. Il filtro, come configurato nella configurazione del modello, verrà applicato all'output generato dal modello. Tuttavia, il modello utilizza tutti i dati disponibili per apprendere i modelli. Pertanto, se usi il filtro del prodotto nella configurazione del modello, questa sezione mostrerà il numero totale di prodotti analizzati dal modello per apprendere i modelli, che potrebbero differire dal numero di prodotti che corrispondono ai criteri di filtro definiti.

   1. **Elementi consigliati sui prodotti con attendibilità elevata:** Un campione di raccomandazioni fornite ai clienti che il modello ritiene probabile possano essere acquistati dal cliente.    
      Se viene aggiunto un catalogo di prodotti, gli ID dei prodotti vengono sostituiti con i nomi dei prodotti. I nomi dei prodotti forniscono informazioni più fruibili e intuitive sulle previsioni.
       > [!div class="mx-imgBorder"]
       > ![Elenco che mostra suggerimenti ad alta affidabilità per un gruppo selezionato di singoli clienti.](media/product-recommendation-highconfidence.PNG "Elenco che mostra suggerimenti ad alta affidabilità per un gruppo selezionato di singoli clienti")

## <a name="manage-predictions"></a>Gestisci previsioni

È possibile ottimizzare, risolvere i problemi, aggiornare o eliminare le previsioni. Esamina un report sull'usabilità dei dati di input per scoprire come rendere un previsione più veloce e affidabile. Per ulteriori informazioni, vedi [Gestisci previsioni](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]