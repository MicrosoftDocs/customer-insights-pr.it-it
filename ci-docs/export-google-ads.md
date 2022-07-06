---
title: Esportare segmenti in Google Ads (anteprima)
description: Scopri come configurare la connessione ed esportare in Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b7f08936d7d90322cb4e62396a2961fe06273b76
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081641"
---
# <a name="export-segments-to-google-ads-preview"></a>Esportare segmenti in Google Ads (anteprima)

Esporta segmenti di profili cliente unificati in un elenco di gruppi di destinatari di Google Ads e utilizzali per fare pubblicità su Ricerca Google, Gmail, YouTube e Rete Display di Google. 


## <a name="prerequisites-for-connection"></a>Prerequisiti per la connessione

-   Devi disporre di un [account Google Ads](https://ads.google.com/) e delle credenziali di amministratore corrispondenti.
-   Soddisfi i requisiti dei [criteri di corrispondenza dei clienti](https://support.google.com/adspolicy/answer/6299717).
-   Soddisfi i requisiti delle [dimensioni degli elenchi per il remarketing](https://support.google.com/google-ads/answer/7558048).
-   Disponi di [segmenti configurati](segments.md).
-   I profili cliente unificati nei segmenti esportati contengono campi che rappresentano un indirizzo e-mail, telefono, ID inserzionista per dispositivi mobili, ID utente di terze parti o indirizzo.

## <a name="known-limitations"></a>Limitazioni note

- L'esportazione in Google Ads è limitata ai segmenti.
- L'esportazione di segmenti con un totale di 1 milione di profili di clienti può richiedere fino a 30 minuti a causa delle limitazioni sul lato del fornitore. 
- La corrispondenza in Google Ads può richiedere fino a 48 ore.

## <a name="set-up-connection-to-google-ads"></a>Configurare la connessione a Google Ads

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Google Ads** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti l'**[ID cliente Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Esegui autenticazione con Google Ads** e fornisci le tue credenziali Google Ads.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione. 

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Google Ads. Se non vedi questo nome di sezione, non sono disponibili connessioni di questo tipo.

1. Se desideri creare un nuovo destinatario, lascia vuoto il campo ID destinatari di Google. Creeremo automaticamente un nuovo destinatario nel tuo account Google Ads e utilizzeremo il nome del segmento esportato. Se desideri aggiornare un destinatario di Google Ads esistente, inserisci il tuo [ID destinatario di Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. Nella sezione **Corrispondenza dati**, seleziona uno o più campi dati da esportare e seleziona il campo che rappresenta i campi dati corrispondenti in Customer Insights.

1. Seleziona i segmenti da esportare. 

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). 

Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Google Ads, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Google Ads rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE [footer-include](includes/footer-banner.md)]
