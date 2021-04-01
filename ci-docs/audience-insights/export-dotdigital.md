---
title: Esportare dati di Customer Insights in DotDigital
description: Scopri come configurare la connessione a DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598022"
---
# <a name="connector-for-dotdigital-preview"></a>Connettore per DotDigital (anteprima)

Esporta segmenti di profili cliente unificati nelle rubriche di DotDigital e usali per campagne, messaggi e-mail di marketing e per costruire segmenti di clientela con DotDigital. 

## <a name="prerequisites"></a>Prerequisiti

-   Devi disporre di un [account DotDigital](https://dotdigital.com/) e delle credenziali di amministratore corrispondenti.
-   In DotDigital sono presenti rubriche e ID corrispondenti. L'ID è presente nell'URL quando selezioni e apri una rubrica. Per ulteriori informazioni, vedi [Rubriche di DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Disponi di [segmenti configurati](segments.md) in Audience Insights.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="connect-to-dotdigital"></a>Connettersi a DotDigital

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. Sotto **DotDigital**, seleziona **Configura**.

1. Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Riquadro di configurazione per l'esportazione in DotDigital.":::

1. Immetti il **nome utente e la password di DogDigital**.

1. Immetti l'**[ID rubrica DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione a DotDigital.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Avanti** per configurare l'esportazione.

## <a name="configure-the-connector"></a>Configurare il connettore

1. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**, **Nome completo**, **Sesso** e **Codice postale**.

1. Seleziona i segmenti da esportare. Puoi esportare in totale fino a 1 milione di profili cliente in DotDigital.

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab). I tuoi segmenti sono ora visualizzati sotto [Rubriche DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) in DotDigital.

## <a name="known-limitations"></a>Limitazioni note

- Fino a 1 milione di profili per esportazione in DotDigital.
- L'esportazione in DotDigital è limitata ai segmenti.
- L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 3 ore a causa delle limitazioni sul lato provider. 
- Il numero di profili che puoi esportare in DotDigital dipende ed è limitato dal tuo contratto con DotDigital.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a DotDigital, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che DotDigital rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]