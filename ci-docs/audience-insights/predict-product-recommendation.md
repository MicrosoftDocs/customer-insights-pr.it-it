---
title: Previsione di raccomandazioni sui prodotti
description: Prevedi i prodotti che è probabile che un cliente acquisterà o con cui interagirà.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598068"
---
# <a name="product-recommendation-prediction-preview"></a>Previsione di raccomandazioni sui prodotti (anteprima)

Il modello di raccomandazione prodotti crea serie di raccomandazioni predittive sui prodotti. Le raccomandazioni si basano sul comportamento di acquisto precedente e sui clienti con modelli di acquisto simili. È possibile creare nuove previsioni di raccomandazioni sui prodotti nella pagina **Intelligenza** > **Previsioni**. Seleziona **Le mie previsioni** per visualizzare altre previsioni che hai creato.

Le raccomandazioni sui prodotti possono essere soggette alle leggi e ai regolamenti locali, nonché alle aspettative dei clienti, che il modello non è stato costruito per tenere in particolare considerazione.  Come utente di questa funzionalità predittiva, **devi rivedere le raccomandazioni prima di distribuirle ai clienti** per assicurarti di rispettare le leggi o i regolamenti applicabili, nonché le aspettative dei clienti per ciò che potresti consigliare. 

Inoltre, l'output di questo modello fornirà raccomandazioni basati sull'ID del prodotto. Il meccanismo di consegna dovrà prendere gli ID prodotto previsti e mapparli al contenuto appropriato per i tuoi clienti per tenere conto della località, del contenuto dell'immagine e di altri contenuti o comportamenti specifici dell'azienda.

## <a name="sample-guide"></a>Guida di esempio

Se sei interessato a provare questa funzionalità ma non hai i dati per completare i requisiti di seguito, puoi [creare un'implementazione di esempio](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Prerequisiti

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.
- Conoscenza dell'attività aziendale per comprendere i diversi tipi di prodotti del tuo business e come i tuoi clienti interagiscono con essi. Supportiamo la raccomandazione di prodotti che sono stati precedentemente acquistati dai tuoi clienti o raccomandazioni per nuovi prodotti.
- Dati su transazioni, acquisti e la relativa cronologia:
    - Identificatori di transazione per distinguere acquisti o transazioni.
    - Identificatori cliente per mappare le transazioni ai clienti.
    - Date dell'evento di transazione che specificano le date in cui è avvenuta la transazione.
    - (Facoltativo) Informazioni sull'ID prodotto della transazione.
    - (Facoltativo) Se una transazione è un reso o meno.
    - Lo schema dei dati semantici richiede le seguenti informazioni:
        - **ID transazione:** un identificatore univoco di un acquisto o di una transazione.
        - **Data transazione:** la data dell'acquisto o della transazione.
        - **Valore della transazione:** il valore numerico dell'acquisto o transazione.
        - **ID prodotto univoco:** l'ID del prodotto o del servizio acquistato se i tuoi dati sono a livello di voce singola.
        - (Facoltativo) **Acquisto o reso:** un campo vero/falso che identifica se la transazione era o meno un reso. Se il **Valore della transazione** è negativo, useremo queste informazioni per dedurre un reso.


## <a name="create-a-product-recommendation-prediction"></a>Creare una previsione di raccomandazioni sui prodotti

1. In Customer Insights, vai a **Intelligence** > **Previsioni**.

1. Seleziona il riquadro **Modello di elementi consigliati per il prodotto (anteprima)** e seleziona **Utilizza questo modello**.
   > [!div class="mx-imgBorder"]
   > ![Riquadro Modello di raccomandazione prodotto con il pulsante Utilizza questo modello](media/product-recommendation-usethismodel.PNG "Riquadro Modello di raccomandazione prodotto con il pulsante Utilizza questo modello")

1. Rivedi le informazioni sui requisiti del modello. Se disponi dei dati obbligatori, seleziona **Inizia**.

### <a name="name-model"></a>Assegna nome a modello

1. Specifica un nome per il modello per distinguerlo dagli altri modelli.

1. Immettere un nome per l'entità di output utilizzando solo lettere e numeri, senza spazi. Questo è il nome che verrà utilizzato dall'entità modello. Quindi seleziona **Avanti**.

### <a name="define-product-recommendation-configuration"></a>Definire la configurazione delle raccomandazioni sui prodotti

1. Imposta il **Numero di prodotti** che vuoi consigliare a un cliente. Questo valore dipende da come il metodo di consegna inserisce i dati. Se puoi consigliare tre prodotti, imposta questo valore di conseguenza.
   
   >[!TIP]
   > Puoi selezionare **Salva e chiudi** in qualsiasi momento per salvare la previsione come bozza. Troverai la bozza di previsione nella scheda **Le mie previsioni**.

1. Scegli se **Suggerire prodotti acquistati di recente dai clienti**.

1. Se hai scelto di *non* consigliare i prodotti acquistati di recente, imposta la **Finestra per guardare indietro**. Questa impostazione specifica il intervallo di tempo che il modello considera prima di consigliare nuovamente il prodotto all'utente. Ad esempio, indica che un cliente acquista un laptop ogni 2 anni. Questa finestra esaminerà la cronologia degli acquisti degli ultimi 2 anni e, se trova un articolo, l'articolo verrò escluso dalle raccomandazioni.

1. Seleziona **Avanti**.

### <a name="add-required-data"></a>Aggiungi dati obbligatori

1. Seleziona **Aggiungi dati** in **Cronologia transazioni cliente** e scegli l'entità che fornisce le informazioni sulla cronologia di transazioni/acquisti come descritto nei [prerequisiti](#prerequisites).

1. Esegui il mapping dei campi semantici agli attributi nell'entità della cronologia degli acquisti e seleziona **Avanti**. Per le descrizioni dei campi, esamina i [prerequisiti](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definire la relazione dell'entità](media/product-recommendation-purchasehistorymapping.PNG "Pagina della cronologia degli acquisti che mostra gli attributi semantici mappati ai campi nell'entità della cronologia degli acquisti selezionata")

1. Se i campi seguenti non sono compilati, configura la relazione tra l'entità della cronologia degli acquisti e l'entità *Cliente*.
    1. Seleziona **Entità cronologia acquisti**.
    1. Seleziona il **campo** che identifica il cliente nell'entità della cronologia degli acquisti. Deve essere correlato all'ID cliente primario dell'entità *Cliente*.
    1. Seleziona l'**Entità cliente** che corrisponde all'entità cliente primaria.
    1. Immetti un nome che descrive la relazione.
       > [!div class="mx-imgBorder"]
       > ![Pagina della cronologia degli acquisti che mostra la creazione di una relazione con il cliente](media/model-purchase-join.png "Pagina della cronologia degli acquisti che mostra la creazione di una relazione con il cliente")

1. Seleziona **Salva**.

1. Seleziona **Avanti**.

### <a name="set-schedule-and-review-configuration"></a>Impostare la pianificazione ed esaminare la configurazione

1. Imposta una frequenza per ripetere il training del modello. Questa impostazione è importante per aggiornare l'accuratezza delle previsioni quando nuovi dati vengono importati in Customer Insights. La maggior parte delle aziende può ripetere il training una volta al mese e ottenere una buona precisione per le loro previsioni.

1. Seleziona **Avanti**.

1. Rivedi la configurazione. Puoi tornare a qualsiasi parte della configurazione di previsione selezionando **Modifica** sotto il valore mostrato. Oppure puoi selezionare un passaggio di configurazione dall'indicatore di avanzamento.

1. Se tutti i valori sono configurati correttamente, seleziona **Salva ed esegui** per iniziare il processo di previsione. Nella scheda **Le mie previsioni**, puoi vedere lo stato delle tue previsioni. Il completamento del processo potrebbe richiedere diverse ore a seconda della quantità di dati utilizzati nella previsione.

## <a name="review-a-prediction-status-and-results"></a>Rivedere lo stato e i risultati di una previsione

1. Vai alla scheda **Le mie previsioni** su **Intelligenza** > **Previsioni**.
   > [!div class="mx-imgBorder"]
   > ![Visualizzazione della pagina Le mie previsioni](media/product-recommendation-mypredictions.PNG "Visualizzazione della pagina Le mie previsioni")

1. Seleziona la previsione da rivedere.
   - **Nome della previsione:** il nome della previsione specificato durante la creazione.
   - **Tipo di previsione:** il tipo di modello utilizzato per la previsione
   - **Entità di output:** nome dell'entità per memorizzare l'output della previsione. Puoi trovare un'entità con questo nome su **Dati** > **Entità**.
   - **Campo previsione:** questo campo viene popolato solo per alcuni tipi di previsioni e non viene utilizzato nella previsione di abbandono.
   - **Stato:** lo stato corrente dell'esecuzione della previsione.
        - **In coda:** la previsione è attualmente in attesa dell'esecuzione di altri processi.
        - **In aggiornamento:** la previsione sta attualmente eseguendo la fase di "valutazione" dell'elaborazione per produrre risultati che confluiranno nell'entità di output.
        - **Non riuscita:** la previsione non è stata completata. Seleziona **Registri** per altri dettagli.
        - **Completata:** la previsione è stata completata. Seleziona **Visualizza** sotto i puntini di sospensione verticali per rivedere la previsione
   - **Modificata:** la data in cui è stata modificata la configurazione per la previsione.
   - **Ultimo aggiornamento:** la data in cui sono stati aggiornati i risultati della previsione risulta nell'entità di output.

1. Seleziona i puntini di sospensione verticali accanto alla previsione per cui desideri esaminare i risultati e seleziona **Visualizza**.
   > [!div class="mx-imgBorder"]
   > ![Visualizzazione delle opzioni nel menu dei puntini di sospensione veriticali per una previsione che include modifica, aggiornamento, visualizzazione, registri ed eliminazione](media/product-recommendation-verticalellipses.PNG "Visualizzazione delle opzioni nel menu dei puntini di sospensione veriticali per una previsione che include modifica, aggiornamento, visualizzazione, registri ed eliminazione")

1. Esistono tre sezioni principali di dati nella pagina dei risultati:
    1. **Prestazioni del modello di training:** A, B o C sono possibili punteggi. Questo punteggio indica le prestazioni della previsione e può aiutarti a prendere la decisione di utilizzare i risultati archiviati nell'entità di output.
        - I punteggi sono determinati in base alle seguenti regole:
            - **A** Il modello verrà considerato di qualità **A** se la metrica "Successo @ K" è almeno il 10% in più rispetto alla baseline. 
            - **B** Il modello verrà considerato di qualità **B** se la metrica "Successo @ K" è tra 0 e 10% in più rispetto alla baseline.
            - **C** Il modello verrà considerato di qualità **C** se la metrica "Successo @ K" è inferiore alla baseline.
               
               > [!div class="mx-imgBorder"]
               > ![Visualizzazione del risultato delle prestazioni del modello](media/product-recommendation-modelperformance.PNG "Visualizzazione del risultato delle prestazioni del modello")
            - **Linea di base** : Il modello prende i prodotti più consigliati in base al conteggio degli acquisti di tutti i clienti e utilizza le regole apprese identificate dal modello per creare una serie di raccomandazioni per i clienti. Le previsioni vengono quindi confrontate con i prodotti di punta, come calcolato dal numero di clienti che hanno acquistato il prodotto. Se un cliente ha almeno un prodotto tra i prodotti consigliati che è stato visto anche nei prodotti più acquistati, viene considerato parte della baseline. Se ci fossero 10 di questi clienti che hanno acquistato un prodotto consigliato su 100 clienti totali, la baseline sarebbe 10%.
            - **Successo @ K** : Utilizzando un set di convalida di periodo di tempo delle transazioni, le raccomandazioni vengono create per tutti i clienti e confrontate con il set di convalida delle transazioni. Ad esempio, in un periodo di 12 mesi, il mese 12 potrebbe essere accantonato come set di dati di convalida. Se il modello prevede almeno una cosa che acquisteresti nel mese 12 in base a ciò che ha appreso dagli 11 mesi precedenti, il cliente aumenterebbe la metrica "Successo @ K".
    
    1. **Prodotti più consigliati (con conteggio):** I primi 5 prodotti previsti per i tuoi clienti.
       > [!div class="mx-imgBorder"]
       > ![Grafico che mostra i primi 5 prodotti più consigliati](media/product-recommendation-topproducts.PNG "Grafico che mostra i primi 5 prodotti più consigliati")
    
    1. **Elementi consigliati sui prodotti con attendibilità elevata:** Un campione di raccomandazioni fornite ai clienti che il modello ritiene probabile possano essere acquistati dal cliente.
       > [!div class="mx-imgBorder"]
       > ![Elenco che mostra suggerimenti ad alta affidabilità per un gruppo selezionato di singoli clienti](media/product-recommendation-highconfidence.PNG "Elenco che mostra suggerimenti ad alta affidabilità per un gruppo selezionato di singoli clienti")

## <a name="fix-a-failed-prediction"></a>Correggere una previsione non riuscita

1. Vai alla scheda **Le mie previsioni** su **Intelligenza** > **Previsioni**.

1. Seleziona la previsione per la quale desideri visualizzare i registri degli errori e seleziona **Registri**.

1. Esamina tutti gli errori. Esistono diversi tipi di errori che possono verificarsi e descrivono quale condizione ha causato l'errore. Ad esempio, un errore che non contiene dati sufficienti per eseguire una previsione accurata viene in genere risolto caricando dati aggiuntivi in Customer Insights.

## <a name="refresh-a-prediction"></a>Aggiornare una previsione

Le previsioni si aggiornano automaticamente con la stessa [pianificazione degli aggiornamenti dei dati](system.md#schedule-tab) come configurata nelle impostazioni.

1. Vai alla scheda **Le mie previsioni** su **Intelligenza** > **Previsioni**.

1. Seleziona i puntini di sospensione verticali accanto alla previsione che vuoi aggiornare.

1. Seleziona **Aggiorna**.

## <a name="delete-a-prediction"></a>Eliminare una previsione

L'eliminazione di un previsione rimuove anche la relativa entità di output.

1. Vai alla scheda **Le mie previsioni** su **Intelligenza** > **Previsioni**.

1. Seleziona i puntini di sospensione verticali accanto alla previsione che vuoi eliminare.

1. Seleziona **Elimina.**


[!INCLUDE[footer-include](../includes/footer-banner.md)]