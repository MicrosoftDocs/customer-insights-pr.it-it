---
title: Visualizzare la configurazione di sistema
description: Scopri le impostazioni di sistema in Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246252"
---
# <a name="view-system-configuration"></a>Visualizzare la configurazione di sistema

Visualizza le informazioni sul sistema, lo stato del sistema e l'utilizzo dell'API.

## <a name="view-api-usage"></a>Visualizzare l'utilizzo dell'API

Visualizza i dettagli sull'utilizzo dell'API in tempo reale e scopri quali eventi si sono verificati in un determinato intervallo di tempo.

1. Vai ad **Amministratore** > **Sistema** e seleziona la scheda **Utilizzo API**.

1. **Seleziona un intervallo di tempo** da visualizzare.

   La pagina **Utilizzo API** contiene tre sezioni:

   - **Chiamate API** - un grafico che visualizza il numero aggregato di chiamate all'API nel intervallo di tempo selezionato.
   - **Trasferimento dati** - un grafico che mostra la quantità di dati trasferiti tramite l'API nella intervallo di tempo selezionata.
   - **Operazioni** - una tabella con righe per ogni operazione API disponibile e dettagli sull'utilizzo delle operazioni. Seleziona il nome di un'operazione per accedere al [riferimento API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Le operazioni che usano l'[inserimento dati in tempo reale](real-time-data-ingestion.md) contengono il simbolo di binocolo per visualizzare l'uso dell'API in tempo reale.

   1. Seleziona il binocolo per aprire il riquadro **Utilizzo API in tempo reale** contenente dettagli sull'utilizzo per l'operazione.
   1. **Seleziona un intervallo di tempo** da visualizzare.
   1. Usa la casella **Raggruppa per** per scegliere come presentare al meglio le tue interazioni in tempo reale. Raggruppa i dati in base alle opzioni **Metodo** API, **Nome qualificato entità** (entità inserita), **Creato da** (origine dell'evento), **Risultato** (esito positivo o negativo) o **Codici errore**. I dati sono disponibili come grafico cronologico e come tabella.

## <a name="view-system-information"></a>Visualizzare informazioni sul sistema

Visualizza nome visualizzato, ID, area geografica, tipo e ID sessione dell'ambiente.

1. Vai ad **Amministratore** > **Sistema** e seleziona la scheda **Informazioni**.

1. Per visualizzare la lingua e il paese/l'area geografica, seleziona la scheda **Generale**.

### <a name="update-preferred-language-or-countryregion"></a>Aggiornare la lingua preferita o il paese/l'area geografica

Customer Insights [supporta molte lingue](/dynamics365/get-started/availability). L'app utilizza la preferenza di lingua per visualizzare elementi come il menu, il testo delle etichette e i messaggi di sistema nella lingua preferita.

I dati e le informazioni importati inseriti manualmente non vengono tradotti.

1. Vai ad **Amministratore** > **Sistema** e seleziona la scheda **Generale**.

1. Per cambiare la lingua preferita, seleziona una **lingua** dal menu a discesa.

1. Per modificare la formattazione preferita per date, ora e numeri, utilizza il menu a discesa **Formato paese/area geografica**. Viene visualizzata un'anteprima della formattazione. Il sistema suggerisce automaticamente una selezione quando scegli una nuova lingua.

1. Seleziona **Salva**.

## <a name="view-system-status"></a>Visualizza stato del sistema

Tieni traccia dello stato delle attività, dell'inserimento dati, delle esportazioni dei dati e di molti altri importanti processi del prodotto. Esamina le informazioni per garantire la completezza delle attività e dei processi attivi.

1. Vai ad **Amministratore** > **Sistema** e seleziona la scheda **Stato**.

   Vengono visualizzate le informazioni sullo stato e sull'elaborazione per vari processi. Visualizza il **nome** dell'attività, lo **stato** dell'esecuzione più recente e quando è stato eseguito l'**ultimo aggiornamento**.

1. Per visualizzare i dettagli delle ultime esecuzioni, seleziona il nome dell'attività o del processo.

1. Per visualizzare i dettagli sullo stato di un'attività, seleziona lo stato. Viene visualizzato il riquadro **Dettagli stato**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Riquadro dei dettagli dello stato del sistema":::

1. Per visualizzare i dettagli sullo stato per tutte le attività, seleziona **Intero flusso di lavoro**.

### <a name="status-definitions"></a>Definizioni stato

Il sistema usa i seguenti stati per attività e processi:

|Status  |Definizione  |
|---------|---------|
|Annullati |L'attività o il processo è stato annullato dall'utente prima del completamento.   |
|Non inviata   |Sono stati rilevati errori nell'attività o nel processo.         |
|Errore  |L'attività o il processo non è riuscito.  |
|Non avviato   |L'origine dati non ha ancora dati inseriti o l'attività è ancora in modalità bozza.         |
|In elaborazione  |L'attività o il processo è in corso.  |
|Aggiornamento in corso    |L'attività o il processo è in corso. Per annullare questa operazione, seleziona **Aggiornamento** e **Annulla processo**. L'interruzione dell'aggiornamento di un'attività o di un processo ripristinerà l'ultimo stato di aggiornamento.       |
|Ignorato  |L'attività o il processo è stato ignorato. Uno o più dei processi downstream da cui dipende questa attività non riescono o vengono ignorati.|
|Operazione riuscita  |L'attività o il processo è stato completato. Per le origini dati, indica che i dati sono stati inseriti correttamente se un'ora è menzionata nella colonna **Aggiornato**.|
|In coda | L'elaborazione viene messa in coda e inizierà quando tutte le attività e i processi upstream saranno completati. Per altre informazioni, vedi [Aggiorna processi](#refresh-processes).|

### <a name="refresh-processes"></a>Aggiorna processi

L'aggiornamento di attività e processi viene eseguito in base alla [pianificazione configurata](schedule-refresh.md).

|Processo  |Descrizione  |
|---------|---------|
|Attività  |Viene eseguito manualmente (aggiornamento singolo). Dipende dal processo di unione. Le informazioni dettagliate dipendono dalla sua elaborazione.|
|Collegamento analisi |Viene eseguito manualmente (aggiornamento singolo). Dipende dai segmenti.  |
|Preparazione analisi |Viene eseguito manualmente (aggiornamento singolo). Dipende dai segmenti.  |
|Preparazione dei dati   |Ha bisogno di un'entità per funzionare. Le entità origine dati dipendono dall'importazione. Le entità arricchite dipendono dagli arricchimenti. L'entità Cliente dipende dall'unione.  |
|Origini dati   |Non dipende da nessun altro processo. La corrispondenza dipende dal buon esito di questo processo.  |
|Arricchimenti   |Viene eseguito manualmente (aggiornamento singolo). Dipende dal processo di unione. |
|Esporta destinazioni |Viene eseguito manualmente (aggiornamento singolo). Dipende dai segmenti.  |
|Informazioni dettagliate |Viene eseguito manualmente (aggiornamento singolo). Dipende dai segmenti.  |
|Intelligenza   |Dipende dall'unione.   |
|Corrispondenza |Dipende dall'elaborazione delle origini dati utilizzate nella definizione della corrispondenza.      |
|Misure  |Viene eseguito manualmente (aggiornamento singolo). Dipende dal processo di unione.  |
|Unire   |Dipende dal buon esito del processo di corrispondenza. Segmenti, misure, arricchimento, ricerca, impegni, previsioni e preparazione dei dati dipendono dal buon esito di questo processo.   |
|Profili   |Viene eseguito manualmente (aggiornamento singolo). Dipende dal processo di unione. |
|Ricerca   |Viene eseguito manualmente (aggiornamento singolo). Dipende dal processo di unione. |
|Segmenti  |Viene eseguito manualmente (aggiornamento singolo). Dipende dal processo di unione. Le informazioni dettagliate dipendono dalla sua elaborazione.|
|Di sistema   |Dipende dal buon esito del processo di corrispondenza. Segmenti, misure, arricchimento, ricerca, impegni, previsioni e preparazione dei dati dipendono dal buon esito di questo processo.   |
|Utente  |Viene eseguito manualmente (aggiornamento singolo). Dipende dalle entità.  |

Seleziona lo stato di un processo per vedere i dettagli dello stato dell'intero processo in si trova. I processi di aggiornamento precedenti possono consentirti di individuare le operazioni da eseguire per affrontare un'attività o un processo **Ignorato** o **In coda**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
