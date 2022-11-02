---
title: Corrispondere le condizioni per l'unificazione dei dati
description: Metti in corrispondenza le entità per creare profili cliente unificati.
recommendations: false
ms.date: 10/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721526"
---
# <a name="match-conditions-for-data-unification"></a>Corrispondere le condizioni per l'unificazione dei dati

Questo passaggio nell'unificazione definisce l'ordine di corrispondenza e le regole per la corrispondenza tra entità. Questo passaggio richiede almeno due entità.

> [!NOTE]
> Dopo aver creato le condizioni di corrispondenza e selezionato **Avanti**, non è possibile rimuovere un'entità o un attributo selezionato. Se necessario, seleziona **Indietro** per rivedere le entità e gli attributi selezionati prima di continuare.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Includere entità arricchite (anteprima)

Se hai arricchito le entità a livello di origine dati per migliorare i risultati dell'unificazione, selezionale. Per altre informazioni, vedi [Arricchimento per le origini dati](data-sources-enrichment.md). Se hai selezionato entità arricchite nella pagina **Record duplicati**, non è necessario selezionarli nuovamente.

1. Nella pagina **Condizioni corrispondenti** seleziona **Utilizza entità arricchite** nella parte superiore della pagina.

1. Nel riquadro **Usa entità arricchite** scegli una o più entità arricchite.

1. Seleziona **Fatto**.

## <a name="specify-the-match-order"></a>Specificare l'ordine di corrispondenza

Ogni corrispondenza unifica due o più entità in un'unica entità consolidata. Allo stesso tempo, conserva i record del cliente univoci. L'ordine di corrispondenza indica l'ordine in cui il sistema tenta di abbinare i record.

> [!IMPORTANT]
> La prima entità è chiamata entità primaria, che serve da base per i profili unificati. Ulteriori entità selezionate verranno aggiunte a questa entità.
>
> Considerazioni importanti:
>
> - Scegli l'entità con i dati del profilo più completi e affidabili sui tuoi clienti come entità primaria.
> - Scegli l'entità che ha diversi attributi in comune con altre entità (ad esempio nome, numero di telefono o indirizzo e-mail) come entità primaria.

1. Nella pagina **Condizioni corrispondenti** usa le frecce di spostamento su e giù per spostare le entità nell'ordine desiderato oppure trascinale nella posizione desiderata. Ad esempio, seleziona **eCommerceCustomers** come entità primaria e **loyCustomers** come seconda entità.

1. Per avere ogni record nell'entità come un cliente univoco indipendentemente dal fatto che venga trovata una corrispondenza, seleziona **Includi tutti i record**. Tutti i record in questa entità che non corrispondono ai record in altre entità sono inclusi nel profilo unificato. I record che non hanno una corrispondenza sono chiamati singleton.
  
L'entità primaria *Contacts:eCommerce* è abbinata all'entità successiva *CustomerLoyalty:Loyalty*. Il set di dati che risulta dal primo passaggio di corrispondenza viene confrontato con l'entità seguente se hai più di due entità.

:::image type="content" source="media/m3_match.png" alt-text="Screenshot dell'ordine di corrispondenza selezionato per le entità." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definire le regole per le coppie di corrispondenze

Le regole di corrispondenza specificano la logica con cui verrà eseguita la corrispondenza per una specifica coppia di entità. Una regola è costituita da una o più condizioni.

L'avviso accanto al nome di un'entità indica che non è stata definita alcuna regola di corrispondenza per una coppia di corrispondenze.

1. Seleziona **Aggiungi regola** per una coppia di entità per definire le regole di corrispondenza.

1. Nel riquadro **Aggiungi regola** configura le condizioni per la regola.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Screenshot del riquadro Aggiungi regola.":::

   - **Seleziona Entità/Campo (prima riga)**: scegli un'entità e un attributo probabilmente univoci per un cliente. Ad esempio, un numero di telefono o un indirizzo e-mail. Evita la corrispondenza in base agli attributi del tipo di attività. Ad esempio, un ID acquisto probabilmente non troverà corrispondenze in altri tipi di record.

   - **Seleziona entità/campo (seconda riga)**: scegli un attributo correlato all'attributo dell'entità specificata nella prima riga.

   - **Normalizza**: Seleziona una delle seguenti opzioni di normalizzazione per gli attributi selezionati.
     - **Numeri**: converte altri sistemi numerici, come i numeri romani, in numeri arabi. *VIII* diventa *8*.
     - **Simboli**: rimuove tutti i simboli e i caratteri speciali. *Head&Shoulder* diventa *HeadShoulder*.
     - **Testo in minuscolo**: converte tutti i caratteri in minuscolo. *TUTTO MAIUSCOLO e titolo* diventa *tutto maiuscolo e titolo*.
     - **Tipo (telefono, nome, indirizzo, organizzazione)**: standardizza nomi, titoli, numeri di telefono, indirizzi e organizzazioni.
     - **Unicode in ASCII**: converte la notazione Unicode in caratteri ASCII. */u00B2* diventa *2*.
     - **Spazio vuoto**: rimuove tutti gli spazi. *Hello World* diventa *HelloWorld*.

   - **Precisione**: Consente di impostare il livello di precisione da applicare per questa condizione.
     - **Di base**: Scegli tra *Basso (30%)*, *Medio (60%)*, *Alto (80%)* ed *Esatto (100%)*. Seleziona **Esatto** per abbinare solo i record che corrispondono al 100 percento.
     - **Personalizzato**: Consente di impostare una percentuale per la corrispondenza dei record. Il sistema metterà in corrispondenza solo i record che superano questa soglia.

   - **Nome**: nome della regola.

1. Per abbinare le entità solo se gli attributi soddisfano più condizioni, seleziona **Aggiungi** > **Aggiungi condizione** per aggiungere più condizioni a una regola di corrispondenza. Le condizioni sono collegate a un operatore logico AND e quindi eseguite solo se tutte le condizioni sono soddisfatte.

1. Facoltativamente, considera opzioni avanzate come le [eccezioni](#add-exceptions-to-a-rule) o [condizioni di corrispondenza personalizzate](#specify-custom-match-conditions).

1. Seleziona **Fine** per finalizzare la regola.

1. Facoltativamente, [aggiungi altre regole](#add-rules-to-a-match-pair).

1. Fare clic su **Avanti**.

> [!div class="nextstepaction"]
> [Passaggio successivo: unifica i campi](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Aggiungere regole a una coppia di corrispondenze

Le regole di corrispondenza rappresentano set di condizioni. Per corrispondere le entità per condizioni in base a più attributi, aggiungi più regole.

1. Seleziona **Aggiungi regola** per l'entità a cui vuoi aggiungere le regole.

1. Segui i passaggi in [Definire le regole per le coppie di corrispondenze](#define-rules-for-match-pairs).

> [!NOTE]
> L'ordine delle regole è importante. L'algoritmo di corrispondenza tenta di abbinare un determinato record cliente in base alla prima regola e continua con la seconda regola solo se con la prima non è stata identificata alcuna corrispondenza.

## <a name="advanced-options"></a>Opzioni avanzate

### <a name="add-exceptions-to-a-rule"></a>Aggiungere eccezioni a una regola

Nella maggior parte dei casi, la corrispondenza delle entità porta a profili cliente univoci con dati consolidati. Per affrontare rari casi di falsi positivi e falsi negativi, puoi definire eccezioni per una regola di corrispondenza. Le eccezioni vengono applicate dopo l'elaborazione delle regole di corrispondenza ed evitano la corrispondenza di tutti i record, che soddisfano i criteri di eccezione.

Ad esempio, se la tua regola di corrispondenza combina cognome, città e data di nascita, il sistema identificherà i gemelli con lo stesso cognome che vivono nella stessa città con lo stesso profilo. Puoi specificare un'eccezione che non corrisponde ai profili se i nomi nelle entità combinate non sono gli stessi.

1. Nel riquadro **Modifica regola** seleziona **Aggiungi** > **Aggiungi eccezione**.

1. Specifica i criteri di eccezione.

1. Seleziona **Fatto** per salvare la regola.

### <a name="specify-custom-match-conditions"></a>Specificare le condizioni di corrispondenza personalizzate

Specifica le condizioni che sovrascrivono la logica di corrispondenza predefinita. Le opzioni disponibili sono quattro:

|Opzione  |Description |Esempio  |
|---------|---------|---------|
|Corrisponde sempre     | Definisce i valori per le chiavi primarie che corrispondono sempre.         |  Abbina sempre la riga con chiave primaria *12345* alla riga con chiave primaria *54321*.       |
|Mai nessuna corrispondenza     | Definisce i valori per le chiavi primarie che non corrispondono mai.        | Non abbinare mai la riga con chiave primaria *12345* alla riga con chiave primaria *54321*.        |
|Ignora            | Definisce i valori che il sistema deve sempre ignorare in fase di corrispondenza. |  Ignora i valori *11111* e *Sconosciuto* durante la corrispondenza.        |
|Mapping alias    | Definisce i valori che il sistema deve considerare come lo stesso valore.         | Considera *Joe* uguale a *Joseph*.        |

1. Seleziona **Personalizza**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Pulsante Personalizza":::

1. Scegli il **Tipo personalizzato** e seleziona **Scarica modello**. Rinomina il modello senza utilizzare spazi. Usa un modello separato per ogni opzione di corrispondenza.

1. Apri il file modello scaricato e inserisci i dettagli. Il modello contiene campi per specificare l'entità e i valori della chiave primaria dell'entità da utilizzare nella corrispondenza personalizzata. I nomi delle entità sono sensibili alla distinzione tra maiuscole e minuscole. Ad esempio, se desideri la chiave primaria *12345* dall'entità *Vendite* in modo che corrisponda sempre alla chiave primaria *34567* dall'entità *Contatto*, compila il modello:
   - Entity1: Vendite
   - Entity1Key: 12345
   - Entity2: Contatto
   - Entity2Key: 34567

   Lo stesso file di modello può specificare record di corrispondenza personalizzati da più entità.

   > [!NOTE]
   > Se desideri specificare la corrispondenza personalizzata per la deduplicazione in un'entità, fornisci la stessa entità sia come Entità1 che Entità2 e imposta i diversi valori di chiave primaria. È necessario definire almeno una regola di deduplicazione per l'entità per utilizzare la corrispondenza personalizzata.

1. Dopo aver aggiunto tutte le sostituzioni, salva il file di modello.

1. Vai a **Dati** > **Origini dati** e inserisci i file di modello come nuove entità.

1. Dopo aver caricato i file, seleziona nuovamente l'opzione **Personalizza**. Seleziona le entità richieste nel menu a discesa e seleziona **Fatto**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Screenshot della finestra di dialogo per scegliere le sostituzioni per uno scenario di corrispondenza personalizzata.":::

1. L'applicazione della corrispondenza personalizzata dipende dall'opzione di corrispondenza da utilizzare.

   - Per **Corrisponde sempre** o **Mai nessuna corrispondenza**, continua con il passaggio successivo.
   - Per **Ignora** o **Mapping alias**, seleziona **Modifica** su una regola di corrispondenza esistente o crea una nuova regola. Nel menu a discesa Normalizzazione scegli l'opzione **Ignora personalizzato** o **Mapping alias** e seleziona **Fatto**.

1. Seleziona **Fine** nel riquadro **Personalizza** per applicare la configurazione di corrispondenza personalizzata.

   Ogni file modello inserito è la propria origine dati. Se vengono rilevati record che richiedono un trattamento di corrispondenza speciale, aggiorna l'origine dati appropriata. L'aggiornamento verrà utilizzato durante il successivo processo di unificazione. Ad esempio, identifichi gemelli quasi con lo stesso nome che vivono allo stesso indirizzo che erano stati uniti in una sola persona. Aggiorna l'origine dati per identificare i gemelli come record separati e univoci.

> [!div class="nextstepaction"]
> [Passaggio successivo: unifica i campi](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
