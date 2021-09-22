---
title: Gestire i cookie e il consenso dell'utente per memorizzare i dati dell'utente
description: Scopri in che modo vengono utilizzati i cookie e il consenso dell'utente per identificare i visitatori del sito Web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036743"
---
# <a name="manage-cookies-and-user-consent"></a>Gestire i cookie e il consenso utente

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La funzionalità relativa alle informazioni dettagliate sull'interazione di Dynamics 365 Customer Insights utilizza cookie e archiviazione locale (`localStorage`) per identificare i visitatori del sito Web.

I cookie sono piccoli file che memorizzano informazioni sulle interazioni di un utente con il sito Web. Vengono archiviati nei Web browser. Quando gli utenti visitano un sito Web del quale hanno memorizzato i cookie, il browser invia tali informazioni al server, che restituisce informazioni univoche per l'utente. Questa è la tecnologia che consente, ad esempio, a un carrello online di mantenere gli articoli selezionati al suo interno anche se un utente si allontana dal sito Web.

## <a name="user-consent"></a>Consenso dell'utente

Il [Regolamento generale sulla protezione dei dati (GDPR)](/dynamics365/get-started/gdpr/) è un regolamento dell'Unione europea (UE) che indica alle organizzazioni come gestire la privacy e la sicurezza dei propri utenti. I cookie spesso memorizzano o raccolgono "dati personali", come un identificatore online, che è tutelato dal GDPR. Se la tua azienda impiega persone all'interno della UE o effettua vendite all'interno ti tale area, sarà vincolata dal GDPR. [Ulteriori informazioni su come Microsoft può aiutarti a conformarti al GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Per consentire all'SDK delle informazioni dettagliate dell'interazione di memorizzare cookie o altre informazioni sensibili, è necessario specificare se gli utenti hanno fornito il proprio consenso in tal senso. Ciò si verifica durante l'inizializzazione dell'SDK.

Se indichi che non l'utente non ha fornito alcun consenso, l'SDK non memorizzerà alcun dato e non invierà eventi che possono essere utilizzati per tenere traccia del comportamento dell'utente. Eventuali dati precedentemente memorizzati verranno eliminati dal browser.

Se non viene specificato alcun valore in merito al consenso dell'utente, l'SDK presume che l'utente abbia acconsentito. Ciò significa che se tu (come nostro cliente) non specifichi un valore per il consenso dell'utente nell'SDK, i dati verranno raccolti. Tuttavia, se specifichi che il valore per il consenso dell'utente deve essere "true", i dati non verranno raccolti se un utente rifiuta o non fornisce il consenso esplicito.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Archiviazione dei dati dei visitatori nella funzionalità relativa alle informazioni dettagliate sull'interazione

### <a name="cookies"></a>Biscotti

- _msei
    - Memorizza l'ID utente anonimo. Questo cookie viene impostato nel dominio del cliente e scade dopo 365 giorni.

### <a name="local-storage"></a>Spazio di archiviazione locale

La funzionalità relativa alle informazioni dettagliate sull'interazione utilizza anche l'archiviazione locale (`localStorage`) per tenere traccia dei dati non sensibili. Questi dati sono completamente memorizzati nel browser stesso, senza traffico inviato da o verso i tuoi server.

- *EISession.Id* 
    - Memorizza le informazioni sulla sessione utente in corso, come l'ID sessione, quando è iniziata e quando scade.
- *EISession.Previous*
    - Memorizza l'URL della pagina visitata in precedenza nella sessione corrente.
    
Le chiavi nella memoria locale non scadono automaticamente. Verranno ripristinate durante la prossima sessione dall'SDK.

## <a name="deleting-cookies"></a>Eliminazione dei cookie

I tuoi clienti possono eliminare manualmente i cookie e le chiavi di archiviazione locale in qualsiasi momento tramite le impostazioni del loro browser.


[!INCLUDE[footer-include](../includes/footer-banner.md)]