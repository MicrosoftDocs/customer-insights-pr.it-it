---
title: Esportazione dei segmenti in Klaviyo (anteprima)
description: Scopri come configurare la connessione ed esportare in Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724598"
---
# <a name="export-segments-to-klaviyo-preview"></a>Esportazione dei segmenti in Klaviyo (anteprima)

Esporta segmenti di profili cliente unificati in Klaviyo e usali per attività di marketing.

## <a name="prerequisites"></a>Prerequisiti

- Un [account Klaviyo](https://www.klaviyo.com/) e le credenziali di amministratore corrispondenti.
- Una [chiave API Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- Un [ID elenco Klaviyo](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Il collegamento privato in combinazione con Bring your own storage (BYOS) non è supportato.
- È possibile esportare fino a 1 milione di profili cliente per esportazione in Klaviyo e il completamento di tale operazione può richiedere fino a 20 minuti. Il numero di profili cliente che puoi esportare in Klaviyo dipende dal tuo contratto con Klaviyo.
- Solo segmenti.

## <a name="set-up-connection-to-klaviyo"></a>Configurare la connessione a Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Klaviyo**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti la chiave API di Klaviyo per eseguire la procedura di accesso.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Autenticazione con Klaviyo** e immetti le credenziali di amministratore per Klaviyo.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per l'esportazione** scegli una connessione nella sezione Klaviyo. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Immetti l'**ID elenco Klaviyo**.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
