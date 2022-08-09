---
title: Esporta i segmenti di Customer Insights in Adobe Campaign Standard (anteprima)
description: Scopri come utilizzare i segmenti di Customer Insights in Adobe Campaign Standard.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195525"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Esporta i segmenti di Customer Insights in Adobe Campaign Standard (anteprima)

Esporta segmenti destinati a gruppi di destinatari pertinenti in Adobe Campaign Standard.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagramma di processo dei passaggi descritti in questo articolo.":::

## <a name="prerequisites"></a>Prerequisiti

- Una licenza Adobe Campaign Standard.
- Il nome e la chiave di un [account di archiviazione BLOB di Azure](/azure/storage/blobs/create-data-lake-storage-account). Per trovare il nome e la chiave, vedi [Gestire le impostazioni dell'account di archiviazione nel portale di Azure](/azure/storage/common/storage-account-manage).
- Un [contenitore di archiviazione BLOB di Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="campaign-overview"></a>Informazioni generali campagna

Per comprendere meglio come utilizzare i segmenti di Customer Insights in Adobe Experience Platform, diamo un'occhiata a una campagna di esempio fittizia.

Supponiamo che la tua azienda offra un servizio mensile su abbonamento ai tuoi clienti negli Stati Uniti. Desideri identificare i clienti i cui abbonamenti devono essere rinnovati nei prossimi otto giorni e che non hanno ancora rinnovato l'abbonamento. Per mantenere questi clienti, intendi inviare loro un'offerta promozionale via e-mail, utilizzando Adobe Campaign Standard.

In questo esempio, vogliamo eseguire la campagna e-mail promozionale una volta. Questo articolo non copre il caso d'uso di eseguire la campagna più di una volta. Tuttavia, Customer Insights e Adobe Campaign Standard possono essere configurati per funzionare anche per uno scenario di campagna ricorrente.

## <a name="identify-your-target-audience"></a>Identificare il gruppo di destinatari di destinazione

Nel nostro scenario, assumiamo che gli indirizzi e-mail dei clienti siano disponibili in Customer Insights e le loro preferenze promozionali siano state analizzate per identificare i membri del segmento.

Il [segmento che hai definito in Customer Insights](segments.md) è chiamato **ChurnProneCustomers** e prevedi di inviare a questi clienti la promozione via e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot della pagina dei segmenti con il segmento ChurnProneCustomers creato.":::

L'e-mail di offerta che desideri inviare conterrà nome, cognome e la data di fine dell'abbonamento del cliente. Informa i clienti dello sconto che riceveranno se rinnovano l'abbonamento prima che termini.

## <a name="export-your-target-audience"></a>Esportare il gruppo di destinatari di destinazione

### <a name="set-up-connection-to-adobe-campaign"></a>Impostare la connessione a Adobe Campaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Adobe Campaign**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti il **Nome account**, la **Chiave dell'account** e il **Contenitore** per il tuo account di archiviazione BLOB.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot della configurazione dell'account di archiviazione. ":::

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Salva** per completare la connessione.

### <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per l'esportazione** scegli una connessione nella sezione Adobe Campaign. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Scegli il segmento che vuoi esportare. In questo esempio, è **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot dell'interfaccia utente per la selezione del segmento con il segmento ChurnProneCustomers selezionato.":::

1. Selezionare **Avanti**.

1. Mappa i campi di **origine** dal segmento Customer Insights ai nomi dei campi di **destinazione** nello schema del profilo Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapping dei campi per il connettore Adobe Campaign Standard.":::

   Se desideri aggiungere più attributi, seleziona **Aggiungi attributo**. Il nome di destinazione può essere diverso dal nome del campo di origine in modo da poter ancora mappare l'output del segmento da Customer Insights ad Adobe Campaign Standard se i campi non hanno lo stesso nome nei due sistemi.

   > [!NOTE]
   > L'indirizzo e-mail viene utilizzato come campo di identità, ma puoi utilizzare qualsiasi altro identificatore dal profilo del cliente per mappare i dati Adobe Campaign Standard.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Assicurati che il numero di record nel segmento esportato rientri nel limite consentito della tua licenza Adobe Campaign Standard.

I dati esportati vengono archiviati nel contenitore dell'archiviazione BLOB di Azure configurato in precedenza. Il seguente percorso viene creato automaticamente nel tuo contenitore: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Esempio: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurare Adobe Campaign Standard

I segmenti esportati contengono le colonne selezionate durante la configurazione dell'esportazione. Questi dati possono essere utilizzati per [creare profili in Adobe Campaign Standard ](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Per utilizzare il segmento in Adobe Campaign Standard, [estendi lo schema di profili](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) in Adobe Campaign Standard per includere due campi aggiuntivi.

Nel nostro esempio, questi campi sono Nome segmento e Data segmento. Useremo questi campi per identificare i profili destinatari in Adobe Campaign Standard per questa campagna.

Se non ci sono altri record in Adobe Campaign Standard oltre a quelli che stai per importare, salta questo passaggio.

## <a name="import-data-into-adobe-campaign-standard"></a>Importare dati in Adobe Campaign Standard

Importa i dati preparati relativi al gruppo di destinatari da Customer Insights in Adobe Campaign Standard per [creare i profili usando un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Il flusso di lavoro di importazione nell'immagine seguente è stato configurato per essere eseguito ogni otto ore e cercare i segmenti Customer Insights esportati (file con estensione csv in Archiviazione BLOB di Azure). Il flusso di lavoro estrae il contenuto del file .csv in un ordine di colonna specificato. Questo flusso di lavoro è stato creato per eseguire la gestione degli errori di base e garantire che ogni record abbia un indirizzo e-mail prima di attivare i dati in Adobe Campaign Standard. Il flusso di lavoro estrae anche il nome del segmento dal nome di file prima di inserirlo nei dati del profilo di Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Screenshot di un flusso di lavoro di importazione nell'interfaccia utente di Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperare il gruppo di destinatari in Adobe Campaign Standard

Una volta importati i dati in Adobe Campaign Standard, [crea un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ed [esegui query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) sui clienti in base al Nome segmento e alla Data segmento per selezionare i profili identificati per la nostra campagna di esempio.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Creare e inviare l'e-mail utilizzando Adobe Campaign Standard

Crea il contenuto dell'e-mail e poi [esegui il test e invia](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) la tua e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail di esempio con offerta di rinnovo da Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
