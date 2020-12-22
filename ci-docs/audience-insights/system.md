---
title: Configurazione del sistema in Audience Insight
description: Informazioni sulle impostazioni di sistema nella funzionalità Audience Insights di Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406136"
---
# <a name="system-configuration"></a>Configurazione di sistema

La pagina **Sistema** include quattro schede: **Stato**, **Pianifica**, **Informazioni** e **Generale**.

> [!div class="mx-imgBorder"]
> ![Pagina Sistema](media/system-tabs.png "Pagina Sistema")

## <a name="status-tab"></a>Scheda Stato

La **scheda Stato** consente di tenere traccia dell'avanzamento dell'inserimento dati, delle esportazioni di dati e di numerosi importanti processi di prodotto. Esamina le informazioni in questa scheda per assicurarti del completamento dei processi attivi.

Questa scheda include tabelle di stato per **Origini dati**, **Processi di sistema** e **Preparazione dei dati**. Ogni tabella tiene traccia del **Nome** dell'attività e dell'entità corrispondente, dello **Stato** dell'esecuzione più recente e di quando è stato eseguito l'**Ultimo aggiornamento**.

Visualizza i dettagli delle ultime diverse esecuzioni dell'attività selezionandone il nome.

### <a name="status-types"></a>Tipi di stato

Esistono sei tipi di stato per le attività. I seguenti tipi di stato sono visualizzati anche nelle pagine *Corrispondenza*, *Unione*, *Origini dati*, *Segmenti*, *Misure*, *Arricchimento*, *Impegni* e *Previsioni*:

- **In elaborazione:** l'attività è in corso. Lo stato può cambiare in Riuscito o Non riuscito.
- **Riuscito:** l'attività è stata completata.
- **Ignorata:** l'attività è stata ignorata. Uno o più dei processi downstream da cui dipende questa attività non riescono o vengono ignorati.
- **Errore:** l'elaborazione dell'attività non è riuscita.
- **Annullata:** l'elaborazione è stata annullata dall'utente prima del termine.
- **In coda:** l'elaborazione è in coda e inizierà una volta completate tutte le attività a valle. Per ulteriori informazioni, vedi [Criteri di aggiornamento](#refresh-policies).

### <a name="refresh-policies"></a>Criteri di aggiornamento

Questo elenco mostra i criteri di aggiornamento per ciascuno dei processi principali:

- **Origini dati:** viene eseguita in base alla [pianificazione configurata](#schedule-tab). Non dipende da nessun altro processo. La corrispondenza dipende dal buon esito di questo processo.
- **Corrispondenza:** viene eseguita in base alla [pianificazione configurata](#schedule-tab). Dipende dall'elaborazione delle origini dati utilizzate nella definizione della corrispondenza. L'unione dipende dal buon esito di questo processo.
- **Unione:** viene eseguita in base alla [pianificazione configurata](#schedule-tab). Dipende dal buon esito del processo di corrispondenza. Segmenti, misure, arricchimento, ricerca, impegni, previsioni e preparazione dei dati dipendono dal buon esito di questo processo.
- **Segmenti**: viene eseguito manualmente (aggiornamento singolo) e in base alla [pianificazione configurata](#schedule-tab). Dipende dall'unione. Le informazioni dettagliate dipendono dalla sua elaborazione.
- **Misure**: viene eseguito manualmente (aggiornamento singolo) e in base alla [pianificazione configurata](#schedule-tab). Dipende dall'unione.
- **Impegni**: viene eseguito manualmente (aggiornamento singolo) e in base alla [pianificazione configurata](#schedule-tab). Dipende dall'unione.
- **Arricchimento**: viene eseguito manualmente (aggiornamento singolo) e in base alla [pianificazione configurata](#schedule-tab). Dipende dall'unione.
- **Ricerca**: viene eseguito manualmente (aggiornamento singolo) e in base alla [pianificazione configurata](#schedule-tab). Dipende dall'unione.
- **Preparazione dei dati**: viene eseguita in base alla [pianificazione configurata](#schedule-tab). Dipende dall'unione.
- **Informazioni dettagliate**: viene eseguito manualmente (aggiornamento singolo) e in base alla [pianificazione configurata](#schedule-tab). Dipende dai segmenti.

Seleziona lo stato di un'attività per visualizzare i dettagli sull'avanzamento dell'intero processo. I criteri di aggiornamento di cui sopra possono aiutare a capire cosa puoi fare per affrontare un'attività **Ignorata** o **In coda**.

## <a name="schedule-tab"></a>Scheda Pianifica

Utilizza la scheda **Pianifica** per pianificare gli aggiornamenti automatici di tutte le [origini dati inserite](data-sources.md). Gli aggiornamenti automatici aiutano a garantire che gli aggiornamenti delle tue origini dati si riflettano nei profili cliente unificati.

1. In Audience Insights, vai a **Amministratore** > **Sistema** e seleziona la scheda **Pianifica**.

2. Lo stato predefinito per l'aggiornamento pianificato è **Disattivato**. Per abilitare gli aggiornamenti pianificati, imposta l'interruttore nella parte superiore dello schermo su **Attivato**.

3. Scegli tra aggiornamenti **settimanali** (impostazione predefinita) e **giornalieri**. Se vuoi pianificare gli aggiornamenti settimanali, seleziona uno o più giorni in cui desideri eseguire l'aggiornamento.

4. Imposta il tuo **Fuso orario**, quindi utilizza il menu a discesa **Ora** per impostare i tempi di aggiornamento. Al termine, seleziona **Imposta**. Se desideri pianificare più aggiornamenti in un solo giorno, seleziona **Aggiungi un altro orario**.

5. Seleziona **Salva** per applicare le modifiche.

## <a name="about-tab"></a>Scheda Informazioni

La scheda **Informazioni** contiene il **nome visualizzato** della tua organizzazione, l'**ID ambiente** attivo, l'**area geografica** e il tuo **ID sessione**. Se hai più di un ambiente di lavoro, devi assegnare a ognuno un nome visualizzato facilmente identificabile.

## <a name="general-tab"></a>Scheda Generale

Ci sono due opzioni nella scheda **Generale**, **Lingua** e **Formato Paese/area geografica**.

L'app [supporta varie lingue](supported-languages.md). Per cambiare la lingua preferita, seleziona una **lingua** dal menu a discesa.

Per modificare la formattazione preferita per date, ora e numeri, utilizza il menu a discesa **Formato paese/area geografica**. Un'anteprima della formattazione viene visualizzata in questo campo. Il sistema suggerirà automaticamente una selezione quando scegli una nuova lingua.

Seleziona **Salva** per confermare le selezioni.

## <a name="api-usage-tab"></a>Scheda utilizzo API

Trova i dettagli sull'utilizzo dell'API in tempo reale e scopri quali eventi sono avvenuti in un determinato intervallo di tempo. Per altre informazioni, vedi [Inserimento dati in tempo reale](real-time-data-ingestion.md).
