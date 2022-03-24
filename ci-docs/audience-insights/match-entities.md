---
title: Mettere in corrispondenza le entità per l'unificazione dei dati
description: Metti in corrispondenza le entità per creare profili cliente unificati.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: ab4ab0dba1bd91b1893cd4b16b8d51381d5b6ef8
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376927"
---
# <a name="match-entities"></a>Mettere in corrispondenza le entità

La fase di corrispondenza specifica in che modo combinare i set di dati in un profilo cliente unificato. Dopo aver completato il [passaggio della mappa](map-entities.md) nel processo di unificazione dei dati, sei pronto per corrispondere le tue entità. La fase di corrispondenza richiede almeno due entità mappate.

La pagina della corrispondenza è composta da tre sezioni: 
- Metriche chiave che riepilogano il numero di record corrispondenti
- Ordine di corrispondenza e regole per la corrispondenza tra entità
- Regole per la deduplicazione delle entità di corrispondenza

## <a name="specify-the-match-order"></a>Specificare l'ordine di corrispondenza

Ogni corrispondenza unifica due o più entità in un'unica entità consolidata. Allo stesso tempo, conserva i record del cliente univoci. L'ordine di corrispondenza indica l'ordine in cui il sistema tenta di abbinare i record.

> [!IMPORTANT]
> L'entità che scegli come tua entità primaria servirà come base per il set di dati profili unificato. Altre entità selezionate durante la fase di corrispondenza verranno aggiunte a questa entità. Ciò non significa che l'entità unificata includerà *tutti* i dati inclusi in questa entità.
>
> Esistono due considerazioni che possono aiutarti a scegliere la gerarchia delle entità:
>
> - Scegli l'entità con i dati di profilo più completi e affidabili sui tuoi clienti come entità principale.
> - Scegli l'entità che ha diversi attributi in comune con altre entità (ad esempio nome, numero di telefono o indirizzo e-mail) come entità primaria.

1. Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Definisci l'ordine** per iniziare la fase di corrispondenza.
1. Seleziona **Ordine entità**. Ad esempio, seleziona **eCommerce:eCommerceContacts** come entità primaria e **LoyaltyScheme:loyCustomers** come seconda entità. 
1. Per avere ogni record nell'entità come un cliente unico e abbinato a ogni entità successiva, seleziona **Includi tutto**.
1. Seleziona **Fatto**. 

Dopo aver specificato l'ordine di corrispondenza, le coppie di corrispondenze definite vengono visualizzate nella sezione **Dettagli dei record abbinati** in **Dati** > **Unifica** > **Corrispondenza**. Le metriche chiave sono vuote fino al completamento del processo di corrispondenza.

:::image type="content" source="media/match-page.png" alt-text="Screenshot della pagina Corrispondenza nell'area Unifica del processo di unificazione dei dati.":::
  
L'entità primaria *eCommerce: eCommerceContacts* è corrisposta all'entità successiva *LoyaltyScheme: loyCustomers*. Il set di dati che risulta dal primo passaggio di corrispondenza viene confrontato con l'entità seguente se hai più di due entità.

## <a name="define-rules-for-match-pairs"></a>Definire le regole per le coppie di corrispondenze

Le regole di corrispondenza specificano la logica con cui verrà eseguita la corrispondenza per una specifica coppia di entità.

L'avviso **Necessita regole** accanto al nome di un'entità suggerisce che non è stata definita alcuna regola di corrispondenza per una coppia di corrispondenze. 

:::image type="content" source="media/match-rule-add.png" alt-text="Screenshot della sezione Dettagli record corrispondenti con il controllo per aggiungere regole evidenziato.":::

1. Seleziona **Aggiungi regola** sotto un'entità nella sezione **Dettagli record abbinati** per definire le regole di corrispondenza.

1. Nel riquadro **Crea regola**, configura le condizioni per la regola.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Screenshot di una regola di corrispondenza aperta con condizioni aggiunte.":::

   - **Entità/Campo (prima riga)**: Scegli un'entità correlata e un attributo per specificare una proprietà del record che è probabilmente univoca per un cliente. Ad esempio, un numero di telefono o un indirizzo e-mail. Evita la corrispondenza in base agli attributi del tipo di attività. Ad esempio, un ID acquisto probabilmente non troverà corrispondenze in altri tipi di record.

   - **Entità/Campo (seconda riga)**: Scegli un attributo correlato all'attributo dell'entità specificata nella prima riga.

   - **Normalizza**: Seleziona una delle seguenti opzioni di normalizzazione per gli attributi selezionati. 
     - Numeri: converte altri sistemi numerici, come i numeri romani, in numeri arabi. *VIII* diventa *8*.
     - Simboli: rimuove tutti i simboli e i caratteri speciali. *Head&Shoulder* diventa *HeadShoulder*.
     - Testo in minuscolo: converte tutti i caratteri in minuscolo. *TUTTO MAIUSCOLO e titolo* diventa *tutto maiuscolo e titolo*.
     - Tipo (telefono, nome, indirizzo, organizzazione): standardizza nomi, titoli, numeri di telefono, indirizzi, ecc. 
     - Unicode in ASCII: converte la notazione Unicode in caratteri ASCII. */u00B2* diventa *2*.
     - Spazio vuoto: rimuove tutti gli spazi. *Hello World* diventa *HelloWorld*.

   - **Precisione**: Consente di impostare il livello di precisione da applicare per questa condizione. 
     - **Di base**: Scegli tra *Basso*, *Medio*, *Alto* ed *Esatto*. Seleziona **Esatto** per abbinare solo i record che corrispondono al 100 percento. Seleziona uno degli altri livelli per mettere in corrispondenza i record che non sono identici al 100 per cento.
     - **Personalizzato**: Consente di impostare una percentuale per la corrispondenza dei record. Il sistema metterà in corrispondenza solo i record che superano questa soglia.

1. Fornisci un **nome** per la regola.

1. [Aggiungi altre condizioni](#add-conditions-to-a-rule) oppure seleziona **Fatto** per finalizzare la regola.

1. Facoltativamente, [aggiungi altre regole](#add-rules-to-a-match-pair).

1. Seleziona **Salva** per applicare le modifiche.

### <a name="add-conditions-to-a-rule"></a>Aggiungere le condizioni a una regola

Per corrispondere le entità solo se gli attributi soddisfano più condizioni, aggiungi più condizioni a una regola di corrispondenza. Le condizioni sono collegate a un operatore logico AND e quindi eseguite solo se tutte le condizioni sono soddisfatte.

1. Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Modifica** nella regola a cui vuoi aggiungere condizioni.

1. Nel riquadro **Modifica regola**, seleziona **Aggiungi condizione**.

1. Seleziona **Fatto** per salvare la regola.

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

1. Seleziona **Fatto** per salvare la regola.

## <a name="define-deduplication-on-a-match-entity"></a>Definire la deduplicazione in un'entità di corrispondenza

Oltre alle [regole di corrispondenza tra entità](#define-rules-for-match-pairs), puoi specificare le regole di deduplicazione. La *deduplicazione* è un altro processo della corrispondenza dei record. Identifica i record duplicati e li unisce in un unico record. I record di origine vengono collegati al record unito con ID alternativi.

I record deduplicati vengono usati nel processo di corrispondenza tra entità. La deduplicazione avviene su singole entità e può essere configurata per ogni entità usata nelle coppie di corrispondenza.

Non è obbligatorio specificare regole di deduplicazione. Se tali regole non vengono configurate, verranno applicate le regole definite dal sistema. Combinano tutti i record in un unico record prima di passare i dati dell'entità alla corrispondenza tra entità per migliorare le prestazioni.

### <a name="add-deduplication-rules"></a>Aggiungere regole di deduplicazione

1. Vai a **Dati** > **Unifica** > **Corrispondenza**.

1. Nella sezione **Dettagli record deduplicati**, seleziona **Imposta entità**. Nel caso in cui le regole di deduplicazione siano già state create, seleziona **Modifica**.

1. Nel riquadro **Preferenze di unione**, seleziona le entità in cui desideri eseguire la deduplicazione.

   1. Specifica come combinare i record duplicati e scegli una delle tre opzioni:
      - **Con più dati**: identifica il record con i campi di attributo con più dati come record vincitore. È l'opzione di unione predefinita.
      - **Piu recente**: il record vincitore è quello più recente. Richiede una data o un campo numerico per definire la recency.
      - **Meno recente**: il record vincitore è quello meno recente. Richiede una data o un campo numerico per definire la recency.

   1. Facoltativamente, per definire regole di deduplicazione sui singoli attributi di un'entità seleziona **Avanzate**. Ad esempio, puoi scegliere di conservare il messaggio e-mail più recente E l'indirizzo più completo da record diversi. Espandi l'entità per vedere tutti i suoi attributi e definisci quale opzione utilizzare per i singoli attributi. Se scegli un'opzione basata sulla recency, devi anche specificare un campo data/ora che definisca la recency. 
 
      > [!div class="mx-imgBorder"]
      > ![Passaggio 1 delle regole di deduplicazione.](media/match-selfconflation.png "Passaggio 1 delle regole di deduplicazione")

   1. Seleziona **Fatto** per applicare le tue preferenze di unione per la deduplicazione.
 
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

1. Dopo aver [eseguito il processo di corrispondenza](#run-the-match-process), vedrai le statistiche di deduplicazione nei riquadri delle metriche chiave.

### <a name="deduplication-output-as-an-entity"></a>Output di deduplicazione come entità

Il processo di deduplicazione crea una nuova entità per ogni entità dalle coppie di corrispondenza per identificare i record deduplicati. Queste entità possono essere trovate insieme a **ConflationMatchPairs:CustomerInsights** nella sezione **Sistema** della pagina **Entità**, con il nome **Deduplication_DataSource_Entity**.

Un'entità di output della deduplicazione contiene le seguenti informazioni:
- ID/chiavi
  - Campo chiave primaria e relativo campo ID alternativo. Il campo ID alternativo è costituito da tutti gli ID alternativi identificati per un record.
  - Il campo Deduplication_GroupId mostra il gruppo o il cluster identificato all'interno di un'entità che raggruppa tutti i record simili in base ai campi di deduplicazione specificati. È utilizzato per scopi di elaborazione del sistema. Se non sono state specificate regole di deduplicazione manuale e si applicano regole di deduplicazione definite dal sistema, potresti non trovare questo campo nell'entità di output della deduplicazione.
  - Deduplication_WinnerId: questo campo contiene l'ID vincitore dei gruppi o cluster identificati. Se Deduplication_WinnerId è uguale al valore della chiave primaria per un record, significa che il record è il record vincitore.
- Campi utilizzati per definire le regole di deduplicazione.
- I campi Regola e Punteggio per indicare quale delle regole di deduplicazione è stata applicata e il punteggio restituito dall'algoritmo di corrispondenza.
 
## <a name="include-enriched-entities-preview"></a>Includere entità arricchite (anteprima)

Se hai arricchito le entità a livello origine dati, selezionale prima di eseguire il processo di corrispondenza. Le entità arricchite possono migliorare i risultati dell'unificazione. Per altre informazioni, vedi [Arricchimento per le origini dati](data-sources-enrichment.md). 

L'entità arricchita contiene i campi originali dell'origine dati e i campi arricchiti. Quindi, se scegli di lavorare con l'entità arricchita, la configurazione esistente non viene influenzata. Tuttavia, potrebbe essere necessario aggiornare le regole di corrispondenza per utilizzare i campi arricchiti.

1. Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Usa entità arricchite** all'inizio della pagina.

1. Nel riquadro **Usa entità arricchite** scegli una o più entità arricchite.

1. Seleziona **Fatto**. Ovunque venga utilizzata l'entità di origine (come l'ordine di corrispondenza o le regole), viene automaticamente modificata nell'entità arricchita.
  
## <a name="run-the-match-process"></a>Eseguire il processo di corrispondenza

Con le regole di corrispondenza configurate, inclusa la corrispondenza tra entità e le regole di deduplicazione, puoi eseguire il processo di corrispondenza. 

Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Esegui** per avviare il processo. L'algoritmo di corrispondenza richiede un po' di tempo per essere completato e non è possibile modificare la configurazione fino al completamento. Per apportare modifiche puoi annullare l'esecuzione. Seleziona lo stato del processo e seleziona **Annulla processo** nel riquadro **Dettagli stato**.

Troverai il risultato di un'esecuzione completata, l'entità profilo del cliente unificata, nella pagina **Entità**. La tua entità cliente unificata è chiamata **Clienti** nella sezione **Profili**. La prima esecuzione di una corrispondenza completata crea l'entità *Cliente*. Tutte le esecuzioni di corrispondenza successive espandono quell'entità.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

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

## <a name="advanced-options"></a>Opzioni avanzate

### <a name="add-exceptions-to-a-rule"></a>Aggiungere eccezioni a una regola

Nella maggior parte dei casi, la corrispondenza delle entità porta a profili utente univoci con dati consolidati. Per affrontare in modo dinamico rari casi di falsi positivi e falsi negativi, puoi definire eccezioni per una regola di corrispondenza. Le eccezioni vengono applicate dopo l'elaborazione delle regole di corrispondenza ed evitano la corrispondenza di tutti i record, che soddisfano i criteri di eccezione.

Ad esempio, se la tua regola di corrispondenza combina cognome, città e data di nascita, il sistema identificherà i gemelli con lo stesso cognome che vivono nella stessa città con lo stesso profilo. Puoi specificare un'eccezione che non corrisponde ai profili se i nomi nelle entità combinate non sono gli stessi.

1. Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Modifica** nella regola a cui vuoi aggiungere condizioni.

1. Nel riquadro **Modifica regola**, seleziona **Aggiungi eccezione**.

1. Specifica i criteri di eccezione. 

1. Seleziona **Fatto** in modo da salvare la regola.

### <a name="specify-custom-match-conditions"></a>Specificare le condizioni di corrispondenza personalizzate

È possibile specificare condizioni che sovrascrivono la logica di corrispondenza predefinita. Le opzioni disponibili sono quattro: 

|Opzione  |Description |Esempio  |
|---------|---------|---------|
|Corrisponde sempre     | Definisce i valori che corrispondono sempre.         |  Abbina sempre *Mike* e *MikeR*.       |
|Mai nessuna corrispondenza     | Definisce valori che non corrispondono mai.        | Non abbina mai *John* e *Jonathan*.        |
|Ignora personalizzato     | Definisce i valori che il sistema deve sempre ignorare in fase di corrispondenza. |  Ignora i valori *11111* e *Sconosciuto* durante la corrispondenza.        |
|Mapping alias    | Definisce i valori che il sistema deve considerare come lo stesso valore.         | Considera *Joe* uguale a *Joseph*.        |

1. Vai a **Dati** > **Unifica** > **Corrispondenza** e seleziona **Corrispondenza personalizzata** nella sezione **Dettagli record corrispondenti**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Screenshot della sezione delle regole di corrispondenza con il controllo per la corrispondenza personalizzata evidenziato.":::

1. Nel riquadro **Personalizzazione** vai alla scheda **Record**.

1. Scegli l'opzione di corrispondenza personalizzata nel menu a discesa **Tipo personalizzato** e seleziona **Scarica modello**. Hai bisogno di un modello separato per ogni opzione di corrispondenza.

1. Apri il file modello scaricato e inserisci i dettagli. Il modello contiene campi per specificare l'entità e i valori della chiave primaria dell'entità da utilizzare nella corrispondenza personalizzata. Ad esempio, se desideri la chiave primaria *12345* dall'entità *Vendite* in modo che corrisponda sempre alla chiave primaria *34567* dall'entità *Contatto*, compila il modello:
    - Entity1: Vendite
    - Entity1Key: 12345
    - Entity2: Contatto
    - Entity2Key: 34567

   Lo stesso file di modello può specificare record di corrispondenza personalizzati da più entità.
   
   Se desideri specificare la corrispondenza personalizzata per la deduplicazione in un'entità, fornisci la stessa entità sia come Entità1 che Entità2 e imposta i diversi valori di chiave primaria.

1. Dopo aver aggiunto tutte le sostituzioni, salva il file di modello.

1. Vai a **Dati** > **Origini dati** e inserisci i file di modello come nuove entità.

1. Dopo aver caricato i file e le entità disponibili, seleziona nuovamente l'opzione **Corrispondenza personalizzata**. Vedrai le opzioni per specificare le entità che desideri includere. Seleziona le entità richieste nel menu a discesa e seleziona **Fatto**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Screenshot della finestra di dialogo per scegliere le sostituzioni per uno scenario di corrispondenza personalizzata.":::

1. L'applicazione della corrispondenza personalizzata dipende dall'opzione di corrispondenza da utilizzare. 

   - Per **Corrisponde sempre** o **Mai nessuna corrispondenza**, continua con il passaggio successivo.
   - Per **Ignora personalizzato** o **Mapping alias**, seleziona **Modifica** su una regola di corrispondenza esistente o crea una nuova regola. Nel menu a discesa Normalizzazione scegli l'opzione **Ignora personalizzato** o **Mapping alias** e seleziona **Fatto**.

1. Seleziona **Salva** nella pagina **Corrispondenza** per applicare la configurazione di corrispondenza personalizzata.

1. Seleziona **Esegui** nella pagina **Corrispondenza** per avviare il processo di corrispondenza. Altre regole di corrispondenza specificate vengono sovrascritte dalla configurazione di corrispondenza personalizzata.

#### <a name="known-issues"></a>Problemi noti

- L'autoconflazione non mostra i dati normalizzati nelle entità di deduplicazione. Tuttavia, applica la normalizzazione internamente durante la deduplicazione. È progettata per tutte le normalizzazioni. 
- Se l'impostazione del tipo semantico viene rimossa nella fase **Mapping** quando una regola di corrispondenza utilizza le opzioni Mapping alias o Ignora personalizzato, la normalizzazione non verrà applicata. Ciò accade solo se si cancella il tipo semantico dopo aver configurato la normalizzazione nella regola di corrispondenza perché il tipo semantico sarà sconosciuto.


## <a name="next-step"></a>Passaggio successivo

Dopo aver completato il processo di corrispondenza per almeno una coppia di corrispondenza, continua con il passaggio [**Unisci**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
