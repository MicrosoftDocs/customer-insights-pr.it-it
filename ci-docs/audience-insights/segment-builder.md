---
title: Creare e gestire segmenti
description: Crea segmenti di clienti per raggrupparli in base a vari attributi.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377793"
---
# <a name="create-and-manage-segments"></a>Creare e gestire segmenti

> [!IMPORTANT]
> Ci sono diverse modifiche che verranno introdotte nell'esperienza di creazione del segmento a settembre 2021: 
> - Il generatore di segmenti avrà un aspetto leggermente diverso con elementi ridisegnati e un flusso utente migliorato.
> - Nuovi operatori datetime e un selezionatore di date migliorato sono abilitati nel generatore di segmenti.
> - Potrai aggiungere o rimuovere condizioni e regole dai segmenti. 
> - Diventeranno disponibili regole nidificate che iniziano con una condizione OR. Non hai più bisogno di una condizione AND nel livello più esterno.
> - Un riquadro laterale per selezionare gli attributi sarà costantemente disponibile.
> - Un'opzione per selezionare i percorsi relazione dell'entità.
> Per provare il nuovo generatore di segmenti, invia un'e-mail con oggetto "Richiesta di abilitazione del nuovo generatore di segmenti" a cihelp [at] microsoft.com. Includi il nome dell'organizzazione e l'ID del tuo ambiente sandbox.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi del generatore di segmenti." lightbox="media/segment-builder-overview.png":::
>
> 1 - Organizza il segmento con regole e regole secondarie. Ogni regola o regola secondaria è costituita da condizioni. Combina le condizioni con operatori logici
>
> 2 - Scegli il [percorso relazione](relationships.md) tra entità che si applica a una regola. Il percorso relazione determina quali attributi possono essere utilizzati in una condizione.
>
> 3 - Gestisci regole e regole secondarie. Modifica la posizione di una regola o eliminala.
>
> 4 - Aggiungi condizioni e crea il livello di nidificazione appropriato usando regole secondarie.
>
> 5 - Applica operazioni di impostazione a regole connesse.
>
> 6 - Utilizza il riquadro degli attributi per aggiungere attributi di entità disponibili o creare condizioni in base agli attributi. Il riquadro mostra l'elenco di entità e attributi, in base al percorso relazione selezionato, disponibili per la regola selezionata.
>
> 7 - Aggiungi condizioni basate su attributi a regole e regole secondarie esistenti o aggiungile a una nuova regola.
>
> 8 - Annulla e ripeti le modifiche durante la creazione del segmento.

Definisci filtri complessi per all'entità cliente unificata e le sue entità correlate. Ogni segmento, dopo l'elaborazione, crea una serie di record dei clienti che puoi esportare o su cui puoi intervenire. I segmenti sono gestiti nella pagina **Segmenti**. 

Il seguente esempio illustra la funzionalità di segmentazione. Abbiamo definito un segmento per i clienti che hanno ordinato almeno $500 di merci negli ultimi 90 giorni *e* che sono stati coinvolti in una chiamata servizio clienti che è stata riassegnata.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Screenshot dell'interfaccia utente del generatore di segmenti con due gruppi che specificano un segmento di clienti.":::

## <a name="create-a-new-segment"></a>Creare un nuovo segmento

Un nuovo segmento può essere creato in modi diversi. Questa sezione descrive come creare un *segmento vuoto* da zero. Puoi anche creare un *segmento veloce* basato su entità esistenti o utilizzare i modelli apprendimento automatico per ottenere *segmenti suggeriti*. Ulteriori informazioni: [Panoramica dei segmenti](segments.md).

Durante la creazione di un segmento, puoi salvare una bozza. Verrà salvata come segmento inattivo che non può essere attivato se non è terminato con una configurazione valida.

1. Vai alla pagina **Segmenti**.

1. Seleziona **Nuovo** > **Segmento vuoto**.

1. Nel riquadro **Nuovo segmento** scegli un tipo di segmento:

   - **Segmenti dinamici** [aggiornati](segments.md#refresh-segments) su una pianificazione ricorrente.
   - **Segmenti statici** eseguiti una volta quando li crei.

1. Fornisci un **Nome entità di output** per il segmento. Facoltativamente, fornisci un nome visualizzato e una descrizione che aiuti a identificare il segmento.

1. Seleziona **Avanti** per andare alla pagina **Generatore di segmenti** in cui puoi definire un gruppo. Un gruppo è un set di clienti.

1. Scegli l'entità che include l'attributo in base al quale vuoi segmentare.

1. Scegli l'attributo in base a cui segmentare. Questo attributo può avere uno dei quattro tipi di valore: numerico, stringa, data o booleano.

1. Scegli un operatore e un valore per l'attributo selezionato.

   > [!div class="mx-imgBorder"]
   > ![Filtro gruppo clienti.](media/customer-group-numbers.png "Filtro gruppo clienti")

   |Numero |Definizione  |
   |---------|---------|
   |1     |Entity          |
   |2     |Attributo          |
   |3    |Operatore         |
   |4    |valore         |

   1. Per aggiungere più condizioni a un gruppo, è possibile utilizzare due operatori logici:

      - Operatore **AND**: entrambe le condizioni devono essere soddisfatte come parte del processo di segmentazione. Questa opzione è molto utile quando si definiscono condizioni tra entità diverse.

      - Operatore **OR**: una delle condizioni deve essere soddisfatta come parte del processo di segmentazione. Questa opzione è molto utile quando si definiscono più condizioni per la stessa entità.

      > [!div class="mx-imgBorder"]
      > ![Operatore OR in cui è necessario soddisfare una delle condizioni.](media/segmentation-either-condition.png "Operatore OR in cui è necessario soddisfare una delle condizioni")

      Al momento è possibile nidificare un operatore **OR** sotto un operatore **AND**, ma non il contrario.

   1. Ogni gruppo corrisponde a un set di clienti. Puoi combinare gruppi per includere i clienti richiesti per il tuo caso aziendale.    
   Seleziona **Aggiungi gruppo**.

      > [!div class="mx-imgBorder"]
      > ![Aggiungi gruppo di gruppo clienti.](media/customer-group-add-group.png "Aggiungi gruppo per gruppo clienti")

   1. Seleziona uno degli operatori impostati: **Unione**, **Intersecazione** o **Eccezione**.

   > [!div class="mx-imgBorder"]
   > ![Aggiungi unione per gruppo clienti.](media/customer-group-union.png "Aggiungi Union per gruppo clienti")

   - **Union** unisce i due gruppi.

   - **Intersect** sovrappone i due gruppi. Solo i dati che *sono comuni* a entrambi i gruppi vengono mantenuti nel gruppo unificato.

   - **Ad eccezione di** combina i due gruppi. Solo i dati nel gruppo A che *non sono comuni* ai dati nel gruppo B vengono mantenuti.

1. Se l'entità è connessa all'entità cliente unificata tramite [relazioni](relationships.md), devi definire il percorso relazione per creare un segmento valido. Aggiungi le entità dal percorso relazione fino a quando non puoi selezionare l'entità **Cliente: CustomerInsights** dal menu a discesa. Quindi scegli **Tutti i record** per ogni passaggio.

   > [!div class="mx-imgBorder"]
   > ![Percorso relazione durante la creazione del segmento.](media/segments-multiple-relationships.png "Percorso relazione durante la creazione del segmento")

1. Per impostazione predefinita, i segmenti generano un'entità di output che contiene tutti gli attributi dei profili cliente che corrispondono ai filtri definiti. Se un segmento è basato su entità diverse dall'entità *Cliente* puoi aggiungere più attributi da queste entità all'entità di output. Seleziona **Attributi progetto** per scegliere gli attributi che verranno aggiunti all'entità di output.  
  
   Esempio: un segmento si basa su un'entità che contiene i dati sull'impegno del cliente correlati all'entità *Cliente*. Il segmento cerca tutti i clienti che hanno chiamato l'help desk negli ultimi 60 giorni. Puoi scegliere di aggiungere la durata della chiamata e il numero di chiamate a tutti i record cliente corrispondenti nell'entità di output. Queste informazioni potrebbero essere utili per inviare un'e-mail con collegamenti utili ad articoli della guida in linea e domande frequenti per i clienti che chiamano frequentemente.

   > [!NOTE]
   > - Gli attributi previsti funzionano solo per entità che hanno la relazione uno-a-molti con l'entità cliente. Ad esempio, un cliente può avere più abbonamenti.
   > - È possibile proiettare gli attributi solo da un'entità utilizzata in ogni gruppo della query di segmento che si sta creando.
   > - Gli attributi proiettati vengono presi in considerazione quando si utilizzano operatori di gruppo.

1. Seleziona **Salva** per salvare il segmento. Il segmento verrà salvato ed elaborato se tutti i requisiti vengono convalidati. Altrimenti, verrà salvato come bozza.

1. Seleziona **Torna a Segmenti** per tornare alla pagina **Segmenti**.



## <a name="quick-segments"></a>Segmenti rapidi

I segmenti rapidi consentono di creare rapidamente segmenti semplici con un singolo operatore per ottenere informazioni più rapide.

1. Nella pagina **Segmenti**, seleziona **Nuovo** > **Crea a partire da**.

   - Seleziona l'opzione **Profili** per creare un segmento basato sull'*entità cliente unificata*.
   - Seleziona l'opzione **Misure** per creare un segmento per le misure create in precedenza.
   - Seleziona l'opzione **Intelligenza** per creare un segmento attorno a una delle entità di output generate utilizzando le funzionalità **Previsioni** o **Modelli personalizzati**.

2. Nella finestra di dialogo **Nuovo segmento rapido**, seleziona un attributo dal menu a discesa **Campo**.

3. Il sistema fornirà alcune informazioni dettagliate aggiuntive che ti aiuteranno a creare segmenti migliori dei tuoi clienti.
   - Per i campi di categoria, vengono visualizzati i primi 10 conteggi dei clienti. Scegli un **valore** e seleziona **Revisione**.

   - Per un attributo numerico, il sistema mostrerà quale valore dell'attributo rientra nel percentile di ciascun cliente. Scegli un **operatore** e un **valore**, quindi seleziona **Revisione**.

4. Il sistema fornirà una **dimensione stimata del segmento**. Puoi scegliere se generare il segmento che hai definito o modificarlo prima per ottenere una dimensione del segmento diversa.

    > [!div class="mx-imgBorder"]
    > ![Nome e stima per un segmento rapido.](media/quick-segment-name.png "Nome e stima per un segmento rapido")

5. Inserisci un **nome** per il segmento. Se lo desideri, inserisci un **nome visualizzato**.

6. Seleziona **Salva** per creare il segmento.

7. Al termine dell'elaborazione del segmento, puoi visualizzarlo come qualsiasi altro segmento che hai creato.

## <a name="next-steps"></a>Passaggi successivi

[Esporta un segmento](export-destinations.md) ed esplora l'[integrazione della scheda cliente](customer-card-add-in.md) per utilizzare i segmenti in altre applicazioni.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
