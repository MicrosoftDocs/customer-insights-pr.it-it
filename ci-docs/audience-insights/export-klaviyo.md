---
title: Esportare i dati di Customer Insights in Klaviyo
description: Scopri come configurare la connessione ed esportare in Klaviyo.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385793"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Esportare elenchi di segmenti in Klaviyo (anteprima)

Esporta segmenti di profili cliente unificati in Klaviyo e usali per attività di marketing.

## <a name="prerequisites"></a>Prerequisiti

-   Hai un [account Klaviyo](https://www.klaviyo.com/) e le corrispondenti credenziali amministratore.
-   Disponi di [segmenti configurati](segments.md) in Informazioni dettagliate sul gruppo di destinatari.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Puoi esportare fino a 100.000 profili per esportazione in Klaviyo.
- L'esportazione in Klaviyo è limitata ai segmenti.
- Il completamento dell'esportazione di 1 milione di profili in Klaviyo può richiedere fino a 20 minuti. 
- Il numero di profili che puoi esportare in Klaviyo dipende ed è limtato dal contratto con Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Configurare la connessione a Klaviyo

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Klaviyo** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti la [chiave API di Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) per eseguire la procedura di accesso. 

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione a Klaviyo.

1. Seleziona **Autenticazione con Klaviyo** e immetti le credenziali di amministratore per Klaviyo.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per l'esportazione** scegli una connessione nella sezione Klaviyo. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Immetti l'[**ID elenco Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. È necessario esportare segmenti in Klaviyo.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Klaviyo, consenti il trasferimento di dati al di fuori del limite di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i Dati Personali. Microsoft trasferirà tali dati alle tue condizioni, ma sei tu a dover garantire che Klaviyo soddisfi tutti gli obblighi di privacy e sicurezza che sei tenuto a rispettare. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
