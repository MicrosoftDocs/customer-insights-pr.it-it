---
title: Esportare i dati da Customer Insights
description: Gestisci le esportazioni per condividere i dati.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 47bdcc5bb38587063e4414377568943f868107a3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539348"
---
# <a name="exports-preview-overview"></a>Panoramica delle esportazioni (anteprima)

La pagina **Esportazioni** mostra tutte le esportazioni configurate. Le esportazioni condividono dati specifici con varie applicazioni. Possono includere profili o entità del cliente, schemi e dettagli di mappatura. Ogni esportazione richiede una [connessione, impostata da un amministratore, per gestire l'autenticazione e l'accesso](connections.md).

Vai a **Dati** > **Esportazioni** per visualizzare la pagina delle esportazioni. Tutti i ruoli utente possono visualizzare le esportazioni configurate. Utilizza il campo di ricerca nella barra dei comandi per trovare le esportazioni in base al nome, al nome della connessione o al tipo di connessione.

## <a name="set-up-a-new-export"></a>Configurare una nuova esportazione

Per impostare o modificare un'esportazione, è necessario avere delle connessioni disponibili. Le connessioni dipendono dal tuo [ruolo utente](permissions.md):
- Gli amministratori hanno accesso a tutte le connessioni. Possono anche creare nuove connessioni durante la configurazione di un'esportazione.
- I collaboratori possono avere accesso a connessioni specifiche. Dipendono dagli amministratori per configurare e condividere le connessioni. L'elenco delle esportazioni mostra ai contributori se possono modificare o visualizzare solo un'esportazione nella colonna **Le tue autorizzazioni**. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).
- I visualizzatori possono solo visualizzare le esportazioni esistenti ma non crearle.

### <a name="define-a-new-export"></a>Definisci una nuova esportazione

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi esportazione**.

1. Nel riquadro **Imposta esportazione** seleziona la connessione da utilizzare. [Le connessioni](connections.md) sono gestite dagli amministratori. 

1. Fornisci i dettagli richiesti e seleziona **Salva** per creare l'esportazione.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definire una nuova esportazione basata su un'esportazione esistente

1. Vai a **Dati** > **Esportazioni**.

1. Nell'elenco delle esportazioni, seleziona l'esportazione da duplicare.

1. Seleziona **Crea duplicato** nella barra dei comandi per aprire il riquadro **Configura esportazione** con i dettagli dell'esportazione selezionata.

1. Rivedi e adatta l'esportazione e seleziona **Salva** per creare una nuova esportazione.

### <a name="edit-an-export"></a>Modificare un'esportazione

1. Vai a **Dati** > **Esportazioni**.

1. Nell'elenco delle esportazioni, seleziona l'esportazione da modificare.

1. Seleziona **Modifica** nella barra dei comandi.

1. Modifica i valori che vuoi aggiornare e seleziona **Salva**.

## <a name="view-exports-and-export-details"></a>Visualizzare le esportazioni ed esporta i dettagli

Dopo aver creato le destinazioni di esportazione, vengono elencate in **Dati** > **Esportazioni**. Tutti gli utenti possono vedere quali dati sono condivisi e il loro stato più recente.

1. Vai a **Dati** > **Esportazioni**.

1. Gli utenti senza autorizzazioni di modifica selezionano **Visualizza** invece di **Modifica** per vedere i dettagli dell'esportazione.

1. Il riquadro laterale mostra la configurazione di un'esportazione. Senza le autorizzazioni di modifica, non è possibile modificare i valori. Seleziona **Chiudi** per tornare alla pagina delle esportazioni.

## <a name="schedule-and-run-exports"></a>Pianifica ed esegui le esportazioni

Ogni esportazione configurata ha una pianificazione di aggiornamento. Durante un aggiornamento, il sistema cerca dati nuovi o aggiornati per includerli in un'esportazione. Per impostazione predefinita, le esportazioni vengono eseguite come parte di ogni [aggiornamento del sistema programmato](system.md#schedule-tab). Puoi personalizzare la pianificazione dell'aggiornamento o disattivarla per eseguire le esportazioni manualmente.

Le pianificazioni delle esportazioni dipendono dallo stato dell'ambiente. Se vi sono aggiornamenti in corso su [dipendenze](system.md#refresh-policies) quando dovrebbe iniziare un'esportazione pianificata, il sistema completerà prima gli aggiornamenti, quindi eseguirà l'esportazione. Puoi vedere quando un'esportazione è stata aggiornata l'ultima volta nella colonna **Aggiornato**.

### <a name="schedule-exports"></a>Pianifica esportazioni

È possibile definire pianificazioni di aggiornamento personalizzate per singole esportazioni o più esportazioni contemporaneamente. Il programma attualmente definito è elencato nella colonna **Pianificazione** dell'elenco delle esportazioni. L'autorizzazione alla modifica della pianificazione è uguale a quello per la [modifica e la definizione delle esportazioni](export-destinations.md#set-up-a-new-export). 

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona l'esportazione che desideri pianificare.

1. Seleziona **Pianifica** nella barra dei comandi.

1. Nel riquadro **Pianifica esportazione**, imposta **Pianifica esecuzione** su **Attivato** per eseguire l'esportazione automaticamente. Imposta su **Disattivato** per aggiornarla manualmente.

1. Per le esportazioni aggiornate automaticamente, scegli un valore **Ricorrenza** e specificane i dettagli. Il tempo definito si applica a tutte le istanze di una ricorrenza. È il momento in cui un'esportazione dovrebbe iniziare ad aggiornarsi.

1. Applica e attiva le modifiche selezionando **Salva**.

Quando si modifica la pianificazione per più esportazioni, è necessario effettuare una selezione in **Mantieni o sostituisci le pianificazioni**:
- **Mantieni singole pianificazioni**: mantiene la pianificazione definita in precedenza per le esportazioni selezionate e le disabilita o le abilita solamente.
- **Definisci una nuova pianificazione per tutte le esportazioni selezionate**: sovrascrive le pianificazioni esistenti delle esportazioni selezionate.

### <a name="run-exports-on-demand"></a>Eseguire le esportazioni su richiesta

Per esportare i dati senza attendere un aggiornamento pianificato, vai a **Dati** > **Esportazioni**.

- Per eseguire tutte le esportazioni, seleziona **Esegui tutto** nella barra dei comandi. Questa azione eseguirà solo le esportazioni con una pianificazione attiva.
- Per eseguire una singola esportazione, selezionala nell'elenco quindi scegli **Esegui** nella barra dei comandi. È così che esegui le esportazioni senza una pianificazione attiva. 

## <a name="remove-an-export"></a>Rimuovere un'esportazione

1. Vai a **Dati** > **Esportazioni**.

1. Selezionare l'esportazione che si desidera rimuovere.

1. Seleziona **Rimuovi** nella barra dei comandi.

1. Conferma la rimozione selezionando **Rimuovi** nella schermata di conferma.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
