---
title: Crea e modifica eventi affinati
description: Come creare e modificare eventi affinati.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034779"
---
# <a name="create-and-modify-refined-events"></a>Crea e modifica eventi affinati

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Un evento è un dato che rappresenta il comportamento dell'utente, come l'impegno su un sito Web.

- Un evento *base* registra quando un utente visualizza una pagina (evento di visualizzazione) o interagisce con il contenuto (evento di azione).
- Un evento *affinato* è una visualizzazione virtuale di un evento di base. Puoi definire eventi affinati rimuovendo e aggiungendo proprietà o filtrando gli eventi in base ai valori delle proprietà.

Utilizza eventi affinati per ridurre l'ambito di un evento di base per l'[esportazione](export-events.md) o per rimuovere proprietà che non sono necessarie per l'esposizione.

## <a name="create-refined-events"></a>Crea eventi elaborati

Esistono tre modi per creare un evento affinato da un evento di base. 

1. Vai a **Dati**> **Eventi** e scegli una delle seguenti opzioni:
    - Seleziona **Nuovi eventi** poi seleziona **Crea eventi affinati**.
    - Seleziona un evento di base per aprire una visualizzazione dettagliata e seleziona **Crea eventi affinati** dal menu in alto.
    - Seleziona **Altro [...]** per aprire il menu di scelta rapida per un evento di base. Quindi seleziona **Crea eventi affinati**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Opzioni per creare eventi affinati.":::

1. Nella finestra di dialogo **Crea eventi affinati**, immetti le seguenti informazioni:

- Seleziona un evento dall'elenco a discesa **Eventi di base** se stai creando un nuovo evento.
- Immetti un nome nella casella **Nome visualizzato eventi affinati**.
- Aggiorna facoltativamente il **nome effettivo** suggerito senza utilizzare spazi.

3. Seleziona **Crea** per applicare le tue impostazioni.

1. Nella visualizzazione dettagliata del tuo evento affinato, seleziona **Aggiungi e rimuovi proprietà** per aprire il riquadro **Modifica proprietà**. 

1. Utilizza le caselle di controllo per selezionare le proprietà che desideri mostrare e quelle che desideri nascondere. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Modifica proprietà per eventi affinati.":::

1. Seleziona **Conferma** per applicare la selezione.

1. Seleziona **Salva** per salvare la configurazione.

## <a name="edit-refined-events"></a>Modificare eventi affinati

Puoi modificare il nome e le proprietà di un evento affinato.

### <a name="edit-event-name"></a>Modificare il nome evento

1. Vai a **Dati** > **Eventi**. 
1. Seleziona **Altro [...]** per un evento e seleziona **Modifica nome**.
1. Aggiorna il nome dell'evento e seleziona **Rinomina**.

### <a name="edit-selected-properties"></a>Modificare le proprietà selezionate

1. Vai a **Dati** > **Eventi** e seleziona gli eventi affinati per aprire la visualizzazione dettagliata.
1. Seleziona **Aggiungi e rimuovi proprietà**. 
1. Modifica la selezione delle caselle di controllo.
1. Seleziona **Conferma** poi **Salva** per applicare le modifiche.

Per informazioni sull'esportazione di eventi, vedi [Esportare eventi](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
