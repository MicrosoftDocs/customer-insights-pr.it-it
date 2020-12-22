---
title: Creare e gestire segmenti
description: Crea segmenti di clienti per raggrupparli in base a vari attributi.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406144"
---
# <a name="create-and-manage-segments"></a>Creare e gestire segmenti

I segmenti ti consentono di raggruppare i clienti in base ad attributi demografici, transazionali o comportamentali. Puoi utilizzare i segmenti per indirizzare campagne promozionali, attività di vendita e azioni di assistenza clienti per raggiungere i tuoi obiettivi aziendali.

È possibile definire filtri complessi intorno all'entità Profilo cliente e alle entità correlate. Ogni segmento, dopo l'elaborazione, crea una serie di record dei clienti che puoi esportare o su cui puoi intervenire. Si applicano alcuni [limiti di servizio](service-limits.md).

Salvo diversa indicazione, tutti i segmenti sono **Segmenti dinamici**, che vengono aggiornati in base a una pianificazione ricorrente.

Il seguente esempio illustra la funzionalità di segmentazione. Abbiamo definito un segmento per i clienti che hanno ordinato almeno $500 di merci negli ultimi 90 giorni *e* che sono stati coinvolti in una chiamata servizio clienti che è stata riassegnata.

> [!div class="mx-imgBorder"]
> ![Gruppi multipli](media/segmentation-group1-2.png "Gruppi multipli")

## <a name="create-a-new-segment"></a>Creare un nuovo segmento

I segmenti sono gestiti nella pagina **Segmenti**.

1. In Audience Insights, vai alla pagina **Segmenti**.

2. Seleziona **Nuovo** > **Segmento vuoto**.

3. Nel riquadro **Nuovo segmento**, scegli un tipo di segmento e assegna un **Nome**.

   Facoltativamente, fornisci un nome visualizzato e una descrizione che aiuti a identificare il segmento.

4. Seleziona **Avanti** per andare alla pagina **Generatore di segmenti** in cui puoi definire un gruppo. Un gruppo è un set di clienti.

5. Scegli l'entità che include l'attributo in base al quale vuoi segmentare.

6. Scegli l'attributo in base a cui segmentare. Questo attributo può avere uno dei quattro tipi di valore: numerico, stringa, data o booleano.

7. Scegli un operatore e un valore per l'attributo selezionato.

   > [!div class="mx-imgBorder"]
   > ![Filtro gruppo clienti](media/customer-group-numbers.png "Filtro gruppo clienti")

   |Numero |Definizione  |
   |---------|---------|
   |1     |Entity          |
   |2     |Attributo          |
   |3    |Operatore         |
   |4    |valore         |

8. Se l'entità è connessa all'entità cliente unificata tramite [relazioni](relationships.md), devi definire il percorso della relazione per creare un segmento valido. Aggiungi le entità dal percorso della relazione fino a quando non puoi selezionare l'entità **Cliente: CustomerInsights** dal menu a discesa. Quindi, scegli **Tutti i record** per ogni condizione.

   > [!div class="mx-imgBorder"]
   > ![Percorso di relazione durante la creazione del segmento](media/segments-multiple-relationships.png "Percorso di relazione durante la creazione del segmento")

9. Seleziona **Salva** per salvare il segmento. Il segmento verrà salvato ed elaborato se tutti i requisiti vengono convalidati. Altrimenti, verrà salvato come bozza.

10. Seleziona **Torna a Segmenti** per tornare alla pagina **Segmenti**.

## <a name="manage-existing-segments"></a>Gestire segmenti esistenti

Nella pagina **Segmenti**, puoi visualizzare tutti i segmenti salvati e gestirli.

Ogni segmento è rappresentato da una riga che include informazioni aggiuntive sul segmento.

Puoi ordinare i segmenti in una colonna selezionando l'intestazione della colonna.

Utilizza la casella **Cerca** nell'angolo in alto a destra per filtrare i segmenti.

> [!div class="mx-imgBorder"]
> ![Opzioni per gestire un segmento esistente](media/segments-selected-segment.png "Opzioni per gestire un segmento esistente")

Quando selezioni un segmento sono disponibili le seguenti azioni:

- **Visualizza** i dettagli del segmento, inclusa la tendenza del conteggio dei membri, un'anteprima dei membri del segmento.
- **Modifica** il segmento per modificarne le proprietà.
- **Aggiorna** il segmento per includere gli ultimi dati.
- **Attiva** o **Disattiva** il segmento. I segmenti hanno due possibili stati: attivo o inattivo. Questi stati sono utili quando si modifica un segmento. Per i segmenti inattivi, la definizione del segmento esiste, ma non contiene ancora alcun cliente. Quando attivi un segmento, il suo stato cambia da "inattivo" ad "attivo" e inizia a cercare i clienti che corrispondono alla definizione del segmento. Se un [aggiornamento pianificato](system.md#schedule-tab) è configurato, i segmenti inattivi hanno **Stato** elencato come **Ignorato**, a indicare che non è stato nemmeno tentato un aggiornamento. Quando un segmento inattivo viene attivato, verrà aggiornato e incluso negli aggiornamenti pianificati.
  In alternativa, puoi utilizzare la funzionalità **Pianifica più tardi** nel menu a discesa **Attiva/Disattiva** per specificare una data e un'ora future per l'attivazione e la disattivazione di un particolare segmento.
- **Rinomina** il segmento.
- **Scarica** l'elenco dei membri in un file .CSV.
- L'opzione **Aggiungi a** invia l'elenco degli ID cliente nel segmento per l'elaborazione in un'altra applicazione.
- **Elimina** il segmento.

## <a name="refresh-segments"></a>Aggiornare i segmenti

Puoi aggiornare tutti i segmenti contemporaneamente selezionando **Aggiorna tutto** nella pagina **Segmenti** oppure puoi aggiornare uno o più segmenti quando li selezioni e scegli **Aggiorna** dalle opzioni. In alternativa, puoi configurare un aggiornamento ricorrente in **Amministratore** > **Sistema** > **Pianifica**.

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.

## <a name="download-and-export-segments"></a>Scaricare ed esportare segmenti

Puoi scaricare i tuoi segmenti in un file CSV o esportarli in Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Scaricare i segmenti in un file CSV

1. In Audience Insights, vai alla pagina **Segmenti**.

2. Seleziona i puntini di sospensione nel riquadro di un segmento specifico.

3. Seleziona **Scarica come CSV** dall'elenco a discesa delle azioni.

### <a name="export-segments-to-dynamics-365-sales"></a>Esportare segmenti in Dynamics 365 Sales

Prima di esportare segmenti in Dynamics 365 Sales, un amministratore deve [creare la destinazione di esportazione](export-destinations.md) per Dynamics 365 Sales.

1. In Audience Insights, vai alla pagina **Segmenti**.

2. Seleziona i puntini di sospensione nel riquadro di un segmento specifico.

3. Seleziona **Aggiungi a** dall'elenco a discesa delle azioni e seleziona la destinazione di esportazione su cui vuoi inicare i dati.

## <a name="draft-mode-for-segments"></a>Modalità bozza per i segmenti

Se non sono soddisfatti tutti i requisiti per elaborare un segmento, è possibile salvare il segmento come bozza e accedervi dalla pagina **Segmenti**.

Verrà salvato come segmento inattivo e non potrà essere attivato fino a quando non sarà valido.

## <a name="add-more-conditions-to-a-group"></a>Aggiungere più condizioni a un gruppo

Per aggiungere più condizioni a un gruppo, è possibile utilizzare due operatori logici:

- Operatore **AND**: entrambe le condizioni devono essere soddisfatte come parte del processo di segmentazione. Questa opzione è molto utile quando si definiscono condizioni tra entità diverse.

- Operatore **OR**: una delle condizioni deve essere soddisfatta come parte del processo di segmentazione. Questa opzione è molto utile quando si definiscono più condizioni per la stessa entità.

   > [!div class="mx-imgBorder"]
   > ![Operatore OR in cui è necessario soddisfare una delle condizioni](media/segmentation-either-condition.png "Operatore OR in cui è necessario soddisfare una delle condizioni")

Al momento è possibile nidificare un operatore **OR** sotto un operatore **AND**, ma non il contrario.

## <a name="combine-multiple-groups"></a>Combinare più gruppi

Ogni gruppo produce un set specifico di clienti. Puoi combinare questi gruppi per includere i clienti obbligatori per il tuo business case.

1. In Audience Insights, vai alla pagina **Segmenti** e seleziona un segmento.

2. Seleziona **Aggiungi gruppo**.

   > [!div class="mx-imgBorder"]
   > ![Aggiungi gruppo per gruppo clienti](media/customer-group-add-group.png "Aggiungi gruppo per gruppo clienti")

3. Seleziona uno dei seguenti operatori di set: **Unione**, **Intersezione** o **Eccezione**.

   > [!div class="mx-imgBorder"]
   > ![Aggiungi Union per gruppo clienti](media/customer-group-union.png "Aggiungi Union per gruppo clienti")

   Seleziona un operatore di set per definire un nuovo gruppo. Salva i differenti gruppi per determinare quali dati vengono conservati:

   - **Union** unisce i due gruppi.

   - **Intersect** sovrappone i due gruppi. Solo i dati che *sono comuni* a entrambi i gruppi vengono mantenuti nel gruppo unificato.

   - **Ad eccezione di** combina i due gruppi. Solo i dati nel gruppo A che *non sono comuni* ai dati nel gruppo B vengono mantenuti.

## <a name="view-processing-history-and-segment-members"></a>Visualizzare la cronologia di elaborazione e i membri del segmento

Puoi visualizzare i dati consolidati di un segmento esaminandone i dettagli.

Nella pagina **Segmenti** seleziona il segmento da esaminare.

La parte superiore della pagina include un grafo di tendenza che visualizza le modifiche nel numero di membri. Passa il mouse sopra i punti dati per vedere il numero di membri a una data specifica.

Puoi aggiornare l'intervallo di tempo della visualizzazione.

> [!div class="mx-imgBorder"]
> ![Intervallo di tempo segmento](media/segment-time-range.png "Intervallo di tempo segmento")

La parte inferiore contiene un elenco dei membri del segmento.

> [!NOTE]
> I campi che compaiono in questo elenco si basano sugli attributi delle entità del segmento.
>
>L'elenco è un'anteprima dei membri del segmento corrispondenti e mostra i primi 100 record del segmento in modo da poterlo valutare rapidamente e rivederne le definizioni se necessario. Per vedere tutti i record corrispondenti, è necessario [esportare il segmento](export-destinations.md).

## <a name="quick-segments"></a>Segmenti rapidi

Oltre al generatore di segmenti, esiste un altro percorso per la creazione di segmenti. I segmenti rapidi consentono di creare segmenti semplici (con un solo operatore) in modo rapido e con informazioni dettagliate immediate.

1. Nella pagina **Segmenti**, seleziona **Nuovo** > **Crea rapidamente da**.

   - Seleziona l'opzione **Profili** per creare un segmento basato sull'entità cliente unificata.
   - Seleziona l'opzione **Misure** per creare un segmento intorno a ciascun tipo di misure attributo cliente che hai precedentemente creato nella pagina **Misure**.
   - Seleziona l'opzione **Intelligenza** per creare un segmento attorno a una delle entità di output generate utilizzando le funzionalità **Previsioni** o **Modelli personalizzati**.

2. Nella finestra di dialogo **Nuovo segmento rapido**, seleziona un attributo dal menu a discesa **Campo**.

3. Il sistema fornirà alcune informazioni dettagliate aggiuntive che ti aiuteranno a creare segmenti migliori dei tuoi clienti.
   - Per i campi di categoria, vengono visualizzati i primi 10 conteggi dei clienti. Scegli un **valore** e seleziona **Revisione**.

   - Per un attributo numerico, il sistema mostrerà quale valore dell'attributo rientra nel percentile di ciascun cliente. Scegli un **operatore** e un **valore**, quindi seleziona **Revisione**.

4. Il sistema fornirà una **dimensione stimata del segmento**. Puoi scegliere se generare il segmento che hai definito o modificarlo prima per ottenere una dimensione del segmento diversa.

    > [!div class="mx-imgBorder"]
    > ![Nome e stima per un segmento rapido](media/quick-segment-name.png "Nome e stima per un segmento rapido")

5. Inserisci un **nome** per il segmento. Se lo desideri, inserisci un **nome visualizzato**.

6. Seleziona **Salva** per creare il segmento.

7. Al termine dell'elaborazione del segmento, puoi visualizzarlo come qualsiasi altro segmento che hai creato.

Per i seguenti scenari, si consiglia di utilizzare il generatore di segmenti anziché la funzionalità dei segmenti consigliati:

- Creazione di segmenti con filtri su campi di categoria in cui l'operatore è diverso dall'operatore **Is**
- Creazione di segmenti con filtri su campi numerici in cui l'operatore è diverso dagli operatori **Between**, **Greater than** e **Less than**
- Creazione di segmenti con filtri nei campi del tipo di data

## <a name="next-steps"></a>Passaggi successivi

[Esporta un segmento](export-destinations.md) ed esplora [Scheda cliente](customer-card-add-in.md) e [Connettori](export-power-bi.md) per ottenere informazioni dettagliate a livello di cliente.
