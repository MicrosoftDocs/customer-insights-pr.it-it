---
title: Esportare dati in Azure Data Lake Storage Gen2 (anteprima)
description: Scopri come configurare la connessione a Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196445"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Esportare dati in Azure Data Lake Storage Gen2 (anteprima)

Memorizza i tuoi dati di Customer Insights in un account Data Lake Storage Gen2 o usalo per trasferire i tuoi dati ad altre applicazioni.

## <a name="prerequisites"></a>Prerequisiti

- Un [account di archiviazione da utilizzare con Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Per trovare il nome e la chiave dell'account di archiviazione, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).
- Un [contenitore di archiviazione BLOB di Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="known-limitations"></a>Limitazioni note

- Per Azure Data Lake Storage Gen2, puoi scegliere tra il [livello di prestazioni Standard e Premium](/azure/storage/blobs/create-data-lake-storage-account). Se scegli il livello di prestazioni Premium, seleziona i [blocchi premium come tipo di account](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Impostare la connessione a Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Azure Data Lake Gen 2**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti **Nome account**, **Chiave account**, e **Contenitore** per il Azure Data Lake Storage Gen2.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Azure Data Lake. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Immetti il nome della cartella per l'archiviazione Azure Data Lake Storage Gen2.

1. Seleziona la casella accanto a ciascuna delle entità che desideri esportare in questa destinazione.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

I dati esportati vengono archiviati nel contenitore di archiviazione di Azure Data Lake Gen 2 configurato.

> [!TIP]
> L'esportazione di entità che contengono una grande quantità di dati può portare a più file CSV nella stessa cartella per ogni esportazione. La suddivisione delle esportazioni avviene per motivi di prestazioni, al fine di ridurre al minimo il tempo necessario per il completamento di un'esportazione.

[!INCLUDE [footer-include](includes/footer-banner.md)]
