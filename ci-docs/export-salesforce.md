---
title: Esportare i dati in Salesforce Marketing Cloud (anteprima)
description: Scopri come configurare la connessione ed esportare in Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197043"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Esportare i dati in Salesforce Marketing Cloud (anteprima)

Utilizza i dati dei tuoi clienti in Salesforce Marketing Cloud esportandoli tramite una posizione con FTP sicuro.

## <a name="prerequisites"></a>Prerequisiti

- un [host SFTP per Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) e le credenziali di amministratore corrispondenti.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Configurazione della connessione a Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Salesforce Marketing Cloud**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fornisci un **Nome utente**, una **Password** e un **Nome host** e una **Cartella di esportazione** per il tuo account FTP sicuro.

1. Seleziona **Verifica** per testare la connessione.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione SFTP. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Scegli se desideri esportare i tuoi dati **Compresso** o **Decompresso** e il **delimitatore di campo** per i file esportati.

1. Seleziona le entità, ad esempio i segmenti, che vuoi esportare.

   > [!NOTE]
   > Ogni entità selezionata verrà suddivisa in un massimo di cinque file di output quando esportata.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importazione dei dati di Customer Insights dalla posizione con FTP sicuro in Salesforce Marketing Cloud

1. Crea [estensioni dati in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) per importare il file di dati di Customer Insights dalla posizione con FTP sicuro.

2. [Importa i dati dalla posizione con FTP sicuro](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) nell'estensione dati Salesforce Marketing Cloud.

3. Imposta l'automazione per importare i dati nelle estensioni dati. Scopri di più riguardo [automazioni di rilascio file e automazioni programmate](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definisci un'[automazione di rilascio file](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) o un'[automazione programmata ](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Ecco un esempio di [un'automazione con FTP sicuro](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
