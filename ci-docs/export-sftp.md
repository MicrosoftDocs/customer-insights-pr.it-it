---
title: Esportare i dati in host SFTP (anteprima) (video)
description: Scopri come configurare la connessione ed esportare in una posizione SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207234"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Esportare i dati negli host SFTP (anteprima)

Utilizza i dati dei tuoi clienti in applicazioni di terze parti esportandoli in una posizione SFTP (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Prerequisiti

- Disponibilità di un host FTP sicuro e credenziali corrispondenti.

## <a name="known-limitations"></a>Limitazioni note

- Le destinazioni SFTP dietro i firewall non sono attualmente supportate.
- Il tempo di esecuzione di un'esportazione dipende dalle prestazioni del sistema. Consigliamo due core CPU e 1 GB di memoria come configurazione minima del server.
- È possibile esportare fino a 100 milioni di profili cliente e tale operazione può richiedere 90 minuti se si utilizza la configurazione minima consigliata di due core CPU e 1 GB di memoria.
- Se utilizzi una chiave SSH per l'autenticazione, assicurati di [creare la tua chiave privata](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) come formato PEM o SSH.COM. Se usi Putty, converti la tua chiave privata esportandola come Open SSH. Sono supportati i seguenti formati di chiave privata:
  - RSA in formato OpenSSL PEM e ssh.com
  - DSA in formato OpenSSL PEM e ssh.com
  - ECDSA 256/384/521 in formato OpenSSL PEM
  - ED25519 e RSA in formato OpenSSH

## <a name="set-up-connection-to-sftp"></a>Configurare la connessione a SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **SFTP**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Scegli se vuoi eseguire l'autenticazione tramite SSH o nome utente/password per la tua connessione e fornisci i dettagli necessari. Se utilizzi una chiave SSH per l'autenticazione, assicurati di [creare la tua chiave privata](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) come formato PEM o SSH.COM. Se usi Putty, converti la tua chiave privata esportandola come Open SSH. Sono supportati i seguenti formati di chiave privata:
   - RSA in formato OpenSSL PEM e ssh.com
   - DSA in formato OpenSSL PEM e ssh.com
   - ECDSA 256/384/521 in formato OpenSSL PEM
   - ED25519 e RSA in formato OpenSSH

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

> [!TIP]
> L'esportazione di entità che contengono una grande quantità di dati può portare a più file CSV nella stessa cartella per ogni esportazione. La suddivisione delle esportazioni avviene per motivi di prestazioni, al fine di ridurre al minimo il tempo necessario per il completamento di un'esportazione.

[!INCLUDE [footer-include](includes/footer-banner.md)]
