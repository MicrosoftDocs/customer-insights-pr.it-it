---
title: Utilizzare origini dati per inserire dati
description: Scopri come importare dati da varie origini.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
  - ci-data-sources
  - ci-create-data-source
  - customerInsights
---

# <a name="data-sources-overview"></a>Panoramica delle origini dati



La funzionalità Informazioni dettagliate sul gruppo di destinatari in Dynamics 365 Customer Insights si connette ai dati da un ampio insieme di origini. La connessione a un'origine dati viene spesso definita processo di *inserimento dati*. Dopo aver inserito i dati, puoi [unificare](data-unification.md) e agire su di essi.

## <a name="add-a-data-source"></a>Aggiungi un'origine dati

Fai riferimento agli articoli dettagliati su come aggiungere un'origine dati, a seconda dell'opzione scelta.

È possibile aggiungere le seguenti origini dati:

- [Tramite decine di connettori Power Query](connect-power-query.md)
- [Da una cartella di Common Data Model](connect-common-data-model.md)
- [Dal tuo lake Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [Da un database di Azure Synapse Analytics](connect-synapse.md)

> [!NOTE]
> Se stai utilizzando la versione di prova, la sezione dei metodi di importazione include un'opzione **Raccolta dati di Customer Insights**. Scegli questa opzione per selezionare un campione di set di dati disponibile per vari settori. Per ulteriori informazioni, vedi la [versione di valutazione di Dynamics 365 Customer Insights](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Aggiungere dati dalle origini dati locale

L'inserimento di dati da origini dati locale in informazioni dettagliate gruppo di destinatari è supportata in base ai flussi di dati Microsoft Power Platform. Puoi abilitare i flussi di dati in Customer Insights [fornendo l'URL dell'ambiente Microsoft Dataverse](create-environment.md) quando si allestisce l'ambiente.

Le origini dati che vengono create dopo aver associato un ambiente Dataverse con Customer Insights usano [flussi di dati Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) per impostazione predefinita. I flussi di dati supportano la connettività locale utilizzando il gateway di dati. Puoi rimuovere e ricreare origini dati che esistevano prima dell'associazione dell'ambiente Dataverse [utilizzando i gateway dati locali](/data-integration/gateway/service-gateway-app).

I gateway dati di un ambiente esistente Power BI o Power Apps saranno visibili e potrai riutilizzarli in Customer Insights. La pagina delle origini dati mostra i collegamenti per andare all'ambiente Microsoft Power Platform in cui è possibile visualizzare e configurare i gateway dati locale.

> [!IMPORTANT]
> Assicurati che i gateway siano aggiornati all'ultima versione. È possibile installare un aggiornamento e riconfigurare un gateway direttamente da un prompt visualizzato sullo schermo del gateway oppure [scaricare l'ultima versione](https://powerapps.microsoft.com/downloads/). Se non si utilizza l'ultima versione del gateway, l'aggiornamento del flusso di dati non viene eseguito e viene visualizzato un messaggio di errore come **La parola chiave non è supportata: proprietà di configurazione. Nome parametro: parola chiave**.

## <a name="review-ingested-data"></a>Esamina i dati inseriti
Se il tuo ambiente contiene flussi di dati di Power Platform, nella pagina **Origini dati** sono elencate tre sezioni: 
- **Condivisa**: origini dati che possono essere gestite da tutti gli amministratori di Customer Insights. I flussi di dati Power BI, il tuo account di archiviazione e il collegamento a un data lake gestito da Dataverse sono esempi di origini dati condivise.
- **Gestito da me**: i flussi di dati di Power Platform creati possono essere gestiti solo da te. Altri amministratori di Customer Insights possono solo visualizzare questi flussi di dati, ma non modificarli, aggiornarli o eliminarli.
- **Gestito da altri**: flussi di dati di Power Platform creati da altri amministratori. Puoi solo visualizzarli. Indica il titolare del flusso di dati a cui rivolgersi per qualsiasi assistenza.
> [!NOTE]
> Tutte le entità possono essere visualizzate e utilizzate da altri utenti. La contestualità dell'utente si applica solo alle origini dati e non alle entità che risultano dai flussi di dati.

Se non viene utilizzato alcun flusso di dati di Power Platform, non vedrai alcun gruppo né sezione. La pagina **Origini dati** contiene solo un elenco di tutte le origini dati.

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
