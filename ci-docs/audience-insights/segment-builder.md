---
title: Creare segmenti con il generatore di segmenti
description: Crea segmenti di clienti per raggrupparli in base a vari attributi.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494505"
---
# <a name="create-segments"></a>Creare segmenti

Definisci filtri complessi per all'entità cliente unificata e le sue entità correlate. Ogni segmento, dopo l'elaborazione, crea una serie di record dei clienti che puoi esportare o su cui puoi intervenire. I segmenti sono gestiti nella pagina **Segmenti**. Puoi [creare nuovi segmenti](#create-a-new-segment) usando il [generatore di segmenti](#segment-builder) oppure [creare segmenti rapidi](#quick-segments) da altre aree dell'app.

## <a name="segment-builder"></a>Generatore di segmenti

L'immagine seguente illustra i vari aspetti del generatore di segmenti. Mostra un segmento che risulta in un gruppo di clienti. I clienti hanno ordinato le merci in un intervallo di tempo specifico e hanno raccolto vari punti premio oppure hanno speso una certa somma di denaro. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi del generatore di segmenti." lightbox="media/segment-builder-overview.png":::

1 - Organizza il segmento con regole e regole secondarie. Ogni regola o regola secondaria è costituita da condizioni. Combina le condizioni con operatori logici

2 - Scegli il [percorso relazione](relationships.md) tra entità che si applica a una regola. Il percorso relazione determina quali attributi possono essere utilizzati in una condizione.

3 - Gestisci regole e regole secondarie. Modifica la posizione di una regola o eliminala.

4 - Aggiungi condizioni e crea il livello di nidificazione appropriato usando regole secondarie.

5 - Applica operazioni di impostazione a regole connesse.

6 - Utilizza il riquadro degli attributi per aggiungere attributi di entità disponibili o creare condizioni in base agli attributi. Il riquadro mostra l'elenco di entità e attributi, in base al percorso relazione selezionato, disponibili per la regola selezionata.

7 - Aggiungi condizioni basate su attributi a regole e regole secondarie esistenti o aggiungile a una nuova regola.

8 - Annulla e ripeti le modifiche durante la creazione del segmento.

L'esempio precedente illustra la capacità di segmentazione. È stato definito un segmento per i clienti che hanno acquistato almeno 500 USD di merce online *e* sono interessati allo sviluppo di software.

## <a name="create-a-new-segment"></a>Creare un nuovo segmento

Un nuovo segmento può essere creato in modi diversi. Questa sezione descrive come creare il tuo segmento da zero. Puoi anche creare un *segmento veloce* basato su entità esistenti o utilizzare i modelli apprendimento automatico per ottenere *segmenti suggeriti*. Ulteriori informazioni: [Panoramica dei segmenti](segments.md).

Durante la creazione di un segmento, puoi salvare una bozza. Verrà salvata come segmento inattivo che non può essere attivato se non è terminato con una configurazione valida.

1. Vai alla pagina **Segmenti**.

1. Seleziona **Nuovo** > **Crea un valore personalizzato**.

1. Nella pagina del generatore di segmenti definisci la prima regola. Una regola è costituita da una o più condizioni e definisce un insieme di clienti.

1. Nella sezione **Regola1** scegli un attributo di un'entità in base al quale filtrare i clienti. Sono disponibili due modi per scegliere gli attributi: 
   - Esamina l'elenco delle entità e degli attributi disponibili nel riquadro **Aggiungi alla regola** e seleziona l'icona **+** accanto all'attributo da aggiungere. Scegli se desideri aggiungere l'attributo a una regola esistente o utilizzarlo per creare una nuova regola.
   - Digita il nome dell'attributo nella sezione della regola per visualizzare i suggerimenti corrispondenti.

1. Scegli gli operatori per specificare i valori corrispondenti della condizione. L'attributo può avere uno dei quattro tipi di dati come valore: numerico, stringa, data o booleano. A seconda del tipo di dati dell'attributo, sono disponibili diversi operatori per specificare la condizione. 

1. Seleziona **Aggiungi condizione** per aggiungere più condizioni a una regola. Per creare una regola in base alla regola corrente, seleziona **Aggiungi regola secondaria**.

1. Se una regola utilizza entità diverse da *Cliente*, devi impostare il percorso relazione. Il percorso relazione è necessario per informare il sistema circa le relazioni tramite le quali vuoi accedere all'entità profilo unificata. Seleziona **Imposta percorso relazione** per mappare l'entità selezionata all'entità cliente unificata. Se esiste un solo percorso di relazione possibile, il sistema lo selezionerà automaticamente. Percorsi relazione differenti possono produrre risultati differenti. Ogni regola può avere il proprio percorso di relazione.

   :::image type="content" source="media/relationship-path.png" alt-text="Potenziale percorso di relazione durante la creazione di una regola basata su un'entità mappata all'entità cliente unificata.":::

   Ad esempio, l'entità *eCommerce_eCommercePurchases* nello screenshot ha quattro opzioni da mappare all'entità *Cliente*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Customer
   - eCommerce_eCommercePurchases > Customer
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Customer
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Customer Quando si sceglie l'ultima opzione, possiamo includere gli attributi di tutte le entità elencate nelle condizioni della regola. Probabilmente otterremo meno risultati perché i record dei clienti corrispondenti devono essere parte di tutte le entità. In questo esempio i clienti hanno effettuato l'acquisto di merci tramite e-commerce (*eCommerce_eCommercePurchases*) presso un POS (*POS_posPurchases*) e partecipano al nostro programma fedeltà (*loyaltyScheme_loyCustomers)*. Quando si sceglie la seconda opzione, possiamo scegliere solo gli attributi dall'entità *eCommerce_eCommerceAcquisti* e *Customer*. Ciò si traduce probabilmente in più profili di clienti risultanti.

1. Se in una regola sono presenti più condizioni, è possibile scegliere l'operatore da cui vengono connesse.

   - Operatore **AND**: tutte le condizioni devono essere soddisfatte per includere un record nel segmento. Questa opzione è molto utile quando si definiscono condizioni tra entità diverse.

   - Operatore **OR**: una delle condizioni deve essere soddisfatta per includere un record nel segmento. Questa opzione è molto utile quando si definiscono più condizioni per la stessa entità.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regola con due condizioni AND.":::

   Quando si utilizza l'operatore OR, tutte le condizioni devono essere basate su entità incluse nel percorso di relazione.

   1. È possibile creare più regole per creare diversi set di record del cliente. Puoi combinare gruppi per includere i clienti richiesti per il tuo caso aziendale. Per creare una nuova regola, selezionare **Aggiungi regola**. In particolare, se non è possibile includere un'entità in una regola a causa del percorso di relazione specificato, è necessario creare una nuova regola per scegliere gli attributi da essa.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Aggiunta di una nuova regola a un segmento e scelta dell'operatore Set.":::

   1. Seleziona uno degli operatori impostati: **Unione**, **Intersecazione** o **Eccezione**.

   - **Union** unisce i due gruppi.

   - **Intersect** sovrappone i due gruppi. Solo i dati che *sono comuni* a entrambi i gruppi vengono mantenuti nel gruppo unificato.

   - **Ad eccezione di** combina i due gruppi. Solo i dati nel gruppo A che *non sono comuni* ai dati nel gruppo B vengono mantenuti.

1. Per impostazione predefinita, i segmenti generano l'entità di output contenente tutti gli attributi dei profili cliente che corrispondono ai filtri definiti. Se un segmento è basato su entità diverse dall'entità *Cliente* puoi aggiungere più attributi da queste entità all'entità di output. Seleziona **Attributi progetto** per scegliere gli attributi che verranno aggiunti all'entità di output.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Esempio di attributi proiettati selezionati nel riquadro laterale da aggiungere all'entità di output.":::
  
   Esempio: un segmento si basa su un'entità che contiene dati di acquisto, correlati all'entità *Customer*. Il segmento cerca tutti i clienti provenienti dalla Spagna che hanno acquistato merci nell'anno in corso. È possibile scegliere di aggiungere attributi, ad esempio il prezzo delle merci o la data di acquisto, a tutti i record cliente corrispondenti nell'entità di output. Queste informazioni potrebbero essere utili per analizzare le correlazioni stagionali alla spesa totale.

   > [!NOTE]
   > - Gli attributi previsti funzionano solo per entità che hanno la relazione uno-a-molti con l'entità cliente. Ad esempio, un cliente può avere più abbonamenti.
   > - È possibile solo proiettare attributi da un'entità che viene utilizzata in ogni regola di query del segmento che si sta creando.
   > - Gli attributi proiettati vengono presi in considerazione quando si utilizzano operatori di gruppo.

1. Prima di salvare ed eseguire il segmento, seleziona **Modifica dettagli** accanto al nome del segmento. Specifica un nome per il tuo segmento e aggiorna il valore **Nome entità di output** suggerito per il segmento. Puoi anche aggiungere una descrizione al segmento.

1. Seleziona **Esegui** per salvare ed elaborare il segmento se tutti i requisiti sono convalidati. In caso contrario, verrà salvato come bozza di segmento inattivo.

1. Seleziona **Torna a Segmenti** per tornare alla pagina **Segmenti**.

> [!TIP]
> - Il generatore di segmenti non suggerirà valori validi dalle entità durante l'impostazione degli operatori per le condizioni. Puoi andare a **Dati** > **Entità** e scaricare i dati dell'entità per vedere quali valori sono disponibili.
> - Le condizioni basate sulle date ti consentono di passare da date fisse a un intervallo di date mobile.
> - Se si hanno più regole per il segmento, verrà visualizzata una barra blu attorno alla regola che si sta modificando.
> - È possibile spostare regole e condizioni in altri punti della definizione del segmento. Seleziona [...] accanto a una regola o condizione e scegli come e dove spostarla.
> - I controlli **Annulla** e **Ripristina** nella barra dei comandi consentono di eseguire il rollback delle modifiche.

## <a name="quick-segments"></a>Segmenti rapidi

I segmenti rapidi consentono di creare rapidamente segmenti semplici con un singolo operatore per ottenere informazioni più rapide.

1. Nella pagina **Segmenti**, seleziona **Nuovo** > **Crea a partire da**.

   - Seleziona l'opzione **Profili** per creare un segmento basato sull'*entità cliente unificata*.
   - Seleziona l'opzione **Misure** per creare un segmento per le misure create in precedenza.
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
