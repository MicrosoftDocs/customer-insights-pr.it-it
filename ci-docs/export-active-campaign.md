---
title: Esporta segmenti in ActiveCampaign
description: Scopri come configurare la connessione ed esportare in ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725405"
---
# <a name="export-segments-to-activecampaign-preview"></a>Esportazione di segmenti in ActiveCampaign (anteprima)

Esporta segmenti di profili cliente unificati in ActiveCampaign e usali per attività di marketing.

## <a name="prerequisites"></a>Prerequisiti

- Un [account ActiveCampaign](https://www.activecampaign.com/) e credenziali di amministratore corrispondenti.
- Un [ID elenco ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- Una [chiave API ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) e un nome host endpoint REST.
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Il collegamento privato in combinazione con Bring your own storage (BYOS) non è supportato.
- È possibile esportare fino a 1 milione di profili cliente per esportazione in ActiveCampaign e il completamento di questa operazione può richiedere fino a 90 minuti. Il numero di profili di clienti che puoi esportare in ActiveCampaign dipende dal tuo contratto con ActiveCampaign.
- Solo segmenti.

## <a name="set-up-connection-to-activecampaign"></a>Configurazione della connessione ad ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **ActiveCampaign**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti chiave API ActiveCampaign e nome host endpoint REST. Il nome host dell'endpoint REST è solo il nome host, senza https://.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per l'esportazione** scegli una connessione dalla sezione ActiveCampaign. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Immetti l'**ID elenco ActiveCampaign**.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente.

1. Eventualmente, esporta **Nome**, **Cognome** e **Telefono** per creare e-mail più personalizzate. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
