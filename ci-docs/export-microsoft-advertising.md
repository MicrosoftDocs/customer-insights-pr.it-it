---
title: Esporta segmenti in Microsoft Advertising (anteprima)
description: Scopri come configurare la connessione ed eseguire l'esportazione in Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196537"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Esporta segmenti in Microsoft Advertising (anteprima)

Esporta i segmenti di Customer Insights in Microsoft Advertising per creare segmenti di pubblico Customer Match. Usa questi segmenti di pubblico per le tue campagne pubblicitarie.

## <a name="prerequisites"></a>Prerequisiti

- Un [account Microsoft Advertising](https://ads.microsoft.com/) e le credenziali di amministratore corrispondenti.
- L'ID account e l'ID cliente Microsoft Advertising. Puoi trovare l'ID cliente (`cid`) e l'ID account (`aid`) nei parametri dell'URL quando sei connesso a Microsoft Advertising.
- Hai accettato i termini di utilizzo di Customer Match.
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 500.000 profili cliente per esportazione in Microsoft Advertising e il completamento di tale operazione può richiedere fino a 10 minuti.
- Solo segmenti.

## <a name="set-up-connection-to-microsoft-advertising"></a>Configurare la connessione a Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Microsoft Advertising**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. L'impostazione predefinita è amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti l'**ID cliente Microsoft Advertising**.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Autentica con Microsoft Advertising** e fornisci le tue credenziali di amministratore per Microsoft Advertising.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Microsoft Advertising. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Seleziona i segmenti da esportare. I gruppi di destinatari Customer Match in Microsoft Advertising vengono creati automaticamente con il nome dei segmenti selezionati per l'esportazione. Ciascun segmento risulterà in un gruppo di destinatari Customer Match.

1. Inserisci il tuo **ID cliente Microsoft Advertising e il tuo ID account**.

1. Nella sezione **Corrispondenza dei dati** , nel campo **Email** , seleziona il campo con l'indirizzo e-mail del cliente.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
