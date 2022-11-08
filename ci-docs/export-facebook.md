---
title: Esportare segmenti in Facebook Ads Manager (anteprima) (video)
description: Scopri come configurare la connessione ed esportare in Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724605"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Esportare segmenti in Facebook Ads Manager (anteprima)

Esporta segmenti di profili cliente unificati in Gestione inserzioni di Facebook per creare campagne in Facebook e Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Prerequisiti

- Un [account inserzioni Facebook](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) che includa un [account aziendale Facebook](https://business.facebook.com/).
- Un [account inserzioni Facebook con privilegi di amministratore](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- I termini Gruppo di destinatari personalizzato devono essere accettati dall'utente che imposta la connessione in Customer Insights.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 10 milioni di profili cliente per esportazione in Gestione inserzioni di Facebook e il completamento di tale operazione può richiedere fino a 90 minuti.
- Solo segmenti.
- L'integrazione degli annunci Facebook non supporta gli utenti con più di 25 account pubblicitari.
- Tipo *elenco clienti* Facebook solo in [gruppi di destinatari personalizzati](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > In alcuni casi, nell'elenco a discesa, potrebbero essere visualizzati segmenti di pubblico personalizzati di diversi tipi. Se selezioni un tipo diverso da *elenco clienti*, l'esportazione non riuscirà.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurare la connessione a Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Gestione inserzioni Facebook**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. [Consenti ai collaboratori di utilizzare la connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Esegui l'autenticazione con Facebook Ads:

   1. Seleziona **Continua con Facebook** per accedere al tuo account inserzioni Facebook.

   1. Consenti l'autorizzazione **ads_management** dopo l'autenticazione con Facebook.

   1. Seleziona l'**account inserzioni Facebook** che vuoi utilizzare.

   1. Seleziona un **gruppo di destinatari personalizzato esistente** dall'elenco a discesa o crea un **nuovo gruppo di destinatari personalizzato**.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione**, scegli una connessione dalla sezione Gestione inserizioni Facebook. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Nel campo **Connetti i dati**, seleziona **E-mail**, **Nome e indirizzo** o **Telefono** per l'invio a Gestione inserzioni di Facebook.

1. Mappa gli attributi corrispondenti dall'entità cliente unificata per l'identificatore chiave selezionato.
   > [!TIP]
   > Le migliori possibilità di corrispondenza si hanno se selezioni **E-mail** come identificatore chiave. L'aggiunta di identificatori aggiuntivi può migliorare la corrispondenza.

1. Seleziona **Aggiungi attributo** per mappare più attributi da inviare a Facebook Ads Manager. Gli attributi di Gestione annunci di Facebook sono mapping ai seguenti nomi descrittivi per l'utente: **FN** = **Nome**, **LN** = **Cognome**, **FI** = **Iniziali**, **PHONE** = **Telefono**, **GEN** = **Sesso**, **DOB** = **Data di nascita**, **ST** = **Stato**, **CT** = **Città**, **ZIP** = **Codice postale**, **COUNTRY** = **Paese/Area geografica**

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
