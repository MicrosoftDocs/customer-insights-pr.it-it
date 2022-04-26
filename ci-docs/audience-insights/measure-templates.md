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
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529406"
---
# <a name="use-a-template-to-build-a-measure"></a>Usare un modello per costruire una misura

È possibile utilizzare modelli predefiniti di [misure](measures.md) di uso comune per crearli. Descrizioni dettagliate dei modelli e un'esperienza guidata ti aiutano a creare misure efficienti. I modelli si basano sui dati mappati dall'entità *Impegno unificato*. Quindi assicurati di aver configurato [impegni del cliente](activities.md) prima di creare una misura da un modello.

Per creare misure personalizzate, vedi [Usare il generatore di misure per creare misure da zero](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

Modelli di misura disponibili: 
- Valore medio transazione
- Valore transazione totale
- Ricavi medi giornalieri
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

1. Nella sezione **Imposta periodo di tempo** definisci l'intervallo di tempo dei dati da utilizzare. Scegli se vuoi che la nuova misura copra l'intero set di dati selezionando **Sempre** o se vuoi che la misura si concentri su un **Periodo di tempo specifico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot che mostra la sezione del periodo di tempo durante la configurazione di una misura da un modello.":::

1. Nella sezione successiva, seleziona **Aggiungi dati** per scegliere gli impegni e mappare i dati corrispondenti dalla entità *Impegno unificato*.

    1. Passaggio 1 di 2: sotto **Tipo di impegno**, scegli il tipo di entità che desideri utilizzare. Per **Impegni**, seleziona le entità che desideri mappare.
    1. Passaggio 2 di 2: scegli l'attributo dall'entità *Impegno unificato* per il componente richiesto dalla formula. Ad esempio, per valore medio della transazione, è l'attributo che rappresenta il valore della transazione. Per **Timestamp impegno**, scegli l'attributo dall'entità Impegno unificato che rappresenta la data e l'ora dell'impegno.
   
1. Una volta completata la mappatura dei dati, puoi vedere lo stato come **Completato** e il nome degli impegni e degli attributi mappati.

1. Ora puoi selezionare **Esegui** per calcolare i risultati della misura. Per perfezionarlo in un secondo momento, seleziona **Salva bozza**.

# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

Questa funzione è disponibile solo per le misure create in ambienti con clienti individuali come target primario.

---
