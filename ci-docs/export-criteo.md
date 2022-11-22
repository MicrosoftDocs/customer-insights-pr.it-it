---
title: Esportazione dei segmenti in Criteo (anteprima)
description: Informazioni su come configurare la connessione e l'esportazione in Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760031"
---
# <a name="export-segments-to-criteo-preview"></a>Esportazione dei segmenti in Criteo (anteprima)

Esporta segmenti di profili clienti unificati per generare campagne, fornire e-mail marketing e utilizzare gruppi specifici di clienti con Criteo.

## <a name="prerequisites"></a>Prerequisiti

- Un [account Criteo Dynamics Retargeting](https://www.criteo.com/login/) e le credenziali di amministratore corrispondenti.
- [Segmenti configurati](segments.md).
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 1 milione di profili cliente per esportazione in Criteo e il completamento di tale  operazione può richiedere fino a 30 minuti. Il numero di profili cliente che puoi esportare in Criteo dipende dal tuo contratto con Criteo.
- Solo segmenti.

## <a name="set-up-connection-to-criteo"></a>Configurare la connessione a Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Criteo**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Autenticati con Criteo** e fornisci il tuo nome utente e le credenziali di amministratore per Criteo.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** scegli una connessione nella sezione Criteo. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
