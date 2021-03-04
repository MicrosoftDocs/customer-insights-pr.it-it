---
title: Entità e set di dati
description: Visualizza i dati nella pagina Entità.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269381"
---
# <a name="entities-in-audience-insights"></a>Entità in Audience Insights

Dopo [aver configurato le origini dati](data-sources.md), vai alla pagina **Entità** per valutare la qualità dei dati inseriti. Le entità sono considerate set di dati. Molteplici funzionalità di Dynamics 365 Customer Insights sono basate su queste entità. La loro stretta revisione può aiutare a convalidare l'output di tali funzionalità.

La pagina **Entità** elenca le entità e include diverse colonne:

- **Nome**: il nome dell'entità di dati. Se viene visualizzato un simbolo di avviso accanto al nome di un'entità, significa che i dati per tale entità non sono stati caricati correttamente.
- **Origine**: il tipo di origine dati che hanno inserito l'entità
- **Autore creazione**: nome della persona che ha creato l'entità
- **Data di creazione**: data e ora di creazione dell'entità
- **Aggiornato da**: nome della persona che ha aggiornato l'entità
- **Ultimo aggiornamento**: data e ora dell'ultimo aggiornamento dell'entità
- **Ultimo aggiornamento**: data e ora dell'ultimo aggiornamento dati

## <a name="exploring-a-specific-entitys-data"></a>Esplorazione dei dati di un'entità specifica

Seleziona un'entità per esplorare i diversi campi e record inclusi all'interno dell'entità.

> [!div class="mx-imgBorder"]
> ![Seleziona un'entità](media/data-manager-entities-data.png "Seleziona un'entità")

- La scheda **Dati** è selezionata per impostazione predefinita e mostra una tabella che elenca i dettagli sui singoli record dell'entità.

> [!div class="mx-imgBorder"]
> ![Tabella Campi](media/data-manager-entities-fields.PNG "Tabella Campi")

- La scheda **Campi** mostra una tabella per esaminare i dettagli per l'entità selezionata, ad esempio i nomi dei campi, i tipi di dati e i tipi. La colonna **Tipo** mostra i tipi associati a Common Data Model che vengono identificati automaticamente dal sistema o [mappati manualmente](map-entities.md) dagli utenti. Si tratta di tipi semantici che possono differire dai tipi di dati degli attributi; ad esempio il campo *E-mail* sotto ha come tipo di dati *Testo* ma il relativo tipo Common Data Model (semantico) potrebbe essere *Emai* o *EmailAddress*.

> [!NOTE]
> Entrambe le tabelle mostrano solo un esempio dei dati dell'entità. Per visualizzare il set di dati completo, vai alla pagina **Origini dati** seleziona un'entità, seleziona **Modifica**, quindi visualizza i dati di questa entità con l'editor Power Query come spiegato in [Origini dati](data-sources.md).

Per altre informazioni sui dati inseriti nell'entità, la colonna **Riepilogo** fornisce alcune caratteristiche importanti dei dati, ad esempio valori Null, valori mancanti, valori univoci, conteggi e distribuzioni, a seconda di come sono applicabili ai dati.

Seleziona l'icona del grafico per visualizzare il riepilogo dei dati.

> [!div class="mx-imgBorder"]
> ![Simbolo di riepilogo](media/data-manager-entities-summary.png "Tabella riepilogo dati")

### <a name="next-step"></a>Passaggio successivo

Vedi l'argomento [Unificare](data-unification.md) per informazioni sulle operazioni di *mapping*, *corrispondenza* e *Unione* sui dati inseriti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]