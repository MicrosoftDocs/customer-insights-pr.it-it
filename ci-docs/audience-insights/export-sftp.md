---
title: Esportare dati di Customer Insights in host SFTP
description: Scopri come configurare la connessione a un host SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643508"
---
# <a name="connector-for-sftp-preview"></a>Connettore per SFTP (anteprima)

Utilizza i tuoi dati cliente in applicazioni di terze parti esportandoli in un host SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Prerequisiti

- Disponibilità di un host SFTP e credenziali corrispondenti.

## <a name="connect-to-sftp"></a>Connessione a SFTP

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. In **SFTP**, seleziona **Configura**.

1. Assegna alla tua destinazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Fornisci un **Nome utente**, una **Password** e un **Nome host** per il tuo account SFTP. Esempio: se la cartella radice del server SFTP è /root/folder e desideri che i dati vengano esportati in /root/folder/ci_export_destination_folder, l'host deve essere sftp://<server_address>/ci_export_destination_folder".

1. Seleziona **Verifica** per testare la connessione.

1. Al termine della verifica, scegli se desideri esportare i tuoi dati **compressi** o **decompressi** e seleziona il **delimitatore di campo** per i file esportati.

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Avanti** per iniziare a configurare l'esportazione.

## <a name="configure-the-connection"></a>Configurare la connessione

1. Seleziona gli **attributi del cliente** da esportare. È possibile esportare uno o più attributi.

1. Seleziona **Avanti**.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati via SFTP, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che la destinazione di esportazione rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
