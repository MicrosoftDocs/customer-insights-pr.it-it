---
title: Esportare dati di Customer Insights in Microsoft Advertising
description: Scopri come configurare la connessione ed eseguire l'esportazione in Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14479e915dd6ae76e018b59bee5980a600bb222d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647434"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Esporta segmenti in Microsoft Advertising (anteprima)

Esporta i segmenti di Customer Insights in Microsoft Advertising per creare segmenti di pubblico Customer Match. Usa questi segmenti di pubblico per le tue campagne pubblicitarie.

## <a name="prerequisites"></a>Prerequisiti

-   Hai un [account Microsoft Advertising](https://ads.microsoft.com/) e le corrispondenti credenziali di amministratore.
-   Hai accettato i termini di utilizzo di Customer Match. 
-   [Segmenti configurati](segments.md) in Customer Insights.
-   I profili cliente unificati nei segmenti esportati contengono un campo con un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 500'000 profili di clienti per esportazione in Microsoft Advertising.
- L'esportazione in Microsoft Advertising è limitata ai segmenti.
- Esportare fino a 500'000 profili di clienti in Microsoft Advertising può richiedere fino a 10 minuti per essere completato. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Configurare la connessione a Microsoft Advertising

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Microsoft Advertising** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. L'impostazione predefinita è amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione a Microsoft Advertising.

1. Seleziona **Autentica con Microsoft Advertising** e fornisci le tue credenziali di amministratore per Microsoft Advertising.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Microsoft Advertising. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Seleziona i segmenti da esportare. I gruppi di destinatari con corrispondenza con il cliente in Microsoft Advertising vengono creati automaticamente con il nome dei segmenti selezionati per l'esportazione. Ciascun segmento risulterà in un gruppo di destinatari con corrispondenza con il cliente. 

1. Inserisci il tuo **ID cliente Microsoft Advertising e il tuo ID account**. Puoi trovare l'ID cliente (`cid`) e l'ID account (`aid`) nei parametri dell'URL quando sei connesso a Microsoft Advertising.

1. Nella sezione **Corrispondenza dei dati** , nel campo **Email** , seleziona il campo con l'indirizzo e-mail del cliente. È necessario esportare i segmenti in Microsoft Advertising.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Microsoft Advertising, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che Microsoft Advertising soddisfi eventuali obblighi di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
