---
title: Entità in Customer Insights
description: Visualizza i dati nella pagina Entità.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183565"
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

## <a name="entity-specific-information"></a>Informazioni specifiche dell'entità

La sezione seguente fornisce informazioni su alcune entità create dal sistema.

### <a name="corrupted-data-sources"></a>Origini dati danneggiate

I campi di un'origine dati inserita possono contenere dati danneggiati. I record con campi danneggiati vengono esposti nelle entità create dal sistema. La conoscenza dei record danneggiati consente di identificare quali dati rivedere e aggiornare nel sistema di origine. Dopo il successivo aggiornamento dell'origine dati, i record corretti vengono inseriti in Customer Insights e passati ai processi downstream. 

Ad esempio, una colonna "compleanno" ha il tipo di dati impostato su "data". Il record del cliente ha la data di nascita inserita in formato "01/01/19777". Il sistema contrassegnerà questo record come danneggiato. Qualcuno può ora modificare la data di nascita nel sistema di origine in "1977". Dopo un aggiornamento automatico delle origini dati, il campo ora ha un formato valido e il record verrà rimosso dall'entità danneggiata.

Vai a **Dati** > **Entità** e cerca le entità corrotte nella sezione **Sistema**. Schema di denominazione delle entità danneggiate: "DataSourceName_EntityName_corrupt". Seleziona un'entità danneggiata per identificare i campi danneggiati e il motivo a livello di singolo record.

   :::image type="content" source="media/corruption-reason.png" alt-text="Motivo di danneggiamento.":::

Customer Insights elabora ancora i record danneggiati. Tuttavia, potrebbero causare problemi quando si lavora con i dati unificati.

I seguenti controlli vengono eseguiti sui dati importati per esporre i record danneggiati:

- Il valore di un campo non corrisponde al tipo di dati della sua colonna.
- I campi contengono caratteri che fanno sì che le colonne non corrispondano allo schema previsto. Ad esempio: virgolette formattate in modo errato, virgolette senza caratteri di escape o caratteri di nuova riga.
- Se sono presenti colonne datetime/date/datetimeoffset, il loro formato deve essere specificato nel modello se non segue il formato ISO standard.

[!INCLUDE [footer-include](includes/footer-banner.md)]