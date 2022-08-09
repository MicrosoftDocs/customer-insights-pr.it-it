---
title: Esportare segmenti in LiveRamp (anteprima)
description: Scopri come configurare la connessione ed esportare in LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196721"
---
# <a name="export-segments-to-liverampreg-preview"></a>Esportare segmenti in LiveRamp&reg; (anteprima)

Attiva i tuoi dati in LiveRamp per connetterti con oltre 500 piattaforme su digitale, social e TV. Utilizza i tuoi dati in LiveRamp per indirizzare, eliminare e personalizzare le campagne pubblicitarie.

## <a name="prerequisites"></a>Prerequisiti

- Un abbonamento LiveRamp per utilizzare questo connettore. Per ottenere un abbonamento, [contatta LiveRamp](https://liveramp.com/contact/) direttamente. [Altre informazioni sull'oboarding di LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Limitazioni note

- L'esportazione LiveRamp utilizza un'esportazione SFTP. Le destinazioni SFTP dietro i firewall non sono attualmente supportate.
- Se utilizzi una chiave SSH per l'autenticazione, assicurati di [creare la tua chiave privata](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) come formato PEM o SSH.COM. Se usi Putty, converti la tua chiave privata esportandola come Open SSH. Sono supportati i seguenti formati di chiave privata:
  - RSA in formato OpenSSL PEM e ssh.com
  - DSA in formato OpenSSL PEM e ssh.com
  - ECDSA 256/384/521 in formato OpenSSL PEM
  - ED25519 e RSA in formato OpenSSH
- Il tempo di esecuzione di un'esportazione dipende dalle prestazioni del sistema. Consigliamo due core CPU e 1 GB di memoria come configurazione minima del server.
- L'esportazione di entità con un massimo di 100 milioni di profili cliente può richiedere 90 minuti se si utilizza la configurazione minima consigliata di due core CPU e 1 GB di memoria.
- Il numero effettivo di profili (o dati) che puoi esportare in LiveRamp dipende dal tuo abbonamento con LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Configurare la connessione a LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **LiveRamp**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Scegli se vuoi eseguire l'autenticazione tramite SSH o nome utente/password per la tua connessione e fornisci i dettagli necessari.

1. Seleziona **Verificare** per testare la connessione a LiveRamp.

1. Dopo la verifica, leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione LiveRamp. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Nel campo **Connetti i dati**, seleziona **E-mail**, **Nome e indirizzo** o **Telefono** per eseguire l'invio a LiveRamp per la risoluzione dell'identità.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Connettore LiveRamp con mapping degli attributi.":::

1. Mappate gli attributi corrispondenti della vostra entità *Cliente* per l'identificatore di chiave selezionato.

1. Seleziona **Aggiungi attributo** per mappare più attributi da inviare a LiveRamp.

   > [!TIP]
   > L'invio di più attributi dell'identificatore chiave a LiveRamp probabilmente ti farà ottenere un tasso di corrispondenza più elevato.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
