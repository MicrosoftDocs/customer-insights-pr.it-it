---
title: Esecuzione dell'esempio SDK iOS
description: Progetto di esempio per conoscere l'SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036833"
---
# <a name="run-the-ios-sdk-sample"></a>Esecuzione dell'esempio SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Questo progetto iOS di esempio ti aiuta a capire come funziona l'SDK in un'app. Non dovrai scrivere il codice. Aggiungi la tua chiave di inserimento e puoi vedere subito gli eventi nella tua area di lavoro.

## <a name="prerequisites"></a>Prerequisiti

- [Xcode, versione 9+](https://developer.apple.com/xcode/downloads/)
- [Chiave di inserimento](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Download dell'esempio SDK iOS

1. [Scarica l'esempio SDK iOS di informazioni dettagliate sull'interazione](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Decomprimi il file compresso `ei-ios-sample.zip`.
1. Apri il progetto dell'app di esempio in Xcode.
1. Nel file `EIConfig.plist` sostituisci la stringa `“YOUR-INGESTION-KEY”` nel campo `ingestionKey` con la chiave di inserimento dell'area di lavoro delle informazioni dettagliate sull'interazione in **Amministratore** > **Area di lavoro** > **Guida all'installazione**.
1. Seleziona **Esegui** per avviare il progetto di esempio.
1. Visualizza gli eventi nella tua area di lavoro.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
