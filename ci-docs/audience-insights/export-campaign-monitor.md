---
title: Esportare i dati di Customer Insights in Campaign Monitor
description: Scopri come configurare la connessione ed esportare in Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be9c92a087ab4664077d18fe8585bf96715c1535
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228158"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Esportare segmenti in Campaign Monitor (anteprima)

Esporta segmenti di profili cliente unificati in Campaign Monitor e utilizzali per le attività di marketing.

## <a name="prerequisites"></a>Prerequisiti

-   Hai un [account Campaign Monitor](https://www.campaignmonitor.com/) e le corrispondenti credenziali di amministratore.
-   Disponi di [segmenti configurati](segments.md) in Informazioni dettagliate sul gruppo di destinatari.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Puoi esportare fino a 1 milione di profili di clienti per esportazione in Campaign Monitor.
- L'esportazione in Campaign Monitor è limitata ai segmenti.
- Esportare fino a 1 milione di profili di clienti in Campaign Monitor può richiedere fino a 20 minuti per essere completato. 
- Il numero di profili di clienti che puoi esportare in Campaign Monitor dipende dal tuo contratto con Campaign Monitor ed è limitato.

## <a name="set-up-connection-to-campaign-monitor"></a>Impostare la connessione a Campaign Monitor

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Campaign Monitor** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connettiti** per inizializzare la connessione a Campaign Monitor.

1. Seleziona **Autentica con Campaign Monitor** e fornisci le tue credenziali di amministratore per Campaign Monitor.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Campaign Monitor. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Immetti il tuo [**ID elenco Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Genera la chiave API](https://www.campaignmonitor.com/api/getting-started/) dalle **Impostazioni dell'account** in Campaign Monitor prima per visualizzare l'ID elenco API.  

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. È necessario per esportare i segmenti in Campaign Monitor.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Campaign Monitor, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che Campaign Monitor soddisfi eventuali obblighi di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
