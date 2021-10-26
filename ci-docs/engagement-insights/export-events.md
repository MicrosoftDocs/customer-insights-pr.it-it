---
title: Esportare eventi affinati
description: Come esportare eventi affinati ed eventi di base.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606227"
---
# <a name="export-events"></a>Esportare eventi

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un evento rappresenta il comportamento dell'utente. Registra quando un utente visualizza una pagina (evento di visualizzazione) o interagisce con il contenuto (evento di azione). Quando puoi decidere quali proprietà dei dati desideri visualizzare in un report, questa visualizzazione virtuale dei dati viene chiamata *evento affinato*. Per maggiori informazioni, vedi [Creare e modificare eventi](refined-events.md).

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

Ci sono due modi per far apparire la finestra di dialogo **Esporta eventi** : 
- Vai a **Dati** > **Esportazioni** e seleziona **Nuova esportazione**.
- Vai a **Dati** > **Eventi**, seleziona **Altre entità [...]** accanto all'evento che vuoi esportare e seleziona **Esporta** dal menu a tendina. 

:::image type="content" source="media/new-export.png" alt-text="Creare una nuova esportazione.":::

Verranno indicati i passaggi per creare un'esportazione:

1. Fornire un **nome di esportazione** e poi selezionare **Avanti**.

1. Nell'elenco a discesa **Selezione eventi** scegli gli eventi di base e gli eventi affinati da includere nell'esportazione. 

1. Nella sezione **Struttura dei file** , seleziona la cadenza (oraria o giornaliera) per creare nuovi file nell'archivio di destinazione e poi seleziona **Avanti**. Gli eventi vengono esportati continuamente man mano che arrivano.

1. Nella finestra di dialogo **Scegli il formato** , seleziona il formato per la tua esportazione. Scegli tra i formati **Modello dati comuni**, **CSV** e **JSON** . Per utilizzare l'esportazione con altre applicazioni Dynamics 365, raccomandiamo il formato **Modello dati comuni** .

1. Nella finestra di dialogo **Scegli destinazione** , specificate la posizione Azure Data Lake Storage Gen 2.
    1. **Nome account ADLS Gen 2** è il nome dell'account di archiviazione in cui desideri salvare l'esportazione. 
    1. **Percorso cartella** definisce la posizione in cui deve essere archiviata l'esportazione nel file system e nella struttura di directory dell'account di archiviazione.
    1. **Chiave condivisa** è disponibile nel portale di Azure per l'account di archiviazione.

1. Rivedi e conferma le tue selezioni per finire.

## <a name="view-and-manage-exports"></a>Visualizzare e gestire esportazioni

Dopo aver configurato un'esportazione, vai a **Dati** > **Esportazioni** per vederla. Seleziona **Altri [...]** per qualsiasi esportazione esistente per modificarla o eliminarla.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
