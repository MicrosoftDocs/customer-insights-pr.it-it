---
title: Segmenti in Customer Insights
description: Panoramica sui segmenti e su come crearli e gestirli.
ms.date: 03/30/2022
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
ms.openlocfilehash: 9791e971387eb7db91ed7c4e4fe76552656013ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647069"
---
# <a name="segments-overview"></a>Panoramica dei segmenti

I segmenti ti consentono di raggruppare i clienti in base ad attributi demografici, transazionali o comportamentali. Puoi utilizzare i segmenti per indirizzare campagne promozionali, attività di vendita e azioni di assistenza clienti per raggiungere i tuoi obiettivi aziendali.

I profili del cliente che corrispondono ai filtri di una definizione di segmento sono indicati come *membri* di un segmento. Si applicano alcuni [limiti di servizio](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Creare un nuovo segmento

Un nuovo segmento può essere creato in modi diversi: 

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

- Segmento complesso con costruttore di segmenti: [Costruire il nostro](segment-builder.md#create-a-new-segment) 
- Segmenti semplici con un operatore: [segmento veloce](segment-builder.md#quick-segments) 
- Modo basato sull'intelligenza artificiale per trovare clienti simili: [clienti simili](find-similar-customer-segments.md) 
- Suggerimenti basati sull'intelligenza artificiale per misure o attributi: [segmenti suggeriti per migliorare le misure](suggested-segments.md) 
- Suggerimenti basati sulle attività: [segmenti suggeriti in base all'attività del cliente](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

- Segmento complesso con costruttore di segmenti: [Costruire il nostro](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Gestire segmenti esistenti

Vai alla pagina **Segmenti** per visualizzare tutti i segmenti salvati e gestirli.

Ogni segmento è rappresentato da una riga che include informazioni aggiuntive sul segmento.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento selezionato con elenco a discesa delle opzioni e opzioni disponibili." lightbox="media/segments-selected-segment.png":::

Quando si seleziona un segmento sono disponibili le seguenti azioni:

- **Visualizza** i dettagli del segmento, inclusa la tendenza del conteggio dei membri, un'anteprima dei membri del segmento.
- **Scarica** l'elenco dei membri in un file .CSV.
- **Modifica** il segmento per modificarne le proprietà.
- **Crea duplicato** di un segmento. Puoi scegliere di modificare subito le proprietà o semplicemente salvare il duplicato.
- **Aggiorna** il segmento per includere gli ultimi dati.
- **Attiva** o **Disattiva** il segmento. Per i segmenti inattivi, la definizione del segmento esiste, ma non contiene ancora alcun cliente. Un segmento attivo cerca i clienti che corrispondono alla definizione del segmento. Se un [aggiornamento pianificato](system.md#schedule-tab) è configurato, i segmenti inattivi hanno **Stato** elencato come **Ignorato**, a indicare che non è stato nemmeno tentato un aggiornamento. Quando un segmento inattivo viene attivato, verrà aggiornato e incluso negli aggiornamenti pianificati.
  In alternativa, puoi utilizzare la funzionalità **Pianifica più tardi** nel menu a discesa **Attiva/Disattiva** per specificare una data e un'ora future per l'attivazione e la disattivazione di un particolare segmento.
- **[Trova clienti simili](find-similar-customer-segments.md)** dal segmento.
- **Rinomina** il segmento.
- **Tag** per [gestire i tag](work-with-tags-columns.md#manage-tags) per il segmento.
- **Scarica** l'elenco dei membri in un file .CSV.
- **Gestisci esportazioni** per vedere i segmenti relativi alle esportazioni e gestirli. [Altre informazioni sulle esportazioni.](export-destinations.md)
- **Elimina** il segmento.
- **Colonne** per [personalizzare le colonne](work-with-tags-columns.md#customize-columns) visualizzate.
- **Filtro** per [filtrare in base ai tag](work-with-tags-columns.md#filter-on-tags).
- **Nome di ricerca** per eseguire la ricerca in base al nome del segmento.

## <a name="refresh-segments"></a>Aggiornare i segmenti

Puoi aggiornare tutti i segmenti contemporaneamente selezionando **Aggiorna tutto** nella pagina **Segmenti** oppure puoi aggiornare uno o più segmenti quando li selezioni e scegli **Aggiorna** dalle opzioni. In alternativa, puoi configurare un aggiornamento ricorrente in **Amministratore** > **Sistema** > **Pianifica**. Quando viene configurato un aggiornamento ricorrente, si applicano le seguenti regole:
- Tutti i segmenti con tipo **Dinamico** o **Espansione** verranno aggiornati automaticamente alla cadenza impostata. Al termine dell'aggiornamento, il campo **Stato** indica se si sono verificati problemi durante l'aggiornamento del segmento. Il campo **Ultimo aggiornamento** mostra un timestamp dell'ultimo aggiornamento completato. Se si verifica un errore, selezionalo per visualizzare i dettagli su ciò che è accaduto.
- I segmenti con tipo **Statico** *non* vengono aggiornati automaticamente. Il campo **Ultimo aggiornamento** mostra un timestamp dell'ultima volta che i segmenti statici sono stati eseguiti o aggiornati manualmente.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Esportare segmenti

Puoi esportare un segmento dalla pagina dei segmenti o dalla [pagina delle esportazioni](export-destinations.md). 

1. Vai alla pagina **Segmenti**.

1. Seleziona **Mostra più [...]** per il segmento che desideri esportare.

1. Seleziona **Gestisci esportazioni** dall'elenco a discesa delle azioni.

1. La pagina **Esportazioni (anteprima) per segmento** si apre. Potete vedere tutte le esportazioni configurate raggruppate in base al fatto che contengano o meno il segmento corrente.

   1. Per aggiungere il segmento selezionato a un'esportazione, **Modifica** la rispettiva esportazione per selezionare il segmento corrispondente, quindi salva. Negli ambienti per clienti individuali puoi invece selezionare l'esportazione nella lista e selezionare **Aggiungi segmento** per ottenere lo stesso risultato.

   1. Per creare una nuova esportazione con il segmento selezionato, seleziona **Aggiungi esportazione**. Per ulteriori informazioni sulla creazione di esportazioni, vedi [Configura una nuova esportazione](export-destinations.md#set-up-a-new-export).

1. Seleziona **Indietro** per tornare alla pagina principale dei segmenti.

## <a name="view-processing-history-and-segment-members"></a>Visualizzare la cronologia di elaborazione e i membri del segmento

Puoi visualizzare i dati consolidati di un segmento esaminandone i dettagli.

Nella pagina **Segmenti** seleziona il segmento da esaminare.

La parte superiore della pagina include un grafo di tendenza che visualizza le modifiche nel numero di membri. Passa il mouse sopra i punti dati per vedere il numero di membri a una data specifica.

Puoi aggiornare l'intervallo di tempo della visualizzazione.

> [!div class="mx-imgBorder"]
> ![Intervallo di tempo segmento.](media/segment-time-range.png "Intervallo di tempo segmento")

La parte inferiore contiene un elenco dei membri del segmento.

> [!NOTE]
> I campi che compaiono in questo elenco si basano sugli attributi delle entità del segmento.
>
>L'elenco è un'anteprima dei membri del segmento corrispondenti e mostra i primi 100 record del segmento in modo da poterlo valutare rapidamente e rivederne le definizioni se necessario. Per vedere tutti i record corrispondenti, è necessario [esportare il segmento](export-destinations.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
