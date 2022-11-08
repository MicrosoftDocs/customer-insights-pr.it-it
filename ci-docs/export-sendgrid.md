---
title: Esportare segmenti in SendGrid (anteprima)
description: Scopri come configurare la connessione ed esportare in SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724853"
---
# <a name="export-segments-to-sendgrid-preview"></a>Esportare segmenti in SendGrid (anteprima)

Esporta segmenti di profili cliente unificati nell'elenco di contatti SendGrid e usali per campagne e e-mail marketing in SendGrid.

## <a name="prerequisites"></a>Prerequisiti

- Un [account SendGrid](https://sendgrid.com/) e le credenziali di amministratore corrispondenti.
- [Elenchi di contatti esistenti in SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) e gli ID corrispondenti.
- Una [chiave API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Il collegamento privato in combinazione con Bring your own storage (BYOS) non è supportato.
- È possibile esportare fino a 100.000 profili cliente in totale in SendGrid e il completamento di questa operazione può richiedere alcune ore. Il numero di profili cliente che puoi esportare in SendGrid dipende dal tuo contratto con SendGrid.
- Solo segmenti.

## <a name="set-up-connection-to-sendgrid"></a>Configurare la connessione a SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **SendGrid**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti la **chiave API SendGrid**.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione SendGrid. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Immetti l'**ID elenco SendGrid**.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente.

1. Eventualmente, seleziona campi come **Nome**, **Cognome**, **Paese/Area geografica**, **Stato**, **Città** e **Codice postale**.

1. Seleziona i segmenti che vuoi esportare rispettando le limitazioni note.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
