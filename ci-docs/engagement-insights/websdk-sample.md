---
title: Eseguire un esempio di SDK Web
description: Scopri come personalizzare ed eseguire un esempio di SDK Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036608"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Eseguire l'esempio di SDK Web per la funzionalità relativa alle informazioni dettagliate sull'interazione di Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La libreria SDK Web della funzionalità relativa alle informazioni dettagliate sull'interazione è una libreria JavaScript con codice di esempio che puoi utilizzare sul tuo sito Web.

## <a name="prerequisites"></a>Prerequisiti

- Installare [Visual Studio Code](https://code.visualstudio.com/).
- [Installa l'estensione Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) in Visual Studio Code e acquisisci familiarità con l'esecuzione di Live Server.
- Devi disporre della [chiave di inserimento](instrument-website.md).

## <a name="run-sample"></a>Eseguire esempio

1. [Scarica l'esempio SDK Web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Decomprimi il file compresso `ei_websdk_sample.zip`.

1. Apri la cartella decompressa in Visual Studio Code.

1. Nel file `ei_websdk_sample.html` sostituisci la stringa "INGESTION_KEY" con la tua chiave di inserimento dal portale della funzionalità relativa alle informazioni dettagliate sull'interazione e la stringa "NAME" con il nome globale in cui desideri creare l'istanza dell'SDK. Assicurati di sostituire tutte le occorrenze.

1. Apri il file `ei_websdk_sample.html` utilizzando Live Server in Visual Studio Code selezionando **Passa allo stato Live** dalla barra di stato.

1. All'apertura della pagina, dovrebbe essere inviato automaticamente un evento di visualizzazione. Se si fa clic su uno dei pulsanti nella pagina verranno inviati eventi di azione. Il pulsante **Tieni traccia degli eventi** invierà anche eventi personalizzati. Se selezionato, il pulsante **Passa a Bing** invierà un evento di azione prima di accedere al sito Web Bing.

1. Guarda gli eventi mostrati durante lo spostamento nella tua area di lavoro. Quest'area di lavoro è associata alla chiave di inserimento immessa al passaggio 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]