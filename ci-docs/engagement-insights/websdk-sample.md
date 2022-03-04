---
title: Eseguire un esempio di SDK Web
description: Scopri come personalizzare ed eseguire un esempio di SDK Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225336"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Eseguire l'esempio di SDK Web per la funzionalità relativa alle informazioni dettagliate sull'interazione di Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La libreria SDK Web della funzionalità relativa alle informazioni dettagliate sull'interazione è una libreria JavaScript con codice di esempio che puoi utilizzare sul tuo sito Web.

## <a name="prerequisites"></a>Prerequisiti

- Installare [Visual Studio Code](https://code.visualstudio.com/).
- [Installa l'estensione Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) in Visual Studio Code e acquisisci familiarità con l'esecuzione di Live Server.
- Dovete avere uno [spazio di lavoro di insights di impegno](create-workspace.md).

## <a name="run-sample"></a>Eseguire esempio

1. [Scarica l'esempio SDK Web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Decomprimi il file compresso `ei_websdk_sample.zip`.

1. Apri la cartella decompressa in Visual Studio Code.

1. Vai al portale degli approfondimenti sull'impegno per il tuo spazio di lavoro. Seleziona **Amministratore** > **Area di lavoro**  e poi **Guida all'installazione**. Seguite la prima opzione e selezionate **Copy code** per copiare lo snippet di codice JavaScript.

1. Nel file `ei_websdk_sample.html` , incollate il frammento di codice che avete appena copiato sotto questa linea:

   - <-- INCOLLA IL FRAMMENTO DI CODICE JAVASCRIPT DAL PORTALE ENGAGMENT INSIGHTS QUI SOTTO QUESTA LINEA -->

1. Apri il file `ei_websdk_sample.html` utilizzando Live Server in Visual Studio Code selezionando **Passa allo stato Live** dalla barra di stato.

1. All'apertura della pagina, dovrebbe essere inviato automaticamente un evento di visualizzazione. Se si fa clic su uno dei pulsanti nella pagina verranno inviati eventi di azione. Il pulsante **Tieni traccia degli eventi** invierà anche eventi personalizzati. Se selezionato, il pulsante **Passa a Bing** invierà un evento di azione prima di accedere al sito Web Bing.

1. Guarda gli eventi mostrati durante lo spostamento nella tua area di lavoro. Quest'area di lavoro è associata alla chiave di inserimento immessa al passaggio 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
