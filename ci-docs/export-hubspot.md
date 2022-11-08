---
title: Esportare dati di Customer Insights in HubSpot
description: Scopri come configurare la connessione ed esportare in HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725359"
---
# <a name="export-segments-to-hubspot-preview"></a>Esportare segmenti in HubSpot (anteprima)

Esportare segmenti di profili cliente unificati in HubSpot e utilizzarli per attività di e-mail marketing.

## <a name="prerequisites-for-a-connection"></a>Prerequisiti per una connessione

- Un [account HubSpot](https://www.hubspot.com/) e le credenziali di amministratore corrispondenti.
- [Chiave API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) di HubSpot.
- [Segmenti configurati](segments.md) in Customer Insights.

## <a name="known-limitations"></a>Limitazioni note

- Il collegamento privato in combinazione con Bring your own storage (BYOS) non è supportato.
- Fino a 100.000 profili cliente per esportazione in HubSpot, il cui completamento può richiedere fino a 15 minuti. Il numero di profili cliente che puoi esportare in HubSpot dipende e si limita dal tuo contratto con HubSpot.
- Solo segmenti.

## <a name="set-up-connection-to-hubspot"></a>Configurare la connessione a HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **HubSpot** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti le credenziali di HubSpot quando richiesto.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connettiti** per inizializzare la connessione a HubSpot.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione HubSpot. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. Ripeti gli stessi passaggi per altri campi facoltativi.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
