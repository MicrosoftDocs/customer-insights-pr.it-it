---
title: Panoramica delle esportazioni (anteprima)
description: Gestisci le esportazioni per condividere i dati.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: a70aadda4fc0eff3ddb4c89665506762613c291a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194973"
---
# <a name="exports-preview-overview"></a>Panoramica delle esportazioni (anteprima)

 Le esportazioni ti consentono di condividere dati specifici con varie applicazioni. Possono includere profili di clienti, entità, schemi e dettagli del mapping. Ogni esportazione richiede una [connessione, impostata da un amministratore, per gestire l'autenticazione e l'accesso](connections.md). La pagina **Esportazioni** mostra tutte le esportazioni configurate.

## <a name="export-types"></a>Tipi di esportazione

Ci sono due tipi principali di esportazioni:  

- **Esportazioni dati in uscita**: ti consente di esportare qualsiasi tipo di entità disponibile in Customer Insights. Le entità selezionate per l'esportazione vengono esportate con tutti i campi di dati, metadati, schemi e dettagli del mapping.
- **Esportazioni segmenti** ti consente di esportare entità segmento da Customer Insights. I segmenti rappresentano una lista di profili di clienti. Quando configuri l'esportazione, selezioni i campi di dati inclusi, a seconda del sistema di destinazione in cui esporti i dati.

### <a name="export-segments"></a>Esportare segmenti

**Esportazione di segmenti in ambienti per account aziendali (B2B) o singoli consumatori (B2C)**  
La maggior parte delle opzioni di esportazione supporta entrambi i tipi di ambienti. L'esportazione di segmenti in vari sistemi di destinazione comporta requisiti specifici. 

**Esportazioni di segmenti in ambienti per singoli consumatori (B2C)**  
- I segmenti nel contesto degli ambienti per i clienti individuali sono costruiti sull'entità *unificata del profilo del cliente* . Ogni segmento che soddisfa i requisiti dei sistemi di destinazione (per esempio, un indirizzo e-mail) può essere esportato.

**Ambienti di esportazione del segmento per account aziendali (B2B)**  
- I segmenti nel contesto degli ambienti per i conti aziendali sono costruiti sull'entità del *conto* . Per esportare i segmenti di conto così com'è, il sistema di destinazione deve supportare i segmenti di conto puri. Questo è il caso di [LinkedIn](export-linkedin-ads.md) quando si sceglie l'opzione **azienda** durante la definizione dell'esportazione.
- Tutti gli altri sistemi di destinazione richiedono campi dall'entità di contatto. Per assicurarsi che i segmenti di account possano recuperare i dati dai contatti correlati, la definizione del tuo segmento deve proiettare gli attributi dell'entità contatto. Scopri di più su come [configurare i segmenti e gli attributi del progetto](segment-builder.md).

**Limiti alle esportazioni dei segmenti**  
- I sistemi di destinazione di terze parti possono limitare il numero di profili di clienti che puoi esportare. 
- Per i clienti individuali, vedrai il numero effettivo di membri del segmento quando selezioni un segmento per l'esportazione. Riceverai un avviso se un segmento è troppo grande. 
- Per i conti aziendali, vedrai il numero di conti in un segmento; tuttavia, il numero di contatti che possono essere proiettati non appare. In alcuni casi, questo potrebbe portare il segmento esportato a contenere effettivamente più profili di clienti di quelli accettati dal sistema di destinazione. Se si superano i limiti del sistema di destinazione, l'esportazione viene saltata.

## <a name="set-up-a-new-export"></a>Configurare una nuova esportazione

Per impostare o modificare un'esportazione, devi disporre delle connessioni appropriate. Le connessioni dipendono dal tuo [ruolo utente](permissions.md):
- Gli **amministratori** hanno accesso a tutte le connessioni. Possono anche creare nuove connessioni durante la configurazione di un'esportazione.
- I **collaboratori** possono avere accesso a connessioni specifiche. Dipendono dagli amministratori per configurare e condividere le connessioni. L'elenco delle esportazioni mostra ai contributori se possono modificare o visualizzare solo un'esportazione nella colonna **Le tue autorizzazioni**. Per maggiori informazioni, vai a [Permettere ai collaboratori di usare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Gli spettatori** possono solo visualizzare le esportazioni esistenti, non crearle.

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi esportazione**.

1. Nel riquadro **Configura esportazione** seleziona la [connessione](connections.md) da utilizzare.

1. Fornisci i dettagli richiesti e seleziona **Salva** per creare l'esportazione. Per i dettagli richiesti, consulta la documentazione di Customer Insights per la specifica esportazione.

## <a name="manage-existing-exports"></a>Gestire le esportazioni esistenti

Vai a **Dati** > **Esportazioni** per visualizzare le esportazioni, il nome della connessione, il tipo di connessione e lo stato. Tutti i ruoli utente possono visualizzare le esportazioni configurate. Puoi ordinare l'elenco delle esportazioni in base a qualsiasi colonna o utilizzare la casella di ricerca per trovare l'esportazione che desideri gestire.

Seleziona un'esportazione per visualizzare le azioni disponibili.

:::image type="content" source="media/exports_showmore.png" alt-text="Pagina Esportazioni":::

- **Visualizza** o **modifica** l'esportazione. Gli utenti senza autorizzazioni di modifica selezionano **Visualizza** invece di **Modifica** per vedere i dettagli dell'esportazione.
- **Esegui** l'esportazione per esportare i dati più recenti.
- **Crea un duplicato** di un'esportazione.
- **[Pianifica](#schedule-and-run-exports)** l'esportazione.
- **Rimuovi la connessione** per rimuovere la connessione per questa esportazione. Rimuovi non rimuove la connessione, ma disattiva l'esportazione. La colonna **Connessione utilizzata** Nessuna connessione.
- **Rimuovi** l'esportazione.

## <a name="schedule-and-run-exports"></a>Pianifica ed esegui le esportazioni

Ogni esportazione configurata ha una pianificazione di aggiornamento. Durante un aggiornamento, il sistema cerca dati nuovi o aggiornati per includerli in un'esportazione. Per impostazione predefinita, le esportazioni vengono eseguite come parte di ogni [aggiornamento del sistema programmato](system.md#schedule-tab). Puoi personalizzare la pianificazione dell'aggiornamento o disattivarla per eseguire le esportazioni manualmente.

Le pianificazioni delle esportazioni dipendono dallo stato dell'ambiente. Se vi sono aggiornamenti in corso su [dipendenze](system.md#refresh-processes) quando dovrebbe iniziare un'esportazione pianificata, il sistema completerà prima gli aggiornamenti, quindi eseguirà l'esportazione. La colonna **Aggiornata** mostra quando un'esportazione è stata aggiornata l'ultima volta.

### <a name="schedule-exports"></a>Pianifica esportazioni

Definisci le pianificazioni di aggiornamento personalizzate per singole esportazioni o più esportazioni contemporaneamente. Il programma attualmente definito è elencato nella colonna **Pianificazione** dell'elenco delle esportazioni. L'autorizzazione alla modifica della pianificazione è uguale a quello per la [modifica e la definizione delle esportazioni](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona l'esportazione che desideri pianificare.

1. Selezionare **Pianifica**.

1. Nel riquadro **Pianifica esportazione**, imposta **Pianifica esecuzione** su **Attivato** per eseguire l'esportazione automaticamente. Imposta su **Disattivato** per aggiornarla manualmente.

1. Per le esportazioni aggiornate automaticamente, scegli un valore **Ricorrenza** e specificane i dettagli. Il tempo definito si applica a tutte le istanze di una ricorrenza. È il momento in cui un'esportazione dovrebbe iniziare ad aggiornarsi.

1. Seleziona **Salva**.

Quando modifichi la pianificazione per più esportazioni, effettua una selezione in **Mantieni o sostituisci le pianificazioni**:

- **Mantieni singole pianificazioni**: mantiene la pianificazione definita in precedenza per le esportazioni selezionate e le disabilita o le abilita solamente.
- **Definisci una nuova pianificazione per tutte le esportazioni selezionate**: sovrascrive le pianificazioni esistenti delle esportazioni selezionate.

### <a name="run-exports-on-demand"></a>Eseguire le esportazioni su richiesta

Per esportare i dati senza attendere un aggiornamento pianificato, vai a **Dati** > **Esportazioni**.

- Per eseguire tutte le esportazioni, seleziona **Esegui tutto** nella barra dei comandi. Vengono eseguite solo le esportazioni con una pianificazione attiva. Per eseguire un'esportazione non attiva, esegui una singola esportazione.
- Per eseguire una singola esportazione, selezionala nell'elenco quindi scegli **Esegui** nella barra dei comandi.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
