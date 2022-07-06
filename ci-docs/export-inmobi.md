---
title: Esportazione dei dati di Customer Insights in InMobi
description: Informazioni su come configurare la connessione e l'esportazione in InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056544"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Esportare un elenco di segmenti e altri dati in InMobi (anteprima)

Esporta elenchi di segmenti o altri dati dalla tua istanza di Customer Insights in [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Prerequisiti

1. Hai un [account InMobi](https://www.inmobi.com/) e le credenziali di amministratore.
1. Hai il nome dell'account di archiviazione BLOB di Azure e la chiave dell'account corrispondente. Per ulteriori informazioni, vedi [Gestire le impostazioni di un account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage). Nell'account di archiviazione è presente un contenitore in cui esportare i dati inMobi. Per ulteriori informazioni, vedi [Creare un contenitore](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi creerà una connessione diretta all'archiviazione BLOB e configurerà un'importazione automatica dei tuoi dati in InMobi. Contatta il tuo rappresentante InMobi per avviare il processo.

## <a name="known-limitations"></a>Limitazioni note

1. Per Azure Blob Storage è possibile scegliere tra il [livello di prestazioni Standard e Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se scegli il livello di prestazioni Premium, seleziona i [blocchi premium come tipo di account](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Impostare la connessione ad Archiviazione BLOB di Azure e configurare un'esportazione

1. Segui le istruzioni per [impostare una connessione all'archiviazione BLOB di Azure](export-azure-blob-storage.md).
2. Segui le istruzioni per [configurare un'esportazione](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
