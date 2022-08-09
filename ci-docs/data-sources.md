---
title: Panoramica delle origini dati
description: Scopri come importare o inserire i dati da varie origini.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6ab97c535454e84c1bb18aca00bca2568eb65a2a
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207096"
---
# <a name="data-sources-overview"></a>Panoramica delle origini dati

Dynamics 365 Customer Insights fornisce connessioni per portare dati da un'ampia serie di origini. La connessione a un'origine dati viene spesso definita processo di *inserimento dati*. Dopo aver inserito i dati, puoi [unificare](data-unification.md), generare informazioni dettagliate e attivare i dati per la creazione di esperienze personalizzate.

## <a name="add-or-edit-data-sources"></a>Aggiungere o modificare origini dati

Puoi collegare o importare origini dati in Customer Insights. I collegamenti seguenti forniscono istruzioni sull'aggiunta e sulla modifica di origini dati.

**Collega un'origine dati**

Se disponi di dati preparati in uno dei servizi dati di Microsoft Azure, Customer Insights può connettersi facilmente all'origine dati senza dover reinserire i dati. Selezionare una delle seguenti opzioni:
- [Azure Data Lake Storage (file csv o parquet in una cartella Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics (database di Data Lake)](connect-synapse.md)
- [Data lake Microsoft Dataverse](connect-dataverse-managed-lake.md)

**Importazione e trasformazione**

Se usi origini dati locali, dati Microsoft o di terze parti, importa e trasforma i dati usando i connettori Power Query.
- [Connettori Power Query](connect-power-query.md)

## <a name="review-data-sources"></a>Esaminare le origini dati

Se l'ambiente è stato configurato per usare l'archiviazione di Customer Insights e usi origini dati locali, usi i flussi di dati di Power Platform. Cin i flussi di dati di Power Platform, puoi visualizzare le origini dati condivise e le origini dati gestite da altri. La pagina **Origini dati** elenca le origini dati in tre sezioni:
- **Condivisa**: origini dati che possono essere gestite da tutti gli amministratori di Customer Insights. I flussi di dati Power Platform, il tuo account di archiviazione e il collegamento a un data lake gestito da Dataverse sono esempi di origini dati condivise.
- **Gestito da me**: flussi di dati di Power Platform creati e gestiti solo da te. Altri amministratori di Customer Insights possono solo visualizzare questi flussi di dati, ma non modificarli, aggiornarli o eliminarli.
- **Gestito da altri**: flussi di dati di Power Platform creati da altri amministratori. Puoi solo visualizzarli. Indica il titolare del flusso di dati a cui rivolgersi per qualsiasi assistenza.
> [!NOTE]
> Tutte le entità possono essere visualizzate e utilizzate da altri utenti. Sebbene le origini dati siano di proprietà dell'utente che le ha create, le entità risultanti dall'inserimento dei dati possono essere usate da ogni utente di Customer Insights.

Se il tuo ambiente non usa i flussi d dati di Power Platform, la pagina **Origini dati** contiene solo un elenco di tutte le origini dati. Nessuna sezione visualizzata.

## <a name="manage-existing-data-sources"></a>Gestire origini dati esistenti

Vai a **Dati** > **Origini dati** per visualizzare il nome di ogni origine dati inserita, il relativo stato e la data dell'ultimo aggiornamento dei dati per tale origine. Puoi ordinare l'elenco delle origini dati in base a qualsiasi colonna o utilizzare la casella di ricerca per trovare l'origine dati che vuoi gestire.

Seleziona un'origine dati per visualizzare le azioni disponibili.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Origine dati aggiunta.":::

- [**Modifica**](#add-or-edit-data-sources) l'origine dati per modificarne le proprietà.
- [**Aggiorna**](#refresh-data-sources) l'origine dati per includere i dati più recenti.
- [**Arricchisci**](data-sources-enrichment.md) l'origine dati prima dell'unificazione.
- **Elimina** l'origine dati. Un'origine dati può essere eliminata solo se i dati non vengono usati in alcuna elaborazione come unificazione, informazioni dettagliate, attivazioni o esportazioni.

## <a name="refresh-data-sources"></a>Aggiornare le origini dati

Le origini dati possono essere aggiornate in base a una pianificazione automatica o manualmente su richiesta. Le [origini dati locali](connect-power-query.md#add-data-from-on-premises-data-sources) aggiornano le relative pianificazioni che vengono configurate durante l'inserimento dati. Per le origini dati collegate, l'inserimento dati usa gli ultimi dati disponibili da tale origine dati.

Vai ad **Amministratore** > **Sistema** > [**Pianifica**](system.md#schedule-tab) per configurare gli aggiornamenti pianificati dal sistema delle origini dati inserite.

Per aggiornare un'origine dati su richiesta:

1. Vai a **Dati** > **Origini dati**.

1. Seleziona l'origine dati che vuoi aggiornare e seleziona **Aggiorna**. L'origine dati è ora attivata per un aggiornamento manuale. L'aggiornamento di un'origine dati aggiornerà sia lo schema dell'entità che i dati per tutte le entità specificate nell'origine dati.

1. Seleziona lo stato per aprire il riquadro **Dettagli stato** e visualizzare l'avanzamento del processo. Per annullare il processo, seleziona **Annulla processo** nella parte inferiore del riquadro.

[!INCLUDE [footer-include](includes/footer-banner.md)]
