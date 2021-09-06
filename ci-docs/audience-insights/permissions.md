---
title: Gestire le autorizzazioni utente
description: Informazioni su autorizzazioni e ruoli utente.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 430ad902a5a75552243bc4a094361a749364383717278f687dd6e8ef33749c6f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7028319"
---
# <a name="user-permissions"></a>Autorizzazioni utente

La pagina **Autorizzazioni** consente di configurare ruoli e autorizzazioni per l'utilizzo di Informazioni dettagliate sul gruppo di destinatari.

Devi disporre delle autorizzazioni di amministratore per visualizzare la pagina. Per accedere alla pagina delle autorizzazioni in Informazioni dettagliate sul gruppo di destinatari, vai a **Amministratore** > **Autorizzazioni**.

Esistono tre tipi di ruoli:

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
- Completa le sezioni *Unificazione dei dati* (**Mapping**, **Corrispondenza** e **Unione**) che risultano nell'entità profilo cliente unificata.
- Definisci **Relazioni** e **Impegni**.
- Crea segmenti usando la pagina **Segmenti**.
- Crea misure utilizzando la pagina **Misure**.
- Gestisci la configurazione e arricchisci i profili cliente dalla pagina **Arricchimento** (solo per arricchimenti del produttore).
- Gestisci e crea esportazioni in base alle connessioni condivise con i collaboratori. [Ulteriori informazioni su come gli amministratori consentono ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Amministratore

- Tutte le autorizzazioni disponibili per il contributore.
- Modifica le impostazioni nella pagina **Sistema**, inclusa la lingua di lavoro e gli orari di aggiornamento per i processi di sistema.
- Visualizza e aggiungi le autorizzazioni usando la pagina **Autorizzazioni**.
- Imposta le definizioni di ricerca e filtro per la pagina Clienti utilizzando la pagina **Indicizzazione ricerca e filtro** (accessibile tramite la pagina **Clienti**).
- Gestisci le connessioni e consenti loro altri ruoli utente nella pagina **Connessioni**.
- Gestisci la configurazione e arricchisci i profili cliente dalla pagina **Arricchimento** (per tutti gli arricchimenti).
- Gestisci e crea esportazioni nella pagina **Esportazioni**.
- Installa e utilizza il **componente aggiuntivo Scheda cliente**.
- Aggiungi e usa il **connettore Power Apps**.
- Abilita l'utilizzo delle [API di Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Assegnare ruoli e autorizzazioni

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Amministratore** > **Autorizzazioni**.

1. Seleziona **Aggiungi utenti** per aprire il riquadro **Aggiungi/Modifica autorizzazioni**.

1. Utilizza il campo **Cerca** per trovare il gruppo o l'utente Azure Active Directory di cui si desidera modificare le autorizzazioni. Seleziona un **Ruolo** da assegnare a quell'utente o gruppo.

1. Seleziona **Salva**. L'ambiente corrente verrà automaticamente condiviso con l'utente o i membri del gruppo di cui hai modificato le autorizzazioni. Gli utenti possono accedere all'app Customer Insights e utilizzarla in base al ruolo specificato.

## <a name="view-current-permissions"></a>Visualizzare le autorizzazioni correnti

In Informazioni dettagliate sul gruppo di destinatari, vai a **Amministratore** > **Autorizzazioni** per vedere quali assegnazioni di ruolo sono attualmente attive.

- La colonna **Tipo** specifica un singolo utente, gruppo o applicazione. Il sistema supporta singoli utenti e gruppi.
- I ruoli sono specificati nella colonna **Ruolo**.
- Seleziona qualsiasi titolo di colonna per ordinare i risultati in base al valore di quella colonna.
- Utilizza il campo **Cerca** nella parte superiore della pagina per individuare utenti specifici.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
