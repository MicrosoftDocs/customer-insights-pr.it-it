---
title: Creare segmenti con il generatore di segmenti
description: Crea segmenti di clienti per raggrupparli in base a vari attributi.
ms.date: 10/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bd01edfe7d63d6c7712a808224171f1bb8ad8a2b
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673555"
---
# <a name="create-segments"></a>Creare segmenti

Definisci filtri complessi per all'entità cliente unificata e le sue entità correlate. Ogni segmento, dopo l'elaborazione, crea una serie di record dei clienti che puoi esportare o su cui puoi intervenire. I segmenti sono gestiti nella pagina **Segmenti**. Puoi [creare nuovi segmenti](#create-a-new-segment) usando il costruttore di segmenti o [creare segmenti rapidi](#quick-segments) da altre aree dell'applicazione. 

> [!TIP]
> - I segmenti rapidi sono supportati solo in ambienti per **clienti individuali**.    
> - I segmenti basati su **clienti individuali** includono automaticamente le informazioni di contatto disponibili per i membri del segmento. Negli ambienti per la **contabilità aziendale**, i segmenti sono basati su conti (società o filiali). Per includere le informazioni di contatto in un segmento, usa la funzionalità degli **attributi del progetto** nel costruttore del segmento.
>    - Verifica che le fonti dei dati di contatto siano [mappate semanticamente all'entità ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Generatore di segmenti

L'immagine seguente illustra i vari aspetti del generatore di segmenti. Mostra un segmento che risulta in un gruppo di clienti. I clienti ordinavano merci in un lasso di tempo specifico e raccoglievano punti premio o spendevano una certa quantità di denaro. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi del generatore di segmenti." lightbox="media/segment-builder-overview.png":::

1. Organizza il tuo segmento con regole e sottoregole. Ogni regola o regola secondaria è costituita da condizioni. Combina le condizioni con operatori logici

1. Scegli il [percorso di relazione](relationships.md) tra entità che si applica a una regola. Il percorso relazione determina quali attributi possono essere utilizzati in una condizione.

1. Gestire regole e sottoregole. Modifica la posizione di una regola o eliminala.

1. Aggiungete condizioni e costruite il giusto livello di annidamento usando le sottoregole.

1. Applica le operazioni di set alle regole collegate.

1. Usa il pannello degli attributi per aggiungere gli attributi disponibili dell'entità o per creare condizioni basate sugli attributi. Il riquadro mostra l'elenco di entità e attributi, in base al percorso relazione selezionato, disponibili per la regola selezionata.

1. Aggiungi condizioni basate su attributi a regole e sottoregole esistenti o aggiungile a una nuova regola.

1. Annullare e rifare le modifiche durante la costruzione del segmento.

L'esempio precedente illustra la capacità di segmentazione. È stato definito un segmento per i clienti che hanno acquistato almeno 500 USD di merce online *e* sono interessati allo sviluppo di software.

## <a name="create-a-new-segment"></a>Creare un nuovo segmento

Un nuovo segmento può essere creato in modi diversi. Questa sezione descrive come creare il tuo segmento da zero. Puoi anche creare un *segmento veloce* basato su entità esistenti o utilizzare i modelli apprendimento automatico per ottenere *segmenti suggeriti*. Per maggiori informazioni, vai a [Panoramica dei segmenti](segments.md).

Durante la creazione di un segmento, puoi salvare una bozza. Nella fase di bozza, un segmento viene salvato come segmento inattivo. Quando hai completato la configurazione del segmento, eseguilo per attivare il segmento. Puoi anche usare l'opzione **Attivare** per attivare un segmento nella pagina **Tutti i segmenti**.

1. Vai alla pagina **Segmenti**.

1. Seleziona **Nuovo** > **Crea un valore personalizzato**.

1. Nella pagina del costruttore di segmenti, si definiscono o si compongono le regole. Una regola consiste in una o più condizioni che definiscono un insieme di clienti.

1. Nella sezione **Regola1** scegli un attributo di un'entità in base al quale filtrare i clienti. Sono disponibili due modi per scegliere gli attributi: 
   - Esamina l'elenco delle entità e degli attributi disponibili nel riquadro **Aggiungi alla regola** e seleziona l'icona **+** accanto all'attributo da aggiungere. Scegli se desideri aggiungere l'attributo a una regola esistente o utilizzarlo per creare una nuova regola.
   - Digita il nome dell'attributo nella sezione della regola per visualizzare i suggerimenti corrispondenti.

1. Scegli gli operatori per specificare i valori corrispondenti della condizione. L'attributo può avere uno dei quattro tipi di dati come valore: numerico, stringa, data o booleano. A seconda del tipo di dati dell'attributo, sono disponibili diversi operatori per specificare la condizione. Per i segmenti con conti commerciali, sono disponibili due operatori speciali per includere potenziali gerarchie tra i conti ingeriti. Usa il *figlio di* e il *genitore di* operatori per includere conti correlati. 

1. Seleziona **Aggiungi condizione** per aggiungere più condizioni a una regola. Per creare una regola in base alla regola corrente, seleziona **Aggiungi regola secondaria**.

1. Se una regola utilizza entità diverse da *Cliente*, devi impostare il percorso relazione. Il percorso relazione è necessario per informare il sistema circa le relazioni tramite le quali vuoi accedere all'entità profilo unificata. Seleziona **Imposta percorso relazione** per mappare l'entità selezionata all'entità cliente unificata. Se esiste un solo percorso di relazione possibile, il sistema lo selezionerà automaticamente. Percorsi relazione differenti possono produrre risultati differenti. Ogni regola può avere il proprio percorso di relazione.

   :::image type="content" source="media/relationship-path.png" alt-text="Potenziale percorso di relazione durante la creazione di una regola basata su un'entità mappata all'entità cliente unificata.":::

   Ad esempio, l'entità *eCommerce_eCommercePurchases* nello screenshot ha quattro opzioni da mappare all'entità *Cliente*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Customer
   - eCommerce_eCommercePurchases > Customer
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Customer
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Customer Quando si sceglie l'ultima opzione, possiamo includere gli attributi di tutte le entità elencate nelle condizioni della regola. Probabilmente otterremo meno risultati perché i record di clienti corrispondenti devono far parte di tutte le entità. In questo esempio, hanno acquistato beni attraverso il commercio elettronico *(eCommerce_eCommercePurchases*) in un punto di vendita *(POS_posPurchases*) e partecipano al nostro programma di fedeltà *(loyaltyScheme_loyCustomers*). Quando si sceglie la seconda opzione, possiamo scegliere solo gli attributi dall'entità *eCommerce_eCommerceAcquisti* e *Customer*. Ciò si traduce probabilmente in più profili di clienti risultanti.

1. Se in una regola sono presenti più condizioni, è possibile scegliere l'operatore da cui vengono connesse.  
   - Operatore **AND**: tutte le condizioni devono essere soddisfatte per includere un record nel segmento. Questa opzione è molto utile quando si definiscono condizioni tra entità diverse.
   - Operatore **OR**: una delle condizioni deve essere soddisfatta per includere un record nel segmento. Questa opzione è molto utile quando si definiscono più condizioni per la stessa entità.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regola con due condizioni AND.":::

   Quando si utilizza l'operatore OR, tutte le condizioni devono essere basate su entità incluse nel percorso di relazione.

   - È possibile creare più regole per creare diversi set di record del cliente. Puoi combinare gruppi per includere i clienti richiesti per il tuo caso aziendale. Per creare una nuova regola, selezionare **Aggiungi regola**. In particolare, se non è possibile includere un'entità in una regola a causa del percorso di relazione specificato, è necessario creare una nuova regola per scegliere gli attributi da essa.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Aggiunta di una nuova regola a un segmento e scelta dell'operatore Set.":::

   - Seleziona uno degli operatori impostati: **Unione**, **Intersecazione** o **Eccezione**.

      - **Union** unisce i due gruppi.
      - **Intersect** sovrappone i due gruppi. Solo i dati *comuni* a entrambi i gruppi rimangono nel gruppo unificato.
      - **Ad eccezione di** combina i due gruppi. Solo i dati del gruppo A *non comune* ai dati del gruppo B vengono mantenuti.

1. Per impostazione predefinita, i segmenti generano l'entità di output contenente tutti gli attributi dei profili cliente che corrispondono ai filtri definiti. Se un segmento è basato su entità diverse dall'entità *Cliente* puoi aggiungere più attributi da queste entità all'entità di output. Seleziona **Attributi progetto** per scegliere gli attributi che verranno aggiunti all'entità di output. 

   > [!IMPORTANT]
   > Per i segmenti basati su account aziendali, i dettagli di uno o più contatti di ciascun account dall'entità *ContactProfile* deve essere inclusa nel segmento per consentire a tale segmento di essere attivato o esportato in destinazioni che richiedono informazioni di contatto. Per ulteriori informazioni sull'entità *ContactProfile*, vedi [Mappature semantiche](semantic-mappings.md).
   > Un output di esempio per un segmento basato su account aziendali con attributi previsti dei contatti potrebbe essere simile al seguente: 
   >
   > |ID  |Il nome dell'account  |Ricavi  |Nome contatto  | Ruolo contatto|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [CEO, Responsabile approvvigionamenti]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Esempio di attributi proiettati selezionati nel riquadro laterale da aggiungere all'entità di output.":::
  
   Per esempio: Un segmento si basa su un'entità che contiene i dati di acquisto, che sono collegati all'entità *Cliente* . Il segmento cerca tutti i clienti provenienti dalla Spagna che hanno acquistato merci nell'anno in corso. È possibile scegliere di aggiungere attributi, ad esempio il prezzo delle merci o la data di acquisto, a tutti i record cliente corrispondenti nell'entità di output. Queste informazioni potrebbero essere utili per analizzare le correlazioni stagionali alla spesa totale.

   > [!NOTE]
   > - Gli **attributi di progetto** funzionano solo per le entità che hanno una relazione uno-a-molti con l'entità cliente. Ad esempio, un cliente può avere più abbonamenti.
   > - Se l'attributo che volete proiettare è a più di un salto dall'entità *Cliente* , come definito dalla relazione, questo attributo dovrebbe essere usato in ogni regola della query di segmento che state costruendo. 
   > - Se l'attributo che si vuole proiettare è a un solo salto dall'entità *Cliente* , questo attributo non ha bisogno di essere presente in ogni regola della query di segmento che si sta costruendo. 
   > - Gli **attributi proiettati** sono presi in considerazione quando si usano gli operatori di set.

1. Prima di salvare ed eseguire il segmento, seleziona **Modifica dettagli** accanto al nome del segmento. Fornisci un nome per il tuo segmento e aggiorna il **nome dell'entità Output** suggerito per il segmento. Puoi anche aggiungere una descrizione al segmento.

1. Seleziona **Esegui** per salvare il segmento, attivarlo e iniziare ad elaborare il tuo segmento in base a tutte le regole e condizioni. Altrimenti, sarà salvato come un segmento inattivo.
   
1. Seleziona **Torna a Segmenti** per tornare alla pagina **Segmenti**.

1. Per impostazione predefinita, il segmento viene creato come segmento dinamico. Ciò significa che il segmento viene aggiornato durante gli aggiornamenti del sistema. Per [interrompere l'aggiornamento automatico](segments.md#manage-existing-segments), seleziona l'opzione **Rendi statico**. I segmenti statici possono essere [aggiornati manualmente](segments.md#refresh-segments) in qualsiasi momento.

> [!TIP]
> - Il generatore di segmenti non suggerirà valori validi dalle entità durante l'impostazione degli operatori per le condizioni. Puoi andare a **Dati** > **Entità** e scaricare i dati dell'entità per vedere quali valori sono disponibili.
> - Le condizioni basate sulle date ti consentono di passare da date fisse a un intervallo di date mobile.
> - Se hai più regole per il tuo segmento, la regola che stai modificando ha una linea blu verticale accanto. 
> - È possibile spostare regole e condizioni in altri punti della definizione del segmento. Seleziona [...] accanto a una regola o condizione e scegli come e dove spostarla.
> - I controlli **Undo** e **Redo** nella barra dei comandi ti permettono di annullare le modifiche.

## <a name="quick-segments"></a>Segmenti rapidi

I segmenti rapidi consentono di creare rapidamente segmenti semplici con un singolo operatore per ottenere informazioni più rapide.

1. Nella pagina **Segmenti**, seleziona **Nuovo** > **Crea a partire da**.
   - Seleziona l'opzione **Profili** per creare un segmento basato sull'*entità cliente unificata*.
   - Seleziona l'opzione **Misure** per costruire un segmento intorno alle misure che hai creato in precedenza.
   - Seleziona l'opzione **Intelligenza** per creare un segmento attorno a una delle entità di output generate utilizzando le funzionalità **Previsioni** o **Modelli personalizzati**.

2. Nella finestra di dialogo **Nuovo segmento rapido**, seleziona un attributo dal menu a discesa **Campo**.

3. Il sistema fornirà ulteriori informazioni dettagliate che ti aiuteranno a creare segmenti migliori dei tuoi clienti.
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
