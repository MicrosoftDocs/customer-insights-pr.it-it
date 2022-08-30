---
title: Panoramica dei segmenti
description: Panoramica sui segmenti e su come crearli e gestirli.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304800"
---
# <a name="segments-overview"></a>Panoramica dei segmenti

I segmenti ti consentono di raggruppare i clienti in base ad attributi demografici, transazionali o comportamentali. Puoi utilizzare i segmenti per indirizzare campagne promozionali, attività di vendita e azioni di assistenza clienti per raggiungere i tuoi obiettivi aziendali.

I profili del cliente o del contatto che corrispondono ai filtri di una definizione di segmento sono indicati come *membri* di un segmento. Si applicano alcuni [limiti di servizio](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Crea un segmento

Scegli come creare un segmento in base al gruppo di destinatari di riferimento.

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (B2C)](#tab/b2c)

- Segmenti complessi con generatore di segmenti: [genera i tuoi segmenti](segment-builder.md)
- Segmenti semplici con un operatore: [segmento veloce](segment-quick.md)
- Metodo basato sull'intelligenza artificiale per trovare clienti simili: [clienti simili](find-similar-customer-segments.md)
- Suggerimenti generati mediante intelligenza artificiale basati su misure o attributi: [segmenti suggeriti basati su misure](suggested-segments.md)
- Suggerimenti basati sulle attività: [segmenti suggeriti in base all'attività del cliente](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Account aziendali (B2B)](#tab/b2b)

Segmento di account o segmento di contatti (anteprima) con il generatore di segmenti: [Crea un valore personalizzato](segment-builder.md)

> [!NOTE]
> La maggior parte delle destinazioni di esportazione richiede informazioni di contatto per scopi di marketing. Pertanto, crea segmenti di contatti da utilizzare per tali esportazioni.

---

## <a name="manage-existing-segments"></a>Gestire segmenti esistenti

Vai alla pagina **Segmenti** per visualizzare i segmenti creati, il loro stato e l'ultimo aggiornamento dei dati. Puoi ordinare l'elenco dei segmenti in base a qualsiasi colonna o utilizzare la casella di ricerca per trovare il segmento che vuoi gestire.

> [!TIP]
> Negli ambienti B2B, la colonna **Tipo di gruppo di destinatari** identifica se un segmento è basato su account o contatti.

Seleziona un segmento per visualizzare le azioni disponibili.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento selezionato con elenco a discesa delle opzioni e opzioni disponibili." lightbox="media/segments-selected-segment.png":::

- [**Visualizza**](#view-segment-details) i dettagli del segmento, inclusa la tendenza del conteggio dei membri e un'anteprima dei membri del segmento.
- **Scarica** l'elenco dei membri in un file .CSV.
- **Modifica** il segmento per modificarne le proprietà.
- **Crea duplicato** di un segmento. Puoi scegliere di modificarne le proprietà immediatamente o di salvare il duplicato.
- [**Aggiorna**](#refresh-segments) il segmento per includere i dati più recenti.
- **Attiva** o **Disattiva** il segmento. I segmenti non attivi non verranno aggiornati durante un [aggiornamento pianificato](schedule-refresh.md) e il relativo **stato** sarà **Ignorato**, a indicare che non è stato nemmeno tentato un aggiornamento. I segmenti attivi vengono aggiornati in base al tipo: statici o dinamici.
- **Rendi statico** o **rendi dinamico** il tipo di segmento. I segmenti statici devono essere aggiornati manualmente. I segmenti dinamici vengono aggiornati automaticamente durante l'aggiornamento del sistema
- [**Trova clienti simili**](find-similar-customer-segments.md) dal segmento.
- **Rinomina** il segmento.
- **Tag** per [gestire i tag](work-with-tags-columns.md#manage-tags) per il segmento.
- [**Gestisci le esportazioni**](#export-segments) per vedere i segmenti relativi alle esportazioni e gestirli. [Altre informazioni sulle esportazioni.](export-destinations.md)
- **Elimina** il segmento.
- **Colonne** per [personalizzare le colonne](work-with-tags-columns.md#customize-columns) visualizzate.
- **Filtro** per [filtrare in base ai tag](work-with-tags-columns.md#filter-on-tags).
- **Nome di ricerca** per eseguire la ricerca in base al nome del segmento.

## <a name="view-segment-details"></a>Visualizzare i dettagli di un segmento

Nella pagina **Segmenti**, seleziona un segmento per visualizzare la cronologia di elaborazione e i membri del segmento.

La parte superiore della pagina include un grafo di tendenza che visualizza le modifiche nel numero di membri. Passa il mouse sopra i punti dati per vedere il numero di membri a una data specifica. Modifica l'intervallo di tempo della visualizzazione.

:::image type="content" source="media/segment-time-range.png" alt-text="Intervallo di tempo segmento.":::

La parte inferiore contiene un elenco dei membri del segmento.

> [!NOTE]
> I campi che compaiono in questo elenco si basano sugli attributi delle entità del segmento.
>
> L'elenco è un'anteprima dei membri del segmento corrispondenti e mostra i primi 100 record del segmento in modo da poterlo valutare rapidamente e rivederne le definizioni se necessario. Per vedere tutti i record corrispondenti, seleziona **Vedi altro** che apre la pagina [**Entità**](entities.md) o [esporta il segmento](export-destinations.md).

## <a name="refresh-segments"></a>Aggiornare i segmenti

I segmenti possono essere aggiornati in base a una pianificazione automatica o manualmente su richiesta. Per aggiornare manualmente uno o più segmenti, selezionali e scegli **Aggiorna**.

Per [pianificare un aggiornamento automatico](schedule-refresh.md), vai ad **Amministratore** > **Sistema** > **Pianifica**. Si applicano le seguenti regole:

- Tutti i segmenti con tipo **Dinamico** o **Espansione** verranno aggiornati automaticamente alla cadenza impostata. Al termine dell'aggiornamento, il campo **Stato** indica se si sono verificati problemi durante l'aggiornamento del segmento. Il campo **Ultimo aggiornamento** mostra un timestamp dell'ultimo aggiornamento completato. Se si verifica un errore, selezionalo per visualizzare i dettagli su ciò che è accaduto.
- I segmenti con tipo **Statico** *non* vengono aggiornati automaticamente. Il campo **Ultimo aggiornamento** mostra un timestamp dell'ultima volta che il segmento statico è stato eseguito o aggiornato manualmente.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Esportare segmenti

Esporta i segmenti in altre app per utilizzare ulteriormente i dati. Esporta un segmento dalla pagina dei segmenti o dalla [pagina delle esportazioni](export-destinations.md).

1. Vai alla pagina **Segmenti** e seleziona il segmento che vuoi esportare.

1. Seleziona **Gestisci esportazioni**. La pagina **Esportazioni (anteprima) per segmento** si apre. Visualizza tutte le esportazioni configurate raggruppate in base al fatto che contengano o meno il segmento corrente.

   1. Per aggiungere il segmento selezionato a un'esportazione, **Modifica** la rispettiva esportazione per selezionare il segmento corrispondente, quindi salva. Negli ambienti per clienti individuali, seleziona l'esportazione nella lista e seleziona **Aggiungi segmento** per ottenere lo stesso risultato.

   1. Per creare una nuova esportazione con il segmento selezionato, seleziona **Aggiungi esportazione**. Per ulteriori informazioni sulla creazione di esportazioni, vedi [Configura una nuova esportazione](export-destinations.md#set-up-a-new-export).

1. Seleziona **Indietro** per tornare alla pagina principale dei segmenti.

## <a name="track-usage-of-a-segment"></a>Tenere traccia dell'utilizzo di un segmento

Se utilizzi i segmenti nelle app che si basano sulla stessa organizzazione Microsoft Dataverse collegata a Customer Insights, puoi monitorare l'utilizzo di un segmento. Per i [Segmenti di Customer Insights utilizzati nei percorsi del cliente di Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), il sistema ti informa sull'utilizzo di quel segmento.

Quando modifichi un segmento utilizzato nell'ambiente Customer Insights o in un percorso del cliente in Marketing, un banner nel [generatore di segmenti](segment-builder.md) ti informa sulle dipendenze. Controlla i dettagli della dipendenza direttamente nel banner o selezionando **Utilizzo** nel generatore di segmenti.

Il riquadro **Utilizzo del segmento** mostra i dettagli sull'utilizzo di questo segmento nelle app basate su Dataverse. Per i segmenti utilizzati nei percorsi dei clienti, troverai un collegamento per esaminare il percorso in Marketing in cui viene utilizzato questo segmento. Se disponi delle autorizzazioni per accedere all'app Marketing, visualizza ulteriori dettagli in quell'app.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Riquadro laterale con i dettagli dell'utilizzo del segmento nel generatore di segmenti.":::

Il sistema ti informa sull'utilizzo di un segmento tracciato quando tenti di eliminarlo. Se il segmento che stai per eliminare viene utilizzato in un percorso del cliente in Marketing, il percorso si interromperà per tutti gli utenti nel segmento. Se il viaggio fa parte di una campagna di marketing, l'eliminazione influirà sulla campagna stessa. Tuttavia, puoi comunque eliminare il segmento nonostante gli avvisi.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Finestra di dialogo per confermare l'eliminazione del segmento quando un segmento viene utilizzato in un'applicazione Dataverse.":::

### <a name="supported-apps"></a>App supportate

L'utilizzo è attualmente monitorato nelle seguenti app basate su Dataverse:

- [Percorsi del cliente in Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
