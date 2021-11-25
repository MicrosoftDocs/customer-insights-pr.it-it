---
title: Crea un nuovo ambiente
description: Lo scopo di un ambiente e come crearne uno nuovo.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 8ff04a6b2ffbd513a77f7f8a33358f3d8f559c7e
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673647"
---
# <a name="create-a-new-environment"></a>Crea un nuovo ambiente 

## <a name="overview"></a>Panoramica

Un ambiente è uno spazio in cui gestisci le aree di lavoro e le connessioni. Il modo in cui utilizzi gli ambienti dipende dalla tua organizzazione e dal tuo caso d'uso. Ad esempio puoi creare:

- Un ambiente singolo.
- Ambienti separati di test e di produzione.
- Ambienti separati per team o reparti specifici della tua organizzazione che contengono eventi rilevanti per ogni destinatario.
- Ambienti separati per le diverse filiali globali della società.
- Connessioni alla funzionalità Informazioni dettagliate sul gruppo di destinatari di Customer Insights.

## <a name="create-a-new-environment"></a>Crea un nuovo ambiente

1. Sul lato destro del banner principale, seleziona il selezionatore di ambienti e poi **+Nuovo**.

   :::image type="content" source="media/environment-picker.png" alt-text="Seleziona il selezionatore di ambienti.":::

1. Nel riquadro **Configurazione** , digita un **nome per l'ambiente**.

1. Scelga il **Tipo** di conto, a seconda del tipo di piano.

1. Scegli **Regione** e seleziona **Avanti**. 

1. Digita in **Nome dell'area di lavoro** un valore che consenta di raccogliere dati per app o siti Web specifici. Per maggiori informazioni, vedi [Creare uno spazio di lavoro](create-workspace.md).

1. Scegli il **Tipo di area di lavoro** (Web o per dispositivi mobili) che vuoi creare. 

1. Seleziona **Mostra impostazioni avanzate** per abilitare o disabilitare queste impostazioni opzionali:

   - Allinea **Da sconosciuto a conosciuto** a "enabled" per associare gli eventi web agli utenti che si sono autenticati in precedenza. Per ulteriori informazioni, vedi [Riconoscere eventi Web da visitatori autenticati in precedenza](unknown-to-known.md).
   - Attiva **Filtro traffico bot** su "abilitato" per rimuovere il traffico web dai bot per questo spazio di lavoro. 

1. Seleziona **Completa** quando hai finito. 

1. Installa lo snippet di codice per iniziare a ricevere dati, e poi seleziona **Fine** per creare lo spazio di lavoro. Per ulteriori informazioni, vedi [Panoramica delle risorse per gli sviluppatori](developer-resources.md).

> [!NOTE]
> Ora puoi aggiungere membri e assegnare il loro livello di autorizzazione dall'elenco dei **ruoli** . Per altre informazioni, vedi [Ruoli e autorizzazioni](user-roles.md). 

Per ulteriori informazioni, vedi [Gestire ambienti e aree di lavoro](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Lavora con il tuo nuovo ambiente

- [Creare un'area di lavoro](../engagement-insights/create-workspace.md) e aggiungere membri.
- [Aggiunga del codice al suo sito web](../engagement-insights/instrument-website.md) o alla sua [applicazione mobile](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Visualizza un [rapporto in tempo reale](../engagement-insights/view-reports.md) o crea [rapporti personalizzati](../engagement-insights/custom-reports.md).
- [Crea eventi affinati](../engagement-insights/refined-events.md) per l'esportazione.
- [Esporta i dati](../engagement-insights/export-events.md) in Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
