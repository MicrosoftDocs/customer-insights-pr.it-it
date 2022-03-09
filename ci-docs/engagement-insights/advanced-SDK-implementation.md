---
title: Scenari dell'SDK Web avanzati
description: Scenari avanzati da considerare durante la strumentazione del tuo sito Web con un SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227203"
---
# <a name="advanced-web-sdk-instrumentation"></a>Strumentazione SDK Web avanzata

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Questo articolo ti guida attraverso scenari avanzati da considerare durante la [strumentazione del tuo sito Web](instrument-website.md) con un SDK della funzionalità relativa alle informazioni dettagliate sull'interazione di Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Impostazione dei dettagli utente per il tuo evento

L'SDK ti consente di definire le informazioni utente che possono essere inviate con ogni evento. Puoi specificare i dettagli dell'utente in una proprietà chiamata `user` (il dato previsto per questa proprietà è l'oggetto `IUser`), simile a `src`, `name` e `cfg` nella configurazione del frammento di codice.

L'oggetto `IUser` contiene le seguenti proprietà stringa:

- **localId**: l'ID locale dell'utente.
- **authId**: l'ID utente autenticato.
- **authType**: il tipo di autenticazione utilizzato per ottenere l'ID utente autenticato.
- **name**: il nome dell'utente.
- **email**: l'indirizzo e-mail dell'utente.

L'esempio seguente mostra un frammento di codice che invia informazioni sull'utente. Dove vedi le funzioni precedute da un simbolo asterisco *, sostituisci la funzione con la tua implementazione personalizzata:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Puoi anche specificare le informazioni dell'utente chiamando l'API `setUser(user: IUser)`. La telemetria inviata dopo aver chiamato l'API `setUser` conterrà le informazioni dell'utente.

## <a name="adding-custom-properties-for-each-event"></a>Aggiunta di proprietà personalizzate per ogni evento

L'SDK ti consente di specificare proprietà personalizzate che possono essere inviate con ogni evento. Puoi specificare le proprietà personalizzate come un oggetto contenente coppie chiave-valore (il valore può essere di tipo `string | number | boolean`). Puoi aggiungere l'oggetto in una proprietà denominata `props`, simile a `src`, `name` e `cfg` nella configurazione del frammento di codice.

L'esempio seguente mostra un frammento di codice che invia proprietà personalizzate:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Puoi anche specificare le singole proprietà personalizzate chiamando l'API `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>Invio di eventi personalizzati

Puoi utilizzare l'SDK per inviare eventi personalizzati. Devi specificare un nome per l'evento e le proprietà da inviare con l'evento.

L'esempio seguente mostra un frammento di codice che rileva un evento personalizzato. "NAME" è il valore nella chiave `name` nella configurazione del frammento. È anche il nome della variabile nell'oggetto finestra in cui viene caricato l'SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
