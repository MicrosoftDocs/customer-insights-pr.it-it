---
title: Esportare dati di Customer Insights in Azure Data Lake Storage Gen2
description: Scopri come configurare la connessione a Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477184"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Connettore per Azure Data Lake Storage Gen2 (anteprima)

Archivia i dati di Customer Insights in Azure Data Lake Storage Gen2 o utilizzali per trasferire i dati ad altre applicazioni.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Configurare il connettore per Azure Data Lake Storage Gen2

1. In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.

1. In **Azure Data Lake Storage Gen2**, seleziona **Configura**.

1. Assegna alla tua destinazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Immetti **Nome account**, **Chiave account**, e **Contenitore** per il Azure Data Lake Storage Gen2.
    - Per scoprire come creare un account di archiviazione da usare con Azure Data Lake Storage Gen2, vedi [Creare un account di archiviazione](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Per altre informazioni su come trovare il nome dell'account Azure Data Lake Gen2 e la chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Seleziona **Avanti**.

1. Seleziona la casella accanto a ciascuna delle entità che desideri esportare in questa destinazione.

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md#export-data-on-demand). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).
