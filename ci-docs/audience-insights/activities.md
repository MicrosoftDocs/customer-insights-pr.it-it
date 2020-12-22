---
title: Impegni cliente
description: Definisci gli impegni cliente e visualizzali nella sequenza temporale del cliente.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667234"
---
# <a name="customer-activities"></a>Impegni cliente

Combina gli impegni cliente da [varie origini dati](data-sources.md) in Dynamics 365 Customer Insights per creare la sequenza temporale di un cliente che elenchi gli impegni in ordine cronologico. Puoi includere la sequenza temporale nelle app di interazione con i clienti in Dynamics 365 tramite il [componente aggiuntivo Scheda cliente](customer-card-add-in.md) o in un dashboard di Power BI.

## <a name="define-an-activity"></a>Definire un impegno

Le tue origini dati includono entità con dati transazionali e dati di impegni provenienti da più origini dati. Identifica queste entità e seleziona gli impegni che vuoi visualizzare nella sequenza temporale del cliente. Scegli l'entità che include il tuo impegno o i tuoi impegni di destinazione.

1. In Audience Insights, vai a **Dati** > **Impegni**.

1. Seleziona **Aggiungi impegno**.

   > [!NOTE]
   > Un'entità deve avere almeno un attributo di tipo **Data** per essere incluso in una sequenza temporale del cliente e non puoi aggiungere entità senza campi **Data**. Il controllo **Aggiungi impegno** è disabilitato se non viene trovata tale entità.

1. Nel riquadro **Aggiungi impegno**, imposta i valori per i seguenti campi:

   - **Entità**: seleziona un'entità che include dati transazionali o di impegni.
   - **Chiave primaria**: seleziona il campo che identifica in modo univoco un record. Non deve contenere valori duplicati, valori vuoti o valori mancanti.
   - **Timestamp**: seleziona il campo che rappresenta l'ora di inizio dell'impegno.
   - **Evento**: seleziona il campo che è l'evento per l'impegno.
   - **Indirizzo Web**: seleziona il campo che rappresenta un URL che fornisce informazioni aggiuntive su questo impegno. Ad esempio, il sistema transazionale che genera questo impegno. Questo URL può essere qualsiasi campo di origine dati oppure può essere costruito come un nuovo campo usando una trasformazione Power Query. Questi dati URL verranno archiviati nell'entità Impegno unificata, che può essere consumata a valle utilizzando le API.
   - **Dettagli**: facoltativamente, seleziona il campo che viene aggiunto per ulteriori dettagli.
   - **Icona**: opzionalmente, seleziona l'icona che rappresenta questo impegno.
   - **Tipo di impegno**: definisci il riferimento del tipo di impegno al Common Data Model che meglio descrive la definizione semantica dell'impegno.

1. Nella sezione **Configura relazione**, configura i dettagli per connettere i dati dei tuopi impegni al cliente corrispondente.

   > [!div class="mx-imgBorder"]
   > ![Definire la relazione dell'entità](media/activities-entities-define.png "Definire la relazione dell'entità")

    - **Campo dell'entità Impegno**: seleziona il campo nell'entità impegno che verrà utilizzato per stabilire una relazione con un'altra entità.
    - **Entità cliente**: seleziona l'entità cliente di origine corrispondente con cui l'entità impegno sarà in relazione. Puoi creare una correlazione solo con quelle entità cliente di origine utilizzate nel processo di unificazione dei dati.
    - **Campo entità cliente**: questo campo mostra la chiave primaria dell'entità cliente di origine come selezionata nel processo di mapping. Questo campo chiave primaria nell'entità cliente di origine viene utilizzato per stabilire una relazione con l'entità impegno.
    - **Nome**: se esiste già una relazione tra questa entità impegno e l'entità cliente di origine selezionata, il nome della relazione sarà in sola lettura. Se tale relazione non esiste, verrà creata una nuova relazione con il nome fornito qui.

1. Seleziona **Salva** per applicare le modifiche.

1. Nella pagina **Impegni** seleziona **Esegui**.

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.

## <a name="edit-an-activity"></a>Modifica un impegno

1. In Audience Insights, vai a **Dati** > **Impegni**.

2. Seleziona l'entità impegno che vuoi modificare e seleziona **Modifica**. In alternativa, puoi passare con il mouse sopra la riga dell'entità e selezionare l'icona **Modifica**.

3. Fate clic sull'icona **Modifica**.

4. Nel riquadro **Modifica impegno**, aggiorna i valori e seleziona **Salva**.

5. Nella pagina **Impegni** seleziona **Esegui**.

## <a name="delete-an-activity"></a>Eliminare un impegno

1. In Audience Insights, vai a **Dati** > **Impegni**.

2. Seleziona l'entità impegno che vuoi rimuovere e seleziona **Elimina**. In alternativa, puoi passare con il mouse sopra la riga dell'entità e selezionare l'icona **Elimina**. Inoltre, puoi selezionare più entità impegno da eliminare contemporaneamente.
   > [!div class="mx-imgBorder"]
   > ![Modificare o eliminare la relazione di entità](media/activities-entities-edit-delete.png "Modificare o eliminare la relazione di entità")

3. Seleziona l'icona **Elimina**.

4. Conferma l'eliminazione.
