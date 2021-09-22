---
title: Riconosci gli eventi Web di visitatori autenticati in precedenza tramite Da sconosciuto a noto
description: La funzione Da sconosciuto a noto consente di associare eventi su un sito Web a visitatori che si sono autenticati in precedenza.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036788"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Riconosci gli eventi Web di visitatori autenticati in precedenza

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La funzionalità **Da sconosciuto a noto** nella funzionalità delle informazioni dettagliate consente di associare eventi in un sito Web a visitatori che si sono autenticati in precedenza. Se la funzione è disabilitata, i visitatori che si sono autenticati durante una visita precedente e poi sono usciti non vengono identificati se non si autenticano di nuovo quando tornano. 

Ad esempio, una persona ha visitato un sito Web nell'ultima settimana, ha effettuato l'accesso al proprio account utente sul sito e ha sfogliato il catalogo prodotti. La persona torna la settimana successiva per esaminare più prodotti senza accedere al proprio account. Il proprietario del sito che utilizza la funzionalità **Da sconosciuto a noto** saprebbe che la stessa persona è tornata e cosa ha fatto sul sito. Ciò consente report e analisi più precisi delle attività del sito Web.

## <a name="enable-unknown-to-known"></a>Abilita Da sconosciuto a noto

Per abilitare questa funzionalità devi essere un [amministratore dell'area di lavoro](user-roles.md). 

1. Nelle informazioni dettagliate, vai ad **Amministratore** > **Area di lavoro**. 
2. Seleziona la scheda **Impostazioni**.
3. Nella sezione **Da sconosciuto a noto**, imposta l'interruttore su **Abilitato**.

![Abilita Da sconosciuto a noto](media/U2Ktoggle.png "Abilita Da sconosciuto a noto")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Aggiunta del codice JavaScript al frammento del rilevamento del tuo sito

Un sito Web può catturare l'**authId utente** con il seguente esempio JavaScript utilizzando l'[SDK Web delle informazioni dettagliate sul coinvolgimento](advanced-SDK-implementation.md). Per far funzionare la funzionalità **Da sconosciuto a noto**, è necessario acquisire authId *e* abilitare userMapping:True nel frammento JavaScript come nell'esempio qui sotto.

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
