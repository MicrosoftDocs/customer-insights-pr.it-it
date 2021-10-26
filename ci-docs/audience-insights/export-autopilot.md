---
title: Esportare dati di Customer Insights in Autopilot
description: Scopri come configurare la connessione ed esportare in Autopilot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4cceb64484e8e257a90b8cbaedff4419659bb399
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618434"
---
# <a name="export-segments-to-autopilot-preview"></a>Esportare segmenti in Autopilot (anteprima)

Esporta segmenti di profili cliente unificati in Autopilot e usali per l'e-mail marketing in Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Prerequisiti per una connessione

-   Devi disporre di un [account Autopilot](https://www.autopilothq.com/) e delle credenziali di amministratore corrispondenti.
-   Disponi di [segmenti configurati](segments.md) in Informazioni dettagliate sul gruppo di destinatari.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 100'000 profili di clienti in totale in Autopilot.
- L'esportazione in Autopilot è limitata ai segmenti.
- Esportare fino a 100'000 profili di clienti in Autopilot può richiedere alcune ore per essere completato. 
- Il numero di profili di clienti che puoi esportare in Autopilot dipende dal tuo contratto con Autopilot ed è limitato.

## <a name="set-up-connection-to-autopilot"></a>Configurare la connessione ad Autopilot

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Autopilot** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti la [chiave API Autopilot](https://autopilot.docs.apiary.io/#).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione a Autopilot.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Autopilot. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**.

1. Seleziona i segmenti da esportare. È fortemente **consigliato di non esportare più di 100.000 profili cliente in totale** in Autopilot. 

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Autopilot, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Autopilot rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
