---
title: Utilizzare origini dati per inserire dati
description: Scopri come importare dati da varie origini.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304701"
---
# <a name="data-sources-overview"></a>Panoramica delle origini dati

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

La funzionalità Audience Insights in Dynamics 365 Customer Insights si connette ai dati da un ampio insieme di origini. La connessione a un'origine dati viene spesso definita processo di *inserimento dati*. Dopo aver inserito i dati, puoi [unificare](data-unification.md) e agire su di essi.

## <a name="add-a-data-source"></a>Aggiungi un'origine dati

Fai riferimento agli articoli dettagliati su come aggiungere un'origine dati, a seconda dell'opzione scelta.

Puoi aggiungere un'origine dati in tre modi principali:

- [Attraverso dozzine di connettori Power Query](connect-power-query.md)
- [Da una cartella di Common Data Model](connect-common-data-model.md)
- [Dal tuo lake Microsoft Dataverse](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Aggiungere dati dalle origini dati locale

L'inserimento di dati da origini dati locale in informazioni dettagliate gruppo di destinatari è supportata in base ai flussi di dati Microsoft Power Platform. I flussi di dati possono essere abilitati in Customer Insights [fornendo l'URL dell'ambiente Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) quando si imposta l'ambiente.

Le origini dati create dopo l'associazione di un ambiente Dataverse con Customer Insights utilizzeranno i [flussi di dati Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) per impostazione predefinita. I flussi di dati supportano la connettività locale utilizzando il gateway di dati. Rimuovi e ricrea le origini dati che esistevano prima che un ambiente Dataverse fosse associato per [utilizzare i gateway di dati locale](/data-integration/gateway/service-gateway-app.md).

I gateway dati di un ambiente esistente Power BI o Power Apps saranno visibili e potrai riutilizzarli in Customer Insights. La pagina delle origini dati mostra i collegamenti per andare all'ambiente Microsoft Power Platform in cui è possibile visualizzare e configurare i gateway dati locale.

## <a name="review-ingested-data"></a>Esamina i dati inseriti

Vedrai il nome di ciascuna origine dati inserita, il suo stato e l'ultima volta che i dati sono stati aggiornati per quell'origine. Puoi ordinare l'elenco delle origini dati per colonna.

> [!div class="mx-imgBorder"]
> ![Origine dati aggiunta](media/configure-data-datasource-added.png "Origine dati aggiunta")

|Stato  |Descrizione  |
|---------|---------|
|Operazione riuscita   |L'inserimento dell'origine dati è riuscito se un'ora è menzionata nella colonna **Aggiornato**.
|Non avviato   |L'origine dati non è ancora stata inserita o è ancora in modalità bozza.         |
|Aggiornamento in corso    |L'inserimento dati è in corso. Puoi annullare questa operazione selezionando **Arresta aggiornamento** nella colonna **Azioni**. L'interruzione dell'aggiornamento di un'origine dati la riporterà al suo ultimo stato di aggiornamento.       |
|Non inviato     |Si sono verificati errori durante l'inserimento dati.         |

Seleziona il valore nella colonna **Stato** di qualsiasi origine dati per esaminare maggiori dettagli. Nel riquadro **Dettagli stato** espandi **Origini dati**. Seleziona **Vedi dettagli** per altre informazioni sullo stato di aggiornamento, inclusi i dettagli di errore e gli aggiornamenti del processo downstream.

Il caricamento dei dati può richiedere tempo. Al termine del completamento dell'aggiornamento, i dati inseriti possono essere rivisti dalla pagina **Entità**. Per ulteriori informazioni, vedi [Entità](entities.md).

## <a name="refresh-a-data-source"></a>Aggiornare un'origine dati

Le origini dati possono essere aggiornate in base a una pianificazione automatica o manualmente su richiesta. 

Vai a **Amministratore** > **Sistema** > [**Pianifica**](system.md#schedule-tab) per configurare gli aggiornamenti pianificati di tutte le origini dati inserite.

Per aggiornare un origine dati su richiesta, segui questi passaggi:

1. In Audience Insights, vai a **Dati** > **Origini dati**.

2. Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri aggiornare e seleziona **Aggiorna** dall'elenco a discesa.

3. L'origine dati è ora attivata per un aggiornamento manuale. L'aggiornamento di un'origine dati aggiornerà sia lo schema dell'entità che i dati per tutte le entità specificate nell'origine dati.

4. Seleziona **Arresta aggiornamento** se desideri annullare un aggiornamento esistente e riportare l'origine dati allo stato dell'ultimo aggiornamento.

## <a name="delete-a-data-source"></a>Eliminare un'origine dati

1. In Audience Insights, vai a **Dati** > **Origini dati**.

2. Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri rimuovere e seleziona **Elimina** dal menu a tendina.

3. Conferma l'eliminazione.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
