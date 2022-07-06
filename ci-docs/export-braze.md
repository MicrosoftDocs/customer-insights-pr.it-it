---
title: Esportare segmenti in Braze (anteprima)
description: Informazioni su come configurare la connessione e l'esportazione in Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081496"
---
# <a name="export-segments-to-braze-preview"></a>Esportare segmenti in Braze (anteprima)

Esportare segmenti di profili cliente unificati in Braze e utilizzarli per attività di marketing.

## <a name="prerequisites"></a>Prerequisiti

- Un [account Braze](https://www.braze.com/) e le credenziali di amministratore corrispondenti.
- Disporre di [segmenti in Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail e un ID cliente Braze.

## <a name="known-limitations"></a>Limitazioni note

- L'esportazione in Braze è limitata ai segmenti.
- Esportare fino a 1 milione di profili cliente in Braze può richiedere fino a 40 minuti.
- Il numero di profili cliente che puoi esportare in Braze dipende ed è limitato dal tuo contratto con Braze.

## <a name="set-up-connection-to-braze"></a>Configurare la connessione a Braze

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Braze** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fornisci la tua [chiave API Braze](https://www.braze.com/docs/api/basics/) per continuare con l'accesso.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione a Braze.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** scegli una connessione nella sezione Braze. Se non vedi questa sezione, non ci sono connessioni di questo tipo disponibili per te.  

1. Aggiungi un **nome visualizzato** per la tua esportazione

1. Aggiungi l'identificatore API del segmento Braze in cui desideri esportare nel campo **Identificatore API segmento Braze**. Puoi trovare l'identificatore nei dettagli del segmento sulla piattaforma Braze.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. Nel campo **ID cliente**, seleziona il campo che rappresenta l'ID Braze del cliente. È necessario esportare i segmenti in Braze. Puoi scegliere più campi facoltativamente.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Braze, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati su tua istruzione, ma sei tenuto a garantire che Braze soddisfi qualsiasi obbligo di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
