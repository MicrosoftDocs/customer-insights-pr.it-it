---
title: Esportare dati di Customer Insights in Marketo
description: Scopri come configurare la connessione a Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267086"
---
# <a name="connector-for-marketo-preview"></a>Connettore per Marketo (anteprima)

Esporta segmenti di profili cliente unificati per generare campagne, fornire e-mail marketing e utilizzare gruppi specifici di clienti con Marketo.

## <a name="prerequisites"></a>Prerequisiti

-   Devi disporre di un [account Marketo](https://login.marketo.com/) e delle credenziali di amministratore corrispondenti.
-   In Marketo sono presenti elenchi e ID corrispondenti. Per ulteriori informazioni, vedi [Elenchi Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Disponi di [segmenti configurati](segments.md).
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="connect-to-marketo"></a>Connessione a Marketo

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. Sotto **Marketo**, seleziona **Configura**.

1. Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Immetti **[ID client Marketo, segreto client e nome host dell'endpoint REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Immetti l'**[ID elenco Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati** e seleziona **Connetti** per inizializzare la connessione a Marketo.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Screenshot di esportazione per la connessione a Marketo":::

1. Seleziona **Avanti** per configurare l'esportazione.

## <a name="configure-the-connector"></a>Configurare il connettore

1. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. 

1. Facoltativamente, puoi esportare **Nome**, **Cognome**, **Città**, **Regione** e **Paese** come campi aggiuntivi per creare messaggi di posta elettronica più personalizzati. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona i segmenti da esportare. Puoi esportare in totale fino a 1 milione di profili cliente in Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Selezionare campi e segmenti da esportare in Marketo":::

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab). I tuoi segmenti sono ora visualizzati sotto [Elenchi Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) in Marketo.

## <a name="known-limitations"></a>Limitazioni note

- Fino a 1 milione di profili per esportazione in Marketo.
- L'esportazione in Marketo è limitata ai segmenti.
- L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 3 ore. 
- Il numero di profili che puoi esportare in Marketo dipende ed è limitato dal tuo contratto con Marketo.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Marketo, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Marketo rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]