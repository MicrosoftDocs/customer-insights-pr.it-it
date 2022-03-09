---
title: Esportare dati di Customer Insights in SendGrid
description: Scopri come configurare la connessione ed esportare in SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 65d60e7e70e3444b0695b905431bab9a0269ceef
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231577"
---
# <a name="export-segments-to-sendgrid-preview"></a>Esportare segmenti in SendGrid (anteprima)

Esporta segmenti di profili cliente unificati nell'elenco di contatti SendGrid e usali per campagne e e-mail marketing in SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Prerequisiti per una connessione

-   Devi disporre di un [account SendGrid](https://sendgrid.com/) e delle credenziali di amministratore corrispondenti.
-   In SendGrid sono presenti elenchi di contatti e ID corrispondenti. Per ulteriori informazioni, vedere [SendGrid: gestire i contatti](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Disponi di [segmenti configurati](segments.md) in Informazioni dettagliate sul gruppo di destinatari.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Fino a 100'000 profili di clienti in totale a SendGrid.
- L'esportazione in SendGrid è limitata ai segmenti.
- Esportare fino a 100'000 profili di clienti su SendGrid può richiedere fino a qualche ora per essere completato. 
- Il numero di profili di clienti che puoi esportare su SendGrid dipende dal tuo contratto con SendGrid ed è limitato.

## <a name="set-up-connection-to-sendgrid"></a>Configurare la connessione a SendGrid

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **SendGrid** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Inserisci la tua **Chiave API SendGrid** [Chiave API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione a SendGrid.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione SendGrid. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Immetti l'**[ID elenco SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**, **Paese/area geografica**, **Stato**, **Città** e **Codice postale**.

1. Seleziona i segmenti da esportare. È fortemente **consigliato di non esportare più di 100.000 profili cliente in totale** in SendGrid. 

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a SendGrid, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che SendGrid rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
