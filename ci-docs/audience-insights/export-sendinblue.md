---
title: Esportazione dei dati di Customer Insights in Sendinblue
description: Scopri come configurare la connessione ed esportare in Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d870ff31ce2d441e619ac18899c4d1b6c69ca41
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231424"
---
# <a name="export-segments-to-sendinblue-preview"></a>Esportazione di segmenti in Sendinblue (anteprima)

Esporta i segmenti di profii clienti unificati per generare campagne, offrire e-mail marketing e utilizzare gruppi specifici di clienti con Sendinblue.

## <a name="prerequisites-for-connection"></a>Prerequisiti per la connessione

-   Hai un [account Sendinblue](https://www.sendinblue.com/) e le corrispondenti credenziali amministratore.
-   Vi sono elenchi esistenti in Sendinblue e gli ID corrispondenti.
-   Disponi di [segmenti configurati](segments.md).
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Fino a 1 milione di profili di clienti per esportazione verso Sendinblue.
- L'esportazione in Sendinblue è limitata ai segmenti.
- L'esportazione di segmenti con un totale di 1 milione di profili di clienti può richiedere fino a 90 minuti. 
- Il numero di profili di clienti che puoi esportare su Sendinblue dipende dal tuo contratto con Sendinblue ed è limitato.

## <a name="set-up-connection-to-sendinblue"></a>Configurazione della connessione con Sendinblue

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Sendinblue** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita sono solo gli amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti la **[chiave API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati** e seleziona **Connetti** per inizializzare la connessione a Sendinblue.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per l'esportazione** scegli una connessione dalla sezione Sendinblue. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Immissione dell'**ID elenco Sendinblue** 

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. 

1. Facoltativamente, puoi esportare **nome**, **cognome** e **telefono** per creare e-mail più personalizzate. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona i segmenti da esportare. 

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Sendinblue, consenti il trasferimento di dati al di fuori del limite di conformità per Dynamics 365 Customer Insights, inclusi i dati potenzialmente sensibili come i Dati Personali. Microsoft trasferirà tali dati alle tue condizioni, ma sei tu a dover garantire che Sendinblue soddisfi tutti gli obblighi di privacy e sicurezza che sei tenuto a rispettare. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
