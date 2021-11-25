---
title: Richieste diritti dell'interessato (DSR) ai sensi del GDPR | Microsoft Docs
description: Rispondere alle richieste diritti dell'interessato per la funzionalità Informazioni dettagliate sul gruppo di destinatari di Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732685"
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


## <a name="engagement-insights-preview"></a>Informazioni dettagliate sull'interazione (anteprima)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Eliminazione ed esportazione dei dati degli eventi contenenti informazioni identificabili dell'utente finale

Le sezioni seguenti descrivono come eliminare ed esportare i dati degli eventi che potrebbero contenere dati personali.

Per eliminare o esportare dati:

1. Contrassegna le proprietà degli eventi che contengono dati con informazioni personali.
2. Elimina o esporta i dati associati a valori specifici (ad esempio: un ID utente specificato).

#### <a name="tag-and-update-event-properties"></a>Contrassegnare e aggiornare le proprietà degli eventi

I dati personali sono contrassegnati a livello di proprietà dell'evento. Innanzitutto, contrassegna le proprietà prese in considerazione per l'eliminazione o l'esportazione.

Per contrassegnare una proprietà dell'evento come contenente informazioni personali, procedi nel seguente modo:

1. Apri l'area di lavoro contenente l'evento.

1. Vai a **Dati** > **Eventi** per visualizzare l'elenco degli eventi nell'area di lavoro selezionata.
  
1. Seleziona l'evento che desideri contrassegnare.

1. Seleziona **Modifica proprietà** per aprire il pannello che elenca tutte le proprietà dell'evento selezionato.
     
1. Seleziona **...** e scegli **Modifica** per raggiungere la finestra di dialogo **Aggiorna proprietà**.

   ![Modifica evento.](engagement-insights/media/edit-event.png "Modifica evento")

1. Nella finestra **Aggiorna proprietà** scegli **...** nell'angolo in alto a destra, quindi scegli la casella **Contiene EUII**. Scegli **Aggiorna** per salvare le modifiche.

   ![Salva le modifiche.](engagement-insights/media/update-property.png "Salva le modifiche")

   > [!NOTE]
   > Ogni volta che lo schema dell'evento cambia o che crei un nuovo evento, è consigliabile valutare le proprietà dell'evento associate e contrassegnarle o deselezionarle come contenenti dati personali, se necessario.

#### <a name="delete-or-export-tagged-event-data"></a>Eliminare o esportare i dati degli eventi con tag

Se tutte le proprietà dell'evento sono state contrassegnate in modo appropriato come descritto nel passaggio precedente, un amministratore dell'ambiente può inviare una richiesta di eliminazione in merito ai dati dell'evento contrassegnati.

Per gestire le richieste di eliminazione o esportazione di EUII

1. Vai ad **Amministratore** > **Ambiente** > **Impostazioni**.

1. Nella sezione **Gestire le informazioni identificabili dell'utente finale (EUII)** seleziona **Gestisci EUII**.

##### <a name="deletion"></a>Eliminazione

Per l'eliminazione, puoi inserire un elenco di ID utente separati da virgole nella sezione **Elimina le informazioni identificabili dell'utente finale (EUII)**. Questi ID verranno quindi confrontati con tutte le proprietà degli eventi con tag di tutti i progetti nell'ambiente corrente tramite la corrispondenza esatta delle stringhe. 

Se il valore di una proprietà corrisponde a uno degli ID forniti, l'evento associato verrà eliminato definitivamente. A causa dell'irreversibilità di questa azione, devi confermare l'eliminazione dopo aver selezionato **Elimina**.

##### <a name="export"></a>Export

Il processo di esportazione è identico al processo di eliminazione quando si tratta di definire i valori delle proprietà dell'evento nella sezione **Esportare le informazioni identificabili dell'utente finale (EUII)**. Inoltre, dovrai fornire un **URL di Archiviazione BLOB di Azure** per specificare la destinazione dell'esportazione. L'URL del BLOB di Azure deve includere una [firma di accesso condiviso](/azure/storage/common/storage-sas-overview).

Dopo aver selezionato **Esporta**, tutti gli eventi del team corrente che contengono proprietà con tag corrispondenti verranno esportati in formato CSV nella destinazione di esportazione.

### <a name="good-practices"></a>Procedure consigliate

* Cerca di evitare di inviare eventi che contengono dati personali.
* Se devi inviare eventi contenenti dati EUII, limita il numero di eventi e proprietà dell'evento che contengono dati EUII. Possibilmente, limitati a uno di questi eventi.
* Assicurati che il minor numero di persone possibile abbia accesso ai dati personali inviati.
* Per gli eventi contenenti dati personali, assicurati di impostare una proprietà per emettere un identificatore univoco che può essere facilmente collegato a un utente specifico (ad esempio, un ID utente). Ciò semplifica la separazione dei dati e l'esportazione o l'eliminazione dei dati corretti.
* Contrassegna solo una proprietà per evento come contenente dati personali. Idealmente una che contiene solo un identificatore univoco.
* Non contrassegnare proprietà contenenti valori dettagliati (ad esempio, un intero corpo della richiesta). La funzionalità relativa alle informazioni dettagliate sull'interazione utilizza la corrispondenza di stringa esatta quando si decide quali eventi eliminare o esportare.

[!INCLUDE[footer-include](includes/footer-banner.md)]