---
title: Esportare eventi affinati
description: Come esportare eventi affinati ed eventi di base.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032390"
---
# <a name="export-events"></a>Esportare eventi

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un evento rappresenta il comportamento dell'utente. Registra quando un utente visualizza una pagina (evento di visualizzazione) o interagisce con il contenuto (evento di azione). Quando puoi decidere quali proprietà dei dati desideri visualizzare in un report, questa visualizzazione virtuale dei dati viene chiamata *evento affinato*. 

- Puoi esportare eventi ed eventi affinati in una memoria esterna. 
- Le esportazioni sono un flusso di dati di inoltro. Non puoi riempire il flusso. 
- Le esportazioni hanno schemi fissi. Se aggiungi proprietà personalizzate a un evento, non verranno incluse. Dovrai creare una nuova esportazione.

## <a name="prerequisites"></a>Prerequisiti

Prima di configurare un'esportazione, devi disporre dell'accesso e di una sottoscrizione attiva al portale di Azure. Avrai bisogno delle informazioni sull'account di archiviazione durante il processo di esportazione. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Crea un account Azure Data Lake Storage Gen 2

1. Accedi al portale di Azure e [crea un nuovo account di archiviazione](/azure/storage/common/storage-account-create). 

1. Assicurati di abilitare **Spazio dei nomi gerarchico** nella scheda **Avanzata**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Abilitare lo spazio dei nomi gerarchico nella scheda Avanzata.":::

1. Una volta distribuito, vai all'account di archiviazione appena creato. Nel riquadro di spostamento seleziona **Impostazioni** > **Chiavi di accesso**. 

1. Copia **Nome utente** e **Chiave** per usarli durante la creazione di una nuova esportazione.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Chiavi di accesso nell'account di archiviazione.":::

## <a name="export-events"></a>Esporta eventi

Esistono due modi per esportare eventi: 
- Vai a **Dati** > **Esportazioni** e seleziona **Nuova esportazione**.
- Vai a **Dati** > **Eventi**, seleziona **Altre entità [...]** accanto all'evento che vuoi esportare e seleziona **Esporta** dal menu a tendina. 

Verranno indicati i passaggi per creare un'esportazione:

1. Immettere un **nome per l'esportazione**.

1. Nell'elenco a discesa **Selezione eventi** scegli gli eventi di base e gli eventi affinati da includere nell'esportazione. 

1. In **Struttura file**, seleziona la cadenza per creare nuovi file nell'archivio di destinazione. Gli eventi vengono esportati continuamente man mano che arrivano.

1. Seleziona il formato per l'esportazione. Puoi scegliere tra i formati **Common Data Model**, **CSV** e **JSON**. Per utilizzare l'esportazione con altre applicazioni Dynamics 365, consigliamo di utilizzare il formato Common Data Model.

1. Al passaggio **Scegli destinazione** specifica la posizione Azure Data Lake Storage Gen 2.
    1. **Nome account ADLS Gen 2** è il nome dell'account di archiviazione in cui desideri salvare l'esportazione. 
    1. **Percorso cartella** definisce la posizione in cui deve essere archiviata l'esportazione nel file system e nella struttura di directory dell'account di archiviazione.
    1. **Chiave condivisa** è disponibile nel portale di Azure per l'account di archiviazione.

1. Rivedi e conferma le selezioni.

## <a name="view-and-manage-exports"></a>Visualizzare e gestire esportazioni

Dopo aver configurato un'esportazione, vai a **Dati** > **Esportazioni** per vederla. Seleziona **Altri [...]** per qualsiasi esportazione esistente per modificarla o eliminarla.


[!INCLUDE[footer-include](../includes/footer-banner.md)]