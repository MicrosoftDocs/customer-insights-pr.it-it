---
title: Utilizzare origini dati per inserire dati
description: Scopri come importare dati da varie origini.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 78379c827e132b3b172aa7381f4c5ef2c70b9771
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977834"
---
# <a name="data-sources-overview"></a>Panoramica delle origini dati

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

La funzionalità Informazioni dettagliate sul gruppo di destinatari in Dynamics 365 Customer Insights si connette ai dati da un ampio insieme di origini. La connessione a un'origine dati viene spesso definita processo di *inserimento dati*. Dopo aver inserito i dati, puoi [unificare](data-unification.md) e agire su di essi.

## <a name="add-a-data-source"></a>Aggiungi un'origine dati

Fare riferimento agli articoli dettagliati su come aggiungere un'origine dati, a seconda dell'opzione scelta.

È possibile aggiungere le seguenti origini dati:

- [Connettori Power Query](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse lake](connect-dataverse-managed-lake.md)

> [!NOTE]
> Se stai utilizzando la versione di prova, la sezione dei metodi di importazione include un'opzione **Raccolta dati di Customer Insights**. Scegli questa opzione per selezionare un campione di set di dati disponibile per vari settori. Per ulteriori informazioni, vedi la [versione di valutazione di Dynamics 365 Customer Insights](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Aggiungere dati dalle origini dati locale

L'inserimento di dati da origini dati locale in informazioni dettagliate gruppo di destinatari è supportata in base ai flussi di dati Microsoft Power Platform. Puoi abilitare i flussi di dati in Customer Insights [fornendo l'URL dell'ambiente Microsoft Dataverse](create-environment.md) quando si allestisce l'ambiente.

Le origini dati che vengono create dopo aver associato un ambiente Dataverse con Customer Insights usano [flussi di dati Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) per impostazione predefinita. I flussi di dati supportano la connettività locale utilizzando il gateway di dati. Puoi rimuovere e ricreare origini dati che esistevano prima dell'associazione dell'ambiente Dataverse [utilizzando i gateway dati locali](/data-integration/gateway/service-gateway-app).

I gateway dati di un ambiente esistente Power BI o Power Apps saranno visibili e potrai riutilizzarli in Customer Insights. La pagina delle origini dati mostra i collegamenti per andare all'ambiente Microsoft Power Platform in cui è possibile visualizzare e configurare i gateway dati locale.

## <a name="review-ingested-data"></a>Esamina i dati inseriti

Vedrai il nome di ciascuna origine dati inserita, il suo stato e l'ultima volta che i dati sono stati aggiornati per quell'origine. Puoi ordinare l'elenco delle origini dati per colonna.

> [!div class="mx-imgBorder"]
> ![Origine dati aggiunta.](media/configure-data-datasource-added.png "Origine dati aggiunta")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Il caricamento dei dati può richiedere tempo. Al termine del completamento dell'aggiornamento, i dati inseriti possono essere rivisti dalla pagina **Entità**. Per ulteriori informazioni, vedi [Entità](entities.md).

## <a name="refresh-a-data-source"></a>Aggiornare un'origine dati

Le origini dati possono essere aggiornate in base a una pianificazione automatica o manualmente su richiesta. 

Vai a **Amministratore** > **Sistema** > [**Pianifica**](system.md#schedule-tab) per configurare gli aggiornamenti pianificati di tutte le origini dati inserite.

Per aggiornare un origine dati su richiesta, segui questi passaggi:

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Dati** > **Origini dati**.

2. Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri aggiornare e seleziona **Aggiorna** dall'elenco a discesa.

3. L'origine dati è ora attivata per un aggiornamento manuale. L'aggiornamento di un'origine dati aggiornerà sia lo schema dell'entità che i dati per tutte le entità specificate nell'origine dati.

4. Seleziona **Arresta aggiornamento** se desideri annullare un aggiornamento esistente e riportare l'origine dati allo stato dell'ultimo aggiornamento.

## <a name="delete-a-data-source"></a>Eliminare un'origine dati

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Dati** > **Origini dati**.

2. Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri rimuovere e seleziona **Elimina** dal menu a tendina.

3. Conferma l'eliminazione.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
