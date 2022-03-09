---
title: Richieste diritti dell'interessato (DSR) ai sensi del GDPR | Microsoft Docs
description: Rispondere alle richieste diritti dell'interessato per la funzionalità Informazioni dettagliate sul gruppo di destinatari di Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350274"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Richieste diritti dell'interessato ai sensi del GDPR

Il Regolamento generale sulla protezione dei dati (GDPR) dell'Unione europea è in vigore dal 25 maggio 2018. Fornisce diritti significativi alle persone in merito ai loro dati. Il GDPR riguarda la protezione e l'abilitazione dei diritti di privacy degli individui. Puoi trovare ulteriori informazioni sull'impegno di Microsoft per la sicurezza e la conformità nel [Centro protezione Microsoft](https://www.microsoft.com/trust-center).

Microsoft si impegna ad aiutare i clienti a soddisfare i requisiti del GDPR. Include il diritto di eliminare ed esportare dati che comprendono informazioni personali come ID utente, numeri di telefono e indirizzi e-mail. Gli amministratori possono implementare le richieste degli utenti per eliminare o esportare i dati personali.

## <a name="audience-insights"></a>Informazioni dettagliate gruppo di destinatari

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Risposta alle richieste di eliminazione dell'interessato ai sensi del GDPR per la funzionalità Informazioni dettagliate sul gruppo di destinatari di Dynamics 365 Customer Insights

Il "diritto alla cancellazione" mediante rimozione dei dati personali dai dati cliente di un'organizzazione è una protezione chiave del Regolamento generale sulla protezione dei dati (GDPR). La rimozione dei dati personali include la rimozione di tutti i dati personali e di registri generati dal sistema, ad eccezione di informazioni del registro di controllo.

#### <a name="manage-data-subject-delete-requests"></a>Gestire le richieste di eliminazione dell'interessato

Informazioni dettagliate sul gruppo di destinatari offre le seguenti esperienze nel prodotto per eliminare i dati personali per un cliente specifico o un utente di Customer Insights:

- **Gestisci le richieste di eliminazione di dati cliente**: i dati cliente in Customer Insights vengono inseriti dalle origini dati originali esterne a Customer Insights. Tutte le richieste di eliminazione ai sensi del GDPR devono essere eseguite nell'origine dati originale.
- **Gestisci le richieste di eliminazione di dati utente per Customer Insights**: i dati per gli utenti vengono creati da Customer Insights. Tutte le richieste di eliminazione ai sensi del GDPR devono essere eseguite in Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gestire le richieste per eliminare di dati cliente

Un amministratore di Customer Insights può seguire questi passaggi per rimuovere i dati cliente che sono stati eliminati nell'origine dati:

1. Accedere a Dynamics 365 Customer Insights.
2. In Informazioni dettagliate sul gruppo di destinatari, vai a **Dati** > **Origini dati**
3. Per ogni origine dati nell'elenco che contiene i dati cliente eliminati:
   1. Seleziona (...) e quindi **Aggiorna**.
   2. Controlla lo stato dell'origine dati in **Stato**. Un segno di spunta indica che l'aggiornamento è stato completato. Un triangolo di avviso significa che si è verificato un problema. Se viene visualizzato un triangolo di avviso, contatta D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Gestione delle richieste di eliminazione di dati cliente ai sensi del GDPR.](audience-insights/media/gdpr-data-sources.png "Gestione delle richieste di eliminazione di dati cliente ai sensi del GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Gestire le richieste di eliminazione di dati utente

Un amministratore di Customer Insights può seguire questi passaggi per eliminare i dati utente di Customer Insights:

1. Accedere a Dynamics 365 Customer Insights.
2. In Informazioni dettagliate sul gruppo di destinatari, vai a **Amministratore** > **Autorizzazioni**.
3. Seleziona la casella di controllo corrispondente all'utente che vuoi eliminare.
4. Selezionare **Rimuovi**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Rispondere alle richieste di esportazione dell'interessato ai sensi del GDPR

Nell'ambito del nostro impegno a collaborare con gli utenti per il loro percorso verso il regolamento generale sulla protezione dei dati (GDPR), abbiamo elaborato la documentazione che ti assiste nella preparazione. Questa documentazione descrive i passaggi che puoi eseguire per supportare la conformità al GDPR quando utilizzi Informazioni dettagliate sul gruppo di destinatari.

#### <a name="manage-export-and-view-requests"></a>Gestire le richieste di esportazione e visualizzazione

Il diritto della trasferibilità dei dati consente a un interessato di richiedere una copia dei dati personali in formato elettronico (definito come un "formato interoperativo, leggibile su PC, comunemente utilizzato e strutturato") che possa essere trasmesso a un altro controller di dati.

##### <a name="export-customer-data-tenant-admin"></a>Esportare dati cliente (amministratore del tenant)

L'amministratore di un tenant può seguire questa procedura per esportare i dati:

1. Invia un messaggio e-mail a D365CI@microsoft.com specificando l'indirizzo e-mail del cliente nella richiesta. Il team di Customer Insights invierà un messaggio e-mail all'indirizzo di posta elettronica dell'amministratore del tenant registrato, chiedendo la conferma per esportare i dati.
2. Accetta la conferma di esportazione dei dati per il cliente che ha effettuato la richiesta.
3. Ricevi i dati esportati tramite l'indirizzo e-mail dell'amministratore del tenant.

##### <a name="export-user-data-tenant-admin"></a>Esportare dati utente (amministratore del tenant)

1. Invia un messaggio e-mail a D365CI@microsoft.com specificando l'indirizzo e-mail dell'utente nella richiesta. Il team di Customer Insights invierà un messaggio e-mail all'indirizzo di posta elettronica dell'amministratore del tenant registrato, chiedendo la conferma per esportare i dati.
2. Accetta la conferma di esportazione dei dati per l'utente che ha effettuato la richiesta.
3. Ricevi i dati esportati tramite l'indirizzo e-mail dell'amministratore del tenant.

## <a name="consent-management-preview"></a>Gestione del consenso (anteprima)

La funzionalità di gestione del consenso non raccoglie direttamente i dati dell'utente. Importa ed elabora solo i dati del consenso forniti dagli utenti in altre applicazioni.

Per rimuovere i dati del consenso su utenti specifici, rimuovili nelle origini dati inserite nella funzionalità di gestione del consenso. Dopo aver aggiornato l'origine dati, i dati rimossi verranno eliminati anche nel Centro consenso. Le applicazioni che usano l'entità consenso elimineranno anche i dati che sono stati rimossi dall'origine dopo un [aggiornamento](audience-insights/system.md#refresh-processes). Ti consigliamo di aggiornare rapidamente le origini dati dopo aver risposto a una richiesta dell'interessato per la rimozione dei dati dell'utente da tutti gli altri processi e le altre applicazioni.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]