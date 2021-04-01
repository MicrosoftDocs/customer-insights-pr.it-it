---
title: Connettore LiveRamp
description: Scopri come esportare dati in LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597562"
---
# <a name="liverampreg-connector-preview"></a>Connettore LiveRamp&reg; (anteprima)

Attiva i tuoi dati in LiveRamp per connetterti con oltre 500 piattaforme su ecosistemi digitali, social e TV. Utilizza i tuoi dati in LiveRamp per indirizzare, eliminare e personalizzare le campagne pubblicitarie.

## <a name="prerequisites"></a>Prerequisiti

- È necessario un abbonamento LiveRamp per utilizzare questo connettore.
- Per ottenere un abbonamento, [contatta LiveRamp](https://liveramp.com/contact/) direttamente. [Altre informazioni sull'oboarding di LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Connettersi a LiveRamp

1. In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.

1. Nel riquadro **LiveRamp**, seleziona **Configura**.

1. Assegna alla tua destinazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Specifica un **Nome utente** e una **Password** per l'account LiveRamp Secure FTP (SFTP).
Queste credenziali possono essere diverse dalle credenziali di LiveRamp Onboarding.

1. Seleziona **Verificare** per testare la connessione a LiveRamp.

1. Dopo aver verificato con successo, fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**.

1. Seleziona **Avanti** per configurare il connettore LiveRamp.

## <a name="configure-the-connector"></a>Configurare il connettore

1. Nel campo **Scegli il tuo identificatore chiave**, seleziona **E-mail**, **Nome e indirizzo** o **Telefono** per inviare a LiveRamp per la risoluzione dell'identità.

1. Mappa gli attributi corrispondenti dall'entità cliente unificata per l'identificatore chiave selezionato.

1. Seleziona **Aggiungi attributo** per mappare altri attributi da inviare a LiveRamp.

   > [!TIP]
   > L'invio di più attributi dell'identificatore chiave a LiveRamp probabilmente ti farà ottenere un tasso di corrispondenza più elevato.

1. Seleziona i segmenti che desideri esportare in LiveRamp.

1. Seleziona **Salva**.

> [!div class="mx-imgBorder"]
> ![Connettore LiveRamp con mappatura degli attributi](media/export-liveramp-segments.png "Connettore LiveRamp con mappatura degli attributi")

## <a name="export-the-data"></a>Esportare i dati

L'esportazione inizierà a breve se tutti i prerequisiti per l'esportazione sono stati completati. L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).
Una volta completata correttamente l'esportazione, puoi accedere a LiveRamp Onboarding per attivare e distribuire i dati.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Liveramp, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Liveramp rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

[!INCLUDE[footer-include](../includes/footer-banner.md)]