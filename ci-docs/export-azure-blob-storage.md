---
title: Esportare dati di Customer Insights in un archivio BLOB di Azure
description: Scopri come configurare la connessione ed esportare nell'archivio BLOB.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 42095f369c47553e5ddf5fada54e559202c943a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646956"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Esportare l'elenco dei segmenti e altri dati in Archiviazione BLOB di Azure (anteprima)

Archivia i dati di Customer Insights in un archivio BLOB o utilizzali per trasferire i dati ad altre applicazioni.

## <a name="known-limitations"></a>Limitazioni note

1. Per Azure Blob Storage è possibile scegliere tra il [livello di prestazioni Standard e Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se scegli il livello di prestazioni Premium, seleziona i [blocchi premium come tipo di account](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Configurare la connessione all'archiviazione BLOB

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Archiviazione BLOB di Azure** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti il **Nome account**, la **chiave dell'account** e il **Contenitore** per il tuo account di archiviazione BLOB.
    - Per altre informazioni su come trovare il nome dell'account di archiviazione BLOB e sulla chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).
    - Per informazioni su come creare un contenitore, vedi [Creare un contenitore](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleziona **Salva** per completare la connessione. 

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Se hai attivato l'impostazione di eliminazione temporanea per l'account di archiviazione BLOB di Azure, le esportazioni non riusciranno. Disattiva l'eliminazione temporanea per esportare i dati in BLOB. Per ulteriori informazioni, vedi [Abilita l'eliminazione temporanea dei blob](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Archiviazione BLOB di Azure. Se non vedi questo nome di sezione, non sono disponibili connessioni di questo tipo.

1. Seleziona la casella accanto a ciascuna delle entità che desideri esportare in questa destinazione.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).     

Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

I dati esportati vengono archiviati nel contenitore di archiviazione BLOB configurato. I seguenti percorsi di cartelle vengono creati automaticamente nel contenitore:

- Per entità di origine ed entità generate dal sistema:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Esempio: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Il model.json per le entità esportate sarà a livello di %ExportDestinationName%.  
  - Esempio: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
