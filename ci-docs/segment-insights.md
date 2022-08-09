---
title: Informazioni dettagliate sui segmenti (anteprima)
description: Ottieni informazioni dettagliate sui segmenti esistenti per scoprire cosa li differenzia e cosa hanno in comune.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171008"
---
# <a name="segment-insights-preview"></a>Informazioni dettagliate sui segmenti (anteprima)

Scopri ulteriori informazioni e informazioni dettagliate sui segmenti esistenti. Scopri cosa differenzia due segmenti o cosa hanno in comune.

## <a name="segment-overlap"></a>Sovrapposizione segmenti

L'analisi di sovrapposizione dei segmenti mostra quanti e quali clienti sono comuni a due o più segmenti. Ad esempio, come un segmento di clienti frequenti si sovrappone a un segmento che contiene clienti che sono soddisfatti del servizio o del prodotto.
Puoi anche analizzare come cambia la sovrapposizione per attributi specifici.

### <a name="run-an-overlap-analysis"></a>Eseguire un'analisi di sovrapposizione

1. Vai a **Segmenti** e seleziona la scheda **Informazioni dettagliate (anteprima)**.

1. Seleziona **Nuovo** e scegli l'opzione **Sovrapposizione** nel riquadro **Scegli tipo di informazioni dettagliate**.

1. Scegli i segmenti di interesse e seleziona **Avanti**.

1. Facoltativamente, scegli uno o più campi di interesse per analizzare le sovrapposizioni per ogni possibile valore del campo e seleziona **Avanti**.

1. Fornisci un nome per l'analisi di sovrapposizione, un nome visualizzato opzionale e una descrizione.

1. Seleziona **Salva** per iniziare l'analisi. L'analisi di sovrapposizione è pronta quando lo stato passa da Aggiornamento in corso a Operazione completata.

### <a name="view-and-optimize-an-overlap-analysis"></a>Visualizzare e ottimizzare un'analisi di sovrapposizione

1. Dopo aver completato l'analisi, trova i dettagli su questa informazione dettagliata in **Segmenti** > **Informazioni dettagliate (anteprima)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Dettagli delle informazioni sulla sovrapposizione del segmento.":::

1. Seleziona una informazione per vedere i risultati dell'analisi:

   - Il numero di membri che si sovrappongono ai segmenti selezionati per l'analisi.
   - Il numero di membri inclusi in uno dei segmenti ma non nel resto dei segmenti.
   - Se hai selezionato i campi durante la configurazione dell'analisi di sovrapposizione, li troverai nelle schede corrispondenti. Puoi utilizzare il menu a discesa del filtro per selezionare qualsiasi livello di attributo di interesse e la tabella in basso mostrerà i dati corrispondenti.

## <a name="segment-differentiators"></a>Differenziatori segmento

I differenziatori di segmento ti aiutano a scoprire cosa differenzia un segmento dal resto dei tuoi clienti o da un altro segmento. Seleziona un segmento e il sistema identifica gli attributi del profilo e le misure che distinguono il segmento selezionato.

### <a name="run-a-differentiator-analysis"></a>Eseguire l'analisi del differenziatore

1. Vai a **Segmenti** e seleziona la scheda **Informazioni dettagliate (anteprima)**.

1. Seleziona **Nuovo** e scegli l'opzione **Differenziatori** nel riquadro **Scegli tipo di informazioni dettagliate**.

1. Scegli il segmento che desideri analizzare come **Segmento primario** e seleziona **Avanti**.

1. Scegli **Tutti i clienti** o un **segmento secondario** con cui confrontare il segmento primario e seleziona **Avanti**.

1. Facoltativamente, scegli uno o più campi di interesse per attivare l'analisi su attributi specifici e seleziona **Avanti**.

1. Fornisci un nome per l'analisi del differenziatore, un nome visualizzato opzionale e una descrizione.

1. Seleziona **Salva** per iniziare l'analisi. L'analisi del differenziatore è pronta quando lo stato passa da Aggiornamento in corso a Operazione completata.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Visualizzare e ottimizzare l'analisi dei differenziatori

1. Dopo aver completato l'analisi, vai a **Segmenti** > **Informazioni dettagliate (anteprima)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Dettagli delle informazioni sul differenziatore del segmento.":::

1. Seleziona una informazione per vedere i risultati dell'analisi. L'analisi del differenziatore include due schede. La scheda **Attributi** elenca gli attributi del profilo considerati come differenziatori. La scheda **Misure** elenca i differenziatori. Ogni scheda include i seguenti dettagli:

   - Elenco classificato dei differenziatori, ordinato per punteggio di differenza.
   - Il **Punteggio di differenza** per ogni differenziatore. Il punteggio differenza rappresenta il grado di differenza di un attributo tra due segmenti. Maggiore è il punteggio di differenza, più gli attributi differiscono tra i due segmenti. Seleziona un punteggio per aprire il riquadro **Punteggio di differenza** con le distribuzioni dei valori per quell'attributo.

## <a name="manage-segment-insights"></a>Gestire le informazioni dettagliate sui segmenti

Seleziona **Segmenti** > **Informazioni dettagliate (anteprima)** per visualizzare le informazioni dettagliate sui segmenti e per gestirle. Seleziona le informazioni dettagliate sui segmenti per visualizzare le azioni disponibili.

- **Visualizza** l'analisi delle informazioni dettagliate
- **Modifica** le informazioni dettagliate per modificarne le proprietà
- **Aggiorna** le informazioni dettagliate per eseguire nuovamente l'analisi
- **Rinomina** le informazioni dettagliate
- **Elimina** le informazioni dettagliate

[!INCLUDE [footer-include](includes/footer-banner.md)]
