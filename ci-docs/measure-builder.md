---
title: Creare nuove misure con il generatore di misure
description: Crea misure da zero per analizzare le metriche chiave sulla tua attività.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: d003d054145343cc2feeefeeee413810df43185a
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800331"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Usare il generatore di misure per creare misure da zero

Questo articolo spiega come creare una nuova [misura](measures.md) da zero. Il generatore di misure consente di definire i calcoli utilizzando operatori matematici, funzioni di aggregazione e filtri. È possibile creare una misura con attributi di entità correlate all'entità *Cliente* unificata.

La creazione di misure negli ambienti B2C e B2B funziona allo stesso modo. Tuttavia, se hai un ambiente B2B che [utilizza gli account con gerarchie](relationships.md#set-up-account-hierarchies), puoi scegliere di aggregare la misura tra account secondari correlati.

È inoltre possibile creare rapidamente una misura scegliendo da un set di misure predefinite e comunemente utilizzate. Per altre informazioni vedi [usare un modello per creare una misura](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

È possibile creare misure a livello di singoli clienti (attributo cliente, misura cliente) o a livello di azienda/organizzazione (misura aziendale). L'attributo del cliente e la misura del cliente sono due tipi che consentono di monitorare le prestazioni per ogni cliente. Ad esempio, la spesa totale di ciascun cliente. Le misure aziendali ti consentono di monitorare le prestazioni per ogni azienda. Ad esempio, il ricavo totale dell'azienda.

- Attributo del cliente: genera l'output come un nuovo attributo, che viene salvato come una nuova colonna nell'entità generata dal sistema denominata *Customer_Measure*. Quando si aggiorna un attributo del cliente, tutti gli altri attributi del cliente nell'entità *Customer_Measure* vengono aggiornati contemporaneamente. Inoltre, gli attributi del cliente vengono visualizzati nella scheda del profilo del cliente. Una volta eseguito o salvato, l'attributo del cliente non può essere modificato in una misura del cliente.

- Misura del cliente: genera l'output come entità a sé stante e non è possibile modificarla in un attributo del cliente una volta eseguito o salvato. Le misure del cliente non vengono visualizzate nella scheda del profilo del cliente.

- Misura aziendale: genera l'output come entità a sé stante e mostrata nella home page dell'ambiente Customer Insights.

1. Vai in **Misure**.

1. Seleziona **Nuovo** e scegli **Crea un valore personalizzato**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Schermata di configurazione vuota per una misura B2C. " lightbox="media/measure-b2c.png":::

1. Per monitorare le prestazioni a livello aziendale, attiva/disattiva l'opzione **Tipo di misura** sul valore **Livello aziendale**. L'opzione **Livello cliente** è selezionata per impostazione predefinita. L'opzione **Livello cliente** aggiunge automaticamente l'attributo *CustomerId* alle dimensioni mentre l'opzione **Livello aziendale** lo rimuove.

1. Nell'area di configurazione scegli la funzione di aggregazione dal menu a discesa **Seleziona funzione**. Le funzioni di aggregazione includono:
   - **Sum**
   - **Media**
   - **Conteggio**
   - **Numero univoco**
   - **Max**
   - **Min**
   - **First**: usa il primo valore del record di dati
   - **Ultimo**: prende l'ultimo valore aggiunto al record di dati
   - **ArgMax**: trova il record di dati che fornisce il valore massimo da una funzione target
   - **ArgMin**: trova il record di dati che fornisce il valore minimo da una funzione target

1. Seleziona **Aggiungi attributo** per selezionare i dati necessari per creare questa misura.

   1. Seleziona la scheda **Attributi**.
   1. Entità dati: scegli l'entità che include l'attributo che desideri misurare.
   1. Attributo dati: scegli l'attributo che desideri utilizzare nella funzione di aggregazione per calcolare la misura. Puoi selezionare un solo attributo alla volta.
   1. Si può anche selezionare un attributo di dati da una misura esistente selezionando la scheda **Misure** , o si può cercare un'entità o il nome di una misura.
   1. Seleziona **Aggiungi** per aggiungere l'attributo selezionato alla misura.

1. Per creare misure più complesse, puoi aggiungere più attributi o utilizzare operatori matematici nella funzione di misura.

1. Per aggiungere filtri, seleziona **Filtro** nell'area di configurazione. L'applicazione dei filtri utilizzerà solo i record che corrispondono ai filtri per calcolare la misura.
  
   1. Nella sezione **Aggiungi attributo** del riquadro **Filtri** seleziona l'attributo che desideri utilizzare per creare filtri.
   1. Imposta gli operatori di filtro per definire il filtro per ogni attributo selezionato.
   1. Seleziona **Applica** per aggiungere i filtri alla misura.

1. Seleziona **Dimensione** per scegliere più campi da aggiungere come colonne all'entità di output della misura.

   1. Seleziona **Modifica dimensioni** per aggiungere gli attributi di dati in base ai quali raggruppare i valori di misura. Ad esempio, città o sesso.
   > [!TIP]
   > Se hai selezionato **Livello cliente** come **Tipo di misura**, l'attributo *CustomerId* è già stato aggiunto. Se rimuovi l'attributo, l'opzione **Tipo di misura** viene impostata su **Livello aziendale**.
   1. Seleziona **Fatto** per aggiungere le dimensioni alla misura.

1. Se ci sono valori nei tuoi dati che devi sostituire con un intero, seleziona **Regole**. Configura la regola e assicurati di scegliere solo numeri interi come sostituti. Per esempio, sostituite *null* con *0*.

1. Se sono presenti più percorsi tra l'entità di dati mappata e l'entità *Cliente*, è necessario scegliere uno dei [percorsi di relazione tra entità](relationships.md) identificati. I risultati delle misure possono variare a seconda del percorso selezionato.

   1. Seleziona **Percorso di relazione** e scegli il percorso dell'entità che dovrebbe essere usato per identificare la tua misura. Se esiste un solo percorso per l'entità *Cliente*, questo controllo non verrà visualizzato.
   1. Seleziona **Fatto** per applicare la selezione.

1. Per aggiungere altri calcoli per la misura, seleziona **Nuovo calcolo**. È possibile utilizzare solo entità nello stesso percorso entità per nuovi calcoli. Gli altri calcoli verranno visualizzati come nuove colonne nell'entità di output della misura.

1. Seleziona i puntini di sospensione verticali (&vellip;) sul calcolo per **Duplicare**, **Rinominare**, o **Rimuovere** un calcolo da una misura.

1. Nell'area **Anteprima** vedrai lo schema dei dati dell'entità di output della misura, inclusi filtri e dimensioni. L'anteprima reagisce dinamicamente alle modifiche nella configurazione.

1. Seleziona **Modifica dettagli** accanto a Misura senza nome. Specifica un nome per la misura. Facoltativamente, aggiungi [tag](work-with-tags-columns.md#manage-tags) alla misura.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Finestra di dialogo Modifica dettagli.":::

1. Seleziona **Esegui** per calcolare i risultati per la misura configurata. Seleziona **Salva e chiudi** se si desidera mantenere la configurazione corrente ed eseguire la misura in un secondo momento.

1. Vai a **Misure** per vedere la misura appena creata nell'elenco.

# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

È possibile creare misure a livello di singoli account (misura cliente) o a livello di tutti gli account (misura aziendale).

- Misura del cliente: genera l'output come entità a sé stante. Le misure del cliente non vengono visualizzate nella scheda del profilo del cliente.

- Misura aziendale: genera l'output come entità a sé stante e mostrata nella home page dell'ambiente Customer Insights.

1. Vai in **Misure**.

1. Selezionare **Nuovo**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Schermata di configurazione vuota per una misura B2B. ":::

1. Nell'area di configurazione scegli la funzione di aggregazione dal menu a discesa **Seleziona funzione**. Le funzioni di aggregazione includono:
   - **Sum**
   - **Media**
   - **Conteggio**
   - **Numero univoco**
   - **Max**
   - **Min**
   - **First**: usa il primo valore del record di dati
   - **Ultimo**: prende l'ultimo valore aggiunto al record di dati

1. Seleziona **Aggiungi attributo** per selezionare i dati necessari per creare questa misura.

   1. Seleziona la scheda **Attributi**.
   1. Entità dati: scegli l'entità che include l'attributo che desideri misurare.
   1. Attributo dati: scegli l'attributo che desideri utilizzare nella funzione di aggregazione per calcolare la misura. Puoi selezionare un solo attributo alla volta.
   1. Si può anche selezionare un attributo di dati da una misura esistente selezionando la scheda **Misure** , o si può cercare un'entità o il nome di una misura.
   1. Seleziona **Aggiungi** per aggiungere l'attributo selezionato alla misura.

1. Per creare misure più complesse, puoi aggiungere più attributi o utilizzare operatori matematici nella funzione di misura.

1. Per aggiungere filtri, seleziona **Filtro** nell'area di configurazione. L'applicazione dei filtri utilizzerà solo i record che corrispondono ai filtri per calcolare la misura.
  
   1. Nella sezione **Aggiungi attributo** del riquadro **Filtri** seleziona l'attributo che desideri utilizzare per creare filtri.
   1. Imposta gli operatori di filtro per definire il filtro per ogni attributo selezionato.
   1. Seleziona **Applica** per aggiungere i filtri alla misura.

1. Seleziona **Dimensione** per scegliere più campi da aggiungere come colonne all'entità di output della misura.

   1. Seleziona **Modifica dimensioni** per aggiungere gli attributi di dati in base ai quali raggruppare i valori di misura. Ad esempio, città o sesso.
      > [!TIP]
      > Se hai selezionato **Livello cliente** come **Tipo di misura**, l'attributo *CustomerId* è già stato aggiunto. Se rimuovi l'attributo, l'opzione **Tipo di misura** passa a **Livello aziendale**.
   1. Seleziona **Fatto** per aggiungere le dimensioni alla misura.

1. Se ci sono valori nei tuoi dati che devi sostituire con un intero, seleziona **Regole**. Configura la regola e assicurati di scegliere solo numeri interi come sostituti. Per esempio, sostituite *null* con *0*.

1. Puoi usare il toggle **Roll up account secondari** se [usi conti con gerarchie](relationships.md#set-up-account-hierarchies).
   - Se è impostato su **Off**, la misura è calcolata per ogni account. Ogni account ottiene il proprio risultato.
   - Se è impostato su **On**, seleziona **Modifica** per scegliere la gerarchia dell'account in base alle gerarchie acquisite. La misura darà un solo risultato perché è aggregata con i sottoconti.

1. Se sono presenti più percorsi tra l'entità di dati mappata e l'entità *Cliente*, è necessario scegliere uno dei [percorsi di relazione tra entità](relationships.md) identificati. I risultati delle misure possono variare a seconda del percorso selezionato.

   1. Seleziona **Percorso di relazione** e scegli il percorso dell'entità che dovrebbe essere usato per identificare la tua misura. Se esiste un solo percorso per l'entità *Cliente*, questo controllo non verrà visualizzato.
   1. Seleziona **Fatto** per applicare la selezione.

1. Seleziona i puntini di sospensione verticali (&vellip;) sul calcolo per **Duplicare**, **Rinominare**, o **Rimuovere** un calcolo da una misura.

1. Nell'area **Anteprima** vedrai lo schema dei dati dell'entità di output della misura, inclusi filtri e dimensioni. L'anteprima reagisce dinamicamente alle modifiche nella configurazione.

1. Seleziona **Modifica dettagli** accanto a Misura senza nome. Specifica un nome per la misura. Facoltativamente, aggiungi [tag](work-with-tags-columns.md#manage-tags) alla misura.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Finestra di dialogo Modifica dettagli.":::

1. Seleziona **Esegui** per calcolare i risultati per la misura configurata. Seleziona **Salva e chiudi** se si desidera mantenere la configurazione corrente ed eseguire la misura in un secondo momento.

1. Vai a **Misure** per vedere la misura appena creata nell'elenco.
