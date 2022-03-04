---
title: Gestire aree di lavoro e ambienti
description: Come creare, rinominare ed eliminare aree di lavoro e ambienti.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ded9e98f06109b7cdc27f449455b7f58d633722f
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350642"
---
# <a name="manage-environments-and-workspaces"></a>Gestire ambienti e aree di lavoro

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Panoramica

Questo argomento discute come gestire gli spazi di lavoro e gli ambienti una volta che sono già stati creati. 

- Uno *spazio di lavoro* è uno spazio per memorizzare e gestire eventi e rapporti. È qui che puoi visualizzare l'impegno degli utenti in tempo reale. Quando crei un'area di lavoro, selezioni il tipo di dati da inviare all'area di lavoro. Attualmente sono supportati i dati Web e le app mobili. Per altre informazioni, vedi [Creare una nuova area di lavoro e aggiungere membri](create-workspace.md).

- Un *ambiente* è uno spazio in cui si gestiscono gli spazi di lavoro e le connessioni. Per maggiori informazioni, vedere [Creare un nuovo ambiente](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Gestire uno spazio di lavoro esistente

Puoi gestire più aree di lavoro contemporaneamente in un ambiente. Il tuo [ruolo](user-roles.md) determina come puoi lavorarci. 

 - Per gestire l'area di lavoro, devi essere un amministratore dell'ambiente o un amministratore dell'area di lavoro.
 - In qualità di amministratore dell'area di lavoro, puoi rinominare le aree di lavoro esistenti o eliminarle. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centro di amministrazione dello spazio di lavoro.":::

### <a name="edit-a-workspace-name"></a>Modificare il nome di un'area di lavoro

1. Vai a **Amministratore** > **Area di lavoro** e seleziona **Impostazioni**.

1. Immetti un nuovo nome nella casella **Nome area di lavoro**.

1. Seleziona **Salva** per applicare le modifiche.

### <a name="delete-a-workspace"></a>Eliminare un'area di lavoro

L'eliminazione di un'area di lavoro rimuove in modo definitivo tutto il contenuto, i dati, le impostazioni e le autorizzazioni. Questa operazione non può essere annullata.

1. Vai a **Amministratore** > **Area di lavoro** e seleziona **Impostazioni**.

1. Seleziona **Elimina area di lavoro**. 

1. Nella finestra di dialogo **Elimina spazio di lavoro** , inserisci **CONFERMA ELIMINAZIONE** in tutto maiuscolo. 

1. Seleziona **Elimina** per eliminare in modo definitivo l'area di lavoro.

### <a name="manage-workspace-members"></a>Gestire i membri dell'area di lavoro

1. Vai ad **Amministratore** > **Area di lavoro** e seleziona **Membri**.

1. Seleziona **Aggiungi membri** per consentire l'accesso e [assegnare ruoli](user-roles.md). Attualmente è disponibile solo **Amministratore area di lavoro**.

1. Seleziona **Aggiungi membri** per aggiungerli alla tua area di lavoro.

## <a name="manage-an-existing-environment"></a>Gestire un ambiente esistente

Come amministratore dell'ambiente, puoi accedere a un ambiente dal pannello di navigazione sinistro. Puoi configurare le impostazioni dell'ambiente, altri amministratori dell'ambiente e le aree di lavoro. Seleziona le schede per spostarti tra le diverse aree dell'interfaccia di amministrazione.

:::image type="content" source="media/environment-edit.png" alt-text="Interfaccia di amministrazione ambiente.":::

### <a name="edit-an-environment-name"></a>Modificare un nome di ambiente

1. Vai ad **Amministratore** > **Ambiente** e seleziona **Impostazioni**.

1. Aggiorna il campo **Nome ambiente** e seleziona **Salva** per applicare le modifiche.

### <a name="delete-an-environment"></a>Eliminare un ambiente

Gli amministratori dell'ambiente possono eliminare gli ambienti. Prima di poter eliminare un ambiente, è necessario rimuovere tutte le aree di lavoro in esso.

1. Vai ad **Amministratore** > **Ambiente** e seleziona **Impostazioni**.

1. Seleziona **Elimina ambiente**. 

1. Nella finestra di dialogo **Elimina spazio di lavoro** , inserisci **CONFERMA ELIMINAZIONE** in tutto maiuscolo. 

1. Seleziona **Eimina** per eliminare l'ambiente definitivamente.

### <a name="manage-environment-members"></a>Gestire i membri dell'ambiente

1. Vai ad **Amministratore** > **Ambiente** e seleziona **Membri**.

1. Seleziona **Aggiungi membri** per aggiornare i membri e [assegnare ruoli](user-roles.md). Attualmente è disponibile solo **Amministratore ambiente**.

1. Seleziona **Aggiungi membri** per aggiungerli al tuo ambiente.

## <a name="manage-connections"></a>Gestione connessioni

Stabilire connessioni a Informazioni dettagliate sul gruppo di destinatari ti consente di visualizzare report in informazioni dettagliate sull'interazione basati su profili cliente unificati. 

Per ulteriori informazioni, vedi [Creare un collegamento tra Informazioni dettagliate sul gruppo di destinatari e Informazioni dettagliate sull'interazione](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Gestire i dati personali

Per proteggere i dati personali dei clienti, puoi eliminare o esportare i dati che consentono l'identificazione dell'utente finale.

Per ulteriori informazioni, vedi [Eliminare ed esportare i dati degli eventi contenenti informazioni personali](../dsr-rights-requests.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
