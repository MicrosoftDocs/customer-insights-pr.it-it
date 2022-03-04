---
title: Creare e modificare eventi
description: Come creare e modificare gli eventi.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228208"
---
# <a name="create-and-modify-events"></a>Creare e modificare eventi

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un evento è un dato che rappresenta il comportamento dell'utente, come l'impegno su un sito Web.

- Un evento *base* registra quando un utente visualizza una pagina (evento di visualizzazione) o interagisce con il contenuto (evento di azione).
- Un evento *affinato* è una visualizzazione virtuale di un evento di base. Puoi definire eventi affinati rimuovendo e aggiungendo proprietà o filtrando gli eventi in base ai valori delle proprietà.

## <a name="prerequisites"></a>Prerequisiti

Per ottenere gli eventi, i dati del tuo sito web devono prima essere collegati agli approfondimenti sull'impegno con uno snippet di codice. Per maggiori informazioni, vedi [Installare l'SDK web su un sito web](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Collegate prima i vostri dati.":::

## <a name="create-refined-events"></a>Crea eventi affinati

Utilizza eventi affinati per ridurre l'ambito di un evento di base per l'[esportazione](export-events.md) o per rimuovere proprietà che non sono necessarie per l'esposizione.

> [!NOTE]
> Una volta aggiunto l'SDK web al tuo sito web, puoi visualizzare i tuoi eventi di base e creare eventi raffinati. 

Per visualizzare i tuoi eventi di base:

1. Vai a **Dati** nel riquadro di spostamento sinistro.

1. Seleziona **Eventi** per vedere un elenco di tutti gli eventi nell'area di lavoro.

    :::image type="content" source="media/data-events.png" alt-text="Visualizza gli eventi.":::

Per creare un evento raffinato da un evento base: 

1. Vai a **Data** > **Events** e seleziona **+ New events** nella parte superiore dello schermo.

1. Nella finestra di dialogo **Nuovi eventi** , seleziona **Crea eventi raffinati** e poi seleziona **Avanti**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Nuova procedura guidata per gli eventi.":::
     
1. Nella finestra di dialogo **Nuovi eventi** , inserite le seguenti informazioni:

   - Seleziona un evento dal menu a tendina **Eventi di base** .
   - Immetti un nome nella casella **Nome visualizzato eventi affinati**.
   - Aggiorna facoltativamente il **nome effettivo** suggerito senza utilizzare spazi.

1. Seleziona **Crea** per applicare le tue impostazioni.

L'evento perfezionato appare ora nella tua lista **Eventi** .

### <a name="edit-event-name"></a>Modificare il nome evento

Puoi cambiare il nome e le proprietà di un evento base o raffinato.

1. Vai a **Dati** > **Eventi**. 

1. Seleziona **Altro [...]** per un evento e seleziona **Modifica nome**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Opzioni per creare eventi affinati.":::

3. Aggiorna il nome dell'evento e seleziona **Rinomina**.

### <a name="view-the-details-of-a-refined-event"></a>Visualizza i dettagli di un evento raffinato:

1. Nell'elenco degli **eventi** , seleziona il tuo evento base o raffinato. 

1. Seleziona **Aggiungi e rimuovi proprietà** nella parte superiore dello schermo per aprire il pannello **Modifica proprietà** . 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Aggiungere e rimuovere proprietà.":::

1. Utilizza le caselle di controllo per selezionare le proprietà che desideri mostrare e quelle che desideri nascondere. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Modifica proprietà per eventi affinati.":::

1. Seleziona **Conferma** per applicare la tua selezione e poi seleziona **Salva**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Modifica le proprietà selezionate per un evento raffinato

1. Vai a **Dati** > **Eventi** e seleziona gli eventi affinati per aprire la visualizzazione dettagliata.
1. Seleziona **Aggiungi e rimuovi proprietà**. 
1. Modifica la selezione delle caselle di controllo.
1. Seleziona **Conferma** poi **Salva** per applicare le modifiche.

Per informazioni sull'esportazione di eventi, vedi [Esportare eventi](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
