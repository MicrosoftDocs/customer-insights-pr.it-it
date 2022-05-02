---
title: Aggiornamento incrementale per le origini dati basate su Power Query
description: Aggiorna dati nuovi e aggiornati per origini dati di grandi dimensioni basate su Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647189"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Aggiornamento incrementale per le origini dati basate su Power Query

Questo articolo illustra come configurare l'aggiornamento incrementale per le origini dati basate su Power Query.

L'aggiornamento incrementale per le origini dati offre i seguenti vantaggi:

- **Aggiornamenti più rapidi** - Vengono aggiornati solo i dati che sono stati modificati. Ad esempio, potresti aggiornare solo gli ultimi cinque giorni di uno set di dati storici.
- **Maggiore affidabilità** - Con aggiornamenti più piccoli, non è necessario mantenere le connessioni a sistemi di origine volatili per lungo tempo, riducendo il rischio di problemi di connessione.
- **Utilizzo ridotto delle risorse** - L'aggiornamento di un solo sottoinsieme dei dati totali comporta un uso più efficiente delle risorse di elaborazione e riduce l'impatto ambientale.

## <a name="configure-incremental-refresh"></a>Configurare l'aggiornamento incrementale

Customer Insights consente l'aggiornamento incrementale per le origini dati importate tramite Power Query che supportano l'inserimento incrementale. Ad esempio, i database SQL di Azure con campi di data e ora, che indicano quando è stato effettuato l'ultimo aggiornamento dei record di dati.

1. [Crea una nuova origine dati basata su Power Query](connect-power-query.md).

1. Immetti un **Nome** per l'origine dati.

1. Seleziona un'origine dati che supporta l'aggiornamento incrementale, come il [database SQL di Azure](/power-query/connectors/azuresqldatabase).

1. Seleziona le entità o le tabelle da inserire.

1. Completa i passaggi per la trasformazione e seleziona **Avanti**.

1. Nella finestra di dialogo **Configura aggiornamento incrementale**, seleziona **Configura** per aprire le **impostazioni di aggiornamento incrementali**. Se selezioni **Ignora**, l'origine dati aggiornerà l'intero set di dati.
   > [!TIP]
   > Puoi anche applicare l'aggiornamento incrementale in seguito modificando un origine dati esistente.

1. In **Impostazioni aggiornamento incrementale**, configurerai l'aggiornamento incrementale di tutte le entità selezionate durante la creazione dell'origine dati.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurare le entità in un origine dati per l'aggiornamento incrementale.":::

1. Seleziona un'entità e fornisci i seguenti dettagli:

   - **Seleziona la chiave primaria**: seleziona una chiave primaria per l'entità o la tabella.
   - **Definisci il campo "Ultimo aggiornamento"**: in questo campo verranno visualizzati solo gli attributi di tipo data o ora. Seleziona un attributo che indica quando i record sono stati aggiornati l'ultima volta. Verrà utilizzato per identificare i record che rientrano nell'intervallo di tempo dell'aggiornamento incrementale.
   - **Verifica la presenza di aggiornamenti ogni**: specifica l'intervallo di tempo dell'aggiornamento incrementale.

1. Seleziona **Salva** per completare la creazione dell'origine dati. L'aggiornamento iniziale dei dati sarà un aggiornamento completo. Successivamente, l'aggiornamento incrementale dei dati avviene come configurato nel passaggio precedente.


[!INCLUDE [footer-include](includes/footer-banner.md)]
