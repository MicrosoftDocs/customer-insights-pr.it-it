---
title: Esportare i dati di Customer Insights in Adobe Campaign Standard
description: Scopri come utilizzare i segmenti di Customer Insights in Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646974"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Utilizzare i segmenti di Customer Insights in Adobe Campaign Standard (anteprima)

Come utente Dynamics 365 Customer Insights, potresti aver creato segmenti per rendere più efficienti le tue campagne di marketing rivolgendoti a un pubblico pertinente. Per utilizzare un segmento da Customer Insights in Adobe Experience Platform e applicazioni come Adobe Campaign Standard, devi seguire alcuni passaggi descritti in questo articolo.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagramma di processo dei passaggi descritti in questo articolo.":::

## <a name="prerequisites"></a>Prerequisiti

-   Licenza Dynamics 365 Customer Insights
-   Licenza di Adobe Campaign Standard
-   Account di archiviazione BLOB di Azure

## <a name="campaign-overview"></a>Informazioni generali campagna

Per comprendere meglio come utilizzare i segmenti di Customer Insights in Adobe Experience Platform, diamo un'occhiata a una campagna di esempio fittizia.

Supponiamo che la tua azienda offra un servizio mensile su abbonamento ai tuoi clienti negli Stati Uniti. Desideri identificare i clienti i cui abbonamenti devono essere rinnovati nei prossimi otto giorni e che non hanno ancora rinnovato l'abbonamento. Per mantenere questi clienti, intendi inviare loro un'offerta promozionale via e-mail, utilizzando Adobe Campaign Standard.

In questo esempio, vogliamo eseguire la campagna e-mail promozionale una volta. Questo articolo non copre il caso d'uso di eseguire la campagna più di una volta. Tuttavia, Customer Insights e Adobe Campaign Standard possono essere configurati per funzionare anche per uno scenario di campagna ricorrente.

## <a name="identify-your-target-audience"></a>Identificare il gruppo di destinatari di destinazione

Nel nostro scenario, assumiamo che gli indirizzi e-mail dei clienti siano disponibili e le loro preferenze promozionali siano state analizzate per identificare i membri del segmento.

Il [segmento che hai definito in Customer Insights](segments.md) è chiamato **ChurnProneCustomers** e prevedi di inviare a questi clienti la promozione via e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot della pagina dei segmenti con il segmento ChurnProneCustomers creato.":::

L'e-mail di offerta che desideri inviare conterrà nome, cognome e la data di fine dell'abbonamento del cliente. Informa i clienti dello sconto che riceveranno se rinnovano l'abbonamento prima che termini.

## <a name="export-your-target-audience"></a>Esportare il gruppo di destinatari di destinazione

### <a name="configure-a-connection"></a>Configurare una connessione

Con il nostro gruppo di destinatari identificato, possiamo configurare l'esportazione in un account di archiviazione BLOB di Azure.

1. In Customer Insights, vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Adobe Campaign** per configurare la connessione o seleziona **Imposta** nel riquadro **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Riquadro di configurazione per Adobe Campaign Standard.":::

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Immetti **Nome utente**, **Chiave account**, e **Contenitore** dell'account di archiviazione BLOB di Azure in cui vuoi esportare il segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot della configurazione dell'account di archiviazione. "::: 

   - Per altre informazioni su come trovare il nome dell'account dell'archivio BLOB di Azure e la chiave dell'account, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).

   - Per informazioni su come creare un contenitore, vedi [Creare un contenitore](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleziona **Salva** per completare la connessione.

### <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per l'esportazione** scegli una connessione nella sezione Adobe Campaign. Se non vedi questo nome di sezione, non sono disponibili connessioni di questo tipo.

1. Scegli il segmento che vuoi esportare. In questo esempio, è **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot dell'interfaccia utente per la selezione del segmento con il segmento ChurnProneCustomers selezionato.":::

1. Selezionare **Avanti**.

1. Ora mappiamo i campi di **origine** dal segmento Customer Insights ai nomi dei campi di **destinazione** nello schema del profilo Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mappatura dei campi per il connettore Adobe Campaign Standard.":::

   Se desideri aggiungere più attributi, seleziona **Aggiungi attributo**. Il nome di destinazione può essere diverso dal nome del campo di origine in modo da poter ancora mappare l'output del segmento da Customer Insights ad Adobe Campaign Standard se i campi non hanno lo stesso nome nei due sistemi.

   > [!NOTE]
   > L'indirizzo e-mail viene utilizzato come campo di identità, ma puoi utilizzare qualsiasi altro identificatore dal profilo del cliente per mappare i dati Adobe Campaign Standard.

1. Seleziona **Salva**.

Dopo aver salvato la destinazione di esportazione, la trovi in **Dati** > **Esportazioni**.

Ora puoi [esportare il segmento su richiesta](export-destinations.md#run-exports-on-demand). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md).

> [!NOTE]
> Assicurati che il numero di record nel segmento esportato rientri nel limite consentito della tua licenza Adobe Campaign Standard.

I dati esportati vengono archiviati nel contenitore dell'archiviazione BLOB di Azure configurato in precedenza. Il seguente percorso della cartella viene creato automaticamente nel tuo contenitore:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurare Adobe Campaign Standard

I segmenti esportati contengono le colonne selezionate durante la definizione della destinazione di esportazione nel passaggio precedente. Questi dati possono essere utilizzati per [creare profili in Adobe Campaign Standard ](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Per utilizzare il segmento in Adobe Campaign Standard, dobbiamo estendere lo schema di profili in Adobe Campaign Standard per includere due campi aggiuntivi. Scopri come [estendere la risorsa del profilo](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) con nuovi campi in Adobe Campaign Standard.

Nel nostro esempio questi campi sono *Nome segmento e Data segmento (facoltativi)*.

Useremo questi campi per identificare i profili destinatari in Adobe Campaign Standard per questa campagna.

Se non ci sono altri record in Adobe Campaign Standard oltre a quelli che stai per importare, puoi saltare questo passaggio.

## <a name="import-data-into-adobe-campaign-standard"></a>Importare dati in Adobe Campaign Standard

Ora che tutto è a posto, dobbiamo importare i dati preparati destinatari da Customer Insights in Adobe Campaign Standard per creare i profili. Scopri [come importare i profili in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) utilizzando un flusso di lavoro.

Il flusso di lavoro di importazione nell'immagine seguente è stato configurato per essere eseguito ogni otto ore e cercare i segmenti Customer Insights esportati (file con estensione csv in Archiviazione BLOB di Azure). Il flusso di lavoro estrae il contenuto del file .csv in un ordine di colonna specificato. Questo flusso di lavoro è stato creato per eseguire la gestione degli errori di base e garantire che ogni record abbia un indirizzo e-mail prima di attivare i dati in Adobe Campaign Standard. Il flusso di lavoro estrae anche il nome del segmento dal nome di file prima di inserirlo nei dati del profilo di Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Screenshot di un flusso di lavoro di importazione nell'interfaccia utente di Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperare il gruppo di destinatari in Adobe Campaign Standard

Una volta importati i dati in Adobe Campaign Standard, [puoi creare un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ed [eseguire query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) sui clienti in base al *Nome segmento* e alla *Data segmento* per selezionare i profili identificati per la nostra campagna di esempio.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Creare e inviare l'e-mail utilizzando Adobe Campaign Standard

Crea il contenuto dell'e-mail e poi [esegui il test e invia](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) la tua e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail di esempio con offerta di rinnovo da Adobe Campaign Standard.":::
