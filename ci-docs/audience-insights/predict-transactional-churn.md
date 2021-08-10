---
title: Previsione di abbandono transazionale
description: Determina se esiste il rischio che un cliente non acquisti più i tuoi prodotti o servizi.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 28c89693239393d93b7a816535b8c3fffe353935
ms.sourcegitcommit: e57d51ae3cc233f7b6185c074c66efd9800c02c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "6559410"
---
# <a name="transactional-churn-prediction-preview"></a>Previsione di abbandono transazionale (anteprima)

La previsione di abbandono transazionale ti consente di prevedere se un cliente non acquisterà più i tuoi prodotti o servizi in un determinato intervallo di tempo. Puoi creare nuove previsioni di abbandono in **Intelligenza** > **Previsioni**. Seleziona **Le mie previsioni** per visualizzare altre previsioni che hai creato.

> [!TIP]
> Prova l'esercitazione per una previsione di abbandono transazionale utilizzando dati di esempio: [Guida di esempio per una previsione di abbandono transazionale (anteprima)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Prerequisiti

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.
- Conoscenza dell'azienda per capire cosa significa abbandono per la tua azienda. Supportiamo definizioni di abbandono basate sul tempo, ovvero un cliente è considerato come perso dopo un periodo sena acquisti.
- Dati su transazioni/acquisti e la relativa cronologia:
    - Identificatori di transazione per distinguere acquisti/transazioni.
    - Identificatori di cliente per abbinare le transazioni ai clienti.
    - Date dell'evento di transazione, che definiscono le date in cui è avvenuta la transazione.
    - Lo schema dei dati semantici per acquisti/transazioni richiede le seguenti informazioni:
        - **ID transazione:** un identificatore univoco di un acquisto o di una transazione.
        - **Data transazione:** la data dell'acquisto o della transazione.
        - **Valore della transazione:** l'importo in valuta/valore numerico della transazione/articolo.
        - (Facoltativo) **ID prodotto univoco:** l'ID del prodotto o del servizio acquistato se i tuoi dati sono a livello di voce singola.
        - (Facoltativo) **Specifica se la transazione era un reso:** un campo vero/falso che identifica se la transazione era o menu un reso. Se il **Valore della transazione** è negativo, useremo queste informazioni per dedurre un reso.
- (Facoltativo) Dati sugli impegni del cliente:
    - Identificatori di impegni per distinguere gli impegni dello stesso tipo.
    - Identificativi del cliente per mappare gli impegni ai clienti.
    - Informazioni sull'impegno contenenti il nome e la data dell'impegno.
    - Lo schema di dati semantici per gli impegni dei clienti include:
        - **Chiave primaria:** l'identificatore univoco per un impegno. Ad esempio, una visita al sito Web o un record di utilizzo che mostra che il cliente ha provato un campione del prodotto.
        - **Timestamp:** la data e l'ora dell'evento identificato dalla chiave primaria.
        - **Evento:** il nome dell'evento che si desidera utilizzare. Ad esempio, un campo denominato "UserAction" in un negozio di alimentari potrebbe essere un coupon utilizzato dal cliente.
        - **Dettagli:** informazioni dettagliate sull'evento. Ad esempio, un campo denominato "CouponValue" in un negozio di alimentari potrebbe essere il valore monetario del coupon.
- Caratteristiche dei dati consigliate:
    - Dati storici sufficienti: dati di transazione per almeno il doppio della finestra temporale selezionata. Preferibilmente, due o tre anni di cronologia delle transazioni. 
    - Acquisti multipli per cliente: idealmente almeno due transazioni per cliente.
    - Numero di clienti: almeno 10 profili cliente, preferibilmente più di 1.000 clienti univoci. Il modello non riesce con meno di 10 clienti e dati storici insufficienti.
    - Completezza dei dati: meno del 20% dei valori mancanti nel campo dati dell'entità fornita.

> [!NOTE]
> Per un'azienda con un'elevata frequenza di acquisto da parte dei clienti (ogni poche settimane) si consiglia di selezionare una finestra di previsione e una definizione di abbandono più brevi. Per una bassa frequenza di acquisto (ogni pochi mesi o una volta all'anno), scegli una finestra di previsione e una definizione di abbandono più lunghe.

## <a name="create-a-transactional-churn-prediction"></a>Creare una previsione di abbandono transazionale

1. In Customer Insights, vai a **Intelligence** > **Previsioni**.

1. Seleziona il riquadro **Modello di abbandono dei cliente (anteprima)** e seleziona **Utilizza questo modello**.
   
1. Nel riquadro **Modello di abbandono dei clienti**, scegli **Transazionale** e seleziona **Inizia**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Screenshot con l'opzione transazionale selezionata nel riquadro Modello di abbandono dei clienti.":::

### <a name="name-model"></a>Assegna nome a modello

1. Specifica un nome per il modello per distinguerlo dagli altri modelli.

1. Specifica un nome per l'entità di output utilizzando solo lettere e numeri, senza spazi. Questo è il nome che verrà utilizzato dall'entità modello. 

1. Seleziona **Avanti**.

### <a name="define-customer-churn"></a>Definisci abbandono cliente

1. Imposta un periodo in giorni per la previsione dell'abbandono nel campo **Identifica i clienti che potrebbero abbandonare nei prossimi/nelle prossime**. Ad esempio, prevedi il rischio di abbandono dei clienti nei prossimi 90 giorni per allinearti agli sforzi di fidelizzazione del marketing. La previsione del rischio di abbandono per un periodo di tempo più o meno lungo può rendere più difficile prendere in considerazione i fattori nel profilo di rischio di abbandono, ma dipende dalle esigenze aziendali specifiche. 
   >[!TIP]
   > Puoi selezionare **Salva e chiudi** in qualsiasi momento per salvare la previsione come bozza. La previsione della bozza è disponibile nella scheda **Le mie previsioni** per continuare.

1. Immetti il numero di giorni per definire l'abbandono nel campo **Un cliente ha abbandonato se non ha effettuato alcun acquisto per**. Ad esempio, se un cliente non ha effettuato acquisti negli ultimi 30 giorni, potrebbe essere considerato come perso per la tua attività. 

1. Seleziona **Avanti** per continuare

### <a name="add-required-data"></a>Aggiungi dati obbligatori

1. Seleziona **Aggiungi dati** in **Cronologia acquisti** e scegli l'entità che fornisce le informazioni sulla cronologia di transazioni/acquisti come descritto nei [prerequisiti](#prerequisites).

1. Esegui il mapping dei campi semantici agli attributi nell'entità della cronologia degli acquisti e seleziona **Avanti**. Per le descrizioni dei campi, esamina i [prerequisiti](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Eseguire il mapping dei campi semantici dell'entità di acquisto.":::

1. Se i campi seguenti non sono popolati, configura la relazione tra l'entità della cronologia degli acquisti e l'entità Cliente.
    1. Seleziona **Entità cronologia acquisti**.
    1. Seleziona il **campo** che identifica il cliente nell'entità della cronologia degli acquisti. Deve essere correlato all'ID cliente primario dell'entità Cliente.
    1. Seleziona l'**Entità cliente** che corrisponde all'entità cliente primaria.
    1. Immetti un nome che descrive la relazione.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pagina della cronologia degli acquisti che mostra la creazione di una relazione con il cliente.":::
   
1. Seleziona **Avanti**.

1. Facoltativamente, seleziona **Aggiungi dati** in **Impegni cliente**. Scegli l'entità che fornisce le informazioni sugli impegni del cliente come descritto nei prerequisiti.

1. Esegui il mapping dei campi semantici agli attributi nell'entità degli impegni del cliente e seleziona **Avanti**. Per le descrizioni dei campi, esamina i [prerequisiti](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Mapping dei campi dei clienti per i dati transazionali.":::

1. Seleziona un tipo di impegno corrispondente al tipo di impegno del cliente che stai configurando. Seleziona **Creare nuovo** e scegli un tipo di impegno disponibile o creane uno.

1. Dovrai configurare la relazione dall'entità impegno del cliente con l'entità cliente.
    1. Seleziona il campo che identifica il cliente nella tabella degli impegni del cliente. Può essere correlato direttamente all'ID cliente principale dell'entità Cliente.
    1. Seleziona l'entità cliente che corrisponde all'entità cliente primaria
    1. Immetti un nome che descrive la relazione.

1. Seleziona **Salva**.

1. Se hai altri impegni dei clienti che desideri includere, ripeti i passaggi precedenti.

1. Seleziona **Avanti**.

### <a name="set-schedule-and-review-configuration"></a>Impostare la pianificazione ed esaminare la configurazione

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
     Non tutti i clienti sono necessariamente clienti attivi. Alcuni di loro potrebbero non aver avuto alcun impegno per molto tempo e sono già considerati come abbandonati, in base alla tua definizione di abbandono. Prevedere il rischio di abbandono per i clienti che hanno già abbandonato non è utile perché non sono i destinatari di interesse.
   - **Campo previsione:** questo campo viene popolato solo per alcuni tipi di previsioni e non viene utilizzato nella previsione di abbandono.
   - **Stato:** lo stato dell'esecuzione della previsione.
        - **In coda:** la previsione attende l'esecuzione di altri processi.
        - **Aggiornamento in corso:** la previsione è attualmente in esecuzione per produrre risultati che verranno inseriti nell'entità di output.
        - **Errore:** l'esecuzione della previsione non è riuscita. [Esamina i log](manage-predictions.md#troubleshoot-a-failed-prediction) per maggiori informazioni.
        - **Completata:** la previsione è riuscita. Seleziona **Visualizza** sotto i puntini di sospensione verticali per rivedere la previsione
   - **Modificata:** la data in cui è stata modificata la configurazione per la previsione.
   - **Ultimo aggiornamento:** la data in cui sono stati aggiornati i risultati della previsione risulta nell'entità di output.

1. Seleziona i puntini di sospensione verticali accanto alla previsione per cui desideri esaminare i risultati e seleziona **Visualizza**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Controllo Visualizza per visualizzare i risultati di un previsione.":::   

1. Esistono tre sezioni principali di dati nella pagina dei risultati:
    1. **Prestazioni del modello di training:** A, B o C sono possibili punteggi. Questo punteggio indica le prestazioni della previsione e può aiutarti a prendere la decisione di utilizzare i risultati archiviati nell'entità di output. I punteggi sono determinati in base alle seguenti regole:
         
         - **A** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è superiore al tasso di riferimento di almeno il 10%.
            
         - **B** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è fino al 10% superiore al tasso di riferimento.
            
         - **C** quando il modello ha previsto con precisione meno del 50% delle previsioni totali o quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è inferiore al tasso di riferimento.
               
         - **Riferimento** considera l'input dell'intervallo di tempo di previsione per il modello (ad esempio, un anno) e il modello crea diverse frazioni di tempo dividendolo per 2 fino a che non si ottiene un mese o meno. Utilizza queste frazioni per creare una regola aziendale per i clienti che non hanno effettuato acquisti durante tale periodo di tempo. Questi clienti vengono considerati come persi. La regola di business basata sul tempo con la più alta capacità di prevedere chi può abbandonare viene scelta come modello di riferimento.
            
    1. **Probabilità di abbandono (numero di clienti):** gruppi di clienti in base al rischio di abbandono previsto. Questi dati possono aiutarti in un secondo momento se desideri creare un segmento di clienti con elevato rischio di abbandono. Tali segmenti aiutano a capire dove dovrebbe posizionare il limite per l'appartenenza al segmento.
       
    1. **Fattori più influenti:** esistono molti fattori che vengono presi in considerazione durante la creazione della previsione. Ciascuno dei fattori ha la sua importanza calcolata per le previsioni aggregate create da un modello. Puoi utilizzare questi fattori per convalidare i risultati della previsione. Oppure puoi utilizzare queste informazioni in seguito per [creare segmenti](segments.md) che potrebbero contribuire a influenzare il rischio di abbandono per i clienti.

## <a name="manage-predictions"></a>Gestisci previsioni

È possibile ottimizzare, risolvere i problemi, aggiornare o eliminare le previsioni. Esamina un report sull'usabilità dei dati di input per scoprire come rendere un previsione più veloce e affidabile. Per ulteriori informazioni, vedi [Gestisci previsioni](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
