---
title: Esportare i dati in un'archiviazione BLOB di Azure (anteprima)
description: Scopri come configurare la connessione ed esportare nell'archivio BLOB.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195709"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Esportare i dati in un'archiviazione BLOB di Azure (anteprima)

Archivia i dati di Customer Insights in un archivio BLOB o utilizzali per trasferire i dati ad altre applicazioni.

## <a name="prerequisites"></a>Prerequisiti

- Il nome e la chiave di un [account di archiviazione BLOB di Azure](/azure/storage/blobs/create-data-lake-storage-account). Per trovare il nome e la chiave, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).
- Un [contenitore di archiviazione BLOB di Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="known-limitations"></a>Limitazioni note

- Per l'archiviazione BLOB di Azure, scegli tra il [livello di prestazioni Standard e Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se scegli il livello di prestazioni Premium, seleziona i [blocchi premium come tipo di account](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Configurare la connessione all'archiviazione BLOB

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Archiviazione BLOB di Azure**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti il **Nome account**, la **chiave dell'account** e il **Contenitore** per il tuo account di archiviazione BLOB.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Per configurare questa esportazione, devi disporre dell'[autorizzazione](export-destinations.md#set-up-a-new-export) per questo tipo di connessione.

> [!IMPORTANT]
> Se hai attivato l'[impostazione di eliminazione temporanea](/azure/storage/blobs/soft-delete-blob-enable) per l'account di archiviazione BLOB di Azure, le esportazioni non riusciranno. Disattiva l'eliminazione temporanea per esportare i dati in BLOB.

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Archiviazione BLOB di Azure. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Immetti il nome della cartella per l'archiviazione BLOB.

1. Seleziona la casella accanto a ciascuna delle entità che desideri esportare in questa destinazione.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

I dati esportati vengono archiviati nel contenitore di archiviazione BLOB configurato. I seguenti percorsi di cartelle vengono creati automaticamente nel contenitore:

- Per entità di origine ed entità generate dal sistema:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > L'esportazione di entità che contengono una grande quantità di dati può portare a più file CSV nella stessa cartella per ogni esportazione. La suddivisione delle esportazioni avviene per motivi di prestazioni, al fine di ridurre al minimo il tempo necessario per il completamento di un'esportazione.

- Il file model.json per le entità esportate risiede a livello di *%ExportDestinationName%*.  
  
  Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
