---
title: Attività iniziali di SDK Android
description: Informazioni su come personalizzare ed eseguire SDK Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494280"
---
# <a name="get-started-with-the-android-sdk"></a>Attività iniziali di SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Questa esercitazione ti guida attraverso il processo di strumentazione dell'applicazione Android con un SDK di informazioni dettagliate sull'interazione Dynamics 365 Customer Insights. Inizierai a vedere gli eventi nel tuo portale tra cinque minuti o prima.

## <a name="configuration-options"></a>Opzioni di configurazione
Le seguenti opzioni di configurazione possono essere passate all'SDK:

- **ingestionKey**: la chiave di inserimento viene utilizzata per inviare eventi alla tua area di lavoro.

## <a name="prerequisites"></a>Prerequisiti

- Android Studio

- Livello API Android minimo: 16 (Jelly Bean)

- Una chiave di inserimento (vedi sotto per istruzioni su come ottenerla)

## <a name="integrate-the-sdk-into-your-application"></a>Integrazione dell'SDK nell'applicazione
Inizia il processo selezionando un'area di lavoro, quindi la piattaforma mobile Android e scaricando l'SDK Android.

- Utilizza il selettore dell'area di lavoro nel riquadro di navigazione a sinistra per selezionare l'area di lavoro.

- Se non disponi di un'area di lavoro esistente, seleziona **Nuova area di lavoro** e segui i passaggi per creare una [nuova area di lavoro](create-workspace.md).

- Dopo aver creato un'area di lavoro, vai ad **Amministratore** > **Area di lavoro**, quindi seleziona **Guida all'installazione**. 

## <a name="configure-the-sdk"></a>Configurazione dell'SDK

Dopo aver scaricato l'SDK, puoi utilizzarlo in Android Studio per abilitare e definire gli eventi. A tale scopo, è possibile procedere in due modi:
### <a name="option-1-using-jitpack-recommended"></a>Opzione 1. Utilizzo di JitPack (consigliato)
1. Aggiungi il repository JitPack a `build.gradle` radice:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Aggiungi la dipendenza:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>Opzione 2. Utilizzo del collegamento di download
1. Scarica l'[SDK Android delle informazioni dettagliate sull'interazione](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) e posiziona il file `eiandroidsdk-debug.aar` nella cartella `libs`.

1. Apri il file `build.gradle` a livello di progetto e aggiungi i frammenti di codice seguenti:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Aggiungi l'autorizzazione per la rete e Internet nel file `AndroidManifest.xml` che si trova nella cartella `manifests`. 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. Imposta la configurazione dell'SDK di informazioni dettagliate sull'interazione tramite il file `AndroidManifest.xml`. 

## <a name="enable-auto-instrumentation"></a>Abilitazione della strumentazione automatica
1. Copia il frammento XML dalla **Guida all'installazione**. `Your-Ingestion-Key` dovrebbe essere popolata automaticamente.

   > [!NOTE]
   > Non devi sostituire la sezione `${applicationId}`. Viene popolata automaticamente.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Abilita o disabilita l'acquisizione automatica degli eventi `View` impostando il campo `autoCapture` precedente su `true` o `false`. Gli eventi `Action` devono attualmente essere aggiunti manualmente.

1. (Facoltativo) Altre configurazioni includono l'impostazione dell'URL dell'agente di raccolta endpoint. Possono essere aggiunte sotto i metadati della chiave di inserimento in `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>Implementazione di eventi personalizzati

Dopo aver inizializzato l'SDK, puoi lavorare con gli eventi e le loro proprietà nell'ambiente `MainActivity`.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Impostazione della proprietà per tutti gli eventi (facoltativo)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

I seguenti tipi sono supportati per le proprietà degli eventi di contesto:
- Stringa
- Data
- Doppia
- Lungo
- Booleano
- UUID

### <a name="track-an-event"></a>Registra un evento

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Impostazione dei dettagli utente per il tuo evento (facoltativo)

L'SDK ti consente di definire le informazioni utente che possono essere inviate con ogni evento. Puoi specificare le informazioni dell'utente chiamando l'API `setUser(user: User)` sul livello `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

La classe di dati `User` contiene le seguenti proprietà di stringa:

- **localId**: l'ID locale dell'utente.
- **authId**: l'ID utente autenticato.
- **authType**: il tipo di autenticazione utilizzato per ottenere l'ID utente autenticato.
- **name**: il nome dell'utente.
- **email**: l'indirizzo e-mail dell'utente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
