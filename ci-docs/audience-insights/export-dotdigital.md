---
title: Esportare dati di Customer Insights in DotDigital
description: Scopri come configurare la connessione ed esportare in DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f09be0dfa599c1ef7cf0055b7ce1df8784cf447ada64b56bc7543c214f9a5b99
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034641"
---
# <a name="export-segments-to-dotdigital-preview"></a>Esportare segmenti in DotDigital (anteprima)

Esporta segmenti di profili cliente unificati nelle rubriche di DotDigital e usali per campagne, messaggi e-mail di marketing e per costruire segmenti di clientela con DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Prerequisiti per una connessione

-   Devi disporre di un [account DotDigital](https://dotdigital.com/) e delle credenziali di amministratore corrispondenti.
-   In DotDigital sono presenti rubriche e ID corrispondenti. L'ID è presente nell'URL quando selezioni e apri una rubrica. Per ulteriori informazioni, vedi [Rubriche di DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Disponi di [segmenti configurati](segments.md) in Informazioni dettagliate sul gruppo di destinatari.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Fino a 1 milione di profili per esportazione in DotDigital.
- L'esportazione in DotDigital è limitata ai segmenti.
- L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 3 ore a causa delle limitazioni sul lato provider. 
- Il numero di profili che puoi esportare in DotDigital dipende ed è limitato dal tuo contratto con DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Configurare la connessione a DotDigital

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **DotDigital** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti il **nome utente e la password di DogDigital**.

1. Immetti l'**[ID rubrica DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione a DotDigital.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione. 

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione DotDigital. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.


1. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. Ripeti gli stessi passaggi per altri campi facoltativi come **Nome**, **Cognome**, **Nome completo**, **Sesso** e **Codice postale**.

1. Seleziona i segmenti da esportare. Puoi esportare in totale fino a 1 milione di profili cliente in DotDigital.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 
 
I tuoi segmenti sono ora visualizzati sotto [Rubriche DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) in DotDigital.


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a DotDigital, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che DotDigital rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
