---
title: Esportare i dati di Customer Insights in Constant Contact
description: Scopri come configurare la connessione ed esportare in Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 310de0355f71829346f0e35508487e5962d6e912
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647314"
---
# <a name="export-segments-to-constant-contact-preview"></a>Esportare segmenti in Constant Contact (anteprima)

Esporta segmenti di profili cliente unificati in Constant Contact e utilizzali per le attività di marketing. 

## <a name="prerequisites-for-a-connection"></a>Prerequisiti per una connessione

-   Hai un [account Constant Contact](https://www.constantcontact.com/account-home) e le corrispondenti credenziali di amministratore.
-   Hai [segmenti configurati](segments.md) in Customer Insights.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Puoi esportare fino a 1 milione di profili di clienti per esportazione a Constant Contact.
- L'esportazione in Constant Contact è limitata ai segmenti.
- Esportare fino a 1 milione di profili di clienti in Constant Contact può richiedere fino a 1 ora per essere completato. 
- Il numero di profili di clienti che puoi esportare a Constant Contact dipende dal tuo contratto con Constant Contact ed è limitato.

## <a name="set-up-connection-to-constant-contact"></a>Impostare la connessione a Constant Contact

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Constant Contact** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connettiti** per inizializzare la connessione a Constant Contact.

1. Seleziona **Autenticazione con Constant Contact** e fornisci le tue credenziali di amministratore per Constant Contact. 

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Constant Contact. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Immetti il tuo [**ID elenco Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Apri un elenco in Constant Contact per trovare l'ID elenco nell'URL.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. È necessario per esportare i segmenti in Constant Contact.

1. Facoltativamente, puoi esportare Nome e Cognome come campi aggiuntivi per creare messaggi e-mail più personalizzati. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Constant Contact, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che Constant Contact soddisfi eventuali obblighi di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
