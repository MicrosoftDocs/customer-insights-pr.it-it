---
title: Richieste diritti dell'interessato (DSR) ai sensi del GDPR | Microsoft Docs
description: Rispondere alle richieste diritti dell'interessato per la funzionalità Audience Insights di Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e832fbbdfb59cb06d98715223edca438d2c3a7f2
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554328"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Richieste diritti dell'interessato ai sensi del GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Risposta alle richieste di eliminazione dell'interessato ai sensi del GDPR per la funzionalità Audience Insights di Dynamics 365 Customer Insights

Il "diritto alla cancellazione" mediante rimozione dei dati personali dai dati cliente di un'organizzazione è una protezione chiave del Regolamento generale sulla protezione dei dati (GDPR). La rimozione dei dati personali include la rimozione di tutti i dati personali e di registri generati dal sistema, ad eccezione di informazioni del registro di controllo.

### <a name="manage-data-subject-delete-requests"></a>Gestire le richieste di eliminazione dell'interessato

Audience Insights offre le seguenti esperienze nel prodotto per eliminare i dati personali per un cliente specifico o un utente di Customer Insights:

- **Gestisci le richieste di eliminazione di dati cliente**: i dati cliente in Customer Insights vengono inseriti dalle origini dati originali esterne a Customer Insights. Tutte le richieste di eliminazione ai sensi del GDPR devono essere eseguite nell'origine dati originale.
- **Gestisci le richieste di eliminazione di dati utente per Customer Insights**: i dati per gli utenti vengono creati da Customer Insights. Tutte le richieste di eliminazione ai sensi del GDPR devono essere eseguite in Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Gestire le richieste di eliminazione di dati cliente

Un amministratore di Customer Insights può seguire questi passaggi per rimuovere i dati cliente che sono stati eliminati nell'origine dati:

1. Accedere a Dynamics 365 Customer Insights.
2. In Audience Insights, vai a **Dati** > **Origini dati**
3. Per ogni origine dati nell'elenco che contiene i dati cliente eliminati:
   1. Seleziona (...) e quindi **Aggiorna**.
   2. Controlla lo stato dell'origine dati in **Stato**. Un segno di spunta indica che l'aggiornamento è stato completato. Un triangolo di avviso significa che si è verificato un problema. Se viene visualizzato un triangolo di avviso, contatta D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Gestione delle richieste di eliminazione di dati cliente ai sensi del GDPR.](media/gdpr-data-sources.png "Gestione delle richieste di eliminazione di dati cliente ai sensi del GDPR")

#### <a name="manage-delete-requests-for-user-data"></a>Gestire le richieste di eliminazione di dati utente

Un amministratore di Customer Insights può seguire questi passaggi per eliminare i dati utente di Customer Insights:

1. Accedere a Dynamics 365 Customer Insights.
2. In Audience Insights, vai a **Amministratore** > **Autorizzazioni**.
3. Seleziona la casella di controllo corrispondente all'utente che vuoi eliminare.
4. Selezionare **Rimuovi**.

> [!div class="mx-imgBorder"]
> ![Gestire le richieste di eliminazione di dati utente ai sensi del GPDR.](media/gdpr-permissions.png "Gestire le richieste di eliminazione di dati utente ai sensi del GDPR")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Rispondere alle richieste di esportazione dell'interessato ai sensi del GDPR

Nell'ambito del nostro impegno a collaborare con gli utenti per il loro percorso verso il regolamento generale sulla protezione dei dati (GDPR), abbiamo elaborato la documentazione che ti assiste nella preparazione. Questa documentazione descrive i passaggi che puoi eseguire per supportare la conformità al GDPR quando utilizzi Audience Insights.

### <a name="manage-export-and-view-requests"></a>Gestire le richieste di esportazione e visualizzazione

Il diritto della trasferibilità dei dati consente a un interessato di richiedere una copia dei dati personali in formato elettronico (definito come un "formato interoperativo, leggibile su PC, comunemente utilizzato e strutturato") che possa essere trasmesso a un altro controller di dati.

#### <a name="export-customer-data-tenant-admin"></a>Esportare dati cliente (amministratore del tenant)

L'amministratore di un tenant può seguire questa procedura per esportare i dati:

1. Invia un messaggio e-mail a D365CI@microsoft.com specificando l'indirizzo e-mail del cliente nella richiesta. Il team di Customer Insights invierà un messaggio e-mail all'indirizzo di posta elettronica dell'amministratore del tenant registrato, chiedendo la conferma per esportare i dati.
2. Accetta la conferma di esportazione dei dati per il cliente che ha effettuato la richiesta.
3. Ricevi i dati esportati tramite l'indirizzo e-mail dell'amministratore del tenant.

#### <a name="export-user-data-tenant-admin"></a>Esportare dati utente (amministratore del tenant)

1. Invia un messaggio e-mail a D365CI@microsoft.com specificando l'indirizzo e-mail dell'utente nella richiesta. Il team di Customer Insights invierà un messaggio e-mail all'indirizzo di posta elettronica dell'amministratore del tenant registrato, chiedendo la conferma per esportare i dati.
2. Accetta la conferma di esportazione dei dati per l'utente che ha effettuato la richiesta.
3. Ricevi i dati esportati tramite l'indirizzo e-mail dell'amministratore del tenant.


[!INCLUDE[footer-include](../includes/footer-banner.md)]