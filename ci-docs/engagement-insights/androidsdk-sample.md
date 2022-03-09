---
title: Esempio SDK Android
description: Progetto di esempio per conoscere l'SDK Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229923"
---
# <a name="run-the-android-sdk-sample"></a>Eseguire l'esempio SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Questo progetto Android di esempio ti aiuta a capire come funziona l'SDK in un'app. Non dovrai scrivere il codice. Aggiungi la tua chiave di inserimento e puoi vedere subito gli eventi nella tua area di lavoro.

## <a name="prerequisites"></a>Prerequisiti

- [Android Studio](https://developer.android.com/studio)
- [Chiave di inserimento](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Scaricare l'esempio SDK Android

1. [Scarica l'esempio SDK Android di informazioni dettagliate sull'interazione](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Decomprimi il file compresso `ei-android-sample.zip`.
1. Apri la cartella decompressa in Android Studio.
1. Nel file `AndroidManifest.xml` sostituisci la stringa `"Your-Ingestion-Key"` con la chiave di inserimento dell'area di lavoro delle informazioni dettagliate sull'interazione in **Amministratore** > **Area di lavoro** > **Guida all'installazione**. 

   > [!NOTE]
   > Non devi sostituire la sezione `${applicationId}`. Viene popolata automaticamente.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Seleziona **Esegui** per avviare il progetto di esempio.
1. Visualizza gli eventi nella tua area di lavoro.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
