---
title: Esportare segmenti in Adobe Experience Platform (anteprima)
description: Informazioni su come usare i segmenti Customer Insights in Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195295"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Esportare segmenti in Adobe Experience Platform (anteprima)

Esporta segmenti destinati a gruppi di destinatari pertinenti in Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagramma di processo dei passaggi descritti in questo articolo.":::

## <a name="prerequisites"></a>Prerequisiti

- Una licenza Adobe Experience Platform.
- Una licenza Adobe Campaign Standard.
- Il nome e la chiave di un [account di archiviazione BLOB di Azure](/azure/storage/blobs/create-data-lake-storage-account). Per trovare il nome e la chiave, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).
- Un [contenitore di archiviazione BLOB di Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="campaign-overview"></a>Informazioni generali campagna

Per comprendere meglio come utilizzare i segmenti di Customer Insights in Adobe Experience Platform, diamo un'occhiata a una campagna di esempio fittizia.

Supponiamo che la tua azienda offra un servizio mensile su abbonamento ai tuoi clienti negli Stati Uniti. Desideri identificare i clienti i cui abbonamenti devono essere rinnovati nei prossimi otto giorni e che non hanno ancora rinnovato l'abbonamento. Per mantenere questi clienti, vuoi inviare loro un'offerta promozionale via e-mail, utilizzando Adobe Experience Platform.

In questo esempio, vogliamo eseguire la campagna e-mail promozionale una volta. Questo articolo non copre il caso d'uso di eseguire la campagna più di una volta.

## <a name="identify-your-target-audience"></a>Identificare il gruppo di destinatari di destinazione

Nel nostro scenario, assumiamo che gli indirizzi e-mail dei clienti siano disponibili in Customer Insights e le loro preferenze promozionali siano state analizzate per identificare i membri del segmento.

Il [segmento che hai definito in Customer Insights](segments.md) è chiamato **ChurnProneCustomers** e prevedi di inviare a questi clienti la promozione via e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot della pagina dei segmenti con il segmento ChurnProneCustomers creato.":::

L'e-mail di offerta che desideri inviare conterrà nome, cognome e la data di fine dell'abbonamento del cliente. Informa i clienti dello sconto che riceveranno se rinnovano l'abbonamento prima che termini.

## <a name="export-your-target-audience"></a>Esportare il gruppo di destinatari di destinazione

Configureremo l'esportazione da Customer Insights a un account di archiviazione BLOB di Azure.

### <a name="set-up-connection-to-azure-blob-storage"></a>Configurare la connessione all'archiviazione BLOB di Azure

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Archiviazione BLOB di Azure**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti **Nome utente**, **Chiave account** e **Contenitore** per l'account di archiviazione BLOB in cui vuoi esportare il segmento.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot della configurazione dell'account di archiviazione. ":::

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Salva** per completare la connessione.

### <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Archiviazione BLOB di Azure. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Scegli il segmento che vuoi esportare. In questo esempio, è **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot dell'interfaccia utente per la selezione del segmento con il segmento ChurnProneCustomers selezionato.":::

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Assicurati che il numero di record nel segmento esportato rientri nel limite consentito della tua licenza Adobe Campaign Standard.

I dati esportati vengono archiviati nel contenitore di archiviazione BLOB di Azure configurato. I seguenti percorsi di cartelle vengono creati automaticamente nel contenitore:

- Per entità di origine ed entità generate dal sistema:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Il *model.json* per le entità esportate risiederà a livello di *%ExportDestinationName%*.

  Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definire Experience Data Model (XDM) in Adobe Experience Platform

Prima che i dati esportati da Customer Insights possano essere utilizzati in Adobe Experience Platform, definisci lo schema del modello di dati dell'esperienza e [configura i dati per il profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Scopri [cos'è XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e apprendi le [basi della composizione dello schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importa dati in Adobe Experience Platform

Importa i dati preparati relativi al gruppo di destinatari da Customer Insights in Adobe Experience Platform.

1. [Crea una connessione di origine di archiviazione BLOB di Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Configura un flusso di dati](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) per una connessione batch di archiviazione cloud in cui importare l'output del segmento da Customer Insights in Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Creare un gruppo di destinatari in Adobe Campaign Standard

Per inviare l'e-mail per questa campagna, utilizzeremo Adobe Campaign Standard.

1. [Crea un gruppo di destinatari](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard utilizzando i dati in Adobe Experience Platform.

1. [Usa il generatore di segmenti](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard per definire un gruppo di destinatari in base ai dati in Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Creare e inviare l'e-mail utilizzando Adobe Campaign Standard

Crea il contenuto dell'e-mail e poi [esegui il test e invia](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) la tua e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail di esempio con offerta di rinnovo da Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]