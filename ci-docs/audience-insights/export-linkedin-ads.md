---
title: Esportare i dati di Customer Insights in LinkedIn Ads
description: Scopri come configurare la connessione ed esportare in LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2cfaa37fd0ac697f29665792bab27a925d8ea1eede0519d424524a7e5accbfeb
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034228"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Esportare segmenti in LinkedIn Ads (anteprima)

Esporta segmenti di profili cliente unificati in LinkedIn Ads per creare segmenti di pubblico corrispondenti. Utilizza i segmenti di pubblico corrispondenti per il targeting aziendale e il targeting per contatto.

## <a name="prerequisites"></a>Prerequisiti

-   Hai un [account LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e le corrispondenti credenziali di amministratore.
-   Disponi di [segmenti configurati](segments.md) in Informazioni dettagliate sul gruppo di destinatari.
-   I profili cliente nei segmenti esportati contengono un campo con un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 100.000 profili per esportazione in LinkedIn Ads.
- L'esportazione in LinkedIn Ads è limitata ai segmenti.
- L'esportazione fino a 100.000 profili in LinkedIn Ads può richiedere fino a 10 minuti per il completamento. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Configurare la connessione a LinkedIn Ads

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **LinkedIn Ads** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita è Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fornisci il tuo [ID per l'account LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connettiti** per inizializzare la connessione a Campaign Monitor.

1. Seleziona **Autentica con LinkedIn** e fornisci le tue credenziali di amministratore per LinkedIn Campaign Manager.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione LinkedIn Ads. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Scegli se vuoi esportare i dati per il [targeting per contatto](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [targeting aziendale](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) su LinkedIn. 

1. Nella sezione **Corrispondenza dati**, seleziona il campo nel tuo profilo cliente unificato che rappresenta un indirizzo e-mail di un cliente. È necessario esportare i segmenti in LinkedIn Ads.

1. Seleziona i segmenti da esportare. I segmenti di pubblico corrispondenti in LinkedIn Campaign Manager verranno creati automaticamente con il nome dei segmenti che hai selezionato per l'esportazione. Ciascun segmento risulterà in un gruppo di destinatari con corrispondenza con segmenti di pubblico corrispondenti. 

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a LinkedIn Ads, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che LinkedIn Ads soddisfi eventuali obblighi di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
