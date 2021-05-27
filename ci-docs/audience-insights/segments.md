---
title: Segmenti nelle informazioni dettagliate sul gruppo di destinatari
description: Panoramica sui segmenti e su come crearli e gestirli.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034017"
---
# <a name="segments-overview"></a>Panoramica dei segmenti

I segmenti ti consentono di raggruppare i clienti in base ad attributi demografici, transazionali o comportamentali. Puoi utilizzare i segmenti per indirizzare campagne promozionali, attività di vendita e azioni di assistenza clienti per raggiungere i tuoi obiettivi aziendali.

I profili del cliente che corrispondono ai filtri di una definizione di segmento sono indicati come *membri* di un segmento. Si applicano alcuni [limiti di servizio](service-limits.md).

## <a name="create-a-new-segment"></a>Creare un nuovo segmento

Un nuovo segmento può essere creato in modi diversi: 

- Segmento complesso con generatore di segmenti: [segmento vuoto](segment-builder.md#create-a-new-segment)
- Segmenti semplici con un operatore: [segmento veloce](segment-builder.md#quick-segments)
- Modo basato sull'intelligenza artificiale per trovare clienti simili: [clienti simili](find-similar-customer-segments.md)
- Suggerimenti basati sull'intelligenza artificiale per misure o attributi: [segmenti suggeriti per migliorare le misure](suggested-segments.md)
- Suggerimenti basati sulle attività: [segmenti suggeriti in base all'attività del cliente](suggested-segments-activity.md)

## <a name="get-insights-on-existing-segments"></a>Ottenere le informazioni dettagliate sui segmenti esistenti

Scopri ulteriori informazioni sui segmenti esistenti con le [informazioni dettagliate del segmento](segment-insights.md). Scopri cosa differenzia due segmenti o cosa hanno in comune.

## <a name="find-similar-customers"></a>Trova clienti simili

Trova clienti simili ai membri di un segmento selezionato con l'aiuto dell'intelligenza artificiale. Per ulteriori informazioni, vedi [Clienti simili](find-similar-customer-segments.md).

## <a name="manage-existing-segments"></a>Gestire segmenti esistenti

Vai alla pagina **Segmenti** per visualizzare tutti i segmenti salvati e gestirli.

Ogni segmento è rappresentato da una riga che include informazioni aggiuntive sul segmento.

> [!div class="mx-imgBorder"]
> ![Opzioni per gestire un segmento esistente](media/segments-selected-segment.png "Opzioni per gestire un segmento esistente")

Quando selezioni un segmento sono disponibili le seguenti azioni:

- **Visualizza** i dettagli del segmento, inclusa la tendenza del conteggio dei membri, un'anteprima dei membri del segmento.
- **Modifica** il segmento per modificarne le proprietà.
- **Crea duplicato** di un segmento. Puoi scegliere di modificare subito le proprietà o semplicemente salvare il duplicato.
- **Aggiorna** il segmento per includere gli ultimi dati.
- **Attiva** o **Disattiva** il segmento. I segmenti hanno due possibili stati: attivo o inattivo. Questi stati sono utili quando si modifica un segmento. Per i segmenti inattivi, la definizione del segmento esiste, ma non contiene ancora alcun cliente. Quando attivi un segmento, il suo stato cambia da "inattivo" ad "attivo" e inizia a cercare i clienti che corrispondono alla definizione del segmento. Se un [aggiornamento pianificato](system.md#schedule-tab) è configurato, i segmenti inattivi hanno **Stato** elencato come **Ignorato**, a indicare che non è stato nemmeno tentato un aggiornamento. Quando un segmento inattivo viene attivato, verrà aggiornato e incluso negli aggiornamenti pianificati.
  In alternativa, puoi utilizzare la funzionalità **Pianifica più tardi** nel menu a discesa **Attiva/Disattiva** per specificare una data e un'ora future per l'attivazione e la disattivazione di un particolare segmento.
- **Rinomina** il segmento.
- **Scarica** l'elenco dei membri in un file .CSV.
- L'opzione **Aggiungi a** invia l'elenco degli ID cliente nel segmento per l'elaborazione in un'altra applicazione.
- **Elimina** il segmento.

## <a name="refresh-segments"></a>Aggiornare i segmenti

Puoi aggiornare tutti i segmenti contemporaneamente selezionando **Aggiorna tutto** nella pagina **Segmenti** oppure puoi aggiornare uno o più segmenti quando li selezioni e scegli **Aggiorna** dalle opzioni. In alternativa, puoi configurare un aggiornamento ricorrente in **Amministratore** > **Sistema** > **Pianifica**.

> [!TIP]
> Esistono [sei tipi di stato](system.md#status-types) per attività/processi. Inoltre, la maggior parte dei processi [dipende da altri processi a valle](system.md#refresh-policies). Puoi selezionare lo stato di un processo per visualizzare i dettagli sull'avanzamento dell'intero processo. Dopo aver selezionato **Vedi i dettagli** per una delle attività del processo sono disponibili informazioni aggiuntive: tempo di elaborazione, data dell'ultima elaborazione e tutti gli errori e gli avvisi associati all'attività.

## <a name="view-processing-history-and-segment-members"></a>Visualizzare la cronologia di elaborazione e i membri del segmento

Puoi visualizzare i dati consolidati di un segmento esaminandone i dettagli.

Nella pagina **Segmenti** seleziona il segmento da esaminare.

La parte superiore della pagina include un grafo di tendenza che visualizza le modifiche nel numero di membri. Passa il mouse sopra i punti dati per vedere il numero di membri a una data specifica.

Puoi aggiornare l'intervallo di tempo della visualizzazione.

> [!div class="mx-imgBorder"]
> ![Intervallo di tempo segmento](media/segment-time-range.png "Intervallo di tempo segmento")

La parte inferiore contiene un elenco dei membri del segmento.

> [!NOTE]
> I campi che compaiono in questo elenco si basano sugli attributi delle entità del segmento.
>
>L'elenco è un'anteprima dei membri del segmento corrispondenti e mostra i primi 100 record del segmento in modo da poterlo valutare rapidamente e rivederne le definizioni se necessario. Per vedere tutti i record corrispondenti, è necessario [esportare il segmento](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
