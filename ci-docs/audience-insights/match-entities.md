---
title: Mettere in corrispondenza le entità per l'unificazione dei dati
description: Metti in corrispondenza le entità per creare profili cliente unificati.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7ad08b8b782654939c6bfc2ca330a3d31e71054a2f2c97a921971d1056b7cd38
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033682"
---
# <a name="match-entities"></a>Mettere in corrispondenza le entità

La fase di corrispondenza specifica in che modo combinare i set di dati in un profilo cliente unificato. Dopo aver completato il [passaggio della mappa](map-entities.md) nel processo di unificazione dei dati, sei pronto per corrispondere le tue entità. La fase di corrispondenza richiede almeno due entità mappate.

La pagina della corrispondenza è composta da tre sezioni: 
- Metriche chiave che riepilogano il numero di record corrispondenti
- Ordine di corrispondenza e regole per la corrispondenza tra entità
- Regole per la deduplicazione delle entità di corrispondenza

## <a name="specify-the-match-order"></a>Specificare l'ordine di corrispondenza

Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Definisci l'ordine** per iniziare la fase di corrispondenza.

Ogni corrispondenza unifica due o più entità in un'unica entità consolidata. Allo stesso tempo, conserva i record del cliente univoci. Ad esempio, abbiamo selezionato due entità: **eCommerce:eCommerceContacts** come entità primaria e **LoyaltyScheme: loyCustomers** come seconda entità. L'ordine delle entità specifica in quale ordine il sistema tenterà di corrispondere i record.

:::image type="content" source="media/match-page.png" alt-text="Screenshot della pagina Corrispondenza nell'area Unifica del processo di unificazione dei dati.":::
  
L'entità primaria *eCommerce: eCommerceContacts* è corrisposta all'entità successiva *LoyaltyScheme: loyCustomers*. Il set di dati che risulta dal primo passaggio di corrispondenza viene corrisposto alla seguente entità se hai più di due entità.

> [!IMPORTANT]
> L'entità che scegli come tua entità primaria servirà come base per il set di dati profili unificato. Altre entità selezionate durante la fase di corrispondenza verranno aggiunte a questa entità. Ciò non significa che l'entità unificata includerà *tutti* i dati inclusi in questa entità.
>
> Esistono due considerazioni che possono aiutarti a scegliere la gerarchia delle entità:
>
> - Scegli l'entità con i dati di profilo più completi e affidabili sui tuoi clienti come entità principale.
> - Scegli l'entità che ha diversi attributi in comune con altre entità (ad esempio, nome, numero di telefono o indirizzo e-mail) come entità principale.

Dopo aver specificato l'ordine di corrispondenza, vedrai le coppie di corrispondenze definite nella sezione **Dettagli record corrispondenti** in **Dati** > **Unifica** > **Corrispondenza**. Le metriche chiave saranno vuote fino al completamento del processo di corrispondenza.

## <a name="define-rules-for-match-pairs"></a>Definire le regole per le coppie di corrispondenze

Le regole di corrispondenza specificano la logica con cui verrà eseguita la corrispondenza per una specifica coppia di entità.

L'avviso **Necessita regole** accanto al nome di un'entità suggerisce che non è stata definita alcuna regola di corrispondenza per una coppia di corrispondenze. 

:::image type="content" source="media/match-rule-add.png" alt-text="Screenshot della sezione Dettagli record corrispondenti con il controllo per aggiungere regole evidenziato.":::

1. Seleziona **Aggiungi regole** sotto un'entità nella sezione **Dettagli record corrispondenti** per definire le regole di corrispondenza.

1. Nel riquadro **Crea regola**, configura le condizioni per la regola.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Screenshot di una regola di corrispondenza aperta con condizioni aggiunte.":::

   - **Entità/Campo (prima riga)**: Scegli un'entità correlata e un attributo per specificare una proprietà del record che è probabilmente univoca per un cliente. Ad esempio, un numero di telefono o un indirizzo e-mail. Evita la corrispondenza in base agli attributi del tipo di attività. Ad esempio, un ID acquisto probabilmente non troverà corrispondenze in altri tipi di record.

   - **Entità/Campo (seconda riga)**: Scegli un attributo correlato all'attributo dell'entità specificata nella prima riga.

   - **Normalizza**: Seleziona una delle seguenti opzioni di normalizzazione per gli attributi selezionati. 
     - Spazio vuoto: rimuove tutti gli spazi. *Hello World* diventa *HelloWorld*.
     - Simboli: rimuove tutti i simboli e i caratteri speciali. *Head&Shoulder* diventa *HeadShoulder*.
     - Testo in minuscolo: converte tutti i caratteri in minuscolo. *TUTTO MAIUSCOLO e titolo* diventa *tutto maiuscolo e titolo*.
     - Unicode in ASCII: converte la notazione Unicode in caratteri ASCII. */u00B2* diventa *2*.
     - Numeri: converte altri sistemi numerici, come i numeri romani, in numeri arabi. *VIII* diventa *8*.
     - Tipi semantici: standardizza nomi, titoli, numeri di telefono, indirizzi, ecc. 

   - **Precisione**: Consente di impostare il livello di precisione da applicare per questa condizione. 
     - **Di base**: Scegli tra *Basso*, *Medio*, *Alto* ed *Esatto*. Seleziona **Esatta** per mettere in corrispondenza solo i record corrispondenti al 100 per cento. Seleziona uno degli altri livelli per mettere in corrispondenza i record che non sono identici al 100 per cento.
     - **Personalizzato**: Consente di impostare una percentuale per la corrispondenza dei record. Il sistema metterà in corrispondenza solo i record che superano questa soglia.

1. Fornisci un **nome** per la regola.

1. [Aggiungi altre condizioni](#add-conditions-to-a-rule) oppure seleziona **Fatto** per finalizzare la regola.

1. Facoltativamente, [aggiungi altre regole](#add-rules-to-a-match-pair).

1. Seleziona **Salva** per applicare le modifiche.

### <a name="add-conditions-to-a-rule"></a>Aggiungere le condizioni a una regola

Per corrispondere le entità solo se gli attributi soddisfano più condizioni, aggiungi più condizioni a una regola di corrispondenza. Le condizioni sono collegate a un operatore logico AND e quindi eseguite solo se tutte le condizioni sono soddisfatte.

1. Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Modifica** nella regola a cui vuoi aggiungere condizioni.

1. Nel riquadro **Modifica regola**, seleziona **Aggiungi condizione**.

1. Seleziona **Fatto** in modo da salvare la regola.

### <a name="add-rules-to-a-match-pair"></a>Aggiungere regole a una coppia di corrispondenze

Le regole di corrispondenza rappresentano set di condizioni. Per corrispondere le entità per condizioni in base a più attributi, aggiungi più regole.

1.  Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Aggiungi regola** nell'entità a cui vuoi aggiungere regole.

2. Segui i passaggi in [Definire le regole per le coppie di corrispondenze](#define-rules-for-match-pairs).

> [!NOTE]
> L'ordine delle regole è importante. L'algoritmo di corrispondenza tenta di mettere in corrispondenza sulla base della prima regola e continua con la seconda regola solo se non sono state identificate corrispondenze con la prima regola.

### <a name="change-the-entity-order-in-match-rules"></a>Modificare l'ordine delle entità nelle regole di corrispondenza

Puoi riordinare le entità per le regole di corrispondenza per modificare l'ordine in cui vengono elaborate. Le regole in conflitto a causa di un ordine modificato verranno rimosse. Devi ricreare le regole rimosse con una configurazione aggiornata.

1. Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Modifica**.

1. Nel riquadro **Modifica regola** seleziona il controllo **Sposta su/giù** o trascina e rilascia le entità per modificare l'ordine.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opzioni per modificare l'ordine in cui le entità vengono elaborate nella fase di corrispondenza.":::

1. Seleziona **Fatto** in modo da salvare la regola.

## <a name="define-deduplication-on-a-match-entity"></a>Definire la deduplicazione in un'entità di corrispondenza

Oltre alle [regole di corrispondenza tra entità](#define-rules-for-match-pairs), puoi specificare le regole di deduplicazione. La *deduplicazione* è un altro processo della corrispondenza dei record. Identifica i record duplicati e li unisce in un unico record. I record di origine vengono collegati al record unito con ID alternativi.

I record deduplicati verranno usati nel processo di corrispondenza tra entità. La deduplicazione avviene su singole entità e può essere configurata per ogni entità usata nelle coppie di corrispondenza.

Non è obbligatorio specificare regole di deduplicazione. Se tali regole non vengono configurate, verranno applicate le regole definite dal sistema. Combinano tutti i record in un unico record prima di passare i dati dell'entità alla corrispondenza tra entità per migliorare le prestazioni.

### <a name="add-deduplication-rules"></a>Aggiungere regole di deduplicazione

1. Vai a **Dati** > **Unifica** > **Corrispondenza**.

1. Nella sezione **Duplicati uniti**, seleziona **Imposta entità**. Nel caso in cui le regole di deduplicazione siano già state create, seleziona **Modifica**.

1. Nel riquadro **Preferenze di unione**, seleziona le entità in cui desideri eseguire la deduplicazione.

1. Specifica come combinare i record duplicati e scegli una delle tre opzioni:
   - **Con più dati**: identifica il record con i campi di attributo con più dati come record vincitore. È l'opzione di unione predefinita.
   - **Piu recente**: il record vincitore è quello più recente. Richiede una data o un campo numerico per definire la recency.
   - **Meno recente**: il record vincitore è quello meno recente. Richiede una data o un campo numerico per definire la recency.
 
   > [!div class="mx-imgBorder"]
   > ![Passaggio 1 delle regole di deduplicazione.](media/match-selfconflation.png "Passaggio 1 delle regole di deduplicazione")
 
1. Una volta selezionate le entità e impostata la relativa preferenza di unione, seleziona **Aggiungi regola** per definire le regole di deduplicazione a livello di entità.
   - **Seleziona campo** elenca tutti i campi disponibili da quell'entità. Scegli il campo in cui desideri verificare la presenza di duplicati. Scegli campi che sono probabilmente univoci per ogni singolo cliente. Ad esempio, un indirizzo e-mail o la combinazione di nome, città e numero di telefono.
   - Specifica le impostazioni di normalizzazione e precisione.
   - Definisci più condizioni aggiuntive selezionando **Aggiungi condizione**.
 
   > [!div class="mx-imgBorder"]
   > ![Passaggio 2 delle regole di deduplicazione.](media/match-selfconflation-rules.png "Passaggio 2 delle regole di deduplicazione")

  Puoi creare molteplici regole di deduplicazione per un'entità. 

1. L'esecuzione del processo di corrispondenza ora raggruppa i record in base alle condizioni definite nelle regole di deduplicazione. Dopo aver raggruppato i record, i criteri di unione vengono applicati per identificare il record vincitore.

1. Questo record vincitore viene quindi passato alla corrispondenza tra entità, insieme ai record non vincitori (ad esempio, ID alternativi) per migliorare la qualità della corrispondenza.

1. Qualsiasi regola di corrispondenza personalizzata definita sovrascrive le regole di deduplicazione. Se una regola di deduplicazione identifica i record corrispondenti e una regola di corrispondenza personalizzata è impostata per non corrispondere mai a tali record, questi due record non corrisponderanno.

1. Dopo l'[esecuzione del processo di corrispondenza](#run-the-match-process), vedrai le statistiche di deduplicazione nei riquadri delle metriche chiave.

### <a name="deduplication-output-as-an-entity"></a>Output di deduplicazione come entità

Il processo di deduplicazione crea una nuova entità per ogni entità dalle coppie di corrispondenza per identificare i record deduplicati. Queste entità possono essere trovate insieme a **ConflationMatchPairs:CustomerInsights** nella sezione **Sistema** della pagina **Entità**, con il nome **Deduplication_DataSource_Entity**.

Un'entità di output della deduplicazione contiene le seguenti informazioni:
- ID/chiavi
  - Campo chiave primaria e relativo campo ID alternativo. Il campo ID alternativo è costituito da tutti gli ID alternativi identificati per un record.
  - Il campo Deduplication_GroupId mostra il gruppo o il cluster identificato all'interno di un'entità che raggruppa tutti i record simili in base ai campi di deduplicazione specificati. È utilizzato per scopi di elaborazione del sistema. Se non sono state specificate regole di deduplicazione manuale e si applicano regole di deduplicazione definite dal sistema, potresti non trovare questo campo nell'entità di output della deduplicazione.
  - Deduplication_WinnerId: questo campo contiene l'ID vincitore dei gruppi o cluster identificati. Se Deduplication_WinnerId è uguale al valore della chiave primaria per un record, significa che il record è il record vincitore.
- Campi utilizzati per definire le regole di deduplicazione.
- I campi Regola e Punteggio per indicare quale delle regole di deduplicazione è stata applicata e il punteggio restituito dall'algoritmo di corrispondenza.
   
## <a name="run-the-match-process"></a>Eseguire il processo di corrispondenza

Con le regole di corrispondenza configurate, inclusa la corrispondenza tra entità e le regole di deduplicazione, puoi eseguire il processo di corrispondenza. 

Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Esegui** per avviare il processo. L'algoritmo di corrispondenza richiede un po' di tempo per essere completato e non è possibile modificare la configurazione fino al completamento. Per apportare modifiche puoi annullare l'esecuzione. Seleziona lo stato del processo e seleziona **Annulla processo** nel riquadro **Dettagli stato**.

Troverai il risultato di un'esecuzione completata, l'entità profilo del cliente unificata, nella pagina **Entità**. La tua entità cliente unificata è chiamata **Clienti** nella sezione **Profili**. La prima esecuzione di una corrispondenza completata crea l'entità *Cliente*. Tutte le esecuzioni di corrispondenza successive espandono quell'entità.

> [!TIP]
> Dopo aver eseguito il processo di unione, seleziona lo stato del processo per aprire il riquadro **Dettagli attività**. Fornisce una panoramica del tempo di elaborazione, della data dell'ultima elaborazione e di tutti gli errori e gli avvisi associati all'attività. Seleziona **Vedi dettagli** per vedere quali entità hanno partecipato al processo di unione, e cui regole sono state applicate, se la risoluzione del conflitto è riuscita e se gli aggiornamenti sono stati pubblicati correttamente.  
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Percorso di drill-down per ottenere i dettagli dell'elaborazione dal collegamento sullo stato dell'attività.":::

## <a name="review-and-validate-your-matches"></a>Rivedere e convalidare le corrispondenze

Vai a **Dati** > **Unifica** > **Corrispondenza** per valutare la qualità delle tue coppie di corrispondenza e perfezionarle se necessario.

I riquadri nella parte superiore della pagina mostrano le metriche chiave, riepilogando il numero di record e duplicati corrispondenti.

:::image type="content" source="media/match-KPIs.png" alt-text="Screenshot ritagliato delle metriche chiave nella pagina Corrispondenza con numeri e dettagli.":::

- **Record di origine univoci** mostra il numero di record di origine individuali che sono stati elaborati nell'ultima esecuzione della corrispondenza.
- **Record corrispondenti e non corrispondenti** evidenzia quanti record univoci rimangono dopo l'elaborazione delle regole di corrispondenza.
- **Solo record corrispondenti** mostra il numero di corrispondenze in tutte le coppie di corrispondenza.

Puoi valutare i risultati di ogni coppia e le sue regole nella tabella **Dettagli record corrispondenti**. Confronta il numero di record provenienti da una coppia di corrispondenze con la percentuale di record con corrispondenza riuscita.

Rivedi le regole di una coppia di corrispondenze per vedere la percentuale di record corrispondenti completati a livello di regola. Seleziona i puntini di sospensione (...) e quindi seleziona **Anteprima corrispondenza** per visualizzare tutti questi record a livello di regola. Ti consigliamo di dare un'occhiata ad alcuni record per verificare che siano stati corrisposti correttamente.

Prova diverse soglie di precisione sulle condizioni per trovare il valore ottimale.

  1. Seleziona i puntini di sospensione (...) per la regola che desideri sperimentare e seleziona **Modifica**.

  2. Modifica i valori di precisione nelle condizioni che desideri rivedere.

  3. Seleziona **Anteprima** quindi vedi il numero di record corrisposti e non corrisposti per la condizione selezionata.

## <a name="manage-match-rules"></a>Gestire le regole di corrispondenza

Puoi riconfigurare e ottimizzare la maggior parte dei parametri di corrispondenza.

:::image type="content" source="media/match-rules-management.png" alt-text="Screenshot del menu a discesa con le opzioni della regola di corrispondenza.":::

- **Modifica l'ordine delle tue regole** se hai definito più regole. Puoi riordinare le regole di corrispondenza selezionando le opzioni **Sposta su** e **Sposta giù** o tramite trascinamento.

- **Modifica le condizioni della regola** selezionando **Modifica** e scegliendo campi diversi.

- **Disattiva una regola** per mantenere una regola di corrispondenza pur escludendola dal processo di corrispondenza.

- **Duplica le tue regole** se hai definito una regola di corrispondenza e desideri creare una regola simile con modifiche, seleziona **Duplica**.

- **Elimina una regola** selezionando il simbolo **Elimina**.

## <a name="specify-custom-match-conditions"></a>Specificare le condizioni di corrispondenza personalizzate

Puoi specificare condizioni in base a cui alcuni record devono sempre corrispondere o non corrispondere mai. Queste regole possono essere caricate per sostituire il processo di corrispondenza standard. Ad esempio, se nei nostri record sono presenti John Doe I e John Doe II, il sistema potrebbe abbinarli come una singola persona. Le regole di corrispondenza personalizzate ti consentono di specificare che i loro profili si riferiscono a persone diverse. 

1. Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Corrispondenza personalizzata** nella sezione **Dettagli record corrispondenti**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Screenshot della sezione delle regole di corrispondenza con il controllo per la corrispondenza personalizzata evidenziato.":::

1. Se non hai impostato regole di corrispondenza personalizzate, vedrai un nuovo riquadro **Corrispondenza personalizzata** con maggiori dettagli.

1. Seleziona **Compila il modello** per ottenere un file modello che può specificare quali record da quali entità devono sempre corrispondere o non corrispondere mai. Dovrai compilare separatamente i record "Corrisponde sempre" e "Mai nessuna corrispondenza" in due file diversi.

1. Il modello contiene campi per specificare l'entità e i valori della chiave primaria dell'entità da utilizzare nella corrispondenza personalizzata. Ad esempio, se desideri la chiave primaria *12345* dall'entità *Vendite* in modo che corrisponda sempre alla chiave primaria *34567* dall'entità *Contatto*, compila il modello:
    - Entity1: Vendite
    - Entity1Key: 12345
    - Entity2: Contatto
    - Entity2Key: 34567

   Lo stesso file di modello può specificare record di corrispondenza personalizzati da più entità.
   
   Se desideri specificare la corrispondenza personalizzata per la deduplicazione in un'entità, fornisci la stessa entità sia come Entità1 che Entità2 e imposta i diversi valori di chiave primaria.

1. Dopo aver aggiunto tutte le sostituzioni che vuoi applicare, salva il file del modello.

1. Vai a **Dati** > **Origini dati** e inserisci i file di modello come nuove entità. Una volta inseriti, puoi usarli per specificare la configurazione della corrispondenza.

1. Dopo aver caricato i file e le entità disponibili, seleziona nuovamente l'opzione **Corrispondenza personalizzata**. Vedrai le opzioni per specificare le entità che desideri includere. Seleziona le entità richieste dal menu a discesa.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Screenshot della finestra di dialogo per scegliere le sostituzioni per uno scenario di corrispondenza personalizzata.":::

1. Seleziona le entità che desideri utilizzare per **Corrisponde sempre** e **Mai nessuna corrispondenza**, quindi seleziona **Fatto**.

1. Seleziona **Salva** nella pagina **Corrispondenza** per applicare la configurazione di corrispondenza personalizzata.

1. Seleziona **Esegui** nella pagina **Corrispondenza** per avviare il processo di corrispondenza. Altre regole di corrispondenza specificate vengono sovrascritte dalla configurazione di corrispondenza personalizzata.

> [!TIP]
> Vai a **Dati** > **Entità** e rivedi l'entità **ConflationMatchPair** per verificare che le sostituzioni siano state applicate.

## <a name="next-step"></a>Passaggio successivo

Dopo aver completato il processo di corrispondenza per almeno una coppia di corrispondenza, puoi risolvere eventuali contraddizioni nei tuoi dati esaminando l'argomento [**Unione**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
