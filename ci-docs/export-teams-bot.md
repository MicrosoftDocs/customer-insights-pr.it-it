---
title: Bot di Teams per Dynamics 365 Customer Insights (anteprima)
description: Cerca i profili cliente unificati in Microsoft Teams con l'aiuto di un bot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 62a0216de848b5a3a81fdd6ac078feb551fcfec6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081456"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot di Teams per Dynamics 365 Customer Insights (anteprima)

Connettiti con Microsoft Teams per consentire a un bot di cercare profili cliente unificati nei canali di Teams.

> [!div class="mx-imgBorder"]
> ![Bot di Teams che mostra un record del cliente.](media/teams-bot.png "Bot di Teams che mostra un record del cliente")

## <a name="prerequisites"></a>Prerequisiti

Per impostare e configurare il bot, devono essere soddisfatti i seguenti prerequisiti:

- Deve esserci almeno un'[origine dati aggiunta](data-sources.md).
- Il [processo di unificazione](data-unification.md) è stato completato.
- I campi vengono aggiunti all'[indice di ricerca e dei filtri](search-filter-index.md).
- Customer Insights e Teams sono nella stessa organizzazione.
- Il tuo ambiente ha il target primario impostato sui clienti individuali. Gli account aziendali non sono supportati.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Configurare il bot

1. Passa a **Amministratore** > **Destinazioni di esportazione**.
1. Nel riquadro Microsoft Teams, seleziona **Configura**.
1. Vieni reindirizzato all'area **App** in Teams. Puoi anche aprire Teams e selezionare **App** nell'angolo in basso a sinistra o [scaricarla da AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) direttamente.
1. Cerca **Customer Insights** e seleziona l'app.
1. Seleziona **Aggiungi**.
1. Dopo aver effettuato l'accesso a Customer Insights in Teams, viene visualizzato un messaggio di benvenuto e potrai iniziare.

## <a name="things-you-can-do-with-the-bot"></a>Operazioni eseguibili con il bot

Il bot offre funzionalità di ricerca per profili cliente unificati.

- Immetti **cerca** seguito da un nome, un indirizzo e-mail o qualsiasi altro campo nel profilo cliente unificato che viene aggiunto all'indice di ricerca e filtro.

  Otterrai una scheda con un massimo di 15 campi dal profilo cliente risultante. Più corrispondenze restituiscono un elenco di risultati in cui è possibile selezionare un profilo. Puoi aggiungere il termine di ricerca tra virgolette doppie per cercare una corrispondenza esatta.

- Se la tua organizzazione gestisce più ambienti Customer Insights nella stessa organizzazione, puoi immettere **switchinstance** per scegliere l'ambiente a cui connettere il bot.

- Immetti **Aiuto** per visualizzare un elenco di comandi disponibili per il bot.  


[!INCLUDE [footer-include](includes/footer-banner.md)]