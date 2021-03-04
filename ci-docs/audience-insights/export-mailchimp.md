---
title: Esportare dati di Customer Insights in Mailchimp
description: Scopri come configurare la connessione a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267178"
---
# <a name="connector-for-mailchimp-preview"></a>Connettore per Mailchimp (anteprima)

Esporta segmenti di profili cliente unificati in Mailchimp per creare newsletters e campagne tramite messaggi e-mail.

## <a name="prerequisites"></a>Prerequisiti

-   Devi disporre di un [account Mailchimp](https://mailchimp.com/) e delle credenziali di amministratore corrispondenti.
-   In Mailchimp sono presenti destinatari e ID corrispondenti. Per ulteriori informazioni, vedi [Destinatari Mailchimp](https://mailchimp.com/help/create-audience/).
-   Disponi di [segmenti configurati](segments.md)
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="connect-to-mailchimp"></a>Connettiti a MailChimp

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. Sotto **Mailchimp**, seleziona **Configura**.

1. Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Immetti l'**[ID destinatario Mailchimp](https://mailchimp.com/help/find-audience-id/)** e seleziona **Connetti** per inizializzare la connessione a Mailchimp.

1. Seleziona **Esegui autenticazione con MailChimp** e fornisci le tue credenziali Mailchimp.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Screenshot di esportazione per la connessione a Mailchimp":::

1. Seleziona **Avanti** per configurare l'esportazione.

## <a name="configure-the-connector"></a>Configurare il connettore

1. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. 

1. Facoltativamente, puoi esportare **Nome** e **Cognome** come campi aggiuntivi per creare messaggi e-mail più personalizzati. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona i segmenti da esportare. Puoi esportare in totale fino a 1 milione di profili cliente in Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Selezionare campi e segmenti da esportare in Mailchimp":::

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab). I tuoi segmenti sono ora visualizzati sotto [Destinatari Marketo](https://mailchimp.com/help/create-audience/) in Mailchimp.

## <a name="known-limitations"></a>Limitazioni note

- Fino a 1 milione di profili per esportazione in Mailchimp.
- L'esportazione in Mailchimp è limitata ai segmenti.
- L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a tre ore a causa delle limitazioni sul lato provider. 
- Il numero di profili che puoi esportare in Mailchimp dipende ed è limitato dal tuo contratto con Mailchimp.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Mailchimp, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Mailchimp rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]