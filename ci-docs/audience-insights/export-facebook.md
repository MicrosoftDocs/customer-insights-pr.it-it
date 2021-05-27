---
title: Esportare dati di Customer Insights in Gestione inserzioni di Facebook
description: Scopri come configurare la connessione ed esportare in Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976047"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Esportare l'elenco di segmenti in Facebook Ads Manager (anteprima)

Esporta segmenti di profili cliente unificati in Gestione inserzioni di Facebook per creare campagne in Facebook e Instagram.

## <a name="prerequisites-for-connection"></a>Prerequisiti per la connessione

- Devi disporre di un [account per annunci **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) che includa un [account aziendale di **Facebook**](https://business.facebook.com/).
- Devi essere un amministratore nell'[account inserzionista **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitazioni note

- Fino a 10 milioni di profili cliente per esportazione in Facebook Ads Manager.
- L'esportazione in Facebook Ads Manager è limitata ai segmenti.
- Crea o aggiorna segmenti di gruppi di destinatari personalizzati in Facebook solo di tipo *elenco clienti*.
- L'esportazione di segmenti con un totale di 10 milione di profili può richiedere fino a 90 minuti.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurare la connessione a Facebook Ads Manager

Prima che gli utenti possano creare un'esportazione, un amministratore deve configurare la connessione al servizio e consentire ai collaboratori di utilizzare la connessione.

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Facebook Ads Manager** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà **Amministratori**. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Esegui l'autenticazione con Facebook Ads: 

   1. Seleziona **Continua con Facebook** per accedere al tuo account inserzionista Facebook.

   1. Consenti l'autorizzazione **ads_management** dopo l'autenticazione con Facebook.

   1. Seleziona l'**account inserzionista Facebook** che vuoi utilizzare.

   1. Seleziona i **destinatari personalizzati esistenti** dall'elenco a discesa o crea **nuovi destinatari personalizzati**. Per ulteriori informazioni, vedi [**Destinatari in Gestione inserzioni di Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Puoi creare o aggiornare segmenti di pubblico personalizzati solo su Facebook del tipo *elenco clienti* con questa esportazione. In alcuni casi, nell'elenco a discesa vengono visualizzati segmenti di pubblico personalizzati di diversi tipi. La selezione di un tipo diverso da *elenco clienti* comporterà un'esportazione non riuscita. 

1. Rivedi **Privacy e conformità dei dati** e seleziona **Accetto**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**. 

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione **Facebook Ads Manager**. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Nel **campo Scegli identificatore chiave**, seleziona **E-mail**, **Nome e indirizzo** o **Telefono** per inviare a Gestione inserzioni di Facebook. 

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**.

1. Mappa gli attributi corrispondenti dall'entità cliente unificata per l'identificatore chiave selezionato.
   > [SUGGERIMENTO] Le migliori possibilità di corrispondenza si hanno se selezioni **E-mail** come identificatore chiave. L'aggiunta di identificatori aggiuntivi può migliorare la corrispondenza.

1. Seleziona **Aggiungi attributo** per mappare più attributi da inviare a Facebook Ads Manager. Gli attributi di Gestione inserzioni di Facebook sono mapping ai seguenti nomi descrittivi per l'utente: **FN** = **Nome**, **LN** = **Cognome**, **FI** = **Iniziali**, **PHONE** = **Telefono**, **GEN** = **Sesso**, **DOB** = **Data di nascita**, **ST** = **Stato**, **CT** = **Città**, **ZIP** = **Codice postale**, **COUNTRY** = **Paese/Area geografica**

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Gestione inserzioni di Facebook, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Facebook rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
