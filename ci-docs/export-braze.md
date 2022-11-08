---
title: Esportare segmenti in Braze (anteprima)
description: Informazioni su come configurare la connessione e l'esportazione in Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725221"
---
# <a name="export-segments-to-braze-preview"></a>Esportare segmenti in Braze (anteprima)

Esportare segmenti di profili cliente unificati in Braze e utilizzarli per attività di marketing.

## <a name="prerequisites"></a>Prerequisiti

- Un [account Braze](https://www.braze.com/) e le credenziali di amministratore corrispondenti.
- Una [chiave API Braze](https://www.braze.com/docs/api/basics/)
- L'[endpoint REST Braze](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail e un ID cliente Braze.

## <a name="known-limitations"></a>Limitazioni note

- Il collegamento privato in combinazione con Bring your own storage (BYOS) non è supportato.
- È possibile esportare fino a 1 milione di profili cliente per esportazione in Braze e il completamento di questa operazione può richiedere fino a 40 minuti. Il numero di profili cliente che puoi esportare in Braze dipende dal tuo contratto con Braze.
- Solo segmenti.
- Il collegamento privato di Azure non è supportato per l'esportazione Braze.

## <a name="set-up-connection-to-braze"></a>Configurare la connessione a Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Braze**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fornisci la tua chiave API Braze per continuare con l'accesso.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** scegli una connessione nella sezione Braze. Contatta un amministratore se non è disponibile alcuna connessione.

1. Inserisci il tuo endpoint REST nel campo **Nome host** nel formato seguente: `rest.iad-03.braze.com`.

1. Immetti un nome per l'esportazione.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente. Nel campo **ID cliente**, seleziona il campo che rappresenta l'ID Braze del cliente. I segmenti in Braze verranno creati con lo stesso nome del segmento che hanno in Dynamics 365 Customer Insights. Puoi scegliere più campi facoltativi per la corrispondenza dei dati.

1. Seleziona le entità o i segmenti che vuoi esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
