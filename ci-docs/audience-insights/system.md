---
title: Configurazione del sistema in Audience Insight
description: Informazioni sulle impostazioni di sistema nella funzionalità Informazioni dettagliate sul gruppo di destinatari di Dynamics 365 Customer Insights.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2c52f7b8a7d41ae4a985745c7b79bbc62f59bb5a
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354238"
---
# <a name="system-configuration"></a>Configurazione di sistema

Per accedere alle configurazioni di sistema nelle informazioni dettagliate sul gruppo di destinatari, nella barra di spostamento a sinistra seleziona **Amministratore** > **Sistema** per visualizzare un elenco di attività e processi di sistema.

La pagina **Sistema** include le seguenti schede:
- [Condizione](#status-tab)
- [Pianificazione](#schedule-tab)
- [Utilizzo API](#api-usage-tab)
- [Informazioni su](#about-tab)
- [GeneralE](#general-tab)
- [Sicurezza](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Schede Impostazioni nella pagina del sistema.":::

## <a name="status-tab"></a>Scheda Stato

La **scheda Stato** consente di tenere traccia dello stato delle attività, dell'inserimento dati, delle esportazioni dei dati e di molti altri importanti processi del prodotto. Rivedi le informazioni in questa scheda per garantire la completezza delle attività e dei processi attivi.

Questa scheda include tabelle con informazioni sullo stato e sull'elaborazione per vari processi. Ogni tabella tiene traccia del **Nome** dell'attività e dell'entità corrispondente, dello **Stato** dell'esecuzione più recente e di quando è stato eseguito l'**Ultimo aggiornamento**. Puoi visualizzare i dettagli delle ultime esecuzioni selezionando il nome dell'attività o del processo. 

Seleziona lo stato accanto all'attività o al processo nella colonna **Stato** per aprire il riquadro **Dettagli stato**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Riquadro dei dettagli dello stato del sistema":::

### <a name="status-definitions"></a>Definizioni stato

Il sistema usa i seguenti stati per attività e processi:

|Condizione  |Definizione  |
|---------|---------|
|Operazione annullata |L'elaborazione è stata annullata dall'utente prima del completamento.   |
|Non inviata   |Si sono verificati errori durante l'inserimento dati.         |
|Errore  |Elaborazione non riuscita.  |
|Non avviato   |L'origine dati non è ancora stata inserita o è ancora in modalità bozza.         |
|In elaborazione  |L'attività o il processo è in corso.  |
|Aggiornamento in corso    |L'inserimento dati è in corso. Puoi annullare questa operazione selezionando **Arresta aggiornamento** nella colonna **Azioni**. L'interruzione dell'aggiornamento di un'origine dati ripristinerà l'ultimo stato di aggiornamento.       |
|Ignorato  |L'attività o il processo è stato ignorato. Uno o più dei processi downstream da cui dipende questa attività non riescono o vengono ignorati.|
|Operazione riuscita  |L'attività o il processo è stato completato. Per le origini dati, indica che i dati sono stati inseriti correttamente se un'ora è menzionata nella colonna **Aggiornato**.|
|In coda | L'elaborazione viene messa in coda e inizierà quando tutte le attività e i processi upstream saranno completati. Per altre informazioni, vedi [Aggiorna processi](#refresh-processes).|

### <a name="refresh-processes"></a>Aggiorna processi

L'aggiornamento di attività e processi viene eseguito in base alla [pianificazione configurata](#schedule-tab). 

|Processo  |Descrizione  |
|---------|---------|
|Attività  |Viene eseguito manualmente (aggiornamento singolo). Dipende dal processo di unione. Le informazioni dettagliate dipendono dalla sua elaborazione.|
|Collegamento analisi |Viene eseguito manualmente (aggiornamento singolo). Dipende dai segmenti.  |
|Preparazione analisi |Viene eseguito manualmente (aggiornamento singolo). Dipende dai segmenti.  |
|Preparazione dei dati   |Dipende dall'unione.   |
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

## <a name="schedule-tab"></a>Scheda Pianifica

Utilizza la scheda **Pianifica** per pianificare gli aggiornamenti automatici di tutte le [origini dati inserite](data-sources.md). Gli aggiornamenti automatici aiutano a garantire che gli aggiornamenti delle tue origini dati si riflettano nei profili cliente unificati.

> [!NOTE]
> Le origini dati gestite dall'utente si aggiornano in base alle proprie pianificazioni. Per pianificare l'aggiornamento delle origini dati gestite dall'utente, configura le impostazioni di aggiornamento su una specifica origine dati dalla pagina **Origine dati**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Impostazioni dell'aggiornamento di un flusso di dati.":::

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Amministratore** > **Sistema** e seleziona la scheda **Pianifica**.

2. Lo stato predefinito per l'aggiornamento pianificato è **Disattivato**. Per abilitare gli aggiornamenti pianificati, imposta l'interruttore nella parte superiore dello schermo su **Attivato**.

3. Scegli tra aggiornamenti **settimanali** (impostazione predefinita) e **giornalieri**. Se vuoi pianificare gli aggiornamenti settimanali, seleziona uno o più giorni in cui desideri eseguire l'aggiornamento.

4. Imposta il tuo **Fuso orario**, quindi utilizza il menu a discesa **Ora** per impostare i tempi di aggiornamento. Al termine, seleziona **Imposta**. Se desideri pianificare più aggiornamenti in un solo giorno, seleziona **Aggiungi un altro orario**.

5. Seleziona **Salva** per applicare le modifiche.

## <a name="about-tab"></a>Scheda Informazioni

La scheda **Informazioni** contiene il **nome visualizzato** della tua organizzazione, l'**ID ambiente** attivo, l'**area geografica** e il tuo **ID sessione**. Se hai più di un ambiente di lavoro, devi assegnare a ognuno un nome visualizzato facilmente identificabile.

## <a name="general-tab"></a>Scheda Generale

È possibile modificare la lingua e il formato del paese/area geografica nella scheda **Generale**.

Customer Insights [supporta molte lingue](/dynamics365/get-started/availability). L'app utilizza la preferenza di lingua per visualizzare elementi come il menu, il testo delle etichette e i messaggi di sistema nella lingua preferita.

I dati e le informazioni importati inseriti manualmente non vengono tradotti.

### <a name="update-the-settings"></a>Aggiorna le impostazioni

Per cambiare la lingua preferita, seleziona una **lingua** dal menu a discesa.

Per modificare la formattazione preferita per date, ora e numeri, utilizza il menu a discesa **Formato paese/area geografica**. Un'anteprima della formattazione viene visualizzata in questo campo. Il sistema suggerirà automaticamente una selezione quando scegli una nuova lingua.

Seleziona **Salva** per confermare le selezioni.

## <a name="api-usage-tab"></a>Scheda utilizzo API

Trova i dettagli sull'utilizzo dell'API in tempo reale e guarda quali eventi si sono verificati in un determinato intervallo di tempo. Scegli l'intervallo di tempo nel menu a discesa **Seleziona un intervallo di tempo**. 

**Utilizzo API** contiene tre sezioni: 
- **Chiamate API** - un grafico che visualizza il numero aggregato di chiamate all'API nel intervallo di tempo selezionato.

- **Trasferimento dati** - un grafico che mostra la quantità di dati trasferiti tramite l'API nella intervallo di tempo selezionata.

-  **Operazioni** - una tabella con righe per ogni operazione API disponibile e dettagli sull'utilizzo delle operazioni. È possibile selezionare il nome di un'operazione per andare al [riferimento API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operazioni che usano l'[inserimento dati in tempo reale](real-time-data-ingestion.md) contengono un pulsante con un simbolo di binocolo per visualizzare l'uso dell'API in tempo reale. Seleziona il pulsante per aprire un riquadro laterale contenente dettagli sull'utilizzo dell'API in tempo reale nell'ambiente corrente.   
   Usa la casella **Raggruppa per** nel riquadro **Utilizzo API in tempo reale** per scegliere come presentare al meglio le tue interazioni in tempo reale. Puoi raggruppare i dati per metodo API, nome qualificato dell'entità (entità inserita), autore creazione (origine dell'evento), risultato (esito positivo o negativo) o codici di errore. I dati sono disponibili come grafico cronologico e come tabella.

## <a name="security-tab"></a>Scheda Sicurezza

La scheda **Sicurezza** consente di collegare e gestire la tua istanza di [Azure Key Vault](/azure/key-vault/general/basic-concepts) all'ambiente.
Il key vault dedicato può essere utilizzato per mettere in scena e utilizzare i segreti nel confine di conformità di un'organizzazione. Le intuizioni del pubblico possono utilizzare i segreti in Azure Key Vault per impostare le [connessioni](connections.md) a sistemi di terze parti.

Per ulteriori informazioni, vedi [Utilizzo dalla propria istanza di Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
