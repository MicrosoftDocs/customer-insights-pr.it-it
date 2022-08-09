---
title: Esportare segmenti in Snapchat (anteprima)
description: Scopri come configurare la connessione ed esportare in Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195387"
---
# <a name="export-segments-to-snapchat-preview"></a>Esportare segmenti in Snapchat (anteprima)

Esporta segmenti di profili cliente unificati in Snapchat e utilizzali per la pubblicità.

## <a name="prerequisites"></a>Prerequisiti

- Un [account Snapchat Business](https://business.snapchat.com/), un [account Snapchat Ads](https://ads.snapchat.com/) e le credenziali di amministratore corrispondenti. Devi essere almeno un membro di un account organizzazione e un gestore dati di uno specifico account di annunci.
- Almeno un gruppo di destinatari in Snapchat Audience Manager del tipo SAM (Snap Audience Match).
- L'[ID segmento/gruppo di destinatari Snapchat](https://businesshelp.snapchat.com/s/article/custom-audiences). L'ID del gruppo di destinatari può essere trovato nell'URL dopo aver selezionato il destinatario in Snapchat Audience Manager.
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 1 milione di profili cliente e il completamento di questa operazione può richiedere fino a 15 minuti.
- Solo segmenti.

## <a name="set-up-connection-to-snapchat"></a>Configurare la connessione a Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Snapchat**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Autentica con Snapchat** e fornisci le tue credenziali di amministratore per Snapchat.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Snapchat. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Immetti l'**ID segmento/gruppo di destinatari Snapchat**.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
