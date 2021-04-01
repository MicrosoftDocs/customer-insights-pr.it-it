---
title: Esportare dati di Customer Insights in host SFTP
description: Scopri come configurare la connessione a un host SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598390"
---
# <a name="connector-for-sftp-preview"></a>Connettore per SFTP (anteprima)

Utilizza i tuoi dati cliente in applicazioni di terze parti esportandoli in un host SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Prerequisiti

- Disponibilità di un host FTP sicuro e credenziali corrispondenti.

## <a name="connect-to-sftp"></a>Connetti a SFTP

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. In **SFTP**, seleziona **Configura**.

1. Assegna alla tua destinazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Fornisci un **Nome utente**, una **Password** e un **Nome host** e una **Cartella di esportazione** per il tuo account FTP sicuro.

1. Seleziona **Verifica** per testare la connessione.

1. Dopo aver verificato con successo, scegli se desideri esportare i tuoi dati in formato **Compresso** o **Decompresso** e seleziona il **delimitatore di campo** per i file esportati.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Avanti** per iniziare a configurare l'esportazione.

## <a name="configure-the-export"></a>Configurare l'esportazione

1. Seleziona le entità, ad esempio i segmenti, che vuoi esportare.

   > [!NOTE]
   > Ogni entità selezionata sarà fino a cinque file di output quando esportata. 

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitazioni note

- Il tempo di esecuzione di un'esportazione dipende dalle prestazioni del sistema. Consigliamo due core CPU e 1 GB di memoria come configurazione minima del server. 
- L'esportazione di entità con un massimo di 100 milioni di profili cliente può richiedere 90 minuti se si utilizza la configurazione minima consigliata di due core CPU e 1 GB di memoria. 

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati via SFTP, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che la destinazione di esportazione rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]