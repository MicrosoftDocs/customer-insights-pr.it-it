---
title: Esportare segmenti in Campaign Monitor (anteprima)
description: Scopri come configurare la connessione ed esportare in Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196307"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Esportare segmenti in Campaign Monitor (anteprima)

Esporta segmenti di profili cliente unificati in Campaign Monitor e utilizzali per le attività di marketing.

## <a name="prerequisites"></a>Prerequisiti

- Un [account Campaign Monitor](https://www.campaignmonitor.com/) e le credenziali di amministratore corrispondenti.
- Un [ID elenco Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Una [chiave API generata](https://www.campaignmonitor.com/api/getting-started/) da **Impostazioni account** in Campaign Monitor per ottenere l'ID elenco API.
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 1 milione di profili cliente per esportazione in Campaign Monitor e il completamento di tale operazione può richiedere fino a 20 minuti. Il numero di profili di clienti che puoi esportare in Campaign Monitor dipende dal tuo contratto con Campaign Monitor.
- Solo segmenti.

## <a name="set-up-connection-to-campaign-monitor"></a>Impostare la connessione a Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Campaign Monitor**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connettiti** per inizializzare la connessione a Campaign Monitor.

1. Seleziona **Autentica con Campaign Monitor** e fornisci le tue credenziali di amministratore per Campaign Monitor.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Campaign Monitor. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Immetti il tuo **ID elenco Campaign Monitor**.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. È necessario per esportare i segmenti in Campaign Monitor.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
