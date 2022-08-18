---
title: Assegna le autorizzazioni utente
description: Informazioni su autorizzazioni e ruoli utente.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245424"
---
# <a name="assign-user-permissions"></a>Assegna le autorizzazioni utente

L'accesso a Customer Insights è limitato agli utenti della tua organizzazione che vengono aggiunti all'applicazione da un amministratore. Un amministratore può aggiungere, modificare o rimuovere utenti. Un utente può essere un singolo utente, gruppo o applicazione. Esistono tre tipi di ruoli che un utente può avere:

## <a name="viewer"></a>Visualizzatore

- Esplora informazioni dettagliate e segmenti nelle pagine **Home** e **Segmenti**.
- Cerca e filtra i profili cliente utilizzando la pagina **Clienti**. I campi devono essere ricercabili.
- Visualizza ed esplora la pagina **Arricchimento**.
- Esplora ed esporta entità usando la pagina **Entità**.
- Visualizza lo stato dei processi di sistema utilizzando la pagina **Sistema**.
- Visualizza le esportazioni nella pagina **Esportazioni**.
- Installa e usa il dashboard **Power BI Customer Insights**.

## <a name="contributor"></a>Collaboratore

- Tutte le autorizzazioni disponibili per il visualizzatore.
- Carica e trasforma i dati utilizzando la pagina **Origini dati**.
- Completa l'**unificazione dei dati** che genera l'entità del profilo cliente unificato.
- Definisce **Relazioni** e **Impegni**.
- Crea segmenti usando la pagina **Segmenti**.
- Crea misure utilizzando la pagina **Misure**.
- Gestisce la configurazione e arricchisce i profili cliente dalla pagina **Arricchimento** (solo per arricchimenti del produttore).
- Gestisce e crea esportazioni in base alle [connessioni condivise con i collaboratori](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Amministratore

- Tutte le autorizzazioni disponibili per il contributore.
- Modifica le impostazioni nella pagina **Sistema**, inclusa la lingua di lavoro, le pianificazioni di aggiornamento per i processi di sistema e i log di diagnostica di esportazione.
- Modifica le impostazioni nella pagina **Sicurezza**, inclusi utenti, chiavi API, collegamenti privati e insieme di credenziali delle chiavi.
- Imposta le definizioni di ricerca e filtro per la pagina Clienti utilizzando la pagina **Indicizzazione ricerca e filtro** (accessibile tramite la pagina **Clienti**).
- Gestisce le connessioni e consente loro altri ruoli utente nella pagina **Connessioni**.
- Gestisce la configurazione e arricchisce i profili cliente dalla pagina **Arricchimento** (per tutti gli arricchimenti).
- Gestisce e crea esportazioni nella pagina **Esportazioni**.
- Installa e utilizza il **componente aggiuntivo Scheda cliente**.
- Aggiunge e usa il **connettore Power Apps**.
- Abilita l'utilizzo delle [API di Customer Insights](apis.md).
- [Assegna la proprietà dell'ambiente](manage-environments.md#change-the-owner-of-an-environment) ad un altro amministratore.

## <a name="admin-owner"></a>Amministratore (proprietario)

- Tutte le autorizzazioni disponibili per l'amministratore.
- [Reimposta ed elimina](manage-environments.md#reset-an-existing-environment-preview) l'ambiente.

## <a name="add-users"></a>Aggiungere utenti

1. Vai ad **Amministratore** > **Sicurezza** e seleziona la scheda **Utenti**.

1. Seleziona **Aggiungi utenti** per aprire il riquadro **Aggiungi/Modifica autorizzazioni**.

1. Utilizza il campo **Cerca** per trovare il gruppo o l'utente Azure Active Directory che vuoi aggiungere. Seleziona un **Ruolo** da assegnare a quell'utente o gruppo.

1. Seleziona **Salva**. L'ambiente corrente viene automaticamente condiviso con l'utente o i membri del gruppo. Gli utenti possono accedere all'app Customer Insights e utilizzarla in base al ruolo specificato.

## <a name="view-current-permissions"></a>Visualizzare le autorizzazioni correnti

Vai ad **Amministratore** > **Sicurezza** e seleziona la scheda **Utenti** per visualizzare l'elenco di utenti attivi e le relative assegnazioni di ruolo. Puoi ordinare l'elenco degli utenti in base a qualsiasi colonna o utilizzare la casella di ricerca per trovare un determinato utente.

## <a name="manage-current-users"></a>Gestire gli utenti correnti

Vai ad **Amministratore** > **Sicurezza** e seleziona la scheda **Utenti**. Puoi ordinare l'elenco degli utenti in base a qualsiasi colonna o utilizzare la casella di ricerca per trovare l'utente che vuoi gestire.

Seleziona un utente per visualizzare le azioni disponibili.

- Seleziona **Modifica** per modificare il ruolo dell'utente in Customer Insights. Seleziona **Salva** per confermare la modifica.
- Seleziona **Rimuovi** per impedire all'utente di accedere a Customer Insights. Per confermare l'eliminazione seleziona **Elimina**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
