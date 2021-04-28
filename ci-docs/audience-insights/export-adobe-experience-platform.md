---
title: Esportare i dati di Customer Insights in Adobe Experience Platform
description: Scopri come utilizzare i segmenti di informazioni dettagliate gruppo di destinatari in Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760106"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Utilizzare i segmenti di Customer Insights in Adobe Experience Platform (anteprima)

Come utente di informazioni dettagliate gruppo di destinatari per Dynamics 365 Customer Insights, potresti aver creato segmenti per rendere più efficienti le tue campagne di marketing rivolgendoti a un gruppo di destinatari pertinente. Per utilizzare un segmento dalle informazioni dettagliate gruppo di destinatari in Adobe Experience Platform e nelle applicazioni come Adobe Campaign Standard, devi seguire alcuni passaggi descritti in questo articolo.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagramma di processo dei passaggi descritti in questo articolo.":::

## <a name="prerequisites"></a>Prerequisiti

-   Licenza Dynamics 365 Customer Insights
-   Licenza di Adobe Experience Platform
-   Licenza Adobe Campaign Standard
-   Account di archiviazione BLOB di Azure

## <a name="campaign-overview"></a>Informazioni generali campagna

Per comprendere meglio come utilizzare i segmenti delle informazioni dettagliate gruppo di destinatari in Adobe Experience Platform, diamo un'occhiata a una campagna di esempio fittizia.

Supponiamo che la tua azienda offra un servizio mensile su abbonamento ai tuoi clienti negli Stati Uniti. Desideri identificare i clienti i cui abbonamenti devono essere rinnovati nei prossimi otto giorni e che non hanno ancora rinnovato l'abbonamento. Per mantenere questi clienti, desideri inviare loro un'offerta promozionale tramite e-mail, utilizzando Adobe Experience Platform.

In questo esempio, vogliamo eseguire la campagna e-mail promozionale una volta. Questo articolo non copre il caso d'uso di eseguire la campagna più di una volta.

## <a name="identify-your-target-audience"></a>Identificare il gruppo di destinatari di destinazione

Nel nostro scenario, supponiamo che gli indirizzi e-mail dei clienti siano disponibili nelle informazioni dettagliate gruppo di destinatari e che le loro preferenze promozionali siano state analizzate per identificare i membri del segmento.

Il [segmento che hai definito nelle informazioni dettagliate gruppo di destinatari](segments.md) è chiamato **ChurnProneCustomers** e prevedi di inviare a questi clienti la promozione tramite posta elettronica.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot della pagina dei segmenti con il segmento ChurnProneCustomers creato.":::

L'e-mail di offerta che desideri inviare conterrà nome, cognome e la data di fine dell'abbonamento del cliente. Informa i clienti dello sconto che riceveranno se rinnovano l'abbonamento prima che termini.

## <a name="export-your-target-audience"></a>Esportare il gruppo di destinatari di destinazione

Una volta identificato il nostro gruppo di destinatari di destinazione, possiamo configurare l'esportazione dalle informazioni dettagliate gruppo di destinatari a un account di archiviazione BLOB di Azure.

### <a name="configure-a-connection"></a>Configurare una connessione

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Archiviazione BLOB di Azure** oppure seleziona **Imposta** nel riquadro **Archiviazione BLOB di Azure**:

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Riquadro di configurazione per Archiviazione BLOB di Azure."::: per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti **Nome utente**, **Chiave account**, e **Contenitore** per l'account di archiviazione BLOB in cui vuoi esportare il segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot della configurazione dell'account di archiviazione. "::: 
   
    - Per altre informazioni su come trovare il nome dell'account di archiviazione BLOB e sulla chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).
    - Per informazioni su come creare un contenitore, vedi [Creare un contenitore](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleziona **Salva** per completare la connessione. 

### <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Archiviazione BLOB di Azure. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Scegli il segmento che vuoi esportare. In questo esempio, è **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot dell'interfaccia utente per la selezione del segmento con il segmento ChurnProneCustomers selezionato.":::

1. Seleziona **Salva**.

Dopo aver salvato la destinazione di esportazione, la trovi in **Dati** > **Esportazioni**.

Ora puoi [esportare il segmento su richiesta](export-destinations.md#run-exports-on-demand). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md).

> [!NOTE]
> Assicurati che il numero di record nel segmento esportato rientri nel limite consentito dalla licenza di Adobe Campaign Standard.

I dati esportati vengono archiviati nel contenitore dell'archivio BLOB di Azure configurato in precedenza. Il seguente percorso della cartella viene creato automaticamente nel tuo contenitore:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Il *model.json* per le entità esportate risiederà a livello di *%ExportDestinationName%*.

Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definire Experience Data Model (XDM) in Adobe Experience Platform

Prima che i dati esportati dalle informazioni dettagliate gruppo di destinatari possano essere utilizzati all'interno di Adobe Experience Platform, dobbiamo definire lo schema Experience Data Model e [configurare i dati per il profilo del cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Scopri [cos'è XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e apprendi le [basi della composizione dello schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importare i dati in Adobe Experience Platform

Ora che tutto è a posto, dobbiamo importare i dati destinatari preparati dalle informazioni dettagliate gruppo di destinatari in Adobe Experience Platform.

Primo, [crea una connessione di origine dell'archiviazione BLOB di Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Dopo aver definito la connessione di origine, [configura un flusso di dati](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) per una connessione batch di archiviazione cloud per importare l'output del segmento dalle informazioni dettagliate gruppo di destinatari in Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Crea un gruppo di destinatari in Adobe Campaign Standard

Per inviare il messaggio e-mail per questa campagna, utilizzeremo Adobe Campaign Standard. Dopo aver importato i dati in Adobe Experience Platform, è necessario [creare un gruppo di destinatari](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard utilizzando i dati di Adobe Experience Platform.

Scopri come [utilizzare il generatore di segmenti](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard per definire un gruppo di destinatari basato sui dati di Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Creare e inviare l'e-mail utilizzando Adobe Campaign Standard

Crea il contenuto dell'e-mail e poi [esegui il test e invia](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) la tua e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail di esempio con offerta di rinnovo di Adobe Campaign Standard.":::
