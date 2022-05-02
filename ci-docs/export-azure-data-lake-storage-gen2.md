---
title: Esportare dati di Customer Insights in Azure Data Lake Storage Gen2
description: Scopri come configurare la connessione a Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8b14992f8312d333d8a12501e8a28496c8434779
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646776"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Esportare l'elenco dei segmenti e altri dati in Azure Data Lake Storage Gen2 (anteprima)

Memorizza i tuoi dati di Customer Insights in un account Data Lake Storage Gen2 o usalo per trasferire i tuoi dati ad altre applicazioni.

## <a name="known-limitations"></a>Limitazioni note

1. Per Azure Data Lake Storage Gen2 puoi scegliere tra il [livello di prestazioni Standard e Premium](/azure/storage/blobs/create-data-lake-storage-account) quando crei un account di storage per il tuo data lake. Se scegli il livello di prestazioni Premium, seleziona i blocchi premium come tipo di account. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Impostare la connessione a Azure Data Lake Storage Gen2 


1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Azure Data Lake Gen 2** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti **Nome account**, **Chiave account**, e **Contenitore** per il Azure Data Lake Storage Gen2.
    - Per scoprire come creare un account di archiviazione da usare con Azure Data Lake Storage Gen2, vedi [Creare un account di archiviazione](/azure/storage/blobs/create-data-lake-storage-account). 
    - Per altre informazioni sul nome dell'account di archiviazione di Azure Data Lake Gen2 e sulla chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).

1. Seleziona **Salva** per completare la connessione. 

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione **Azure Data Lake**. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Seleziona la casella accanto a ciascuna delle entità che desideri esportare in questa destinazione.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

I dati esportati vengono archiviati nel contenitore di archiviazione di Azure Data Lake Gen 2 configurato. 

[!INCLUDE [footer-include](includes/footer-banner.md)]
