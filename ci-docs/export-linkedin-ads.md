---
title: Esportare segmenti in LinkedIn Ads (anteprima)
description: Scopri come configurare la connessione ed esportare in LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725313"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Esportare segmenti in LinkedIn Ads (anteprima)

Esporta segmenti di profili cliente unificati in LinkedIn Ads per creare segmenti di pubblico corrispondenti. Utilizza i segmenti di pubblico corrispondenti per il targeting aziendale e il targeting per contatto.

## <a name="prerequisites"></a>Prerequisiti

- Un [account LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e le credenziali di amministratore corrispondenti.
- Un [ID account LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [Segmenti configurati](segments.md) in Customer Insights.
- I segmenti esportati richiedono almeno un campo specifico a seconda che tu scelga [targeting per contatto](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [targeting aziendale](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) su LinkedIn. I campi possibili sono elencati nel passaggio **Corrispondenza dati** durante la [configurazione dell'esportazione](#configure-an-export).

## <a name="known-limitations"></a>Limitazioni note

- Il collegamento privato in combinazione con Bring your own storage (BYOS) non è supportato.
- È possibile esportare fino a 100.000 profili cliente per esportazione in LinkedIn Ads e il completamento di tale operazione può richiedere fino a 10 minuti.
- Solo segmenti. Un segmento deve contenere almeno 300 profili univoci.

## <a name="set-up-connection-to-linkedin-ads"></a>Configurare la connessione a LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **LinkedIn Ads**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fornisci il tuo ID account LinkedIn Campaign Manager.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Autentica con LinkedIn** e fornisci le tue credenziali di amministratore per LinkedIn Campaign Manager.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione LinkedIn Ads. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Scegli se vuoi esportare i dati per il [targeting per contatto](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [targeting aziendale](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) su LinkedIn.

1. Nella sezione **Data matching** , per il targeting dei contatti, seleziona almeno un campo che rappresenti l'indirizzo e-mail di un cliente, l'Apple Ad ID, il Google Ad ID, il Google User ID o il nome e cognome. Se scegliete il targeting aziendale, selezionate almeno un campo che rappresenti il nome dell'azienda, il dominio e-mail, l'URL della pagina LinkedIn, il simbolo del titolo o il sito web.

1. Eventualmente, aggiungi altri campi per definire ulteriormente l'esportazione. Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.

1. Seleziona i segmenti da esportare. I segmenti di pubblico corrispondenti in LinkedIn Campaign Manager verranno creati automaticamente con il nome dei segmenti che hai selezionato per l'esportazione. Ciascun segmento risulterà in un gruppo di destinatari con corrispondenza con segmenti di pubblico corrispondenti.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
