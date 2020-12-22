---
title: Esportare dati di Customer Insights in Google Ads
description: Scopri come configurare la connessione a Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568457"
---
# <a name="connector-for-google-ads-preview"></a>Connettore per Google Ads (anteprima)

Esporta segmenti di profili cliente unificati nell'elenco destinatari di Google Ads e utilizzali per fare pubblicità su Google Search, Gmail, YouTube e Rete Display di Google. 

## <a name="prerequisites"></a>Prerequisiti

-   Devi disporre di un [account Google Ads](https://ads.google.com/) e delle credenziali di amministratore corrispondenti.
-   In Google Ads sono presenti destinatari e ID corrispondenti. Per ulteriori informazioni, vedi [Destinatari Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Disponi di [segmenti configurati](segments.md)
-   I profili cliente unificati nei segmenti esportati contengono campi che rappresentano un indirizzo e-mail, un nome e un cognome

## <a name="connect-to-google-ads"></a>Connettiti a Google Ads

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. Sotto **Google Ads**, seleziona **Configura**.

1. Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Immetti l'**[ID cliente Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Immetti il **[Token per sviluppatori di Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Immetti l'**[ID destinatario Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e seleziona **Connetti** per inizializzare la connessione a Google Ads.

1. Seleziona **Esegui autenticazione con Google Ads** e fornisci le tue credenziali Google Ads.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Screenshot di esportazione per la connessione a Google Ads":::

1. Seleziona **Avanti** per configurare l'esportazione.

## <a name="configure-the-connector"></a>Configurare il connettore

1. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. Ripeti gli stessi passaggi per i campi **Nome** e **Cognome**.

1. Seleziona i segmenti da esportare. Puoi esportare in totale fino a 1 milione di profili cliente in Google Ads.

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab). I tuoi segmenti sono ora visualizzati sotto [Destinatari Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/) in Google Ads.

## <a name="known-limitations"></a>Limitazioni note

- Fino a 1 milione di profili per esportazione in Google Ads.
- L'esportazione in Google Ads è limitata ai segmenti.
- L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 5 minuti a causa delle limitazioni sul lato provider. 
- La corrispondenza in Google Ads può richiedere fino a 48 ore.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Google Ads, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Google Ads rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
