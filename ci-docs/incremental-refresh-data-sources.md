---
title: Aggiornamento incrementale per le origini dati di Power Query e Azure Data Lake
description: Aggiorna dati nuovi e aggiornati per origini dati di grandi dimensioni in base alle origini dati di Power Query o Azure Data Lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207142"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Aggiornamento incrementale per le origini dati di Power Query e Azure Data Lake

L'aggiornamento incrementale di origini dati basato su Power Query o Azure Data Lake fornisce i seguenti vantaggi:

- **Aggiornamenti più rapidi** - Vengono aggiornati solo i dati che sono stati modificati. Ad esempio, potresti aggiornare solo gli ultimi cinque giorni di uno set di dati storici.
- **Maggiore affidabilità** - Con aggiornamenti più piccoli, non è necessario mantenere le connessioni a sistemi di origine volatili per lungo tempo, riducendo il rischio di problemi di connessione.
- **Utilizzo ridotto delle risorse** - L'aggiornamento di un solo sottoinsieme dei dati totali comporta un uso più efficiente delle risorse di elaborazione e riduce l'impatto ambientale.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Configurare l'aggiornamento incrementale per le origini dati in base a Power Query

Customer Insights consente l'aggiornamento incrementale per le origini dati importate tramite Power Query che supportano l'inserimento incrementale. Ad esempio, i database SQL di Azure con campi di data e ora, che indicano quando è stato effettuato l'ultimo aggiornamento dei record di dati.

1. [Crea una nuova origine dati basata su Power Query](connect-power-query.md).

1. Seleziona un'origine dati che supporta l'aggiornamento incrementale, come il [database SQL di Azure](/power-query/connectors/azuresqldatabase).

1. Seleziona le entità o le tabelle da inserire.

1. Completa i passaggi per la trasformazione e seleziona **Avanti**.

1. Nella finestra di dialogo **Configura aggiornamento incrementale**, seleziona **Configura** per aprire le **impostazioni di aggiornamento incrementali**. Se selezioni **Ignora**, l'origine dati aggiornerà l'intero set di dati.
   > [!TIP]
   > Puoi anche applicare l'aggiornamento incrementale in seguito modificando un origine dati esistente.

1. In **Impostazioni aggiornamento incrementale**, configurerai l'aggiornamento incrementale di tutte le entità selezionate durante la creazione dell'origine dati.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurare le impostazioni di aggiornamento incrementale.":::

1. Seleziona un'entità e fornisci i seguenti dettagli:

   - **Seleziona la chiave primaria**: seleziona una chiave primaria per l'entità o la tabella.
   - **Definisci il campo "Ultimo aggiornamento"**: in questo campo verranno visualizzati solo gli attributi di tipo data o ora. Seleziona un attributo che indica quando i record sono stati aggiornati l'ultima volta. Verrà utilizzato per identificare i record che rientrano nell'intervallo di tempo dell'aggiornamento incrementale.
   - **Verifica la presenza di aggiornamenti ogni**: specifica l'intervallo di tempo dell'aggiornamento incrementale.

1. Seleziona **Salva** per completare la creazione dell'origine dati. L'aggiornamento iniziale dei dati sarà un aggiornamento completo. Successivamente, l'aggiornamento incrementale dei dati avviene come configurato nel passaggio precedente.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Configurare l'aggiornamento incrementale per le origini dati di Azure Data Lake

Customer Insights consente l'aggiornamento incrementale per le origini dati collegate a Azure Data Lake Storage. Per usare l'inserimento e l'aggiornamento incrementali per un'entità, configura tale entità quando aggiungi l'origine dati Azure Data Lake o versioni successive durante la modifica dell'origine dati. La cartella dei dati entità deve contenere le seguenti cartelle:

- **FullData**: cartella con file di dati contenenti record iniziali
- **IncrementalData**: cartella con le cartelle della gerarchia di data/ora in formato **aaaa/mm/gg/hh** contenente gli aggiornamenti incrementali. **Hhh** rappresenta l'ora UTC degli aggiornamenti e contiene le cartelle **Upserts** e **Deletes**. **Upserts** contiene file di dati con aggiornamenti di record esistenti o nuovi record. **Deletes** contiene file di dati con i record da rimuovere.

1. Quando aggiungi o modifichi un'origine dati, vai al riquadro **Attributi** per l'entità.

1. Rivedi gli attributi. Assicurati che un attributo della data di creazione o dell'ultimo aggiornamento sia impostato con *dateTime* per **Formato dati** e *Calendari.Date* per **Tipo semantico**. Modifica l'attributo se necessario e seleziona **Fatto**.

1. Nel riquadro **Seleziona entità** modifica l'entità. La casella di controllo **Inserimento incrementale** è selezionata.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Configurare le entità in un origine dati per l'aggiornamento incrementale.":::

   1. Passa alla cartella radice che contiene file csv o parquet per i dati completi, upsert dei dati incrementali ed eliminazioni di dati incrementali.
   1. Immetti l'estensione per i dati completi e per entrambi i file (\.csv o \.parquet) incrementali.
   1. Per i file .csv, seleziona il delimitatore di colonna e, se vuoi, la prima riga del file come intestazione di colonna.
   1. Seleziona **Salva**.

1. In **Ultimo aggiornamento** seleziona l'attributo timestamp.

1. Se **Chiave primaria** non è selezionato, seleziona la chiave primaria. La chiave primaria è un attributo univoco per l'entità. Affinché un attributo sia una chiave primaria valida, non deve includere valori duplicati, valori mancanti o valori null. Gli attributi del tipo di dati String, Integer e GUID sono supportati come chiavi primarie.

1. Seleziona **Chiudi** per salvare e chiudere il riquadro.

1. Continua con l'aggiunta o la modifica dell'origine dati.

[!INCLUDE [footer-include](includes/footer-banner.md)]
