---
title: Scenari dell'SDK Web avanzati
description: Scenari avanzati da considerare durante la strumentazione del tuo sito Web con un SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036333"
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
    
L'esempio seguente mostra un frammento di codice che invia informazioni sull'utente. Quando vedi Funzioni con denotazione *, sostituiscilo con la tua implementazione di chiamata di quei valori:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
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

Inoltre puoi specificare le informazioni sull'utente chiamando l'API `setUser(user: IUser)` sull'SDK. La telemetria inviata dopo aver chiamato `setUser API` conterrà le informazioni dell'utente.

## <a name="adding-custom-properties-for-each-event"></a>Aggiunta di proprietà personalizzate per ogni evento

L'SDK ti consente di specificare proprietà personalizzate che possono essere inviate con ogni evento. Puoi specificare le proprietà personalizzate come un oggetto contenente coppie chiave-valore (il valore può essere di tipo `string | number | boolean`). L'oggetto può essere aggiunto in una proprietà chiamata `props`, simile a `src`, `name` e `cfg` nella configurazione del frammento di codice. 

L'esempio seguente mostra un frammento di codice che invia proprietà personalizzate:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
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

Puoi inoltre specificare singolarmente le proprietà personalizzate chiamando l'API `setProperty(name: string, value: string | number | boolean)` sull'SDK.

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