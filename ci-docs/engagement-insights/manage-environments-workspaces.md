---
title: Gestire aree di lavoro e ambienti
description: Come creare, rinominare ed eliminare aree di lavoro e ambienti.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034047"
---
# <a name="manage-environments-and-workspaces"></a>Gestire ambienti e aree di lavoro

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Panoramica

Un'area di lavoro è uno spazio in cui archiviare e gestire eventi e report. È qui che puoi visualizzare l'impegno degli utenti in tempo reale. Quando crei un'area di lavoro, selezioni il tipo di dati da inviare all'area di lavoro. Attualmente sono supportati i dati Web e le app mobili.

Un ambiente è uno spazio in cui gestisci le aree di lavoro e le connessioni. Il modo in cui utilizzi gli ambienti dipende dalla tua organizzazione e dal tuo caso d'uso. Ad esempio puoi creare:

-   Un ambiente singolo.
-   Ambienti separati di test e di produzione.
-   Ambienti separati per team o reparti specifici della tua organizzazione che contengono eventi rilevanti per ogni destinatario.
-   Ambienti separati per le diverse filiali globali della società.
-   Connessioni alla funzionalità Informazioni dettagliate sul gruppo di destinatari di Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Scegliere un ambiente e creare un'area di lavoro 

Ogni area di lavoro deve essere in un ambiente. Puoi selezionare un ambiente preesistente o crearne uno nuovo quando crei un'area di lavoro. Quindi puoi scegliere di aggiungere membri dell'area di lavoro e iniziare a raccogliere dati.

**Per creare la tua prima area di lavoro**

1. Nelle informazioni dettagliate sull'interazione seleziona **Nuovo** dalla commutazione dell'area di lavoro. 

   :::image type="content" source="media/New-workspace.png" alt-text="Selettore dell'area di lavoro della pagina Customer Insights.":::

1. Scegli un ambiente dall'elenco o seleziona **Crea nuovo ambiente**.

1. Immetti un nome in **Nome area di lavoro**. 

1. Seleziona il tipo di ambiente che desideri creare, a seconda che tu voglia misurare ciò che accade su un sito Web o in un'app mobile. 

1. Puoi aggiungere membri e assegnare il relativo livello di autorizzazione dall'elenco **Ruolo**. Quindi seleziona **Fine** per creare l'area di lavoro o **Avanti** per installare il codice. 

1. Installa il frammento di codice per iniziare a ricevere dati, quindi seleziona **Fatto**. 

## <a name="manage-a-workspace"></a>Gestire un'area di lavoro

Puoi gestire più aree di lavoro contemporaneamente in un ambiente. Il tuo [ruolo](user-roles.md) determina come puoi lavorarci. 

 - Per gestire l'area di lavoro, devi essere un amministratore dell'ambiente o un amministratore dell'area di lavoro.
 - In qualità di amministratore dell'area di lavoro, puoi rinominare le aree di lavoro esistenti o eliminarle. 

### <a name="edit-a-workspace-name"></a>Modificare il nome di un'area di lavoro

1. Vai a **Amministratore** > **Area di lavoro** e seleziona **Impostazioni**.

1. Immetti un nuovo nome nella casella **Nome area di lavoro**.

1. Seleziona **Salva** per applicare le modifiche.

### <a name="delete-a-workspace"></a>Eliminare un'area di lavoro

L'eliminazione di un'area di lavoro rimuoverà in modo definitivo tutto il contenuto, i dati, le impostazioni e le autorizzazioni. Questa operazione non può essere annullata.

1. Vai a **Amministratore** > **Area di lavoro** e seleziona **Impostazioni**.

1. Seleziona **Elimina area di lavoro**. 

1. Nella finestra di dialogo **Elimina area di lavoro** immetti **CONFERMA ELIMINAZIONE**. 

1. Seleziona **Elimina** per eliminare in modo definitivo l'area di lavoro.

### <a name="manage-workspace-members"></a>Gestire i membri dell'area di lavoro

1. Vai ad **Amministratore** > **Area di lavoro** e seleziona **Membri**.

1. Seleziona **Aggiungi membri** per consentire l'accesso e [assegnare ruoli](user-roles.md). Attualmente è disponibile solo **Amministratore area di lavoro**.

1. Se configuri una [connessione a Informazioni dettagliate sul gruppo di destinatari](configure-connections.md), puoi selezionare **Consenti accesso ai dati del profilo** per consentire al membro di visualizzare i report basati sui [profili utente](profile-reports.md).

1. Seleziona **Aggiungi membri** per aggiungerli alla tua area di lavoro.

## <a name="manage-an-environment"></a>Gestire un ambiente

In qualità di amministratore dell'ambiente, puoi accedere a un ambiente dal riquadro di spostamento a sinistra. Puoi configurare le impostazioni dell'ambiente, altri amministratori dell'ambiente, aree di lavoro e [connessioni a Informazioni dettagliate sul gruppo di destinatari](configure-connections.md). Seleziona le schede per spostarti tra le diverse aree dell'interfaccia di amministrazione.

:::image type="content" source="media/New-environment.png" alt-text="Interfaccia di amministrazione ambiente.":::

### <a name="create-an-environment"></a>Crea un ambiente

1. Nel selettore dell'area di lavoro, seleziona **+Nuovo**.

1. Nell'esperienza guidata, apri il menu a discesca **Ambiente** e seleziona **Crea nuovo ambiente**. 

1. Specifica un **nome per l'ambiente**.

   :::image type="content" source="media/create-environment.png" alt-text="Entra nell'esperienza guidata per specificare i dettagli dell'ambiente.":::

1. Scegli **Regione** e seleziona **Avanti**. 

1. Fornisci un nome per l'area di lavoro e scegli il tipo di area di lavoro che desideri creare. 

1.  Facoltativamente, aggiungi membri e copia il frammento di codice che completa il processo di creazione.

### <a name="rename-an-environment"></a>Rinominare un ambiente

1. Vai ad **Amministratore** > **Ambiente** e seleziona **Impostazioni**.

1. Aggiorna il campo **Nome ambiente** e seleziona **Salva** per applicare le modifiche.

### <a name="manage-environment-members"></a>Gestire i membri dell'ambiente

1. Vai ad **Amministratore** > **Ambiente** e seleziona **Membri**.

1. Seleziona **Aggiungi membri** per aggiornare i membri e [assegnare ruoli](user-roles.md). Attualmente è disponibile solo **Amministratore ambiente**.

1. Se configuri una [connessione a Informazioni dettagliate sul gruppo di destinatari](configure-connections.md), puoi selezionare **Consenti accesso ai dati del profilo** per consentire al membro di visualizzare i report basati sui [profili utente](profile-reports.md).

1. Seleziona **Aggiungi membri** per aggiungerli al tuo ambiente.

### <a name="delete-an-environment"></a>Eliminare un ambiente

Gli amministratori dell'ambiente possono eliminare gli ambienti. Prima di poter eliminare un ambiente, è necessario rimuovere tutte le aree di lavoro in esso.

1. Vai ad **Amministratore** > **Ambiente** e seleziona **Impostazioni**.

1. Seleziona **Elimina ambiente**. 

1. Nella finestra di dialogo **Elimina area di lavoro** immetti **CONFERMA ELIMINAZIONE**. 

1. Seleziona **Eimina** per eliminare l'ambiente definitivamente.

## <a name="manage-connections"></a>Gestione connessioni

Stabilire connessioni a Informazioni dettagliate sul gruppo di destinatari ti consente di visualizzare report in informazioni dettagliate sull'interazione basati su profili cliente unificati. 

Per ulteriori informazioni, vedi [Configurare le connessioni](configure-connections.md).

## <a name="manage-personal-data"></a>Gestire i dati personali

Per proteggere i dati personali dei clienti, puoi eliminare o esportare i dati che consentono l'identificazione dell'utente finale.

Per ulteriori informazioni, vedi [Eliminare ed esportare i dati degli eventi contenenti informazioni personali](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
