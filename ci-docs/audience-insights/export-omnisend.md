---
title: Esportare i dati di Customer Insights in Omnisend
description: Scopri come configurare la connessione ed esportare in Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58b54dc24f4656f9dd376415a701539c8796e83e6d4e3c6754f5627ce77c5685
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031771"
---
# <a name="export-segments-to-omnisend-preview"></a>Esportare segmenti in Omnisend (anteprima)

Esporta segmenti di profili cliente unificati in Omnisend e utilizzali per le attività di marketing.

## <a name="prerequisites"></a>Prerequisiti

-   Hai un [account Omnisend](https://www.omnisend.com/) e le corrispondenti credenziali di amministratore.
-   Disponi di [segmenti configurati](segments.md) in Informazioni dettagliate sul gruppo di destinatari.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Puoi esportare fino a 1 milione di profili per l'esportazione in Omnisend e il completamento può richiedere fino a 4 ore.
- L'esportazione in Omnisend è limitata ai segmenti.
- Il numero di profili che puoi esportare in Omnisend dipende dal tuo contratto con Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Configurare la connessione a Omnisend

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Omnisend** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita sono solo gli amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti la [chiave API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connettiti** per inizializzare la connessione a Omnisend.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Omnisend. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. È necessario per esportare i segmenti in Omnisend. Facoltativamente, puoi esportare nome, cognome, indirizzo, Paese/Area geografica, stato, città e codice postale per creare e-mail più personalizzate. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Ommisend, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che Ommisend soddisfi eventuali obblighi di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
