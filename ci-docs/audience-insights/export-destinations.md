---
title: Esportare i dati da Customer Insights
description: Gestisci le esportazioni per condividere i dati.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896148"
---
# <a name="exports-preview-overview"></a>Panoramica delle esportazioni (anteprima)

La pagina **Esportazioni** mostra tutte le esportazioni configurate. Le esportazioni condividono dati specifici con varie applicazioni. Possono includere profili o entità del cliente, schemi e dettagli di mappatura. Ogni esportazione richiede una [connessione, impostata da un amministratore, per gestire l'autenticazione e l'accesso](connections.md).

> [!NOTE]
> Fino a marzo 2021, le esportazioni creavano automaticamente una connessione al servizio corrispondente. Le esportazioni ora richiedono una [connessione, creata e condivisa da un amministratore](connections.md) prima di poterle creare.

Vai a **Dati** > **Esportazioni** per visualizzare la pagina delle esportazioni. Tutti i ruoli utente hanno accesso per visualizzare le esportazioni configurate. Utilizza il campo di ricerca nella barra dei comandi per trovare le esportazioni in base al nome, al nome della connessione o al tipo di connessione.

## <a name="set-up-a-new-export"></a>Configurare una nuova esportazione

Per impostare o modificare un'esportazione, è necessario avere delle connessioni disponibili. Le connessioni dipendono dal tuo [ruolo utente](permissions.md):
- Gli amministratori hanno accesso a tutte le connessioni. Possono anche creare nuove connessioni durante la configurazione di un'esportazione.
- I collaboratori possono avere accesso a connessioni specifiche. Dipendono dagli amministratori per configurare e condividere le connessioni. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).
- I visualizzatori possono solo visualizzare le esportazioni esistenti ma non crearle.

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione** per creare una nuova destinazione di esportazione.

1. Nel riquadro **Imposta esportazione** seleziona la connessione da utilizzare. [Le connessioni](connections.md) sono gestite dagli amministratori. 

1. Fornisci i dettagli richiesti e seleziona **Salva** per creare l'esportazione.

### <a name="edit-an-export"></a>Modificare un'esportazione

1. Seleziona i puntini di sospensione verticali per la destinazione di esportazione che vuoi modificare.

1. Dal menu a discesa seleziona **Modifica**.

1. Modifica i valori che vuoi aggiornare e seleziona **Salva**.

## <a name="view-exports-and-export-details"></a>Visualizzare le esportazioni ed esportare i dettagli

Dopo aver creato le destinazioni di esportazione, vengono elencate in **Dati** > **Esportazioni**. Tutti gli utenti possono vedere quali dati sono condivisi e il loro stato più recente.

1. Vai a **Dati** > **Esportazioni**.

1. Gli utenti senza autorizzazioni di modifica selezionano **Visualizza** invece di **Modifica** per vedere i dettagli dell'esportazione.

1. Questo riquadro laterale mostra la configurazione di questa esportazione. Senza le autorizzazioni di modifica, non è possibile modificare i valori. Seleziona **Chiudi** per tornare alla pagina delle esportazioni.

## <a name="run-exports-on-demand"></a>Eseguire le esportazioni su richiesta

Dopo aver configurato un'esportazione, verrà eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab) fintanto che ha una connessione funzionante.

Per esportare i dati senza attendere un aggiornamento pianificato, vai a **Dati** > **Esportazioni**. è possibile procedere in due modi:

- Per eseguire tutte le esportazioni, seleziona **Esegui tutto** nella barra dei comandi. 
- Per eseguire una singola esportazione, seleziona i puntini di sospensione (...) su un elemento dell'elenco e quindi scegli **Esegui**.

## <a name="remove-an-export"></a>Rimuovere un'esportazione

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona i puntini di sospensione verticali per l'esportazione che vuoi rimuovere.

1. Seleziona **Rimuovi** dal menu a discesa.

1. Conferma la rimozione selezionando **Rimuovi** nella schermata di conferma.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
