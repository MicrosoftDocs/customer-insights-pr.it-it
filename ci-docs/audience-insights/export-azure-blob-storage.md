---
title: Esportare dati di Customer Insights in un archivio BLOB di Azure
description: Istruzioni su come configurare la connessione all'archivio BLOB di Azure.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596182"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Connettore per l'archivio BLOB di Azure (anteprima)

Archivia dati di Customer Insights in un archivio BLOB di Azure o utilizzali per trasferire i tuoi dati in altre applicazioni.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Configurare il connettore per l'archivio BLOB di Azure

1. In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.

1. In **Archivio BLOB di Azure**, seleziona **Configura**.

1. Immetti un valore per **Nome utente**, **Chiave account** e **Contenitore** per l'account dell'archivio BLOB di Azure.
    - Per altre informazioni su come trovare il nome dell'account dell'archivio BLOB di Azure e la chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).
    - Per informazioni su come creare un contenitore, vedi [Creare un contenitore](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Assegna alla tua destinazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Seleziona **Avanti**.

1. Seleziona la casella accanto a ciascuna delle entità che desideri esportare in questa destinazione.

1. Seleziona **Salva**.

I dati esportati vengono archiviati nel contenitore dell'archivio BLOB di Azure configurato. I seguenti percorsi di cartelle vengono creati automaticamente nel contenitore:

- Per entità di origine ed entità generate dal sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Esempio: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Il model.json per le entità esportate risiederà a livello di %ExportDestinationName%
  - Esempio: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md#export-data-on-demand). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]