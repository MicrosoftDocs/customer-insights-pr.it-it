---
title: Esportazione dei dati di Customer Insights in Salesforce Marketing Cloud
description: Scopri come configurare la connessione ed esportare in Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: aaf5c2607099bbfccf7ed75330267da8c3c5fe1b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647394"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Esportazione di segmenti e altri dati in Salesforce Marketing Cloud (anteprima)

Utilizza i dati dei tuoi clienti in Salesforce Marketing Cloud esportandoli tramite una posizione con FTP sicuro.

## <a name="prerequisites-for-connection"></a>Prerequisiti per la connessione

- Disponibilità di un host con FTP sicuro e delle corrispondenti credenziali di amministratore. [Come configurare le posizioni con FTP sicuro per Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Configurazione della connessione a Salesforce Marketing Cloud

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Salesforce Marketing Cloud** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fornisci un **Nome utente**, una **Password** e un **Nome host** e una **Cartella di esportazione** per il tuo account FTP sicuro.

1. Seleziona **Verifica** per testare la connessione.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione SFTP. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Scegli se desideri esportare i tuoi dati **Compresso** o **Decompresso** e il **delimitatore di campo** per i file esportati.

1. Seleziona le entità, ad esempio i segmenti, che vuoi esportare.

   > [!NOTE]
   > Ogni entità selezionata verrà suddivisa in un massimo di cinque file di output quando esportata. 

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importazione dei dati di Customer Insights dalla posizione con FTP sicuro in Salesforce Marketing Cloud

1. Crea [estensioni dati in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) per importare il file di dati di Customer Insights dalla posizione con FTP sicuro.

2. [Importa i dati dalla posizione con FTP sicuro](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) nell'estensione dati Salesforce Marketing Cloud. 

3. Imposta l'automazione per importare i dati nelle estensioni dati. Scopri di più riguardo [automazioni di rilascio file e automazioni programmate](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definisci un'[automazione di rilascio file](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) o un'[automazione programmata ](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Ecco un esempio di [un'automazione con FTP sicuro](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati via SFTP, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che la destinazione di esportazione rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

[!INCLUDE [footer-include](includes/footer-banner.md)]
