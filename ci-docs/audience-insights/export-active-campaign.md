---
title: Esportazione dei dati di Customer Insights in ActiveCampaign
description: Scopri come configurare la connessione ed esportare in ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4fbdd5a51a3df35d31ad072eef64d20ee967d7ee
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618158"
---
# <a name="export-segments-to-activecampaign-preview"></a>Esportazione di segmenti in ActiveCampaign (anteprima)

Esporta segmenti di profili cliente unificati in ActiveCampaign e usali per attività di marketing.

## <a name="prerequisites"></a>Prerequisiti

-   Hai un [account ActiveCampaign](https://www.activecampaign.com/) e le corrispondenti credenziali amministratore.
-   Disponi di [segmenti configurati](segments.md) in Informazioni dettagliate sul gruppo di destinatari.
-   I profili cliente unificati nei segmenti esportati contengono un campo con un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Puoi esportare fino a 1 milione di profili di clienti per esportazione in ActiveCampaign e può richiedere fino a 90 minuti per essere completato.
- L'esportazione in ActiveCampaign è limitata ai segmenti.
- Il numero di profili di clienti che puoi esportare in ActiveCampaign dipende dal tuo contratto con ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Configurazione della connessione ad ActiveCampaign

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Campagna attiva** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti [chiave API ActiveCampaign e nome host endpoint REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Il nome host dell'endpoint REST è solo il nome host, senza https://. 

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione ad ActiveCampaign.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per l'esportazione** scegli una connessione dalla sezione ActiveCampaign. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Immetti l'[**ID elenco ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. È necessario esportare segmenti in ActiveCampaign. Facoltativamente, puoi esportare nome, cognome e telefono per creare e-mail più personalizzate. Seleziona Aggiungi attributo per eseguire il mapping di questi campi.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati ad ActiveCampaign, consenti il trasferimento di dati al di fuori del limite di conformità per Dynamics 365 Customer Insights, inclusi i dati potenzialmente sensibili come i Dati Personali. Microsoft trasferirà tali dati alle tue condizioni, ma sei tu a dover garantire che ActiveCampaign soddisfi tutti gli obblighi di privacy e sicurezza che sei tenuto a rispettare. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
