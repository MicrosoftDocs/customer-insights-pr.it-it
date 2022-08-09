---
title: Richieste diritti dell'interessato (DSR) ai sensi del GDPR | Microsoft Docs
description: Rispondere alle richieste diritti dell'interessato per Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146700"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Richieste diritti dell'interessato ai sensi del GDPR

Il Regolamento generale sulla protezione dei dati (GDPR) dell'Unione europea è in vigore dal 25 maggio 2018. Fornisce diritti significativi alle persone in merito ai loro dati. Il GDPR riguarda la protezione e l'abilitazione dei diritti di privacy degli individui. Puoi trovare ulteriori informazioni sull'impegno di Microsoft per la sicurezza e la conformità nel [Centro protezione Microsoft](https://www.microsoft.com/trust-center).

Microsoft si impegna ad aiutare i clienti a soddisfare i requisiti del GDPR. Include il diritto di eliminare ed esportare dati che comprendono informazioni personali come ID utente, numeri di telefono e indirizzi e-mail. Gli amministratori possono implementare le richieste degli utenti per eliminare o esportare i dati personali.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Risposta alle richieste di eliminazione dell'interessato ai sensi del GDPR per Dynamics 365 Customer Insights

Il "diritto alla cancellazione" mediante rimozione dei dati personali dai dati cliente di un'organizzazione è una protezione chiave del Regolamento generale sulla protezione dei dati (GDPR). La rimozione dei dati personali include la rimozione di tutti i dati personali e di registri generati dal sistema, ad eccezione di informazioni del registro di controllo.

#### <a name="manage-data-subject-delete-requests"></a>Gestire le richieste di eliminazione dell'interessato

Customer Insights offre le seguenti esperienze nel prodotto per eliminare i dati personali per un cliente specifico o un utente:

- **Gestisci le richieste di eliminazione di dati cliente**: i dati cliente in Customer Insights vengono inseriti dalle origini dati originali esterne a Customer Insights. Esegui dapprima le richieste di eliminazione ai sensi del GDPR nell'origine dati originale.
- **Gestisci le richieste di eliminazione di dati utente per Customer Insights**: i dati per gli utenti vengono creati da Customer Insights. Tutte le richieste di eliminazione ai sensi del GDPR devono essere eseguite in Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gestire le richieste per eliminare di dati cliente

Un amministratore di Customer Insights può seguire questi passaggi per rimuovere i dati cliente che sono stati eliminati nell'origine dati. Assicurati che la richiesta di eliminazione sia stata eseguita nella tua origine dati prima di procedere con i passaggi elencati di seguito. 

1. Accedere a Dynamics 365 Customer Insights.
1. Vai a **Dati** > **Origini dati**
1. Per ogni origine dati nell'elenco che contiene i dati cliente eliminati:
   1. Seleziona i puntini di sospensione verticali (&vellip;), quindi scegli **Aggiorna**.
   1. Controlla lo stato dell'origine dati in **Stato**. Un segno di spunta indica che l'aggiornamento è stato completato. Un triangolo di avviso significa che si è verificato un problema. Se viene visualizzato un triangolo di avviso, contatta D365CI@microsoft.com.
1. Dopo il corretto aggiornamento delle origini dati, esegui anche gli aggiornamenti downstream, soprattutto se non hai pianificato un aggiornamento completo ricorrente di Customer Insights. 

> [!IMPORTANT]
> I segmenti statici non sono inclusi in un aggiornamento completo o negli aggiornamenti downstream in esecuzione dopo una richiesta di eliminazione. Per garantire che i dati dei clienti vengano rimossi anche dai segmenti statici, ricrea i segmenti statici con i dati di origine aggiornati.

> [!div class="mx-imgBorder"]
> ![Gestione delle richieste di eliminazione di dati cliente ai sensi del GDPR.](media/gdpr-data-sources.png "Gestione delle richieste di eliminazione di dati cliente ai sensi del GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Gestire le richieste di eliminazione di dati utente

Un amministratore di Customer Insights può seguire questi passaggi per eliminare i dati utente di Customer Insights:

1. Accedere a Dynamics 365 Customer Insights.
2. Vai ad **Amministratore** > **Sicurezza** > **Autorizzazioni**.
3. Seleziona la casella di controllo corrispondente all'utente che vuoi eliminare.
4. Selezionare **Rimuovi**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Rispondere alle richieste di esportazione dell'interessato ai sensi del GDPR

Nell'ambito del nostro impegno a collaborare con gli utenti per il loro percorso verso il regolamento generale sulla protezione dei dati (GDPR), abbiamo elaborato la documentazione che ti assiste nella risposta alle richieste degli interessati.

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

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Gestione della cancellazione dei dati in Dynamics 365 Customer Insights

1. I dati verranno eliminati (partizioni di dati e snapshot di dati) se le partizioni di dati e gli snapshot di dati sono inattivi per più di 30 giorni, nel senso che sono stati sostituiti da una nuova partizione di dati e un nuovo snapshot tramite un aggiornamento delle origini dati.
2. Non tutti i dati e gli snapshot vengono eliminati. La partizione dati e lo snapshot dati più recenti sono per definizione attivi in quanto sono utilizzati in Customer Insights. Per i dati più recenti, non importa se le origini dati non sono state aggiornate negli ultimi 30 giorni.

[!INCLUDE [footer-include](includes/footer-banner.md)]
