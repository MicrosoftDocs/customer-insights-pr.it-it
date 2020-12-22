---
title: Previsione sull'annullamento degli abbonamenti
description: Prevedi se esiste il rischio che un cliente non utilizzi più i prodotti o i servizi relativi all'abbonamento della società.
ms.date: 08/19/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 03178fc1bfe611b1b0ced08bbbef876035875825
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643733"
---
# <a name="subscription-churn-prediction-preview"></a>Previsione di abbandono dell'abbonamento (anteprima)

La previsione di abbandono dell'abbonamento consente di prevedere se esiste il rischio che un cliente non utilizzi più i prodotti o i servizi relativi all'abbonamento della società. Puoi creare una nuova previsione di abbandono dell'abbonamento nella pagina **Intelligenza** > **Previsioni**. Seleziona **Le mie previsioni** per visualizzare altre previsioni che hai creato.

> [!TIP]
> Prova l'esercitazione per una previsione di abbandono dell'abbonamento utilizzando dati di esempio: [Guida di esempio per una previsione di abbandono dell'abbonamento](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Prerequisiti

- [Autorizzazioni di collaboratore](permissions.md) come minimo.
- Conoscenza dell'azienda per capire cosa significa abbandono per la tua azienda. Supportiamo definizioni di abbandono basate sul tempo, nel senso che un cliente è considerato come perso dopo un determinato periodo di tempo dalla fine del suo abbonamento.
- Dati sui tuoi abbonamenti e sulla loro cronologia:
    - Identificatori di abbonamento per distinguere gli abbonamenti.
    - Identificativi del cliente per la corrispondenza tra gli abbonamenti e i clienti.
    - Date degli eventi di abbonamento, che definiscono le date di inizio, le date di fine e le date in cui si sono verificati gli eventi di abbonamento.
    - Informazioni sull'abbonamento per definire se si tratta di un abbonamento ricorrente e con quale frequenza viene rinnovato.
    - Lo schema di dati semantici per gli abbonamenti richiede le seguenti informazioni:
        - **ID abbonamento:** l'identificatore univoco di un abbonamento.
        - **Data di fine dell'abbonamento:** la data di scadenza dell'abbonamento per il cliente.
        - **Data di inizio dell'abbonamento:** la data in cui inizia l'abbonamento per il cliente.
        - **Data della transazione:** la data in cui è avvenuta una modifica dell'abbonamento. Ad esempio, un cliente che acquista o annulla un abbonamento.
        - **È un abbonamento ricorrente:** un campo booleano vero/falso che determina se l'abbonamento verrà rinnovato con lo stesso ID abbonamento senza l'intervento del cliente
        - **Frequenza di ricorrenza (in mesi):** per gli abbonamenti ricorrenti, è il periodo per il quale l'abbonamento verrà rinnovato. Viene rappresentato in mesi. Ad esempio, un abbonamento annuale che si rinnova automaticamente per un cliente ogni anno per un altro anno ha il valore 12.
        - (Facoltativo) **Importo dell'abbonamento:** La quantità di valuta che un cliente paga per il rinnovo dell'abbonamento. Può aiutare a identificare modelli per diversi livelli di abbonamento.
- Dati sugli impegni dei clienti:
    - Identificatori di impegni per distinguere gli impegni dello stesso tipo.
    - Identificativi del cliente per mappare gli impegni ai clienti.
    - Informazioni sull'impegno contenenti il nome e la data dell'impegno.
    - Lo schema di dati semantici per gli impegni dei clienti include:
        - **Chiave primaria:** l'identificatore univoco per un impegno. Ad esempio, una visita al sito Web o un record di utilizzo che mostra che il cliente ha visualizzato un episodio di un programma TV.
        - **Timestamp:** la data e l'ora dell'evento identificato dalla chiave primaria.
        - **Evento:** il nome dell'evento che si desidera utilizzare. Ad esempio, un campo chiamato "UserAction" in un servizio di streaming video potrebbe avere il valore di "Visualizzato".
        - **Dettagli:** informazioni dettagliate sull'evento. Ad esempio, un campo chiamato "ShowTitle" in un servizio di streaming video potrebbe avere il valore di un video visto dal cliente.
   > [!NOTE]
   > Avrai bisogno di almeno due record di attività per il 50% dei clienti per i quali desideri calcolare il tasso di abbandono.

## <a name="create-a-subscription-churn-prediction"></a>Ceare una previsione di abbandono dell'abbonamento

1. In Audience Insights, vai a **Intelligenza** > **Previsioni**.
1. Seleziona il riquadro **Modello di abbandono dell'abbonamento (anteprima)** e seleziona **Utilizza questo modello**.
   > [!div class="mx-imgBorder"]
   > ![Riquadro Modello di abbandono dell'abbonamento con il pulsante Utilizza questo modello](media/subscription-churn-usethismodel.PNG "Riquadro Modello di abbandono dell'abbonamento con il pulsante Utilizza questo modello")

### <a name="name-model"></a>Assegna nome a modello

1. Specifica un nome per il modello per distinguerlo dagli altri modelli.
1. Specifica un nome per l'entità di output utilizzando solo lettere e numeri, senza spazi. Questo è il nome che verrà utilizzato dall'entità modello. Quindi seleziona **Avanti**.

### <a name="define-customer-churn"></a>Definisci abbandono dei clienti

1. Immetti un valore in **Giorni dalla fine dell'abbonamento** dopo il quale la tua azienda considera il cliente come perso. Questo periodo è in genere apprezzato da attività commerciali come offerte o altre attività di marketing che cercano di prevenire la perdita del cliente.
1. Immetti il numero di **Giorni futuri da considerare per prevedere l'abbandono** per impostare una finestra per la quale prevedere l'abbandono. Ad esempio, per prevedere il rischio di abbandono dei tuoi clienti nei prossimi 90 giorni per allinearti agli sforzi di fidelizzazione del reparto marketing. Prevedere il rischio di abbandono per periodi di tempo più o meno lunghi può rendere più difficile la gestione dei fattori nel profilo di rischio di abbandono, ma ciò dipende in larga misura da requisiti aziendali specifici. Seleziona **Avanti** per continuare
   >[!TIP]
   > Puoi selezionare **Salva e chiudi** in qualsiasi momento per salvare la previsione come bozza. La previsione della bozza è disponibile nella scheda **Le mie previsioni** per continuare.

### <a name="add-required-data"></a>Aggiungi dati obbligatori

1. Seleziona **Aggiungi dati** per **Cronologia abbonamento** e scegli l'entità che fornisce le informazioni sulla cronologia dell'abbonamento come descritto nei [prerequisiti](#prerequisites).
1. Se i campi sottostanti non sono compilati, configura la relazione dall'entità della cronologia degli abbonamenti all'entità cliente.
    1. Seleziona **Entità cronologia abbonamenti**.
    1. Seleziona il **Campo** che identifica il cliente nell'entità cronologia abbonamenti. Deve essere correlato all'ID cliente primario dell'entità Cliente.
    1. Seleziona l'**Entità cliente** che corrisponde all'entità cliente primaria.
    1. Immetti un nome che descrive la relazione.
       > [!div class="mx-imgBorder"]
       > ![Pagina della cronologia degli abbonamenti che mostra la creazione di una relazione con il cliente](media/subscription-churn-subscriptionhistoryrelationship.PNG "Pagina della cronologia degli abbonamenti che mostra la creazione di una relazione con il cliente")
1. Seleziona **Avanti**.
1. Mappa i campi semantici agli attributi all'interno dell'entità cronologia abbonamenti e seleziona **Salva**. Per le descrizioni dei campi, esamina i [prerequisiti](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Pagina della cronologia degli abbonamenti che mostra gli attributi semantici mappati ai campi nell'entità cronologia degli abbonamenti selezionata](media/subscription-churn-subscriptionhistorymapping.PNG "Pagina della cronologia degli abbonamenti che mostra gli attributi semantici mappati ai campi nell'entità cronologia degli abbonamenti selezionata")
1. Seleziona **Aggiungi dati** per **Impegni dei clienti** e scegli l'entità che fornisce le informazioni sugli impegni dei clienti come descritto nei prerequisiti.
1. Seleziona un tipo di impegno corrispondente al tipo di impegno del cliente che stai configurando.  Seleziona **Creare nuovo** e specifica un nome se non vedi un'opzione che corrisponde al tipo di impegno di cui hai bisogno.
1. Dovrai configurare la relazione dall'entità impegno del cliente con l'entità cliente.
    1. Seleziona il campo che identifica il cliente nella tabella degli impegni del cliente, che può essere direttamente correlato all'ID cliente primario della tua entità cliente.
    1. Seleziona l'entità cliente che corrisponde all'entità cliente primaria
    1. Immetti un nome che descrive la relazione.
1. Seleziona **Avanti**.
1. Mappa i campi semantici agli attributi all'interno dell'entità impegno del cliente e seleziona **Salva**. Per le descrizioni dei campi, esamina i [prerequisiti](#prerequisites).
1. (Facoltativo) Se hai altri impegni del cliente che desideri includere, ripeti i passaggi precedenti.
   > [!div class="mx-imgBorder"]
   > ![Definire la relazione dell'entità](media/subscription-churn-customeractivitiesmapping.PNG "Pagina degli impegni dei clienti che mostra gli attributi semantici mappati ai campi nell'entità impegno del cliente selezionata")
1. Seleziona **Avanti**.

### <a name="set-schedule-and-review-configuration"></a>Impostare la pianificazione ed esaminare la configurazione

1. Imposta una frequenza per ripetere il training del modello. Questa impostazione è importante per aggiornare la precisione delle previsioni a mano a mano che i nuovi dati vengono inseriti in Audience Insights. La maggior parte delle aziende può ripetere il training una volta al mese e ottenere una buona precisione per le loro previsioni.
1. Seleziona **Avanti**.
1. Rivedi la configurazione. Puoi tornare a qualsiasi parte della configurazione di previsione selezionando **Modifica** sotto il valore mostrato. Oppure puoi selezionare un passaggio di configurazione dall'indicatore di avanzamento.
1. Se tutti i valori sono configurati correttamente, seleziona **Salva ed esegui** per iniziare il processo di previsione. Nella scheda **Le mie previsioni**, puoi vedere lo stato delle tue previsioni. Il completamento del processo potrebbe richiedere diverse ore a seconda della quantità di dati utilizzati nella previsione.

## <a name="review-a-prediction-status-and-results"></a>Rivedere lo stato e i risultati di una previsione

1. Vai alla scheda **Le mie previsioni** su **Intelligenza** > **Previsioni**.
   > [!div class="mx-imgBorder"]
   > ![Visualizzazione della pagina Le mie previsioni](media/subscription-churn-mypredictions.PNG "Visualizzazione della pagina Le mie previsioni")
1. Seleziona la previsione da rivedere.
   - **Nome della previsione:** il nome della previsione specificato durante la creazione.
   - **Tipo di previsione:** il tipo di modello utilizzato per la previsione
   - **Entità di output:** nome dell'entità per memorizzare l'output della previsione. Puoi trovare un'entità con questo nome su **Dati** > **Entità**.
   - **Campo previsione:** questo campo è popolato solo per alcuni tipi di previsioni e non viene utilizzato nella previsione di abbandono dell'abbonamento.
   - **Stato:** lo stato corrente dell'esecuzione della previsione.
        - **In coda:** la previsione è attualmente in attesa dell'esecuzione di altri processi.
        - **In aggiornamento:** la previsione sta attualmente eseguendo la fase di "valutazione" dell'elaborazione per produrre risultati che confluiranno nell'entità di output.
        - **Non riuscita:** la previsione non è stata completata. Seleziona **Registri** per altri dettagli.
        - **Completata:** la previsione è stata completata. Seleziona **Visualizza** sotto i puntini di sospensione verticali per rivedere la previsione
   - **Modificata:** la data in cui è stata modificata la configurazione per la previsione.
   - **Ultimo aggiornamento:** la data in cui sono stati aggiornati i risultati della previsione risulta nell'entità di output.
1. Seleziona i puntini di sospensione verticali accanto alla previsione per cui desideri esaminare i risultati e seleziona **Visualizza**.
   > [!div class="mx-imgBorder"]
   > ![Visualizzazione delle opzioni nel menu dei puntini di sospensione veriticali per una previsione che include modifica, aggiornamento, visualizzazione, registri ed eliminazione](media/subscription-churn-verticalellipses.PNG "Visualizzazione delle opzioni nel menu dei puntini di sospensione veriticali per una previsione che include modifica, aggiornamento, visualizzazione, registri ed eliminazione")
1. Esistono tre sezioni principali di dati nella pagina dei risultati:
    1. **Prestazioni del modello di training:** A, B o C sono possibili punteggi. Questo punteggio indica le prestazioni della previsione e può aiutarti a prendere la decisione di utilizzare i risultati archiviati nell'entità di output.
        - I punteggi sono determinati in base alle seguenti regole:
            - **A** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è maggiore del tasso di abbandono medio storico per almeno il 10% del tasso di abbandono medio storico.
            - **B** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è fino al 10% maggiore del tasso di abbandono medio storico.
            - **C** quando il modello ha previsto con precisione inferiore del 50% delle previsioni totali o quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è inferiore al tasso di abbandono medio storico.
               > [!div class="mx-imgBorder"]
               > ![Visualizzazione del risultato delle prestazioni del modello](media/subscription-churn-modelperformance.PNG "Visualizzazione del risultato delle prestazioni del modello")
    1. **Probabilità di abbandono (numero di clienti):** gruppi di clienti in base al rischio di abbandono previsto. Questi dati possono aiutarti in un secondo momento se desideri creare un segmento di clienti con elevato rischio di abbandono. Tali segmenti aiutano a capire dove dovrebbe posizionare il limite per l'appartenenza al segmento.
       > [!div class="mx-imgBorder"]
       > ![Grafico che mostra la distribuzione dei risultati di abbandono, suddivisi in intervalli da 0-100%](media/subscription-churn-resultdistribution.PNG "Grafico che mostra la distribuzione dei risultati di abbandono, suddivisi in intervalli da 0-100%")
    1. **Fattori più influenti:** esistono molti fattori che vengono presi in considerazione durante la creazione della previsione. Ciascuno dei fattori ha la sua importanza calcolata per le previsioni aggregate create da un modello. Puoi utilizzare questi fattori per convalidare i risultati della previsione. Oppure puoi utilizzare queste informazioni in seguito per [creare segmenti](segments.md) che potrebbero contribuire a influenzare il rischio di abbandono per i clienti.
       > [!div class="mx-imgBorder"]
       > ![Elenco che mostra i fattori influenti e la loro importanza nella previsione del risultato di abbandono](media/subscription-churn-influentialfactors.PNG "Elenco che mostra i fattori influenti e la loro importanza nella previsione del risultato di abbandono")

## <a name="fix-a-failed-prediction"></a>Correggere una previsione non riuscita

1. Vai alla scheda **Le mie previsioni** su **Intelligenza** > **Previsioni**.
1. Seleziona la previsione per la quale desideri visualizzare i registri degli errori e seleziona **Registri**.
   > [!div class="mx-imgBorder"]
   > ![Visualizzazione della barra dei menu dei risultati con chiusura, modifica del modello e pulsanti dei registri](media/subscription-churn-logsbutton.PNG "Visualizzazione della barra dei menu dei risultati con chiusura, modifica del modello e pulsanti dei registri")
1. Esamina tutti gli errori. Esistono diversi tipi di errori che possono verificarsi e descrivono quale condizione ha causato l'errore. Ad esempio, un errore indicante che non sono disponibili dati sufficienti per prevedere con precisione viene in genere risolto caricando dati aggiuntivi.

## <a name="refresh-a-prediction"></a>Aggiornare una previsione

Le previsioni si aggiorneranno automaticamente in base alla stessa [pianificazione di aggiornamento dei dati](system.md#schedule-tab) come configurato nelle impostazioni.

1. Vai alla scheda **Le mie previsioni** su **Intelligenza** > **Previsioni**.
1. Seleziona i puntini di sospensione verticali accanto alla previsione che vuoi aggiornare.
1. Seleziona **Aggiorna**.

## <a name="delete-a-prediction"></a>Eliminare una previsione

1. Vai alla scheda **Le mie previsioni** su **Intelligenza** > **Previsioni**.
1. Seleziona i puntini di sospensione verticali accanto alla previsione che vuoi eliminare.
1. Seleziona **Elimina.**

> [!NOTE]
> L'eliminazione di un previsione rimuoverà l'entità di output.
