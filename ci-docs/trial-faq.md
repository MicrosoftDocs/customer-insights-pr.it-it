---
title: Domande frequenti sulla versione di valutazione di Dynamics 365 Customer Insights
description: Soluzioni alle domande più comuni relative all'impostazione e alla gestione delle prove di Customer Insights. Scopri come risolvere problemi specifici della piattaforma e dell'app.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 41f112466d54c9923d0daf7c55d343f9b5c81d98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051504"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Domande frequenti sulla versione di valutazione di Dynamics 365 Customer Insights

## <a name="sign-up"></a>Iscriversi

### <a name="what-are-the-system-requirements-for-the-trial"></a>Quali sono i requisiti di sistema per la versione di valutazione?

Questa applicazione è un servizio basato su cloud che non richiede un software speciale oltre a un browser web aggiornato, anche se si applicano alcune restrizioni. Per la migliore esperienza di prova, evita di accedere al sito di prova in modalità incognito e scegli la sede di prova più vicina a te. [Per saperne di più sui requisiti delle applicazioni web.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Come posso iscrivermi alla versione di valutazione senza un tenant di Microsoft 365?

Puoi inserire un indirizzo email non lavorativo e creeremo un account e un tenant per te.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Posso iscrivermi a più app Dynamics 365 come Sales, Marketing e Customer Service?

Si, puoi. Per visualizzare tutte le versioni di valutazione disponibili, [visita la pagina dell'hub della versione di valutazione](https://dynamics.microsoft.com/dynamics-365-free-trial). Puoi utilizzare lo stesso account e-mail per iscriverti a versioni di valutazione diverse. Tuttavia, non è possibile avere più app sullo stesso sito di prova. Ogni versione di valutaizone sarà su un'organizzazione e un URL diversi. I dati di prova non verranno condivisi tra le app.

## <a name="trial-app"></a>App di valutazione

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Non ho ricevuto l'e-mail con i dettagli della versione di valutazione dopo la registrazione, cosa devo fare?

Quando ti iscrivi alla versione di valutazione, riceverai un messaggio e-mail con i dettagli della versione di valutazione. Se non vedi il messaggio e-mail nella tua casella di posta, controlla la cartella della posta indesiderata. In alternativa, utilizza i seguenti passaggi per accedere alla tua app:

1. Vai al sito di prova e seleziona **Try for free**.
1. Inserisci l'ID e-mail che hai usato per iscriverti alla prova. Verrai reindirizzato alla tua app di prova.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Come aggiungo altri utenti a una versione di valutazione?

Per aggiungere utenti, vai all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando l'account amministratore di valutazione. Segui le [istruzioni dell'interfaccia di amministrazione](/microsoft-365/admin/add-users/add-users) per aggiungere utenti fino al limite della licenza di valutazione. Se l'utente aggiunto dispone già di un account Microsoft 365, assegnagli un ruolo di sicurezza appropriato nell'organizzazione di valutazione. Per altre informazioni, vedi [Assegnare un ruolo di sicurezza a un utente](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Quanti utenti posso aggiungere al mio ambiente di prova?

Puoi aggiungere un numero illimitato di utenti all'ambiente di valutazione.

### <a name="how-do-i-reset-the-trial-environment"></a>In che modo posso reimpostare l'ambiente di valutazione?

Non puoi reimpostare l'ambiente di valutazione. Tuttavia, puoi attendere la fine del periodo di prova e quindi registrarti nuovamente per una nuova versione di valutazione.

## <a name="trial-expiration-and-extension"></a>Scadenza ed estensione del periodo di valutazione

### <a name="how-do-i-extend-the-trial"></a>In che modo posso estendere la versione di valutazione?

È possibile estendere la prova direttamente nell'app. Puoi estendere la tua versione di valutazione una volta.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Posso convertire la versione di valutazione in una licenza a pagamento?

In genere, ti consigliamo di cominciare con i tuoi dati quando esegui l'aggiornamento alla versione a pagamento di Customer Insights. 

Facoltativamente, se utilizzi solo Customer Insights, puoi copiare i tuoi dati da un ambiente di prova se acquisti Customer Insights. Devi essere l'amministratore della versione di valutazione di Customer Insights e l'amministratore globale del tuo tenant Microsoft 365 o l'amministratore di Dynamics 365 nell'organizzazione per migrare le impostazioni da un ambiente di valutazione a un ambiente a pagamento.

Dopo aver effettuato l'accesso alla tua istanza a pagamento di Customer Insights per la prima volta, ti viene chiesto di creare un nuovo ambiente. In questo processo, puoi scegliere di copiare la configurazione da un ambiente esistente e migrare la maggior parte delle impostazioni. Se disponi delle autorizzazioni sopra menzionate, l'ambiente della versione di valutazione verrà visualizzato in questo elenco. Per ulteriori informazioni, vedi [Copia la configurazione dell'ambiente](create-environment.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Quali sono i limiti e le quote della versione di valutazione?

- Non puoi usare il tuo account Azure Data Lake Storage per archiviare i dati di output in una versione di prova di Customer Insights. Tuttavia, puoi inserire dati da un account di archiviazione di Data Lake Storage.
- È possibile memorizzare fino a 3 GB di dati nell'ambiente Dataverse che viene fornito automaticamente quando si avvia una prova di Customer Insights.

## <a name="customer-insights-specific-questions"></a>Domande specifiche di Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>In che modo posso iniziare a utilizzare la versione di valutazione?

Dopo esserti iscritto alla prova, arriverai alla schermata principale dell'app. La schermata principale fornisce collegamenti a guide e tutorial per l'utente. Per saperne di più, visita i link nella sezione [Risorse aggiuntive](trial-signup.md#additional-resources) nella pagina di iscrizione alla prova.

### <a name="what-features-are-available-in-the-trial"></a>Quali funzionalità sono disponibili nella versione di valutazione?

La maggior parte delle funzionalità di Customer Insights sono disponibili nella prova.

Le funzionalità seguenti **non sono disponibili**:

- Non puoi creare nuovi ambienti che usano il tuo account Azure Data Lake Storage.
- Non puoi eliminare l'ambiente di valutazione.

### <a name="how-long-does-the-trial-last"></a>Quanto dura il processo?

La prova di Customer Insights dura 30 giorni. Puoi estendere la prova una volta dopo 23 giorni quando accedi al tuo ambiente di prova.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Come rimuovo i dati di esempio dalla versione di valutazione?

Non è possibile rimuovere i dati del campione dal processo.
