---
title: Esportare segmenti in Marketo (anteprima)
description: Scopri come configurare la connessione ed esportare in Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724945"
---
# <a name="export-segments-to-marketo-preview"></a>Esportare segmenti in Marketo (anteprima)

Esporta segmenti di profili cliente unificati per generare campagne, fornire e-mail marketing e utilizzare gruppi specifici di clienti con Marketo.

## <a name="prerequisites"></a>Prerequisiti

- Un [account Marketo](https://login.marketo.com/) e le credenziali di amministratore corrispondenti.
- [ID client Marketo, segreto client e nome host dell'endpoint REST](https://developers.marketo.com/rest-api/authentication/).
- [Elenchi esistenti In Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) e gli ID corrispondenti.
- [Segmenti configurati](segments.md).
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Il collegamento privato in combinazione con Bring your own storage (BYOS) non è supportato.
- È possibile esportare fino a 1 milione di profili cliente per esportazione in Marketo e il completamento di tale operazione può richiedere fino a 3 ore. Il numero di profili cliente che puoi esportare in Marketo dipende dal tuo contratto con Marketo.
- Solo segmenti.

## <a name="set-up-connection-to-marketo"></a>Configurare la connessione a Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Marketo**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti **ID client Marketo, segreto client e nome host dell'endpoint REST**. Il nome host dell'endpoint REST è solo il nome host, senza https://. Esempio: xyz-abc-123.mktorest.com.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Marketo. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Immetti l'**ID elenco Marketo**. L'ID elenco è un valore puramente numerico. Ad esempio, se l'ID elenco Marketo è ST12345A7, rimuovi il carattere prima e dopo i numeri e inserisci *12345*.

1. Nella sezione **Corrispondenza dati**, seleziona almeno un campo che rappresenti l'indirizzo e-mail del cliente o l'ID Marketo del cliente.

1. Eventualmente, esporta **Nome**, **Cognome**, **Città**, **Stato**, e **Paese/Area geografica** per creare e-mail più personalizzate. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

I tuoi segmenti sono visualizzati sotto [Elenchi Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) in Marketo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
