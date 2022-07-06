---
title: Panoramica delle origini dati
description: Scopri come importare o inserire i dati da varie origini.
ms.date: 05/18/2022
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
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051458"
---
# <a name="data-sources-overview"></a>Panoramica delle origini dati

Dynamics 365 Customer Insights fornisce connessioni per portare dati da un'ampia serie di origini. La connessione a un'origine dati viene spesso definita processo di *inserimento dati*. Dopo aver inserito i dati, puoi [unificare](data-unification.md), generare informazioni dettagliate e attivare i dati per la creazione di esperienze personalizzate.

## <a name="add-data-sources"></a>Aggiungere origini dati

Puoi collegare o importare origini dati in Customer Insights. I collegamenti seguenti forniscono istruzioni sull'aggiunta di origini dati.

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

Vai a **Dati** > **Origini dati** per visualizzare il nome di ogni origine dati inserita, il relativo stato e la data dell'ultimo aggiornamento dei dati per tale origine. Puoi ordinare l'elenco delle origini dati per colonna.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Origine dati aggiunta.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Il caricamento dei dati può richiedere tempo. Al termine del completamento dell'aggiornamento, i dati inseriti possono essere rivisti dalla pagina **Entità**. Per ulteriori informazioni, vedi [Entità](entities.md).

## <a name="refresh-data-sources"></a>Aggiornare le origini dati

Le origini dati possono essere aggiornate in base a una pianificazione automatica o manualmente su richiesta. Le [origini dati locali](connect-power-query.md#add-data-from-on-premises-data-sources) aggiornano le relative pianificazioni che vengono configurate durante l'inserimento dati. Per le origini dati collegate, l'inserimento dati usa gli ultimi dati disponibili da tale origine dati.

Vai ad **Amministratore** > **Sistema** > [**Pianifica**](system.md#schedule-tab) per configurare gli aggiornamenti pianificati dal sistema delle origini dati inserite.

Per aggiornare un origine dati su richiesta, segui questi passaggi:

1. Vai a **Dati** > **Origini dati**.

1. Seleziona i puntini di sospensione verticali (&vellip;) accanto all'origine dati che desideri aggiornare e seleziona **Aggiorna** dall'elenco a discesa. L'origine dati è ora attivata per un aggiornamento manuale. L'aggiornamento di un'origine dati aggiornerà sia lo schema dell'entità che i dati per tutte le entità specificate nell'origine dati.

1. Seleziona **Arresta aggiornamento** se desideri annullare un aggiornamento esistente e riportare l'origine dati allo stato dell'ultimo aggiornamento.

## <a name="delete-a-data-source"></a>Eliminare un'origine dati

Un'origine dati può essere eliminata solo se i dati non vengono usati in alcuna elaborazione come unificazione, informazioni dettagliate, attivazioni o esportazioni.

1. Vai a **Dati** > **Origini dati**.

2. Seleziona i puntini di sospensione verticali (&vellip;) accanto all'origine dati che desideri rimuovere e seleziona **Elimina** dal menu a tendina.

3. Conferma l'eliminazione.


[!INCLUDE [footer-include](includes/footer-banner.md)]
