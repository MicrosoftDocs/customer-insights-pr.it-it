---
title: Esportare dati di Customer Insights in Marketo
description: Scopri come configurare la connessione ed esportare in Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
---

# <a name="export-segments-to-marketo-preview"></a>Esportare segmenti in Marketo (anteprima)

Esporta segmenti di profili cliente unificati per generare campagne, fornire e-mail marketing e utilizzare gruppi specifici di clienti con Marketo.

## <a name="prerequisites-for-connection"></a>Prerequisiti per la connessione

-   Devi disporre di un [account Marketo](https://login.marketo.com/) e delle credenziali di amministratore corrispondenti.
-   In Marketo sono presenti elenchi e ID corrispondenti. Per ulteriori informazioni, vedi [Elenchi Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Disponi di [segmenti configurati](segments.md).
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Fino a 1 milione di profili di clienti per esportazione in Marketo.
- L'esportazione in Marketo è limitata ai segmenti.
- L'esportazione di segmenti con un totale di 1 milione di profili di clienti può richiedere fino a 3 ore. 
- Il numero di profili di clienti che puoi esportare in Marketo dipende dal tuo contratto con Marketo ed è limitato.

## <a name="set-up-connection-to-marketo"></a>Configurare la connessione a Marketo

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Marketo** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti **[ID client Marketo, segreto client e nome host dell'endpoint REST](https://developers.marketo.com/rest-api/authentication/)**. Il nome host dell'endpoint REST è solo il nome host, senza `https://`. Esempio: `xyz-abc-123.mktorest.com`. 

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati** e seleziona **Connetti** per inizializzare la connessione a Marketo.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Marketo. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Immetti l'**[ID elenco Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. L'ID elenco è un valore puramente numerico. Ad esempio, se l'ID dell'elenco Marketo è ST12345A7, rimuovi il carattere prima e dopo i numeri e inserisci `12345`. 

1. Nella sezione **Corrispondenza dati**, seleziona almeno un campo che rappresenti l'indirizzo e-mail del cliente o l'ID Marketo del cliente. 

1. Facoltativamente, puoi esportare **nome**, **cognome**, **città**, **stato**, e **Paese/Area geografica** per creare e-mail più personalizzate. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona i segmenti da esportare. Puoi esportare in totale fino a 1 milione di profili cliente in Marketo.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). I tuoi segmenti sono ora visualizzati sotto [Elenchi Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) in Marketo.


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Marketo, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Marketo rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
