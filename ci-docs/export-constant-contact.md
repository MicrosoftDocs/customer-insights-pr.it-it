---
title: Esportare segmenti in Constant Contact (anteprima)
description: Scopri come configurare la connessione ed esportare in Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196491"
---
# <a name="export-segments-to-constant-contact-preview"></a>Esportare segmenti in Constant Contact (anteprima)

Esporta segmenti di profili cliente unificati in Constant Contact e utilizzali per le attività di marketing.

## <a name="prerequisites"></a>Prerequisiti

- Un [account Constant Contact](https://www.constantcontact.com/account-home) e le credenziali di amministratore corrispondenti.
- Un [ID elenco Constant Contact](https://app.constantcontact.com/pages/contacts/ui#lists). Apri un elenco in Constant Contact per trovare l'ID elenco nell'URL.
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 1 milione di profili cliente per esportazione in Constant Contact e il completamento di tale operazione può richiedere fino a 1 ora. Il numero di profili di clienti che puoi esportare a Constant Contact dipende dal tuo contratto con Constant Contact.
- Solo segmenti.

## <a name="set-up-connection-to-constant-contact"></a>Impostare la connessione a Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Constant Contact**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Autenticazione con Constant Contact** e fornisci le tue credenziali di amministratore per Constant Contact.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Constant Contact. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Immetti il tuo **ID elenco Constant Contact**.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente.

1. Eventualmente, esporta **Nome** e **Cognome** come campi aggiuntivi per creare e-mail più personalizzate. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
