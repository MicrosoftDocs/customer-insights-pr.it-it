---
title: Esportazione dei segmenti in Criteo (anteprima)
description: Informazioni su come configurare la connessione e l'esportazione in Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081541"
---
# <a name="export-segments-to-criteo-preview"></a>Esportazione dei segmenti in Criteo (anteprima)

Esporta segmenti di profili clienti unificati per generare campagne, fornire e-mail marketing e utilizzare gruppi specifici di clienti con Criteo.

## <a name="prerequisites-for-connection"></a>Prerequisiti per la connessione

-   Devi disporre di un [account Criteo Dynamics Retargeting](https://www.criteo.com/login/) e delle credenziali di amministratore corrispondenti.
-   Disponi di [segmenti configurati](segments.md).
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Fino a 1 milione di profili cliente per esportazione in Criteo.
- L'esportazione in Criteo è limitata ai segmenti.
- L'esportazione di segmenti con un totale di 1 milione di profili di clienti può richiedere fino a 30 minuti. 
- Il numero di profili cliente che puoi esportare in Criteo dipende ed è limitato dal tuo contratto con Criteo.

## <a name="set-up-connection-to-criteo"></a>Configurare la connessione a Criteo

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Criteo** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleziona **Accetto** per confermare la **Privacy e conformità dei dati** e seleziona **Connetti** per inizializzare la connessione a Criteo.

1. Seleziona **Autenticati con Criteo** e fornisci il tuo nome utente e le credenziali di amministratore per Criteo. 

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** scegli una connessione nella sezione Criteo. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo. 

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. 

1. Facoltativamente, puoi esportare **ID inserzionista** e **Nome**

1. Seleziona i segmenti da esportare. 

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Criteo, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati su tua istruzione, ma sei tenuto a garantire che Criteo soddisfi qualsiasi obbligo di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](includes/footer-banner.md)]
