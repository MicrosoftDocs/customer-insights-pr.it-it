---
title: Gestione dei cookie e del consenso utente per memorizzare i dati dell'utente in Dynamics 365 Customer Insights
description: Scopri in che modo vengono utilizzati i cookie e il consenso dell'utente per identificare i visitatori del sito Web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558876"
---
# <a name="manage-cookies-and-user-consent"></a>Gestire i cookie e il consenso utente

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La funzionalità Informazioni dettagliate sull'interazione di Dynamics 365 Customer Insights utilizza i cookie e le chiavi (`localStorage`) per identificare i visitatori del sito Web.

I cookie sono piccoli file che memorizzano informazioni sulle interazioni di un utente con il sito Web. Vengono archiviati nei Web browser. Quando gli utenti visitano un sito Web del quale hanno memorizzato i cookie, il browser invia tali informazioni al server, che restituisce informazioni univoche per l'utente. Questa è la tecnologia che consente, ad esempio, a un carrello online di mantenere gli articoli selezionati al suo interno anche se un utente si allontana dal sito Web.

## <a name="user-consent"></a>Consenso dell'utente

Il [Regolamento generale sulla protezione dei dati (GDPR)](/dynamics365/get-started/gdpr/) è un regolamento dell'Unione europea (UE) che indica alle organizzazioni come gestire la privacy e la sicurezza dei propri utenti. I cookie spesso memorizzano o raccolgono "dati personali", come un identificatore online, che è tutelato dal GDPR. Se la tua azienda impiega persone all'interno della UE o effettua vendite all'interno ti tale area, sarà vincolata dal GDPR. [Ulteriori informazioni su come Microsoft può aiutarti a conformarti al GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Per consentire all'SDK delle informazioni dettagliate dell'interazione di memorizzare cookie o altre informazioni sensibili, è necessario specificare se gli utenti hanno fornito il proprio consenso in tal senso. Ciò si verifica all'inizializzazione dell'SDK impostando il campo `userConsent` nella configurazione.

Se indichi che non l'utente non ha fornito alcun consenso, l'SDK non memorizzerà alcun dato e non invierà eventi che possono essere utilizzati per tenere traccia del comportamento dell'utente. Eventuali dati precedentemente memorizzati verranno eliminati dal browser.

Se non viene specificato alcun valore in merito al consenso dell'utente, l'SDK presume che l'utente abbia acconsentito. Ciò significa che se tu (come nostro cliente) non specifichi un valore per il consenso dell'utente nell'SDK, i dati verranno raccolti. Tuttavia, se specifichi che il valore per il consenso dell'utente deve essere "true", i dati non verranno raccolti se un utente rifiuta o non fornisce il consenso esplicito.

Di seguito è riportato un frammento di codice per inizializzare l'SDK Web con il consenso dell'utente:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Archiviazione dei dati dei visitatori nella funzionalità relativa alle informazioni dettagliate sull'interazione

### <a name="cookies"></a>Biscotti

- _msei
    - Memorizza l'ID utente anonimo. Questo cookie viene impostato nel dominio del cliente e scade dopo 365 giorni.

### <a name="local-storage"></a>Spazio di archiviazione locale

La funzionalità Informazioni dettagliate sull'interazione utilizza anche le chiavi (`localStorage`) per tenere traccia dei dati non sensibili. Questi dati sono completamente memorizzati nel browser stesso, senza traffico inviato da o verso i tuoi server.

- *EISession.Id*
    - Memorizza le informazioni sulla sessione utente in corso, come l'ID sessione, quando è iniziata e quando scade.
- *EISession.Previous*
    - Memorizza l'URL della pagina visitata in precedenza nella sessione corrente.

Le chiavi nell'archiviazione locale non scadono automaticamente e verranno reimpostate nel corso della successiva sessione SDK.

## <a name="deleting-cookies"></a>Eliminazione dei cookie

I tuoi clienti possono eliminare manualmente i cookie e le chiavi di archiviazione locale in qualsiasi momento tramite le impostazioni del loro browser.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
