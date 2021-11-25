---
title: Crea una nuova area di lavoro
description: Lo scopo di uno spazio di lavoro e come crearne uno nuovo.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673448"
---
# <a name="create-a-new-workspace-and-add-members"></a>Creare un nuovo spazio di lavoro e aggiungere membri

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un'area di lavoro ti consente di visualizzare l'attività degli utenti in tempo reale per comprendere meglio il tuo gruppo di destinatari. In essa archivi e gestisci eventi e rapporti.

Quando crei un'area di lavoro, selezioni il tipo di dati su cui vuoi concentrarti. Puoi aggiungere altri utenti o membri a un'area di lavoro esistente in qualsiasi momento. 

## <a name="create-a-new-workspace"></a>Crea una nuova area di lavoro

Il processo di creazione di un'area di lavoro include la configurazione dell'*ambiente* per organizzare l'area di lavoro. Un ambiente è uno spazio che può contenere una o più aree di lavoro. Puoi usare un ambiente per gestire le tue aree di lavoro e le connessioni alla funzionalità di informazioni dettagliate sul gruppo di destinatari.

1. Seleziona **+Nuovo** dalla commutazione dell'area di lavoro.

   :::image type="content" source="media/new-workspace.png" alt-text="Pagina Customer Insights con callout nel riquadro di spostamento e descrizione.":::

1. Nel riquadro **Area di lavoro**, inserisci il **nome di un'area di lavoro**.

   :::image type="content" source="media/workspace-name.png" alt-text="Digitare il nome di uno spazio di lavoro.":::

1. Scegli il tipo di piattaforma (Web o per dispositivi mobili) che vuoi misurare.

1. Seleziona **Mostra impostazioni avanzate** per abilitare o disabilitare queste impostazioni opzionali:

   - Allinea **Da sconosciuto a conosciuto** a "enabled" per associare gli eventi web agli utenti che si sono autenticati in precedenza. Per maggiori informazioni, vedere [Riconoscere eventi web da visitatori precedentemente autenticati](unknown-to-known.md)
   - Attiva **Filtro traffico bot** su "abilitato" per rimuovere il traffico web dai bot per questo spazio di lavoro. 

1. Seleziona **Completa** quando hai finito. 

1. Installa lo snippet di codice per iniziare a ricevere dati, e poi seleziona **Fine** per creare lo spazio di lavoro. Per ulteriori informazioni, vedi [Panoramica delle risorse per gli sviluppatori](developer-resources.md).

> [!NOTE]
> Ora puoi aggiungere membri e assegnare il loro livello di autorizzazione dall'elenco dei **ruoli** . Per altre informazioni, vedi [Ruoli e autorizzazioni](user-roles.md). 

Per ulteriori informazioni, vedi [Gestire ambienti e aree di lavoro](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
