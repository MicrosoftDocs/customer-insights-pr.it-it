---
title: Attività iniziali di SDK iOS
description: Informazioni su come personalizzare ed eseguire l'SDK iOS
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226220"
---
# <a name="get-started-with-the-ios-sdk"></a>Attività iniziali di SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Questa esercitazione ti guida attraverso la strumentazione dell'applicazione iOS con un SDK di informazioni dettagliate sull'interazione Dynamics 365 Customer Insights. Inizierai a vedere gli eventi nel tuo portale tra cinque minuti o prima.

## <a name="configuration-options"></a>Opzioni di configurazione

Le seguenti opzioni di configurazione possono essere passate all'SDK tramite l'apposito file `EIConfig.plist`:

- **ingestionKey**: la chiave di inserimento viene utilizzata per inviare eventi al progetto.
- **autocollectAction**: un valore booleano per abilitare o disabilitare la strumentazione automatica dell'evento azione.
- **autocollectAction**: un valore booleano per abilitare o disabilitare la strumentazione automatica dell'evento di visualizzazione.
- **endpointUrl**: l'URL endpoint a cui verranno diretti gli eventi.

## <a name="prerequisites"></a>Prerequisiti

- Xcode, versione 9+
- iOS, versione 8.2+
- Una chiave di inserimento (vedi sotto per istruzioni su come ottenerla)

## <a name="integrate-the-sdk-into-your-application"></a>Integrazione dell'SDK nell'applicazione

Inizia il processo selezionando un'area di lavoro in cui lavorare, quindi la piattaforma mobile iOS e scaricando l'SDK.

- Utilizza il selettore dell'area di lavoro nel riquadro di navigazione a sinistra per selezionare l'area di lavoro.

- Se non disponi di un'area di lavoro esistente, seleziona **Nuova area di lavoro** e segui i passaggi per creare una [nuova area di lavoro](create-workspace.md).

- Dopo aver creato un'area di lavoro, vai ad **Amministratore** > **Area di lavoro**, quindi seleziona **Guida all'installazione**.

## <a name="configure-the-sdk"></a>Configurazione dell'SDK

Una volta scaricato l'SDK, puoi utilizzarlo in Xcode per abilitare e definire gli eventi. A tale scopo, è possibile procedere in due modi:

### <a name="option-1-using-cocoapods-recommended"></a>Opzione 1. Utilizzo di CocoaPods (consigliato)
CocoaPods è un gestore delle dipendenze per i progetti Swift e Objective-C Cocoa. Il suo utilizzo semplifica l'integrazione dell'SDK di informazioni dettagliate sull'interazione per iOS. CocoaPods ti consente inoltre di eseguire l'aggiornamento all'ultima versione dell'SDK di informazioni sull'interazione. Ecco come usare CocoaPods per integrare l'SDK di informazioni sull'interazione nel tuo progetto Xcode. 

1. Installa CocoaPods. 

1. Crea un nuovo file chiamato Podfile all'interno della directory radice del tuo progetto e aggiungi le seguenti istruzioni. Sostituisci YOUR_TARGET_PROJECT_NAME con il nome del tuo progetto Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
La configurazione del pod precedente contiene sia la versione di debug sia quella di rilascio dell'SDK. Scegli quella più adatta per il tuo progetto.

1. Installa il pod eseguendo il seguente comando: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Opzione 2. Utilizzo del collegamento di download

1. Scarica l'[SDK iOS delle informazioni dettagliate sull'interazione](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) e posiziona il file `EIObjC.xcframework` nella cartella `Frameworks`.

1. Se una cartella `Frameworks` non esiste, creane una nella cartella del progetto.

## <a name="enable-auto-instrumentation"></a>Abilitazione della strumentazione automatica
 
Puoi abilitare facilmente la strumentazione automatica senza codifica. Quando il progetto verrà eseguito, terrà traccia automaticamente degli eventi `view` e `action` utilizzando la chiave di inserimento configurata. 

1. Aggiorna e includi il file `EIConfig.plist` fornito nella cartella della directory del progetto per i seguenti campi:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = SÌ
    - autocollectAction = SÌ

2. Quindi aggiungi il file `EIConfig.plist` al tuo progetto in Xcode. 



Per disabilitare la strumentazione automatica, aggiorna i seguenti campi nel file `EIConfig.plist` incluso nella cartella della directory del progetto. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementazione di eventi personalizzati

1. Apri il progetti in Xcode e passa alle impostazioni **Generali**. 
1. Aggiungi `EIObjC.xcframework` al progetto nella sezione "Framework, Librerie e Contenuto incorporato".

1. Importa il file di intestazione del framework in AppDelegate.m con il frammento di codice seguente:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inizializza l'SDK delle informazioni dettagliate sull'interazione dall'applicazione: didFinishLaunchingWithOptions.
1. Copia il frammento XML dalla **Guida all'installazione**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Registra un evento:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Impostazione dei dettagli utente per il tuo evento

L'SDK ti consente di definire le informazioni utente che possono essere inviate con ogni evento. Puoi specificare le informazioni dell'utente chiamando l'API `setUser:(nonnull EIUser *)user` sull'SDK.

Specificare i dettagli dell'utente sul livello `Analytics` significa che tutte le telemetrie avranno queste informazioni. Tuttavia, se si specifica a livello di evento chiamando l'API `setUser:(nonnull EIUser *)user` sull'oggetto EIEvent, solo quell'evento specifico conterrà le informazioni.

La classe di dati `EIUser` contiene le seguenti proprietà NSString:

- **localId**: l'ID locale dell'utente.
- **authId**: l'ID utente autenticato.
- **authType**: il tipo di autenticazione utilizzato per ottenere l'ID utente autenticato.
- **name**: il nome dell'utente.
- **email**: l'indirizzo e-mail dell'utente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
