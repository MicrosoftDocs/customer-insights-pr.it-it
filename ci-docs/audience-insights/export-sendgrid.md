---
title: Esportare dati di Customer Insights in SendGrid
description: Scopri come configurare la connessione a SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268737"
---
# <a name="connector-for-sendgrid-preview"></a>Connettore per SendGrid (anteprima)

Esporta segmenti di profili cliente unificati nell'elenco di contatti SendGrid e usali per campagne e e-mail marketing in SendGrid. 

## <a name="prerequisites"></a>Prerequisiti

-   Devi disporre di un [account SendGrid](https://sendgrid.com/) e delle credenziali di amministratore corrispondenti.
-   In SendGrid sono presenti elenchi di contatti e ID corrispondenti. Per ulteriori informazioni, vedere [SendGrid: gestire i contatti](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Disponi di [segmenti configurati](segments.md) in Audience Insights.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="connect-to-sendgrid"></a>Connettersi a SendGrid

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. In **SendGrid**, seleziona **Configura**.

1. Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Riquadro di configurazione dell'esportazione in SendGrid.":::

1. Inserisci la tua **Chiave API SendGrid** [Chiave API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Immetti l'**[ID elenco SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione a SendGrid.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Avanti** per configurare l'esportazione.

## <a name="configure-the-connector"></a>Configurare il connettore

1. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**, **Paese/area geografica**, **Stato**, **Città** e **Codice postale**.

1. Seleziona i segmenti da esportare. È fortemente **consigliato di non esportare più di 100.000 profili cliente in totale** in SendGrid. 

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitazioni note

- Fino a 100.000 profili in totale a SendGrid.
- L'esportazione in SendGrid è limitata ai segmenti.
- L'esportazione di un massimo di 100.000 profili in SendGrid può richiedere alcune ore per essere completata. 
- Il numero di profili che puoi esportare in SendGrid dipende ed è limitato dal tuo contratto con SendGrid.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a SendGrid, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che SendGrid rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]