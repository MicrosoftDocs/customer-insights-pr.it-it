---
title: Trovare clienti simili con l'intelligenza artificiale (anteprima) (video)
description: Trova segmenti di clienti simili con l'intelligenza artificiale.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170732"
---
# <a name="find-similar-customers-with-ai-preview"></a>Trovare clienti simili con IA (anteprima)

Trova clienti simili nella tua base clienti tramite l'intelligenza artificiale. Devi avere almeno un segmento creato per utilizzare questa funzionalità. L'espansione dei criteri di un segmento esistente consente di trovare clienti simili a quel segmento.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Trova clienti simili* utilizza strumenti automatizzati per valutare i dati ed elaborare previsioni basate su tali dati. Pertanto tale funzionalità può essere utilizzata come metodo di profilatura, come definito dal Regolamento generale sulla protezione dei dati ("GDPR"). L'uso da parte del cliente di questa funzionalità per elaborare i dati può essere soggetto al GDPR o ad altre leggi o normative. Devi assicurarti che il tuo utilizzo di Dynamics 365 Customer Insights, comprese le previsioni, sia conforme a tutte le leggi e le norme applicabili, comprese le leggi relative alla privacy, ai dati personali, ai dati biometrici, alla protezione dei dati e alla riservatezza delle comunicazioni.

## <a name="find-similar-customers"></a>Trova clienti simili

1. Vai a **Segmenti** e seleziona il segmento su cui vuoi basare il tuo nuovo segmento. Questo è il tuo *segmento di origine*.

1. Seleziona **Trova clienti simili**.

1. Esamina il nome suggerito per il tuo nuovo segmento e modificalo se necessario.

1. Facoltativamente, aggiungi [tag](work-with-tags-columns.md#manage-tags) al nuovo segmento.

1. Rivedi i campi che definiscono il tuo nuovo segmento. Questi campi definiscono la base su cui il sistema proverà a trovare clienti simili al tuo segmento di origine. Il sistema seleziona i campi consigliati per impostazione predefinita. Aggiungi altri campi se necessario.
  I campi che possono ridurre significativamente le prestazioni del modello vengono automaticamente esclusi:
  
   - Campi con i seguenti tipi di dati: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Campi con una cardinalità (il numero di elementi in un campo) inferiore a 2 o superiore a 30

1. Scegli se nel tuo nuovo segmento vuoi includere **Tutti i clienti** eccetto il segmento di origine o solo i clienti di un **segmento differente**.

1. Per impostazione predefinita, il sistema suggerisce di includere solo il 20% della dimensione destinatari di destinazione nell'output. Modifica questa soglia secondo necessità. Aumentando la soglia si ridurrà la precisione.

1. Includi clienti nel segmento di origine selezionando la casella di controllo **Includi membri del segmento di origine oltre ai clienti con attributi simili**.

1. Seleziona **Esegui** nella parte inferiore della pagina per avviare un'[attività di classificazione binaria](#about-similarity-scores) (un metodo di apprendimento automatico) che analizza il set di dati.

## <a name="view-the-similar-segment"></a>Visualizzare il segmento simile

Dopo aver elaborato il segmento simile, troverai il nuovo segmento elencato nella pagina **Segmenti** con il tipo **Espansione**.

Seleziona **Visualizza** per vedere la distribuzione dei risultati nei [punteggi di somiglianza](#about-similarity-scores) e valori dei punteggi di somiglianza sotto **Anteprima membri del segmento**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segmento di clienti simili.":::

## <a name="manage-a-similar-segment"></a>Gestire un segmento simile

[Utilizza e gestisci un segmento simile](segments.md#manage-existing-segments) come fai con altri segmenti. Ad esempio, esporta il segmento o crea una misura.

Modifica, aggiorna, rinomina, scarica ed elimina un segmento simile. La modifica di un segmento simile rielabora i tuoi dati. Il segmento creato in precedenza viene aggiornato con i dati aggiornati.

## <a name="about-similarity-scores"></a>Informazioni sui punteggi di somiglianza

La classificazione binaria del modello apprendimento automatico assegna un punteggio ai clienti del segmento simile. Il punteggio si basa sulla somiglianza con i clienti nel segmento di origine.

- I punteggi di somiglianza inferiori a 0,55 sono i clienti classificati dal sistema come *non simili* ai clienti nel segmento di origine
- I punteggi di somiglianza tra 0,55 e 0,7 sono classificati come *in qualche modo simili*
- I punteggi di somiglianza tra 0,7 e 0,85 sono classificati come *simili*
- I punteggi di somiglianza tra 0,85 e 1 sono i clienti classificati dal sistema come *molto simili*

I clienti con punteggi di somiglianza inferiori a 0,4 non sono inclusi nell'output del modello. Il sistema non li considera abbastanza simili al segmento di origine.

[!INCLUDE [footer-include](includes/footer-banner.md)]
