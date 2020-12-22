---
title: Creare e modificare misure
description: Definisci misure relative al cliente per analizzare e riflettere le prestazioni di determinate aree di business.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406135"
---
# <a name="define-and-manage-measures"></a>Definire e gestire misure

Le **misure** rappresentano gli indicatori di prestazione chiave (KPI) che riflettono le prestazioni e lo stato di aree di business specifiche. Audience Insights offre un'esperienza intuitiva per la creazione di diversi tipi di misure, utilizzando un generatore di query che non richiede di codificare o convalidare le misure manualmente. Puoi tener traccia delle misure aziendali nella pagina **Home**, vedere le misure per clienti specifici sulla **Scheda cliente** e utilizzare le misure per definire i segmenti di clienti nella pagina **Segmenti**.

## <a name="create-a-measure"></a>Creare una misura

Questa sezione illustra come creare una misura da zero. Puoi creare misure con dati provenienti da più origini dati connesse tramite l'entità Cliente. Si applicano alcuni [limiti di servizio](service-limits.md).

1. In Audience Insights, vai a **Misure**.

2. Seleziona **Nuova misura**.

3. Scegli il **tipo** di misura:

   - **Attributo cliente**: un unico campo per cliente che riflette un punteggio, un valore o uno stato per il cliente. Gli attributi del cliente vengono creati come attributi in una nuova entità generata dal sistema chiamata **Customer_Measure**.

   - **Misura del cliente**: informazioni dettagliate sul comportamento del cliente con suddivisione per dimensioni selezionate. Viene generata una nuova entità per ogni misura, potenzialmente con più record per cliente.

   - **Misura aziendale**: tiene traccia delle prestazioni e dello stato dell'azienda. Le misure aziendali possono avere due output diversi: un output numerico che viene visualizzato nella pagina **Home** o una nuova entità che trovi nella pagina **Entità**.

4. Specifica un **Nome** e un **nome visualizzato** facoltativo, quindi seleziona **Avanti**.

5. Nella sezione **Entità**, seleziona la prima entità nell'elenco a discesa. A questo punto, è necessario decidere se sono necessarie altre entità come parte della definizione della misura.

   > [!div class="mx-imgBorder"]
   > ![Definizione misura](media/measure-definition.png "Definizione misura")

   Per aggiungere più entità, seleziona **Aggiungi entità** e seleziona le entità che desideri utilizzare per la misura.

   > [!NOTE]
   > Puoi selezionare solo entità che hanno relazioni con l'entità iniziale. Per ulteriori informazioni sulla definizione delle relazioni, vedi [Relazioni](relationships.md).

6. Facoltativamente, puoi configurare le variabili. Nella sezione **Variabili**, seleziona **Nuova variabile**.

   Le variabili sono calcoli effettuati su ciascuno dei record selezionati. Ad esempio, sommando il punto vendita (POS) e le vendite online per ciascuno dei record dei clienti.

7. Specifica un **nome** per la variabile.

8. Nell'area **Espressione**, scegli un campo con cui iniziare il calcolo.

9. Digita un'espressione nell'area **Espressione** mentre scegli più campi da includere nel calcolo.

   > [!NOTE]
   > Attualmente, solo le espressioni aritmetiche sono supportate. Inoltre, il calcolo delle variabili non è supportato per entità provenienti da diversi [percorsi di entità](relationships.md).

10. Seleziona **Fine**.

11. Nella sezione **Definizione misura**, definirai il modo in cui le entità scelte e le variabili calcolate vengono aggregate in una nuova entità di misura o attributo.

12. Seleziona **Nuova dimensione**. Puoi pensare a una dimensione come a una funzione di *raggruppamento*. L'output dei dati dell'entità o dell'attributo Misura sarà raggruppato per tutte le dimensioni definite.

    > [!div class="mx-imgBorder"]
    > ![Scegliere un ciclo aggregato](media/measures-businessreport-measure-definition2.png "Scegliere un ciclo aggregato")

    Seleziona o inserisci le seguenti informazioni come parte della definizione della tua dimensione:

    - **Entità**: se definisci un'entità Misura, dovrebbe includere almeno un attributo. Se definisci un attributo Misura, includerà solo un attributo per impostazione predefinita. Questa selezione riguarda la scelta dell'entità che include quell'attributo.
    - **Campo**: scegli l'attributo specifico da includere nell'entità Misura o nell'attributo.
    - **Bucket**: sceglie se vuoi aggregare i dati su base giornaliera, mensile o annuale. È una selezione obbligatoria solo se hai selezionato un attributo Tipo data.
    - **Come**: definisce il nome del nuovo campo.
    - **Nome visualizzato**: definisce il nome visualizzato del campo.

    > [!NOTE]
    > La misura aziendale verrà salvata come entità a numero singolo e verrà visualizzata nella pagina **Home** a meno che tu non aggiunga più dimensioni alla tua misura. Dopo aver aggiunto più dimensioni, la misura *non* verrà visualizzata nella pagina **Home**.

13. Facoltativamente, aggiungi funzioni di aggregazione. Qualsiasi aggregazione creata genera un nuovo valore all'interno dell'entità o dell'attributo Misure. Le funzioni di aggregazione supportate sono: **Min**, **Max**, **Media**, **Mediana**, **Somma**, **Numero univoco**, **Primo** (acquisisce il primo record di un valore di dimensione) e **Ultimo** (acquisisce l'ultimo record aggiunto a un valore di dimensione).

14. Seleziona **Salva** per applicare le modifiche alla misura.

## <a name="manage-your-measures"></a>Gestire le misure

Dopo aver creato almeno una misura, vedrai un elenco di misure nella pagina **Misure**.

Troverai informazioni sul tipo di misura, l'autore, la data e l'ora di creazione, la data e l'ora dell'ultima modifica, lo stato (se la misura è attiva, inattiva o non riuscita) e la data e l'ora dell'ultimo aggiornamento. Quando selezioni una misura dall'elenco, puoi visualizzare un'anteprima del suo output.

Per aggiornare tutte le misure contemporaneamente, seleziona **Aggiorna tutto** senza selezionare una misura specifica.

> [!div class="mx-imgBorder"]
> ![Azioni per gestire singole misure](media/measure-actions.png "Azioni per gestire singole misure")

In alternativa, seleziona una misura dall'elenco ed effettua una delle seguenti azioni:

- Seleziona il nome della misura per visualizzarne i dettagli.
- **Modifica** la configurazione della misura.
- **Rinomina** la misura.
- **Elimina** la misura.
- Seleziona i puntini di sospensione (...) e quindi **Aggiorna** per avviare il processo di aggiornamento per la misura.
- Seleziona i puntini di sospensione (...) e quindi **Scarica** per scaricare un file .CSV della misura.

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.

## <a name="next-step"></a>Passaggio successivo

Puoi utilizzare le misure esistenti per creare il tuo primo segmento di clienti nella pagina **Segmenti**. Per ulteriori informazioni, vedi [Segmenti](segments.md).
