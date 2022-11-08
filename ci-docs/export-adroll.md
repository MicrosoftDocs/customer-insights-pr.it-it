---
title: Esportare segmenti in AdRoll (anteprima)
description: Scopri come configurare la connessione ed esportare in AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 81adad4caf2d4c6f792bf920b29fc7c67eef42b0
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724717"
---
# <a name="export-segments-to-adroll-preview"></a>Esportare segmenti in AdRoll (anteprima)

Esporta i segmenti dei profili cliente unificati in AdRoll e utilizzali per la pubblicità.

## <a name="prerequisites"></a>Prerequisiti

- Un [account AdRoll](https://www.adroll.com/) e credenziali di amministratore corrispondenti.
- Un [ID inserzionista AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Il collegamento privato in combinazione con Bring your own storage (BYOS) non è supportato.
- È possibile esportare fino a 250.000 profili cliente per esportazione in AdRoll e il completamento di tale operazione può richiedere fino a 10 minuti. Il numero di profili cliente che puoi esportare in AdRoll dipende dal tuo contratto con AdRoll.
- Solo segmenti. Un segmento deve contenere almeno 100 profili cliente.

## <a name="set-up-connection-to-adroll"></a>Configurare la connessione ad AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **AdRoll**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Esegui autenticazione con AdRoll** e fornisci le tue credenziali di amministratore per AdRoll.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione AdRoll. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Immetti l'**ID inserzionista AdRoll**.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
