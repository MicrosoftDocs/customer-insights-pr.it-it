---
title: Esportare i dati di Customer Insights in host SFTP (video)
description: Scopri come configurare la connessione ed esportare in una posizione SFTP.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b56d628c8286ba6697cccc9b002f609aa929951b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947189"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Esportare segmenti e altri dati su SFTP (anteprima)

Utilizza i dati dei tuoi clienti in applicazioni di terze parti esportandoli in una posizione SFTP (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Prerequisiti per la connessione

- Disponibilità di un host FTP sicuro e credenziali corrispondenti.

## <a name="known-limitations"></a>Limitazioni note

- Le destinazioni SFTP dietro i firewall non sono attualmente supportate. 
- Il tempo di esecuzione di un'esportazione dipende dalle prestazioni del sistema. Consigliamo due core CPU e 1 GB di memoria come configurazione minima del server.
- L'esportazione di entità con un massimo di 100 milioni di profili cliente può richiedere 90 minuti se si utilizza la configurazione minima consigliata di due core CPU e 1 GB di memoria.

## <a name="set-up-connection-to-sftp"></a>Configurare la connessione a SFTP

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **SFTP** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fornisci un **Nome utente**, una **Password** e un **Nome host** e una **Cartella di esportazione** per il tuo account FTP sicuro.

1. Seleziona **Verifica** per testare la connessione.

1. Scegli se desideri esportare i tuoi dati **Compresso** o **Decompresso** e il **delimitatore di campo** per i file esportati.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione SFTP. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Seleziona le entità, ad esempio i segmenti, che vuoi esportare.

   > [!NOTE]
   > Ogni entità selezionata verrà suddivisa in un massimo di cinque file di output quando esportata.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab).
Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).

> [!TIP]
> L'esportazione di entità che contengono una grande quantità di dati può portare a più file CSV nella stessa cartella per ogni esportazione. La suddivisione delle esportazioni avviene per motivi di prestazioni, al fine di ridurre al minimo il tempo necessario per il completamento di un'esportazione.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati via SFTP, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che la destinazione di esportazione rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

[!INCLUDE [footer-include](includes/footer-banner.md)]
