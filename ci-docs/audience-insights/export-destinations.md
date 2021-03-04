---
title: Destinazioni di esportazione
description: Esporta i dati e gestisci le destinazioni di esportazione.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477138"
---
# <a name="export-destinations-preview-overview"></a>Panoramica delle destinazioni di esportazione (anteprima)

La pagina **Destinazioni di esportazione** mostra tutte le posizioni in cui hai impostato l'esportazione dei dati. Puoi anche aggiungere nuove destinazioni per l'esportazione. Mostra anche le opzioni di esportazione attualmente disponibili. Ottieni una rapida panoramica e una descrizione e scopri cosa puoi fare con ogni opzione di estendibilità. Esporta profili, misure e segmenti unificati in app supportate pertinenti per la tua azienda.

Vai a **Amministratore** > **Destinazioni di esportazione** per trovare le seguenti opzioni di estendibilità:

- [Componente aggiuntivo Scheda cliente Dynamics 365](customer-card-add-in.md)
- [Connettore per Gestione inserzioni di Facebook](export-facebook.md)
- [Power Automateconnettore](export-power-automate.md)
- [Power Appsconnettore](export-power-apps.md)
- [Power BIconnettore](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Archiviazione BLOB di Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [Connettore LiveRamp&reg;](export-liveramp.md)
- [Bot per Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API di Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Aggiungere una nuova destinazione di esportazione

Per aggiungere destinazioni di esportazione, disponi delle [autorizzazioni di amministratore](permissions.md). Se esporti su servizi Microsoft, si presuppone che entrambi i servizi siano nella stessa organizzazione.

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. Passa alla scheda **Destinazioni di esportazione personali**.

1. Seleziona **Aggiungi destinazione** per creare una nuova destinazione di esportazione.

1. Nel riquadro **Aggiungi destinazione**, seleziona il **Tipo** di destinazione di esportazione nel menu a discesa.

1. Specifica i dettagli obbligatori e seleziona **Avanti** per creare la destinazione di esportazione.

Puoi anche selezionare **Configura** su un riquadro della scheda **Scopri**.

## <a name="view-export-destinations"></a>Visualizzare le destinazioni di esportazione

Dopo aver creato le destinazioni di esportazione, le troverai in una tabella nella scheda **Destinazioni di esportazione personali**. Questa tabella include tre colonne:

- **Nome visualizzato**: il nome inserito durante la creazione della destinazione.
- **Tipo**: il tipo di destinazione di esportazione impostato durante la creazione della destinazione.
- **Data di creazione**: la data in cui è stata creata la destinazione.

## <a name="edit-an-export-destination"></a>Modificare una destinazione di esportazione

1. Seleziona i puntini di sospensione verticali per la destinazione di esportazione che vuoi modificare.

   > [!div class="mx-imgBorder"]
   > ![Puntini di sospensione verticali](media/export-destinations-page-ellipsis.png "Puntini di sospensione verticali")

1. Seleziona **Modifica** dal menu a discesa.

1. Modifica i valori che richiedono l'aggiornamento e seleziona **Salva**.

## <a name="export-data-on-demand"></a>Esportare dati su richiesta

Dopo aver configurato un connettore per una destinazione di esportazione, le esportazioni verranno eseguite con ogni [aggiornamento pianificato](system.md#schedule-tab).

Per esportare i dati senza attendere un aggiornamento pianificato, vai alla scheda **Destinazioni di esportazione personali** in **Amministratore** > **Destinazioni di esportazione**.

> [!div class="mx-imgBorder"]
> ![Puntini di sospensione verticali](media/export-destinations-page-ellipsis.png "Puntini di sospensione verticali")

- Seleziona **Esporta** sopra l'elenco per eseguire contemporaneamente l'esportazione verso tutte le destinazioni di esportazione.
- Seleziona i puntini di sospensione (...) dopo una voce dell'elenco e quindi sceglie l'opzione **Esporta** per eseguire l'esportazione per una singola destinazione di esportazione.

## <a name="remove-an-export-destination"></a>Rimuovere una destinazione di esportazione

Per rimuovere una destinazione di esportazione, inizia dalla pagina **Destinazioni di esportazione** principale.

1. Seleziona i puntini di sospensione verticali per la destinazione di esportazione che vuoi rimuovere.

   > [!div class="mx-imgBorder"]
   > ![Puntini di sospensione verticali](media/export-destinations-page-ellipsis.png "Puntini di sospensione verticali")

2. Seleziona **Rimuovi** dal menu a discesa.

3. Conferma la rimozione selezionando **Rimuovi** nella schermata di conferma.


[!INCLUDE[footer-include](../includes/footer-banner.md)]