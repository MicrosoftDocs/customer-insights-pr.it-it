---
title: Esportare segmenti in MoEngage
description: Informazioni su come configurare la connessione e l'esportazione in MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199116"
---
# <a name="export-segments-to-moengage-preview"></a>Esportare segmenti in MoEngage (anteprima)

Esporta segmenti di profili cliente unificati in MoEngage e usali per l'e-mail marketing in MoEngage.

## <a name="prerequisites-for-a-connection"></a>Prerequisiti per una connessione

- Un [account MoEngage](https://www.moengage.com/) e le credenziali di amministratore corrispondenti.
- La chiave API MoEngage da Impostazioni > API in MoEngage.
- [Segmenti configurati](segments.md) in Customer Insights.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 100.000 profili cliente per esportazione in MoEngage e il completamento di tale operazione può richiedere fino a 15 minuti. Il numero di profili cliente che puoi esportare in MoEngage dipende dal tuo contratto con MoEngage.
- Solo segmenti.

## <a name="set-up-connection-to-moengage"></a>Configurare la connessione a MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **MoEngage** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti l'[ID API dati e la chiave API MoEngage](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione a MoEngage.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione MoEngage. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. Ripeti gli stessi passaggi per altri campi facoltativi.

1. Seleziona i segmenti da esportare. Creeremo uno o più segmenti con lo stesso nome dei segmenti selezionati in MoEngage sotto **Segmenti** > **Segmenti personalizzati**.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
