---
title: Creare misure dai modelli
description: Definisci le misure utilizzando i modelli per casi d'uso comuni.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170778"
---
# <a name="create-measures-from-templates"></a>Creare misure dai modelli

Usa modelli predefiniti di [misure](measures.md) di uso comune per creare le misure. I modelli si basano sui dati mappati dall'entità *Impegno unificato*. Quindi assicurati di aver configurato [impegni del cliente](activities.md) prima di creare una misura da un modello.

I modelli per misure sono supportati solo in ambienti per **clienti individuali**. Per creare misure personalizzate o misure per B2B, vedi [Usare il generatore di misure](measure-builder.md).

Modelli di misura disponibili:
- Valore medio transazione
- Valore transazione totale
- Ricavi medi giornalieri
- Ricavi medi mensili
- Ricavi medi annuali
- Numero di transazioni
- Punti programma fedeltà ottenuti
- Punti programma fedeltà riscattati
- Saldo punti programma fedeltà
- Durata del cliente attivo
- Durata iscrizione al programma fedeltà
- Tempo dall'ultimo acquisto

## <a name="build-a-new-measure-using-a-template"></a>Creare una nuova misura utilizzando un modello

1. Vai in **Misure**.

1. Seleziona **Nuovo** e seleziona **Scegli un modello**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Screenshot del menu a discesa durante la creazione di una nuova misura con evidenziazione sul modello.":::

1. Trova il modello che si adatta alle tue esigenze e seleziona **Scegli modello**.

1. Rivedi i dati richiesti e seleziona **Attività iniziali** se disponi di tutti i dati.

1. Seleziona **Modifica dettagli** accanto a Nome misura. Specifica un nome per la misura. Facoltativamente, aggiungi [tag](work-with-tags-columns.md#manage-tags) alla misura.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Finestra di dialogo Modifica dettagli.":::

1. Seleziona **Fatto**.

1. Nella sezione **Imposta periodo di tempo** definisci l'intervallo di tempo dei dati. Scegli se vuoi che la nuova misura copra l'intero set di dati selezionando **Sempre** o se vuoi che la misura si concentri su un **Periodo di tempo specifico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot che mostra la sezione del periodo di tempo durante la configurazione di una misura da un modello.":::

1. Nella sezione successiva, seleziona **Aggiungi dati** per scegliere gli impegni e mappare i dati corrispondenti dalla entità *Impegno unificato*.

    1. Passaggio 1 di 2: sotto **Tipo di impegno**, scegli il tipo di entità che desideri utilizzare. Per **Impegni**, seleziona le entità che desideri mappare e quindi seleziona **Avanti**.
    1. Passaggio 2 di 2: scegli l'attributo dall'entità *Impegno unificato* per il componente richiesto dalla formula. Ad esempio, per valore medio della transazione, è l'attributo che rappresenta il valore della transazione. Per **Timestamp impegno**, scegli l'attributo dall'entità *Impegno unificato* che rappresenta la data e l'ora dell'impegno.
    1. Seleziona **Salva**.

    Una volta completato il mapping dei dati, lo stato è **Completato** e viene visualizzato il nome degli impegni e degli attributi mappati.

1. Seleziona **Esegui** per calcolare i risultati della misura. Seleziona **Salva bozza** se vuoi mantenere la configurazione corrente ed eseguire la misura in un secondo momento. Viene visualizzata la pagina **Misure**.

## <a name="next-step"></a>Passaggio successivo

Usa le misure esistenti per creare [un segmento di clienti](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
