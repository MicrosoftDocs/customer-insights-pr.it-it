---
title: Visualizzare e creare dimensioni
description: Come creare, modificare ed eliminare le dimensioni.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623637"
---
# <a name="view-and-create-dimensions"></a>Visualizzare e creare dimensioni

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Una dimensione è un attributo di un evento che descrive, filtra o raggruppa i dati. Se stai eseguendo una promozione di marketing sul tuo sito Web, puoi utilizzare le dimensioni per ordinare i visitatori per utenti nuovi e ricorrenti.  

Engagement insights include dimensioni out-of-the-box (OOB) per le proprietà degli eventi. Ecco alcuni esempi:

- Nome browser
- Nome pagina
- Modello dispositivo
- Sistema operativo
- Paese/area geografica

## <a name="view-dimensions"></a>Visualizza dimensioni

Le dimensioni si basano sulle proprietà degli eventi esistenti. Quando utilizzi il codice di rilevamento per le informazioni dettagliate, le dimensioni del sistema vengono create automaticamente.

1. Vai a **Dati** nel riquadro di spostamento sinistro. 
1. Seleziona **Dimensioni** per visualizzare un elenco di tutte le dimensioni nell'area di lavoro. 
   > [!NOTE]
   > Le dimensioni generate dal sistema sono di sola lettura. Non è possibile modificarle. Puoi solo creare e modificare dimensioni personalizzate.

## <a name="create-a-dimension"></a>Crea una dimensione

Oltre alle dimensioni generate dal sistema, gli amministratori dell'ambiente e dell'area di lavoro possono creare dimensioni personalizzate. Le dimensioni personalizzate si basano sulle proprietà predefinite degli eventi di base oppure possono utilizzare [proprietà personalizzate di un evento](advanced-SDK-implementation.md).

1. Vai a **Dati** > **Dimensioni**.
1. Seleziona **Nuova dimensione**.

   :::image type="content" source="media/add-dimension.png" alt-text="Aggiungi una dimensione a un evento.":::

1. Nel riquadro **Crea una dimensione**, seleziona una proprietà su cui basare la dimensione. L'elenco delle proprietà mostrerà tutte le proprietà nell'area di lavoro non assegnate a una dimensione.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Creare una nuova dimensione.":::
      
3. Immetti un nome nella casella **Nome visualizzato**. Opzionalmente, puoi aggiungere una **Descrizione**.
4. Seleziona **Crea flusso** per salvare la dimensione. Potrebbe essere necessario fino a un minuto prima di poter utilizzare la dimensione in un [report personalizzato](custom-reports.md) o [segmento](segments.md). 

## <a name="edit-a-dimension"></a>Modifica una dimensione

Puoi modificare il nome e la descrizione di una dimensione. Puoi solo modificare le dimensioni create dall'utente, ma non puoi modificare le dimensioni di sistema.


1. Vai a **Dati** > **Dimensioni**.
1. Seleziona la dimensione che vuoi eliminare.
1. Nel riquadro **Modifica dimensione** aggiorna la dimensione.
1. Seleziona **Applica** per salvare le modifiche.

## <a name="delete-a-dimension"></a>Elimina una dimensione

Puoi eliminare solo le dimensioni create dall'utente, ma non puoi rimuovere le dimensioni di sistema.

L'eliminazione di una dimensione è permanente. I report e i segmenti che utilizzano una dimensione eliminata non funzioneranno più. 

1. Vai a **Dati** > **Dimensioni**.
1. Seleziona la dimensione che vuoi eliminare.
1. Nel riquadro **Modifica dimensione** seleziona **Elimina dimensione**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Elimina una dimensione per un evento.":::

1. Immetti **CONFERMA ELIMINAZIONE** (in maiuscolo) per confermare l'eliminazione. 
1. Seleziona **Elimina.**

[!INCLUDE[footer-include](../includes/footer-banner.md)]
