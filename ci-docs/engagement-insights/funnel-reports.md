---
title: Report grafico a imbuto
description: Come utilizzare i report grafico a imbuto per comprendere come il gruppo di destinatari prende le decisioni.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/17/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 901e7ec50037d66c7c5ceb635d1c6cda6cfff83b
ms.sourcegitcommit: 3bafa27adae113948636b30c7462e0af060c7131
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2021
ms.locfileid: "7498647"
---
# <a name="create-and-manage-funnel-reports"></a>Creare e gestire i report grafico a imbuto

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un report del grafico a imbuto raccoglie informazioni sui passaggi che si verificano durante un percorso del cliente tramite il tuo sito Web o la tua app mobile. Ti aiuta a capire come un destinatario progredisce attraverso un processo e identifica i punti di abbandono. Ad esempio, puoi utilizzare un report grafico a imbuto per identificare i percorsi che i tuoi clienti percorrono prima di effettuare un acquisto. Un report grafico a imbuto fornisce dati per consentire decisioni informate e identificare le aree per l'ottimizzazione e il miglioramento dei processi.

## <a name="create-a-funnel-report"></a>Creare un report grafico a imbuto

Per creare il report grafico a imbuto, specifica i passaggi che desideri includere e l'impegno per ogni passaggio. Un'attività è un [evento](glossary.md) che rappresenta il comportamento dell'utente. Il report grafico a imbuto mostra il numero di utenti che hanno completato ogni passaggio definito. 

1. Vai a **Grafici a imbuto** e seleziona **+Nuovo grafico a imbuto** per avviare un report grafico a imbuto.

1. In **Editor grafico a imbuto**, sotto **Passaggi** seleziona **+Aggiungi passaggio**. 

1. Immetti un nome in **Titolo passaggio**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Nuovo report grafico a imbuto.":::

1. Seleziona un **impegno**. Un impegno registra quando un utente visualizza una pagina (impegno **Visualizza**) o interagisce con il contenuto (impegno **Azione**).

1. Usa **Criteri passaggio** per specificare la dimensione dell'impegno. Le [dimensioni](dimensions.md) sono attributi che possono descrivere, filtrare o raggruppare i dati.

1. Facoltativamente, puoi configurare i passaggi del grafico a imbuto multi-condizione. Seleziona **Aggiungi condizione** per specificare più dimensioni in un passaggio. I criteri aggiuntivi devono utilizzare lo stesso tipo di attività. Puoi scegliere se più condizioni sono collegate a un operatore AND oppure OR.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Grafico a imbuto che mostra la configurazione dei passaggi con passaggi a più condizioni.":::

1. Seleziona **Aggiungi passaggio** finché non completi tutti i passaggi desiderati nel report.

1. Seleziona **Salva**, assegna un nome al report e di nuovo **Salva**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Esempio: report grafico a imbuto società Fourth Coffee

Il seguente scenario mostra un modo di utilizzare un report grafico a imbuto. Un'analista della società Fourth Coffee vuole comprendere l'impatto di una recente promozione sulle tariffe di abbonamento. L'analista crea un report grafico a imbuto per identificare l'impegno del cliente. Inizia quando i clienti arrivano sulla home page della società fino a quando non utilizzano il codice promozionale dell'abbonamento. L'analista crea un report grafico a imbuto con i seguenti passaggi:

Passaggio 1: clienti che arrivano sulla home page   
Passaggio 2: clienti che effettuano un acquisto   
Passaggio 3: clienti che utilizzano il codice promozionale per ottenere uno sconto su un abbonamento   
Passaggio 4: registrazione dell'abbonamento   

:::image type="content" source="media/funnel-report-example.png" alt-text="esempio di report grafico a imbuto.":::
  
Questo grafico a imbuto ti consente di vedere il numero degli utenti che hanno utilizzato il codice promozionale dopo un acquisto una tantum per iscriversi al programma di abbonamento.

### <a name="configure-advanced-settings"></a>Configura le impostazioni avanzate 

I report con grafico a imbuto ti consentono di definire un limite al tempo necessario per completare un grafico a imbuto. Ad esempio, puoi impostare il tempo per completare il grafico a imbuto su quattro giorni. Questa impostazione conterà solo le registrazioni di abbonamenti riuscite che si sono verificate entro quattro giorni da quando un utente ha visitato la home page.

1. Vai a **Grafici a imbuto** per aprire **Libreria grafici a imbuto**.

1. Seleziona un nome per aprire il report. 

1. Nel riquadro **Editor di grafici a imbuto**, seleziona **Impostazioni avanzate**. 

1. Imposta il tempo di completamento grafico a imbuto su **Attivato**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editor di grafici a imbuto che mostra impostazioni avanzate e opzioni per limitare il tempo per completare un grafico a imbuto.":::

1. Scegli l'ora in cui il grafico a imbuto deve essere stato completato nell'elenco a discesa **Imposta limite su**.

1. Seleziona **Salva** per applicare le modifiche.


## <a name="cross-channel-funnel-reports"></a>Report del grafico a imbuto tra canali 

Le informazioni dettagliate sul'interazione possono anche raccogliere dati comportamentali dei clienti sulla tua app mobile. Dopo aver strumentato la tua app mobile con l'[SDK Android](get-started-android.md) o l'[SDK iOS](get-started-ios.md) delle informazioni dettagliate sull'interazione, puoi creare report del grafico a imbuto tra canali. 

### <a name="create-a-cross-channel-funnel-report"></a>Creazione di un report del grafico a imbuto tra canali 

1. Segui i passaggi per [creare un report del grafico a imbuto](#create-a-funnel-report).    

1. Per tenere traccia del modo in cui i tuoi clienti interagiscono con il tuo marchio sia sul tuo sito Web che sull'app mobile o su più siti Web, utilizza il selettore dell'area di lavoro per creare passaggi del grafico a imbuto con i dati di altre aree di lavoro. Nell'**Editor del grafico a imbuto** in **Passaggi** seleziona da quale area di lavoro dovrebbero provenire i dati per il passaggio del grafico a imbuto.

## <a name="manage-funnel-reports"></a>Gestire i report grafico a imbuto

Puoi rivedere i report grafico a imbuto per analizzare i dati, tenere traccia delle prestazioni e raccogliere informazioni dettagliate.

> [!NOTE]
> - I report grafico a imbuto delle informazioni dettagliate sull'interazione attualmente supportano scenari in cui tutti gli utenti nel grafico a imbuto sono anonimi o tutti gli utenti sono autenticati. 
> - I dati storici nei report grafico a imbuto sono disponibili per gli ultimi 30 giorni.

### <a name="view-funnel-reports"></a>Visualizzare report grafico a imbuto

1. Vai a **Grafici a imbuto** per aprire **Libreria grafici a imbuto**.
1. Seleziona un nome per aprire il report.    

### <a name="see-the-data-collected-for-a-report"></a>Visualizzare i dati raccolti per un report   

Per visualizzare le informazioni su una fase

- Indica un passaggio nel report.

:::image type="content" source="media/funnel-step-data.png" alt-text="dati grafico a imbuto.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Modificare l'intervallo di date per il report grafico a imbuto

1. Vai a **Grafici a imbuto** per aprire **Libreria grafici a imbuto**.

1. Seleziona un nome per aprire il report.

1. Apri l'**intervallo di tempo** e seleziona un nuovo periodo di tempo dall'elenco o **Intervallo di date fisso** per specificare un intervallo di date.

## <a name="edit-or-delete-funnel-reports"></a>Modificare o eliminare i report grafico a imbuto

Puoi modificare il nome di un report grafico a imbuto, eliminarlo o modificare i passaggi nel report.

### <a name="rename-or-delete-a-funnel-report"></a>Rinominare o eliminare un report grafico a imbuto

1. Vai a **Grafici a imbuto** per aprire **Libreria grafici a imbuto**. 

1. Seleziona **Altro** accanto al report che desideri modificare e scegli **Modifica nome** o **Elimina**.

### <a name="edit-a-funnel-step"></a>Modificare un passaggio del grafico a imbuto  

1. Vai a **Grafici a imbuto** per aprire **Libreria grafici a imbuto**. 

1. Seleziona un nome per aprire il report.

1. Seleziona il passaggio che desideri modificare.

1. Seleziona **Modifica**

1. Nell'**Editor grafico a imbuto** aggiorna le informazioni che desideri modificare.  

1. Seleziona **Salva**.

### <a name="reorder-a-funnel-step"></a>Riordinare un passaggio del grafico a imbuto

1. Vai a **Grafici a imbuto** per aprire **Libreria grafici a imbuto**. 

1. Seleziona un nome per aprire il report.

1. Seleziona il passaggio che desideri riordinare.

1. Seleziona **Sposta**, poi **Su**, **Giù**, **In alto** o **In basso** per spostare il passaggio.

### <a name="delete-a-funnel-step"></a>Eliminare un passaggio del grafico a imbuto

1. Vai a **Grafici a imbuto** per aprire **Libreria grafici a imbuto**. 

1. Seleziona un nome per aprire il report.

1. Seleziona il passaggio che desideri rimuovere e seleziona **Elimina**.

## <a name="funnel-insights"></a>Informazioni dettagliate sul grafico a imbuto 

Le informazioni dettagliate sull'interazione offrono ora informazioni sul grafico a imbuto. Utilizza le informazioni dettagliate sul grafico a imbuto per ottenere informazioni sul comportamento dei clienti in merito ai passaggi nel report grafico a imbuto. Quando crei e salvi un nuovo report grafico a imbuto, le informazioni dettagliate sul grafico a imbuto vengono generate automaticamente per il report. 

Puoi visualizzare le informazioni dettagliate sul grafico a imbuto dalle seguenti categorie, sia a livello principale sia a livello dei passaggi: 

 - Tasso di conversione 
 - Tempo di transizione 
 - Ora completamento 

Utilizza queste informazioni dettagliate per approfondire il comportamento dei clienti e comprendere meglio i punti di uscita e le conversioni per il tuo report grafico a imbuto. 

Le informazioni dettagliate sul grafico a imbuto vengono ricalcolate ogni 24 ore o quando usi il comando **Salva** per il tuo report grafico a imbuto. 

> [!NOTE]
> Per visualizzare le informazioni dettagliate per il grafico a imbuto, devi salvare il report ogni volta che apporti modifiche. 

