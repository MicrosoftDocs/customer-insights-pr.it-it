---
title: Gestire le autorizzazioni utente
description: Informazioni su autorizzazioni e ruoli utente.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f7fcecdea8dc49666dd5c45bf4109c205993f326
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268415"
---
# <a name="user-permissions"></a>Autorizzazioni utente

La pagina **Autorizzazioni** consente di configurare ruoli e autorizzazioni per l'utilizzo di Audience Insights.

Devi disporre delle autorizzazioni di amministratore per visualizzare la pagina. Per accedere alla pagina delle autorizzazioni in Audience Insights, vai a **Amministratore** > **Autorizzazioni**.

Esistono tre tipi di ruoli:

## <a name="viewer"></a>Visualizzatore

- Esplora informazioni dettagliate e segmenti nelle pagine **Home** e **Segmenti**.
- Cerca e filtra i profili cliente utilizzando la pagina **Clienti**. I campi devono essere ricercabili.
- Visualizza ed esplora la pagina **Arricchimento**.
- Esplora ed esporta entità usando la pagina **Entità**.
- Visualizza lo stato dei processi di sistema utilizzando la pagina **Sistema**.
- Esporta segmenti dalla pagina **Segmenti**.
- Installa e usa il dashboard **Power BI Customer Insights**.

## <a name="contributor"></a>Collaboratore

- Tutte le autorizzazioni disponibili per il visualizzatore.
- Carica e trasforma i dati utilizzando la pagina **Origini dati**.
- Completa le sezioni *Unificazione dei dati* (**Mapping**, **Corrispondenza** e **Unione**) che risultano nell'entità profilo cliente unificata.
- Definisci **Relazioni** e **Impegni**.
- Crea segmenti usando la pagina **Segmenti**.
- Crea misure utilizzando la pagina **Misure**.
- Gestisci la configurazione e arricchisci i profili cliente dalla pagina **Arricchimento** (solo per arricchimenti del produttore).

## <a name="administrator"></a>Amministratore

- Tutte le autorizzazioni disponibili per il contributore.
- Modifica le impostazioni nella pagina **Sistema**, inclusa la lingua di lavoro e gli orari di aggiornamento per i processi di sistema.
- Visualizza e aggiungi le autorizzazioni usando la pagina **Autorizzazioni**.
- Imposta le definizioni di ricerca e filtro per la pagina Clienti utilizzando la pagina **Indicizzazione ricerca e filtro** (accessibile tramite la pagina **Clienti**).
- Definisci le destinazioni dei segmenti Dynamics 365 Sales utilizzando la pagina **Destinazioni esportazione**.
- Gestisci la configurazione e arricchisci i profili cliente dalla pagina **Arricchimento** (per tutti gli arricchimenti).
- Installa e utilizza il **componente aggiuntivo Scheda cliente**.
- Aggiungi e usa il **connettore Power Apps**.
- Abilita l'utilizzo delle [API di Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Assegnare ruoli e autorizzazioni

1. In Audience Insights, vai a **Amministratore** > **Autorizzazioni**.

1. Seleziona **Aggiungi utenti** per aprire il riquadro **Aggiungi/Modifica autorizzazioni**.

1. Utilizza il campo **Cerca** per trovare il gruppo o l'utente Azure Active Directory di cui si desidera modificare le autorizzazioni. Seleziona un **Ruolo** da assegnare a quell'utente o gruppo.

1. Seleziona **Salva**. L'ambiente corrente verrà automaticamente condiviso con l'utente o i membri del gruppo di cui hai modificato le autorizzazioni. Gli utenti possono accedere all'app Customer Insights e utilizzarla in base al ruolo specificato.

## <a name="view-current-permissions"></a>Visualizzare le autorizzazioni correnti

In Audience Insights, vai a **Amministratore** > **Autorizzazioni** per vedere quali assegnazioni di ruolo sono attualmente attive.

- La colonna **Tipo** specifica un singolo utente, gruppo o applicazione. Il sistema supporta singoli utenti e gruppi.
- I ruoli sono specificati nella colonna **Ruolo**.
- Seleziona qualsiasi titolo di colonna per ordinare i risultati in base al valore di quella colonna.
- Utilizza il campo **Cerca** nella parte superiore della pagina per individuare utenti specifici.


[!INCLUDE[footer-include](../includes/footer-banner.md)]