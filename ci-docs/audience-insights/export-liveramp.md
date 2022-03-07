---
title: Connettore LiveRamp
description: Scopri come configurare la connessione ed esportare in LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7940db3efacad62ba16099849b3e3ca00d2a5cc1ed31e15a34209c0797e6ae13
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035650"
---
# <a name="export-segments-to-liverampreg-preview"></a>Esportare segmenti in LiveRamp&reg; (anteprima)

Attiva i tuoi dati in LiveRamp per connetterti con oltre 500 piattaforme su digitale, social e TV. Utilizza i tuoi dati in LiveRamp per indirizzare, eliminare e personalizzare le campagne pubblicitarie.

## <a name="prerequisites-for-a-connection"></a>Prerequisiti per una connessione

- È necessario un abbonamento LiveRamp per utilizzare questo connettore.
- Per ottenere un abbonamento, [contatta LiveRamp](https://liveramp.com/contact/) direttamente. [Altre informazioni sull'oboarding di LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Configurare la connessione a LiveRamp

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **LiveRamp** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Specifica un **Nome utente** e una **Password** per l'account LiveRamp Secure FTP (SFTP).
Queste credenziali possono essere diverse dalle credenziali di LiveRamp Onboarding.

1. Seleziona **Verificare** per testare la connessione a LiveRamp.

1. Dopo aver verificato con successo, fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione LiveRamp. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Nel campo **Scegli il tuo identificatore chiave**, seleziona **E-mail**, **Nome e indirizzo** o **Telefono** per inviare a LiveRamp per la risoluzione dell'identità.
   > [!div class="mx-imgBorder"]
   > ![Connettore LiveRamp con mappatura degli attributi.](media/export-liveramp-segments.png "Connettore LiveRamp con mappatura degli attributi")

1. Mappa gli attributi corrispondenti dall'entità cliente unificata per l'identificatore chiave selezionato.

1. Seleziona **Aggiungi attributo** per mappare più attributi da inviare a LiveRamp.

   > [!TIP]
   > L'invio di più attributi dell'identificatore chiave a LiveRamp probabilmente ti farà ottenere un tasso di corrispondenza più elevato.

1. Seleziona i segmenti che desideri esportare in LiveRamp.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Liveramp, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Liveramp rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
