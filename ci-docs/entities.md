---
title: Entità in Customer Insights
description: Visualizza i dati nella pagina Entità.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610103"
---
# <a name="entities-in-customer-insights"></a>Entità in Customer Insights

Dopo [aver configurato le origini dati](data-sources.md), vai alla pagina **Entità** per valutare la qualità dei dati inseriti. Le entità sono considerate set di dati. Molteplici funzionalità di Dynamics 365 Customer Insights sono basate su queste entità. La loro stretta revisione può aiutare a convalidare l'output di tali funzionalità.

Mentre lavori in Customer Insights arricchendo i tuoi dati o creando segmenti, misure e attività, le entità create mediante tali azioni vengono visualizzate nella pagina **Entità**.

## <a name="view-a-list-of-entities"></a>Visualizzare un elenco di entità

Vai a **Dati** > **Entità** per visualizzare un elenco di entità. Le seguenti informazioni sono visualizzate per ogni entità.

- **Nome**: il nome dell'entità dei dati. Se viene visualizzato un simbolo di avviso accanto al nome di un'entità, significa che i dati per tale entità non sono stati caricati correttamente.
- **Origine**: tipo di origine dati che ha inglobato l'entità.
- **Aggiornato**: l'ultima volta che è stata aggiornata l'entità.
- **Stato**: dettagli dell'ultimo aggiornamento dell'entità.

## <a name="explore-a-specific-entitys-data"></a>Esplorare i dati di un'entità specifica

1. Vai in **Dati** > **Entità**.
1. Seleziona un'entità per aprire la pagina dei dettagli.  
1. Esplorare i diversi campi e record inclusi per quell'entità.

- La scheda **Attributi** è selezionata per impostazione predefinita e mostra i dettagli per l'entità selezionata, come nomi di campo, tipi di dati e tipi. La colonna **Tipo** mostra i tipi associati a Common Data Model che vengono identificati automaticamente dal sistema o [mappati manualmente](map-entities.md) dagli utenti. Questi tipi sono tipi semantici che possono differire dai tipi di dati degli attributi. Ad esempio, il campo *E-mail* sotto ha un tipo di dati *Stringa* ma il relativo tipo (semantico) Common Data Model potrebbe essere *E-mail*, *EmailAddress* o *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabella Campi.":::

   > [!NOTE]
   > Questa pagina mostra solo un campione dei dati della tua entità. Per visualizzare il set di dati completo, vai alla pagina **Origini dati** seleziona un'entità, seleziona **Modifica**, quindi visualizza i dati di questa entità con l'editor Power Query come spiegato in [Origini dati](data-sources.md).

   Per altre informazioni sui dati inseriti nell'entità, la colonna **Riepilogo** fornisce alcune caratteristiche importanti dei dati, ad esempio valori Null, valori mancanti, valori univoci, conteggi e distribuzioni, a seconda di ciò che è applicabile ai dati. Seleziona l'icona del grafico per visualizzare il riepilogo dei dati.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabella riepilogo dati.":::

- La scheda **Dati** mostra dettagli sui singoli record dell'entità. I dettagli elencati dipendono dal tipo di dati dell'entità.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Seleziona un'entità.":::

- La scheda **Report** (disponibile per alcune entità) ti consente di visualizzare i dati creando un report che include queste colonne:

  - **Nome rapporto**: nome del rapporto.
  - **Autore**: nome della persona che ha creato l'entità.
  - **Data di creazione**: data e ora di creazione dell'entità.
  - **Modificato da**: nome della persona che ha modificato l'entità.
  - **Modificato**: data e ora di modifica dell'entità.

[!INCLUDE [footer-include](includes/footer-banner.md)]
