---
title: Mettere in corrispondenza le entità per l'unificazione dei dati
description: Metti in corrispondenza le entità per creare profili cliente unificati.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406133"
---
# <a name="match-entities"></a>Mettere in corrispondenza le entità

Dopo aver completato la fase di mapping, puoi mettere in corrispondenza le entità. La fase di corrispondenza specifica in che modo combinare i set di dati in un profilo cliente unificato. La fase di corrispondenza richiede almeno [due entità mappate](map-entities.md).

## <a name="specify-the-match-order"></a>Specificare l'ordine di corrispondenza

Vai a **Unifica** > **Corrispondenza** e seleziona **Imposta ordine** per avviare la fase di corrispondenza.

Ogni corrispondenza unifica due o più entità in una singola entità, pur mantenendo ogni record del cliente univoco. Nel seguente esempio, abbiamo selezionato tre entità: **ContactCSV: TestData** come entità **Primaria**, **WebAccountCSV: TestData** come **Entità 2** e **CallRecordSmall: TestData** come **Entità 3**. Il diagramma sopra le selezioni mostra come verrà eseguito l'ordine di corrispondenza.

> [!div class="mx-imgBorder"]
> ![Modificare l'ordine di corrispondenza dei dati](media/configure-data-match-order-edit-page.png "Modificare l'ordine di corrispondenza dei dati")
  
L'entità **Primaria** è corrispondente all'**Entità 2**. Il set di dati che risulta dalla prima corrispondenza è corrispondente all'**Entità 3**.
In questo esempio, abbiamo selezionato solo due corrispondenze, ma il sistema può supportarne di più.

> [!IMPORTANT]
> L'entità che scegli come tua entità **Primaria** servirà come base per il set di dati unificato principale. Altre entità selezionate durante la fase di corrispondenza verranno aggiunte a questa entità. Allo stesso tempo, ciò non significa che l'entità unificata includerà *tutti* i dati inclusi in questa entità.
>
> Esistono due considerazioni che possono aiutarti a scegliere la gerarchia delle entità:
>
> - Quale entità pensi abbia i dati più completi e affidabili sui tuoi clienti?
> - L'entità appena identificata ha attributi condivisi anche da altre entità (ad esempio nome, numero di telefono o indirizzo e-mail)? In caso contrario, scegli la tua seconda entità più affidabile.

Seleziona **Fatto** per salvare l'ordine di corrispondenza.

## <a name="define-rules-for-your-first-match-pair"></a>Definire le regole per la tua prima coppia di corrispondenza

Dopo aver specificato l'ordine di corrispondenza, vedrai le corrispondenze definite nella pagina **Corrispondenza**. I riquadri nella parte superiore dello schermo saranno vuoti fino a quando non eseguirai l'ordine di corrispondenza.

> [!div class="mx-imgBorder"]
> ![Definire le regole](media/configure-data-match-need-rules.png "Definire le regole")

L'avviso **Necessita regole** suggerisce che non è stata definita alcuna regola di corrispondenza per una coppia di corrispondenze. Le regole di corrispondenza specificano la logica con cui verrà eseguita la corrispondenza per una specifica coppia di entità.

1. Per definire la tua prima regola, apri il riquadro **Definizione regola** selezionando la riga di corrispondenza corrispondente nella tabella delle corrispondenze (1) e quindi selezionando **Crea nuova regola** (2).

   > [!div class="mx-imgBorder"]
   > ![Crea nuova regola](media/configure-data-match-new-rule2.png "Crea nuova regola")

2. Nel riquadro **Modifica regola**, configura le condizioni per quella regola. Ogni condizione è rappresentata da due righe che includono selezioni obbligatorie.

   > [!div class="mx-imgBorder"]
   > ![Riquadro Nuova regola](media/configure-data-match-new-rule-condition.png "Riquadro Nuova regola")

   Entità/Campo (prima): un attributo che verrà utilizzato per la corrispondenza dalla prima corrispondenza tra una coppia di entità. Gli esempi potrebbero includere un numero di telefono o un indirizzo e-mail. Scegli un attributo che sia probabilmente unico per il cliente.

   > [!TIP]
   > Evita la corrispondenza in base agli attributi di tipo impegno. In altre parole, se un attributo sembra essere un impegno, potrebbe essere un criterio insufficiente su cui basare la corrispondenza.  

   Entità/Campo (seconda): un attributo che verrà utilizzato per la corrispondenza dalla seconda corrispondenza tra una coppia di entità.

   Normalizza - **Metodo di normalizzazione**: sono disponibili varie opzioni di normalizzazione per gli attributi selezionati. Ad esempio, rimozione della punteggiatura o degli spazi

   Per la normalizzazione del nome dell'organizzazione (Anteprima), è anche possibile selezionare **Tipo (telefono, nome, organizzazione)**

   > [!div class="mx-imgBorder"]
   > ![Normalizzazione-B2B](media/match-normalization-b2b.png "Normalizzazione-B2B")

   Livello di precisione : il livello di precisione che verrà utilizzato per questa condizione. L'impostazione di un livello di precisione per una condizione di corrispondenza può avere due tipi: **Di base** e **Personalizzato**.  
   - Di base: offre quattro opzioni tra cui scegliere: Bassa, Media, Alta ed Esatta. Seleziona **Esatta** per mettere in corrispondenza solo i record corrispondenti al 100 per cento. Seleziona uno degli altri livelli per mettere in corrispondenza i record che non sono identici al 100 per cento.
   - Personalizzato: utilizza il dispositivo di scorrimento per definire la percentuale personalizzata a cui i record devono corrispondere o immetti un valore nel campo **Personalizzato**. Il sistema metterà in corrispondenza solo i record che superano questa soglia come coppie di corrispondenza di conflazione. I valori sul dispositivo di scorrimento sono compresi tra 0 e 1. Quindi lo 0,64 rappresenta il 64 percento.

3. Seleziona **Fatto** per salvare la regola.

### <a name="add-multiple-conditions"></a>Aggiungere più condizioni

Per mettere in corrispondenza entità solo se sono soddisfatte più condizioni, aggiungi più condizioni collegate tramite un operatore AND.

1. Nel riquadro **Modifica regola**, seleziona **Aggiungi condizione**. Puoi anche eliminare le condizioni selezionando il pulsante Rimuovi accanto a una condizione esistente.

2. Seleziona **Fatto** in modo da salvare la regola.

## <a name="add-multiple-rules"></a>Aggiungere più regole

Ogni condizione si applica a una singola coppia di attributi, mentre le regole rappresentano insiemi di condizioni. Per far corrispondere le tue entità a diversi set di attributi, puoi aggiungere più regole.

1. In Audience Insights, vai a **Dati** > **Unifica** > **Corrispondenza**.

2. Seleziona l'entità che vuoi aggiornare e eseleziona **Aggiungi regole**.

3. Segui la procedura come illustrato in [Definire le regole per la tua prima coppia di corrispondenza](#define-rules-for-your-first-match-pair).

> [!NOTE]
> L'ordine delle regole è importante. L'algoritmo di corrispondenza tenta di mettere in corrispondenza sulla base della prima regola e continua con la seconda regola solo se non sono state identificate corrispondenze con la prima regola.

## <a name="define-deduplication-on-a-match-entity"></a>Definire la deduplicazione in un'entità di corrispondenza

Oltre a specificare le regole di corrispondenza tra entità come descritto nelle sezioni precedenti, è anche possibile specificare regole di deduplicazione. La *deduplicazione* è un processo. Identifica i record duplicati, li unisce in un solo record e collega tutti i record di origine a questo record unito con ID alternativi al record unito.

Una volta identificato un record deduplicato, tale record verrà utilizzato nel processo di corrispondenza tra entità. La deduplicazione viene implementata a livello di entità e può essere applicata a ogni entità utilizzata nel processo di corrispondenza.

### <a name="add-deduplication-rules"></a>Aggiungere regole di deduplicazione

1. In Audience Insights, vai a **Dati** > **Unifica** > **Corrispondenza**.

1. Nella sezione **Duplicati uniti**, seleziona **Imposta entità**.

1. Nella sezione **Preferenze di unione**, seleziona le entità a cui desideri applicare la deduplicazione.

1. Specifica come unire i record duplicati e scegli una delle tre opzioni di unione:
   - *Con più dati*: identifica il record con gli attributi con più dati come record vincitore. Si tratta dell'opzione di unione predefinita.
   - *Piu recente*: il record vincitore è quello più recente. Richiede una data o un campo numerico per definire la recency.
   - *Meno recente*: il record vincitore è quello meno recente. Richiede una data o un campo numerico per definire la recency.
 
   > [!div class="mx-imgBorder"]
   > ![Passaggio 1 delle regole di deduplicazione](media/match-selfconflation.png "Passaggio 1 delle regole di deduplicazione")
 
1. Una volta selezionate le entità e impostata la relativa preferenza di unione, seleziona **Crea nuova regola** per definire le regole di deduplicazione a livello di entità.
   - **Seleziona campo** elenca tutti i campi disponibili di quell'entità in cui desideri deduplicare i dati di origine.
   - Specifica le impostazioni di normalizzazione e precisione in modo simile a quanto specificato nella corrispondenza tra entità.
   - Puoi definire condizioni aggiuntive selezionando **Aggiungi condizione**.
 
   > [!div class="mx-imgBorder"]
   > ![Passaggio 2 delle regole di deduplicazione](media/match-selfconflation-rules.png "Passaggio 2 delle regole di deduplicazione")

  Puoi creare molteplici regole di deduplicazione per un'entità. 

1. L'esecuzione del processo di corrispondenza ora raggruppa i record in base alle condizioni definite nelle regole di deduplicazione. Dopo aver raggruppato i record, i criteri di unione vengono applicati per identificare il record vincitore.

1. Questo record vincitore viene quindi passato alla corrispondenza tra entità.

1. Qualsiasi regola di corrispondenza personalizzata definita per corrispondere sempre e non corrispondere mai sostituisce le regole di deduplicazione. Se una regola di deduplicazione identifica i record corrispondenti e una regola di corrispondenza personalizzata è impostata per non corrispondere mai a tali record, questi due record non corrisponderanno.

1. Dopo l'esecuzione del processo di corrispondenza, vedrai le statistiche di deduplicazione.
   
> [!NOTE]
> Specificare regole di deduplicazione non è obbligatorio. Se non vengono configurate tali regole, vengono applicate le regole definite dal sistema. Queste comprendono tutti i record che condividono la stessa combinazione di valori (corrispondenza esatta) della chiave primaria e i campi nelle regole di corrispondenza in un singolo record prima di passare i dati dell'entità alla corrispondenza tra entità per migliorare le prestazioni e l'integrità del sistema.

## <a name="run-your-match-order"></a>Esegui l'ordine di corrispondenza

Dopo aver definito regole di corrispondenza, inclusa la corrispondenza tra entità e le regole di deduplicazione, puoi eseguire l'ordine di corrispondenza. Nella pagina **Corrispondenza**, seleziona **Esegui** per avviare il processo. Il completamento dell'algoritmo di corrispondeza potrebbe richiedere del tempo. Non puoi modificare le proprietà nella pagina **Corrispondenza** fino al completamento del processo di corrispondenza. Troverai l'entità del profilo cliente unificato creata nella pagina **Entità**. L'entità cliente unificata viene chiamata **ConflationMatchPairs: CustomerInsights**.

Per apportare ulteriori modifiche ed eseguire nuovamente il passaggio, puoi annullare una corrispondenza in corso. Seleziona il testo **Aggiornamento in corso ...** e seleziona **Annulla processo** nella parte inferiore del riquadro laterale visualizzato.

Quando il processo di corrispondenza è completo, il testo **Aggiornamento in corso ...** cambierà in **Completato** e puoi riutilizzare tutte le funzionalità della pagina.

Il primo processo di corrispondenza comporta la creazione di un'entità master unificata. Tutte le successive esecuzioni di corrispondenza determinano l'espansione di tale entità.

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.

## <a name="review-and-validate-your-matches"></a>Rivedere e convalidare le corrispondenze

Valuta la qualità delle coppie di corrispondenza e affinala:

- Nella pagina **Corrispondenza**, troverai due riquadri che mostrano le informazioni dettagliate iniziali sui tuoi dati.

  - **Clienti univoci**: mostra il numero di profili univoci identificati dal sistema.
  - **Record corrispondenti**: mostra il numero di corrispondenze su tutte le coppie di corrispondenza.

- Nella tabella **Ordine corrispondenza**, puoi valutare i risultati di ciascuna coppia di corrispondenze confrontando il numero di record provenienti da questa entità coppia-corrispondenza con la percentuale di record con corrispondenza corretta.

- Nella sezione **Regole** di un'entità della tabella **Ordine corrispondenza**, troverai la percentuale di record con corrispondenza corretta a livello di regola. Selezionando il simbolo della tabella accanto a una regola, puoi visualizzare tutti questi record a livello di regola. Si consiglia di rivedere un sottoinsieme dei record per convalidare la corrispondenza corretta.

- Sperimenta con soglie di precisione diverse intorno alle tue condizioni per identificare il valore ottimale.

  1. Seleziona i puntini di sospensione (...) per la regola della coppia di corrispondenza che vuoi sperimentare e seleziona **Modifica**.

  2. Seleziona la condizione con cui vuoi sperimentare. Ogni criterio è rappresentato da una riga nel riquadro **Regola corrispondenza**.

  3. Quello che vedrai nella pagina **Anteprima criteri** dipende dal livello di precisione selezionato per una condizione. Trova il numero di record corrispondenti e non corrispondenti per la condizione selezionata.

     Ottieni una conoscenza approfondita degli effetti dei diversi livelli di soglia. Puoi confrontare il numero di record corrispondenti sotto ciascuno dei livelli di soglia e visualizzare i record in ciascuna opzione. Seleziona ciascuno dei riquadri e rivedi i dati nella sezione della tabella.

## <a name="optimize-your-matches"></a>Ottimizzare le corrispondenze

Aumenta la qualità riconfigurando alcuni dei tuoi parametri di corrispondenza:

- **Modifica l'ordine di corrispondenza** selezionando **Modifica** e modifica i campi dell'ordine di corrispondenza.

  > [!div class="mx-imgBorder"]
  > ![Modificare l'ordine di corrispondenza dei dati](media/configure-data-match-order-edit.png "Modificare l'ordine di corrispondenza dei dati")

- **Modifica l'ordine delle tue regole** se hai definito più regole. Puoi riordinare le regole di corrispondenza selezionando le opzioni **Sposta su** e **Sposta giù** nella griglia delle regole di corrispondenza.

  > [!div class="mx-imgBorder"]
  > ![Modificare l'ordine delle regole](media/configure-data-change-rule-order.png "Modificare l'ordine delle regole")

- **Duplica le tue regole** se hai definito una regola di corrispondenza e desideri creare una regola simile con modifiche. Puoi farlo selezionando **Duplica**.

  > [!div class="mx-imgBorder"]
  > ![Duplicare una regola](media/configure-data-duplicate-rule.png "Duplicare una regola")

- **Modifica le tue regole** selezionando il simbolo **Modifica**. Puoi applicare le modifiche seguenti:

  - Modifica attributi per una condizione: seleziona nuovi attributi nella riga della condizione specifica.
  - Modifica la soglia per una condizione: regola il dispositivo di scorrimento di precisione.
  - Modifica il metodo di normalizzazione per una condizione: aggiorna il metodo di normalizzazione.

## <a name="specify-your-custom-match-records"></a>Specificare i record di corrispondenza personalizzati

Puoi specificare condizioni in base a cui alcuni record devono sempre corrispondere o non corrispondere mai. Queste regole possono essere caricate in blocco nel processo di corrispondenza.

1. Seleziona l'opzione **Corrispondenza personalizzata** nella schermata **Ordine corrispondenza**.

   > [!div class="mx-imgBorder"]
   > ![Crea una corrispondenza personalizzata](media/custom-match-create.png "Crea una corrispondenza personalizzata")

2. Se non hai entità caricate, vedrai una nuova finestra di dialogo **Corrispondenza personalizzata** che richiede di inserire alcuni dettagli. Se hai fornito questi dettagli in precedenza, vai direttamente al passaggio 8.

   > [!div class="mx-imgBorder"]
   > ![Nuova finestra di dialogo di corrispondenza personalizzata](media/custom-match-new-dialog-box.png "Nuova finestra di dialogo di corrispondenza personalizzata")

3. Seleziona **Compila il modello** per ottenere un file modello che può specificare quali record da quali entità devono sempre corrispondere o non corrispondere mai. Dovrai compilare separatamente i record "Corrisponde sempre" e "Mai nessuna corrispondenza" in due file diversi.

4. Il modello contiene campi per specificare l'entità e i valori della chiave primaria dell'entità da utilizzare nella corrispondenza personalizzata. Ad esempio, se vuoi che la chiave primaria 12345 dell'entità vendite corrisponda sempre alla chiave primaria 34567 dell'entità contatto, devi specificare quanto segue:
    - Entity1: Vendite
    - Entity1Key: 12345
    - Entity2: Contatto
    - Entity2Key: 34567

   Lo stesso file di modello può specificare record di corrispondenza personalizzati da più entità.

5. Dopo aver aggiunto tutte le sostituzioni che vuoi applicare, salva il file del modello.

6. Vai a **Dati** > **Origine dati** e inserisci i file di modello come nuove entità. Una volta inseriti, puoi usarli per specificare la configurazione della corrispondenza.

7. Dopo aver caricato i file e le entità disponibili, seleziona nuovamente l'opzione **Corrispondenza personalizzata**. Vedrai le opzioni per specificare le entità che desideri includere. Seleziona le entità obbligatorie dal menu a discesa.

   > [!div class="mx-imgBorder"]
   > ![Sostituzioni corrispondenza personalizzata](media/custom-match-overrides.png "Sostituzioni corrispondenza personalizzata")

8. Seleziona le entità che desideri utilizzare per **Corrisponde sempre** e **Mai nessuna corrispondenza**, quindi seleziona **Fatto**.

9. Seleziona **Salva** nella pagina **Corrispondenza** per la configurazione della corrispondenza personalizzata che hai appena impostato.

10. Seleziona **Esegui** nella pagina **Corrispondenza** per avviare il processo di corrispondenza e la configurazione della corrispondenza personalizzata verrà applicata. Qualsiasi regola di corrispondenza del sistema viene sostituita dal set di configurazione.

11. Una volta completata la corrispondenza, puoi verificare l'entità **ConflationMatchPair** per confermare che le sostituzioni sono state applicate nelle corrispondenze di conflazione.

## <a name="next-step"></a>Passaggio successivo

Dopo aver completato il processo di corrispondenza per almeno una coppia di corrispondenza, puoi risolvere eventuali contraddizioni nei tuoi dati esaminando l'argomento [**Unione**](merge-entities.md).
