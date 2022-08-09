---
title: Creare segmenti complessi con il generatore di segmenti
description: Usa il generatore di segmenti per creare segmenti complessi di clienti raggruppandoli in base a vari attributi.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170640"
---
# <a name="create-complex-segments-with-segment-builder"></a>Creare segmenti complessi con il generatore di segmenti

Definisci filtri complessi per all'entità cliente unificata e le sue entità correlate. Ogni segmento, dopo l'elaborazione, crea una serie di record dei clienti che puoi esportare o su cui puoi intervenire.

> [!TIP]
> I segmenti basati su **clienti individuali** includono automaticamente le informazioni di contatto disponibili per i membri del segmento. Negli ambienti per la **contabilità aziendale**, i segmenti sono basati su conti (società o filiali). Per includere le informazioni di contatto in un segmento, usa la funzionalità degli **attributi del progetto** nel generatore di segmenti. Verifica che le fonti dei dati di contatto siano [mappate semanticamente all'entità ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Generatore di segmenti

L'immagine seguente illustra i vari aspetti del generatore di segmenti. Mostra un segmento che risulta in un gruppo di clienti. I clienti ordinavano merci in un lasso di tempo specifico e raccoglievano punti premio o spendevano una certa quantità di denaro.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi del generatore di segmenti." lightbox="media/segment-builder-overview.png":::

1. Organizza il tuo segmento con regole e sottoregole. Ogni regola o regola secondaria è costituita da condizioni. Combina le condizioni con operatori logici.

1. Scegli il [percorso di relazione](relationships.md) tra entità che si applica a una regola. Il percorso relazione determina quali attributi possono essere utilizzati in una condizione.

1. Gestire regole e sottoregole. Modifica la posizione di una regola o eliminala.

1. Aggiungete condizioni e costruite il giusto livello di annidamento usando le sottoregole.

1. Applica le operazioni di set alle regole collegate.

1. Usa il pannello degli attributi per aggiungere gli attributi disponibili dell'entità o per creare condizioni basate sugli attributi. Il riquadro mostra l'elenco di entità e attributi, in base al percorso relazione selezionato, disponibili per la regola selezionata.

1. Aggiungi condizioni basate su attributi a regole e sottoregole esistenti o aggiungile a una nuova regola.

1. Annullare e rifare le modifiche durante la costruzione del segmento.

L'esempio precedente illustra la capacità di segmentazione. È stato definito un segmento per i clienti che hanno acquistato almeno 500 USD di merce online *e* sono interessati allo sviluppo di software.

## <a name="create-a-new-segment-with-segment-builder"></a>Creare un nuovo segmento con il generatore di segmenti

1. Vai a **Segmenti**.

1. Seleziona **Nuovo** > **Crea un valore personalizzato**. Nella pagina del generatore di segmenti, si definiscono o si compongono le regole. Una regola consiste in una o più condizioni che definiscono un insieme di clienti.

1. Seleziona **Modifica dettagli** accanto a Segmento senza titolo. Fornisci un nome per il tuo segmento e aggiorna il **nome dell'entità Output** suggerito per il segmento. Facoltativamente, aggiungi una descrizione e [tag](work-with-tags-columns.md#manage-tags) al segmento.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Finestra di dialogo Modifica dettagli.":::

1. Nella sezione **Rule1** scegli un attributo di un'entità in base alla quale desideri filtrare i clienti. Sono disponibili due modi per scegliere gli attributi:
   - Esamina l'elenco delle entità e degli attributi disponibili nel riquadro **Aggiungi alla regola** e seleziona l'icona **+** accanto all'attributo da aggiungere. Scegli se desideri aggiungere l'attributo a una regola esistente o utilizzarlo per creare una nuova regola.
   - Digita il nome dell'attributo nella sezione della regola per visualizzare i suggerimenti corrispondenti.

1. Scegli gli operatori per specificare i valori corrispondenti della condizione. L'attributo può avere uno dei quattro tipi di dati come valore: numerico, stringa, data o booleano. A seconda del tipo di dati dell'attributo, sono disponibili diversi operatori per specificare la condizione. Per i segmenti con conti commerciali, sono disponibili due operatori speciali per includere potenziali gerarchie tra i conti ingeriti. Usa il *figlio di* e il *genitore di* operatori per includere conti correlati.

1. Seleziona **Aggiungi condizione** per aggiungere più condizioni a una regola. Per creare una regola in base alla regola corrente, seleziona **Aggiungi regola secondaria**.

1. Se una regola utilizza entità diverse dall'entità *Cliente*, seleziona **Imposta percorso relazione** per mappare l'entità selezionata all'entità cliente unificata. Se esiste un solo percorso di relazione possibile, il sistema lo seleziona automaticamente. [Percorsi di relazione](relationships.md#relationship-paths) differenti possono produrre risultati differenti. Ogni regola può avere il proprio percorso di relazione.

   :::image type="content" source="media/relationship-path.png" alt-text="Potenziale percorso di relazione durante la creazione di una regola basata su un'entità mappata all'entità cliente unificata.":::

1. Se in una regola sono presenti più condizioni, scegli l'operatore logico che le connette.  
   - Operatore **AND**: tutte le condizioni devono essere soddisfatte per includere un record nel segmento. Usa questa opzione quando definisci condizioni tra entità diverse.
   - Operatore **OR**: una delle condizioni deve essere soddisfatta per includere un record nel segmento. Usa questa opzione quando definisci più condizioni per la stessa entità.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regola con due condizioni AND.":::

   Quando si utilizza l'operatore OR, tutte le condizioni devono essere basate su entità incluse nel percorso di relazione.

1. Per creare diversi set di record del cliente, crea più regole. Per includere i clienti richiesti per il tuo caso aziendale, combina i gruppi. In particolare, se non puoi includere un'entità in una regola a causa del percorso di relazione specificato, crea una nuova regola per scegliere gli attributi dalla stessa.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Aggiunta di una nuova regola a un segmento e scelta dell'operatore Set.":::

   1. Seleziona **Aggiungi regola**.
   1. Seleziona uno degli operatori impostati: **Unione**, **Intersecazione** o **Eccezione**.

      - **Union** unisce i due gruppi.
      - **Intersect** sovrappone i due gruppi. Solo i dati *comuni* a entrambi i gruppi rimangono nel gruppo unificato.
      - **Ad eccezione di** combina i due gruppi. Solo i dati del gruppo A *non comune* ai dati del gruppo B vengono mantenuti.

1. Per impostazione predefinita, l'entità di output conterrà automaticamente tutti gli attributi dei profili cliente che corrispondono ai filtri definiti. Se un segmento è basato su entità diverse dall'entità *Cliente*, seleziona **Attributi progetto** per aggiungere più attributi da queste entità all'entità di output.

   > [!IMPORTANT]
   > Per i segmenti basati su account aziendali, i dettagli di uno o più contatti di ciascun account dall'entità *ContactProfile* devono essere inclusi nel segmento per consentire a tale segmento di essere attivato o esportato in destinazioni che richiedono informazioni di contatto. Per ulteriori informazioni sull'entità *ContactProfile*, vedi [Mappature semantiche](semantic-mappings.md).
   > Un output di esempio per un segmento basato su account aziendali con attributi previsti dei contatti potrebbe essere simile al seguente:
   >
   > |ID  |Il nome dell'account  |Ricavi  |Nome contatto  | Ruolo contatto|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [CEO, Responsabile approvvigionamenti]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Esempio di attributi proiettati selezionati nel riquadro laterale da aggiungere all'entità di output.":::
  
   Per esempio: Un segmento si basa su un'entità che contiene i dati di acquisto, che sono collegati all'entità *Cliente* . Il segmento cerca tutti i clienti provenienti dalla Spagna che hanno acquistato merci nell'anno in corso. Puoi scegliere di aggiungere attributi, ad esempio il prezzo delle merci o la data di acquisto, a tutti i record cliente corrispondenti nell'entità di output. Queste informazioni potrebbero essere utili per analizzare le correlazioni stagionali alla spesa totale.

   > [!NOTE]
   > - Gli **attributi di progetto** funzionano solo per le entità che hanno una relazione uno-a-molti con l'entità cliente. Ad esempio, un cliente può avere più abbonamenti.
   > - Se l'attributo che volete proiettare è a più di un salto dall'entità *Cliente* , come definito dalla relazione, questo attributo dovrebbe essere usato in ogni regola della query di segmento che state costruendo.
   > - Se l'attributo che si vuole proiettare è a un solo salto dall'entità *Cliente* , questo attributo non ha bisogno di essere presente in ogni regola della query di segmento che si sta costruendo.
   > - Gli **attributi proiettati** sono presi in considerazione quando si usano gli operatori di set.

1. Seleziona **Esegui** per creare il segmento. Seleziona **Salva** se vuoi mantenere la configurazione corrente ed eseguire il segmento in un secondo momento. Viene visualizzata la pagina **Segmenti**.

### <a name="segment-builder-tips"></a>Suggerimenti sul generatore di segmenti

Quando crei un segmento con il generatore di segmenti, tieni presente i seguenti suggerimenti:

- Il generatore di segmenti non suggerirà valori validi dalle entità durante l'impostazione degli operatori per le condizioni. Puoi andare a **Dati** > **Entità** e scaricare i dati dell'entità per vedere quali valori sono disponibili.
- Le condizioni basate sulle date ti consentono di passare da date fisse a un intervallo di date mobile.
- Se hai più regole per il tuo segmento, la regola che stai modificando ha una linea blu verticale accanto.
- È possibile spostare regole e condizioni in altri punti della definizione del segmento. Seleziona i puntini di sospensione verticali (&vellip;) accanto a una regola o una condizione e scegli come e dove spostarla.
- I controlli **Undo** e **Redo** nella barra dei comandi ti permettono di annullare le modifiche.
- Dopo aver creato un segmento, alcuni segmenti ti consentono di [monitorare l'utilizzo del segmento](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Passaggi successivi

[Esporta un segmento](export-destinations.md) ed esplora l'[integrazione della scheda cliente](customer-card-add-in.md) per utilizzare i segmenti in altre applicazioni.

[!INCLUDE [footer-include](includes/footer-banner.md)]
