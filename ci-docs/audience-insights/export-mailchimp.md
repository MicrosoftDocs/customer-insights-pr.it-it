---
title: Esportare dati di Customer Insights in Mailchimp
description: Scopri come configurare la connessione ed esportare in Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a6bdf43bb40345b868bf2e7d2c91de169c8ba841ba77f732f455f4c4d496a7f5
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033544"
---
# <a name="export-segments-to-mailchimp-preview"></a>Esportare segmenti in Mailchimp (anteprima)

Esporta segmenti di profili cliente unificati in Mailchimp per creare newsletters e campagne tramite messaggi e-mail.

## <a name="prerequisites-for-connection"></a>Prerequisiti per la connessione

-   Devi disporre di un [account Mailchimp](https://mailchimp.com/) e delle credenziali di amministratore corrispondenti.
-   In Mailchimp sono presenti destinatari e ID corrispondenti. Per ulteriori informazioni, vedi [Destinatari Mailchimp](https://mailchimp.com/help/create-audience/).
-   Disponi di [segmenti configurati](segments.md)
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Fino a 1 milione di profili per esportazione in Mailchimp.
- L'esportazione in Mailchimp è limitata ai segmenti.
- L'esportazione di segmenti con 1 milione di profili può richiedere fino a tre ore. 
- Il numero di profili che puoi esportare in Mailchimp dipende ed è limitato dal tuo contratto con Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Configurare la connessione a Mailchimp

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Mailchimp** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connettiti** per inizializzare la connessione a Mailchimp.

1. Seleziona **Esegui autenticazione con MailChimp** e fornisci le tue credenziali Mailchimp.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione. 

## <a name="configure-the-connector"></a>Configurare il connettore

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati**> **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Mailchimp. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Immetti il tuo **[ID gruppo di destinatari Mailchimp](https://mailchimp.com/help/find-audience-id/)**

3. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. 

1. Facoltativamente, puoi esportare **nome** e **cognome** per creare e-mail più personalizzate. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona i segmenti da esportare. Puoi esportare in totale fino a 1 milione di profili cliente in Mailchimp.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Mailchimp, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Mailchimp rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
