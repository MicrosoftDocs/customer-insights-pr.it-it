---
title: Creare e gestire misure
description: Definisci misure per analizzare e riflettere le prestazioni della tua attività.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f6be11bd97be71bc0c3a58eaee4d8ed45f535877
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732731"
---
# <a name="define-and-manage-measures"></a>Definire e gestire misure

Le misure ti aiutano a comprendere meglio i comportamenti dei clienti e le prestazioni aziendali. Tengono in considerazione i valori rilevanti dei [profili unificati](data-unification.md). Ad esempio, un'azienda vuole vedere la *spesa totale per cliente* per comprendere la cronologia degli acquisti di un singolo cliente oppure misurare le *vendite totali dell'azienda* per comprendere le entrate a livello aggregato nell'intera attività.  

Le misure vengono create utilizzando il generatore di misure, una piattaforma di query di dati con vari operatori e semplici opzioni di mapping. Ti consente di filtrare i dati, raggruppare i risultati, rilevare [percorsi di relazione tra entità](relationships.md) e visualizzare in anteprima l'output.

Utilizza il generatore di misure per pianificare le attività aziendali eseguendo query sui dati dei clienti ed estrai informazioni dettagliate. Ad esempio, creare una misura di *spesa totale per cliente* e *rendimento totale per cliente* aiuta a identificare un gruppo di clienti con una spesa elevata ma un ritorno elevato. Puoi [creare un segmento](segments.md) per guidare le migliori azioni successive. 

## <a name="build-your-own-measure-from-scratch"></a>Creare la misura da zero

Questa sezione illustra come creare una nuova misura da zero. È possibile costruire una misura con attributi di dati da entità di dati che hanno una relazione impostata per connettersi con l'entità profilo cliente unificato.

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Misure**.

1. Seleziona **Nuovo** e scegli **Crea un valore personalizzato**.

1. Seleziona **Modifica nome** e fornisci un **Nome** per la misura. 

1. Nell'area di configurazione scegli la funzione di aggregazione dal menu a discesa **Seleziona funzione**. Le funzioni di aggregazione includono: 
   - **Sum**
   - **Media**
   - **Conteggio**
   - **Numero univoco**
   - **Max**
   - **Min**
   - **First**: usa il primo valore del record di dati
   - **Ultimo**: prende l'ultimo valore aggiunto al record di dati

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori per i calcoli delle misure.":::

1. Seleziona **Aggiungi attributo** per selezionare i dati necessari per creare questa misura.
   
   1. Seleziona la scheda **Attributi**. 
   1. Entità dati: scegli l'entità che include l'attributo che desideri misurare. 
   1. Attributo dati: scegli l'attributo che desideri utilizzare nella funzione di aggregazione per calcolare la misura. Puoi selezionare un solo attributo alla volta.
   1. Si può anche selezionare un attributo di dati da una misura esistente selezionando la scheda **Misure** , o si può cercare un'entità o il nome di una misura. 
   1. Seleziona **Aggiungi** per aggiungere l'attributo selezionato alla misura.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleziona un attributo da utilizzare nei calcoli.":::

1. Per creare misure più complesse, puoi aggiungere più attributi o utilizzare operatori matematici nella funzione di misura.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Crea una misura complessa con operatori matematici.":::

1. Per aggiungere filtri, seleziona **Filtro** nell'area di configurazione. 
  
   1. Nella sezione **Aggiungi attributo** del riquadro **Filtri** seleziona l'attributo che desideri utilizzare per creare filtri.
   1. Imposta gli operatori di filtro per definire il filtro per ogni attributo selezionato.
   1. Seleziona **Applica** per aggiungere i filtri alla misura.

1. Per aggiungere dimensioni, seleziona **Dimensione** nell'area di configurazione. Le dimensioni verranno visualizzate come colonne nell'entità di output della misura.
 
   1. Seleziona **Modifica dimensioni** per aggiungere gli attributi di dati in base ai quali raggruppare i valori di misura. Ad esempio, città o sesso. Per impostazione predefinita, la dimensione *CustomerID* è selezionata per creare *misure a livello di cliente*. È possibile rimuovere la dimensione predefinita se si desidera creare *misure a livello di azienda*.
   1. Seleziona **Fatto** per aggiungere le dimensioni alla misura.

1. Se ci sono valori nei tuoi dati che devi sostituire con un intero, seleziona **Regole**. Configura la regola e assicurati di scegliere solo numeri interi come sostituti. Per esempio, sostituite *null* con *0*.

1. Se sono presenti più percorsi tra l'entità di dati mappata e l'entità *Cliente*, è necessario scegliere uno dei [percorsi di relazione tra entità](relationships.md) identificati. I risultati delle misure possono variare a seconda del percorso selezionato. 
   
   1. Seleziona **Percorso di relazione** e scegli il percorso dell'entità che dovrebbe essere usato per identificare la tua misura. Se esiste un solo percorso per l'entità *Cliente*, questo controllo non verrà visualizzato.
   1. Seleziona **Fatto** per applicare la selezione. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleziona il percorso dell'entità per la misura.":::

1. Per aggiungere altri calcoli per la misura, seleziona **Nuovo calcolo**. È possibile utilizzare solo entità nello stesso percorso entità per nuovi calcoli. Gli altri calcoli verranno visualizzati come nuove colonne nell'entità di output della misura.

1. Seleziona **...** sul calcolo per **duplicare**, **rinominare** o **rimuovere** un calcolo da una misura.

1. Nell'area **Anteprima** vedrai lo schema dei dati dell'entità di output della misura, inclusi filtri e dimensioni. L'anteprima reagisce dinamicamente alle modifiche nella configurazione.

1. Seleziona **Esegui** per calcolare i risultati per la misura configurata. Seleziona **Salva e chiudi** se si desidera mantenere la configurazione corrente ed eseguire la misura in un secondo momento.

1. Vai a **Misure** per vedere la misura appena creata nell'elenco.

# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Misure**.

1. Seleziona **Nuovo** e scegli **Crea un valore personalizzato**.

1. Seleziona **Modifica nome** e fornisci un **Nome** per la misura. 

1. Nell'area di configurazione scegli la funzione di aggregazione dal menu a discesa **Seleziona funzione**. Le funzioni di aggregazione includono: 
   - **Sum**
   - **Media**
   - **Conteggio**
   - **Numero univoco**
   - **Max**
   - **Min**
   - **First**: usa il primo valore del record di dati
   - **Ultimo**: prende l'ultimo valore aggiunto al record di dati

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori per i calcoli delle misure.":::

1. Seleziona **Aggiungi attributo** per selezionare i dati necessari per creare questa misura.
   
   1. Seleziona la scheda **Attributi**. 
   1. Entità dati: scegli l'entità che include l'attributo che desideri misurare. 
   1. Attributo dati: scegli l'attributo che desideri utilizzare nella funzione di aggregazione per calcolare la misura. Puoi selezionare un solo attributo alla volta.
   1. Si può anche selezionare un attributo di dati da una misura esistente selezionando la scheda **Misure** , o si può cercare un'entità o il nome di una misura. 
   1. Seleziona **Aggiungi** per aggiungere l'attributo selezionato alla misura.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleziona un attributo da utilizzare nei calcoli.":::

1. Per creare misure più complesse, puoi aggiungere più attributi o utilizzare operatori matematici nella funzione di misura.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Crea una misura complessa con operatori matematici.":::

1. Per aggiungere filtri, seleziona **Filtro** nell'area di configurazione. 
  
   1. Nella sezione **Aggiungi attributo** del riquadro **Filtri** seleziona l'attributo che desideri utilizzare per creare filtri.
   1. Imposta gli operatori di filtro per definire il filtro per ogni attributo selezionato.
   1. Seleziona **Applica** per aggiungere i filtri alla misura.

1. Per aggiungere dimensioni, seleziona **Dimensione** nell'area di configurazione. Le dimensioni verranno visualizzate come colonne nell'entità di output della misura.
 
   1. Seleziona **Modifica dimensioni** per aggiungere gli attributi di dati in base ai quali raggruppare i valori di misura. Ad esempio, città o sesso. Per impostazione predefinita, la dimensione *CustomerID* è selezionata per creare *misure a livello di cliente*. È possibile rimuovere la dimensione predefinita se si desidera creare *misure a livello di azienda*.
   1. Seleziona **Fatto** per aggiungere le dimensioni alla misura.

1. Se ci sono valori nei tuoi dati che devi sostituire con un intero, seleziona **Regole**. Configura la regola e assicurati di scegliere solo numeri interi come sostituti. Per esempio, sostituite *null* con *0*.

1. Puoi usare il toggle **Roll up account secondari** se [usi conti con gerarchie](relationships.md#set-up-account-hierarchies).
   - Se è impostato su **Off**, la misura è calcolata per ogni account. Ogni account ottiene il proprio risultato.
   - Se è impostato su **On**, seleziona **Modifica** per scegliere la gerarchia dell'account in base alle gerarchie acquisite. La misura darà un solo risultato perché è aggregata con i sottoconti.

1. Se sono presenti più percorsi tra l'entità di dati mappata e l'entità *Cliente*, è necessario scegliere uno dei [percorsi di relazione tra entità](relationships.md) identificati. I risultati delle misure possono variare a seconda del percorso selezionato. 
   
   1. Seleziona **Percorso di relazione** e scegli il percorso dell'entità che dovrebbe essere usato per identificare la tua misura. Se esiste un solo percorso per l'entità *Cliente*, questo controllo non verrà visualizzato.
   1. Seleziona **Fatto** per applicare la selezione. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleziona il percorso dell'entità per la misura.":::

1. Seleziona **...** sul calcolo per **duplicare**, **rinominare** o **rimuovere** un calcolo da una misura.

1. Nell'area **Anteprima** vedrai lo schema dei dati dell'entità di output della misura, inclusi filtri e dimensioni. L'anteprima reagisce dinamicamente alle modifiche nella configurazione.

1. Seleziona **Esegui** per calcolare i risultati per la misura configurata. Seleziona **Salva e chiudi** se si desidera mantenere la configurazione corrente ed eseguire la misura in un secondo momento.

1. Vai a **Misure** per vedere la misura appena creata nell'elenco.

---

## <a name="use-a-template-to-build-a-measure"></a>Usare un modello per costruire una misura

È possibile utilizzare modelli predefiniti di misure di uso comune per crearli. Descrizioni dettagliate dei modelli e un'esperienza guidata ti aiutano a creare misure efficienti. I modelli si basano sui dati mappati dall'entità *Impegno unificato*. Quindi assicurati di aver configurato [impegni del cliente](activities.md) prima di creare una misura da un modello.

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

È possibile utilizzare modelli predefiniti di misure di uso comune per crearli. Descrizioni dettagliate dei modelli e un'esperienza guidata ti aiutano a creare misure efficienti. I modelli si basano sui dati mappati dall'entità *Impegno unificato*. Quindi assicurati di aver configurato [impegni del cliente](activities.md) prima di creare una misura da un modello.

Modelli di misura disponibili: 
- Valore medio transazione
- Valore transazione totale
- Ricavi medi giornalieri
- Ricavi medi annuali
- Numero di transazioni
- Punti programma fedeltà ottenuti
- Punti programma fedeltà riscattati
- Saldo punti programma fedeltà
- Durata del cliente attivo
- Durata iscrizione al programma fedeltà
- Tempo dall'ultimo acquisto

La procedura seguente descrive i passaggi per creare una nuova misura utilizzando un modello.

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Misure**.

1. Seleziona **Nuovo** e seleziona **Scegli un modello**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Screenshot del menu a discesa durante la creazione di una nuova misura con evidenziazione sul modello.":::

1. Trova il modello che si adatta alle tue esigenze e seleziona **Scegli modello**.

1. Rivedi i dati richiesti e seleziona **Attività iniziali** se disponi di tutti i dati.

1. Nel riquadro **Modifica nome** imposta il nome per la misura e l'entità di output. 

1. Seleziona **Fatto**.

1. Nella sezione **Imposta periodo di tempo** definisci l'intervallo di tempo dei dati da utilizzare. Scegli se vuoi che la nuova misura copra l'intero set di dati selezionando **Sempre** o se vuoi che la misura si concentri su un **Periodo di tempo specifico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot che mostra la sezione del periodo di tempo durante la configurazione di una misura da un modello.":::

1. Nella sezione successiva, seleziona **Aggiungi dati** per scegliere gli impegni e mappare i dati corrispondenti dalla entità *Impegno unificato*.

    1. Passaggio 1 di 2: sotto **Tipo di impegno**, scegli il tipo di entità che desideri utilizzare. Per **Impegni**, seleziona le entità che desideri mappare.
    1. Passaggio 2 di 2: scegli l'attributo dall'entità *Impegno unificato* per il componente richiesto dalla formula. Ad esempio, per valore medio della transazione, è l'attributo che rappresenta il valore della transazione. Per **Timestamp impegno**, scegli l'attributo dall'entità Impegno unificato che rappresenta la data e l'ora dell'impegno.
   
1. Una volta completata la mappatura dei dati, puoi vedere lo stato come **Completato** e il nome degli impegni e degli attributi mappati.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Screenshot di una configurazione del modello di misura completata.":::

1. Ora puoi selezionare **Esegui** per calcolare i risultati della misura. Per perfezionarlo in un secondo momento, seleziona **Salva bozza**.

# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

Questa funzione è disponibile solo per le misure create in ambienti con clienti individuali come target primario.

---

## <a name="manage-your-measures"></a>Gestire le misure

Puoi trovare l'elenco delle misure nella pagina **Misure**.

Troverai informazioni sul tipo di misura, l'autore, la data di creazione e lo stato. Quando selezioni una misura dall'elenco, puoi visualizzare in anteprima l'output e scaricare un file CSV.

Per aggiornare tutte le misure contemporaneamente, seleziona **Aggiorna tutto** senza selezionare una misura specifica.

> [!div class="mx-imgBorder"]
> ![Azioni per gestire singole misure.](media/measure-actions.png "Azioni per gestire singole misure.")

Seleziona una misura dall'elenco per le seguenti opzioni:

- Seleziona il nome della misura per visualizzarne i dettagli.
- **Modifica** la configurazione della misura.
- **Aggiorna** la misura in base ai dati più recenti.
- **Rinomina** la misura.
- **Elimina** la misura.
- **Attiva** o **Disattiva**. Le misure inattive non verranno aggiornate durante un [aggiornamento pianificato](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Passaggio successivo

Puoi utilizzare le misure esistenti per creare [un segmento di clientela](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
