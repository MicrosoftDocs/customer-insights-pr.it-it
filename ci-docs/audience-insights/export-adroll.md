---
title: Esportare dati di Customer Insights in AdRoll
description: Scopri come configurare la connessione ed esportare in AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a318750077c71a17e5a47c40722f6153e6640f3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227625"
---
# <a name="export-segments-to-adroll-preview"></a>Esportare segmenti in AdRoll (anteprima)

Esporta i segmenti dei profili cliente unificati in AdRoll e utilizzali per la pubblicità. 

## <a name="prerequisites-for-a-connection"></a>Prerequisiti per una connessione

-   Devi disporre di un [account AdRoll](https://www.adroll.com/) e delle credenziali di amministratore corrispondenti.
-   Disponi di [segmenti configurati](segments.md) in Informazioni dettagliate sul gruppo di destinatari.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Puoi esportare fino a 250.000 profili di clienti alla volta in AdRoll.
- Non puoi esportare in AdRoll segmenti con meno di 100 profili di clienti. 
- L'esportazione in AdRoll è limitata ai segmenti.
- Esportare fino a 250.000 profili di clienti in AdRoll può richiedere fino a 10 minuti per essere completato. 
- Il numero di profili cliente che puoi esportare in AdRoll dipende dal tuo contratto con AdRoll.

## <a name="set-up-connection-to-adroll"></a>Configurare la connessione ad AdRoll

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **AdRoll** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione ad AdRoll.

1. Seleziona **Esegui autenticazione con AdRoll** e fornisci le tue credenziali di amministratore per AdRoll. 

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione AdRoll. Se non vedi questo nome di sezione, non sono disponibili connessioni di questo tipo.

1. Immetti l'**ID inserzionista AdRoll**. Per ulteriori informazioni, vedi [Profili inserzionisti AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. È necessario esportare i segmenti in AdRoll.

1. Seleziona i segmenti da esportare. Seleziona un segmento con almeno 100 membri. Non puoi esportare segmenti più piccoli. Inoltre, la dimensione massima di un segmento da esportare è di 250.000 membri per esportazione. 

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). 

Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati ad AdRoll, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che AdRoll rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
