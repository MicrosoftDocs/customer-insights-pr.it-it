---
title: Esportazione dei dati di Customer Insights in InMobi
description: Informazioni su come configurare la connessione e l'esportazione in InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195893"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Esportare dati di Customer Insights in InMobi (anteprima)

Esporta elenchi di segmenti o altri dati dalla tua istanza di Customer Insights in [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Prerequisiti

- Un [account InMobi](https://www.inmobi.com/) e le credenziali di amministratore.
- Il nome e la chiave di un [account di archiviazione BLOB di Azure](/azure/storage/blobs/create-data-lake-storage-account). Per trovare il nome e la chiave, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).
- Un [contenitore i archiviazione BLOB di Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) in cui esportare i dati InMobi.
- InMobi creerà una connessione diretta all'archiviazione BLOB e configurerà un'importazione automatica dei tuoi dati in InMobi. Contatta il tuo rappresentante InMobi per avviare il processo.

## <a name="known-limitations"></a>Limitazioni note

- Per l'archiviazione BLOB di Azure, scegli tra il [livello di prestazioni Standard e Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se scegli il livello di prestazioni Premium, seleziona i [blocchi premium come tipo di account](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Configurare la connessione all'archiviazione BLOB di Azure

[Configura una connessione alla tua archiviazione BLOB di Azure](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Configurare un'esportazione

[Configura un'esportazione](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
