---
title: Trovare clienti simili con l'intelligenza artificiale (video)
description: Trova segmenti di clienti simili con l'intelligenza artificiale.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: de337ae989558c81fff25a6ff7cca01890ed306b
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934845"
---
# <a name="similar-customers-preview"></a>Clienti simili (anteprima)

Questa funzione ti consente di trovare clienti simili nella tua base di clienti usando l'intelligenza artificiale. Devi avere almeno un segmento creato per utilizzare questa funzione. L'espansione dei criteri di un segmento esistente consente di trovare clienti simili a quel segmento.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Trova clienti simili* utilizza mezzi automatizzati per valutare i dati e fare previsioni basate sui dati e quindi può essere utilizzato come metodo di profiling, in quanto il termine è definito dal Regolamento generale sulla protezione dei dati ("GDPR"). L'uso da parte del cliente di questa funzionalità per elaborare i dati può essere soggetto al GDPR o ad altre leggi o normative. Devi assicurarti che il tuo utilizzo di Dynamics 365 Customer Insights, comprese le previsioni, sia conforme a tutte le leggi e le norme applicabili, comprese le leggi relative alla privacy, ai dati personali, ai dati biometrici, alla protezione dei dati e alla riservatezza delle comunicazioni.

## <a name="finding-similar-customers"></a>Trovare clienti simili

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Segmenti** e seleziona il segmento su cui desideri basare il nuovo segmento. Questo è il tuo *segmento di origine*.

1. Nella barra delle azioni, seleziona **Trova clienti simili**.

1. Esamina il nome suggerito per il tuo nuovo segmento e modificalo se necessario.

1. Rivedi i campi che definiscono il tuo nuovo segmento. Questi campi definiscono la base su cui il sistema proverà a trovare clienti simili al tuo segmento di origine. Il sistema selezionerà i campi consigliati per impostazione predefinita.
  I campi che possono ridurre significativamente le prestazioni del modello vengono automaticamente esclusi:
  
   - Campi con i seguenti tipi di dati: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Campi con una cardinalità (il numero di elementi in un campo) inferiore a 2 o superiore a 30

1. Scegli se vuoi includere **Tutti i clienti** o solo i clienti di un **Segmento specifico esistente** nel tuo nuovo segmento.

1. Escludi i clienti nel segmento di origine selezionando la casella di controllo **Escludi tutti nel segmento di origine**.

1. Per impostazione predefinita, il sistema suggerisce di includere solo il 20% della dimensione destinatari di destinazione nell'output. Modifica questa soglia secondo necessità. Aumentando la soglia si ridurrà la precisione.

1. Seleziona **Esegui** nella parte inferiore della pagina per avviare un'attività di classificazione binaria (un metodo di apprendimento automatico) che analizza il set di dati.

## <a name="view-the-similar-segment"></a>Visualizzare il segmento simile

Dopo aver elaborato il segmento simile, troverai il nuovo segmento elencato nella pagina **Segmenti**.

> [!div class="mx-imgBorder"]
> ![Segmento di clienti simili.](media/expanded-segment.png "Segmento di clienti simili")

Seleziona **Visualizza** nella barra delle azioni per aprire i dettagli del segmento. Questa visualizzazione contiene informazioni sulla distribuzione dei risultati attraverso [punteggi di somiglianza](#about-similarity-scores). Troverai anche i valori del punteggio di somiglianza in **Anteprima dei membri del segmento**.

## <a name="use-the-output-of-a-similar-segment"></a>Usare l'output di un segmento simile

Puoi [utilizzare l'output di un segmento simile](segments.md) come fai con altri segmenti. Ad esempio, esporta il segmento o crea una misura.

## <a name="refresh-and-edit-a-similar-segment"></a>Aggiornare e modificare un segmento simile

Per aggiornare un segmento simile, selezionalo nella pagina **Segmenti** e seleziona **Aggiorna** nella barra delle azioni.

La modifica di un segmento simile rielaborerà i tuoi dati. Il segmento creato in precedenza viene aggiornato con i dati aggiornati.    
Per modificare un segmento simile, selezionalo nella pagina **Segmenti** e seleziona **Modifica** nella barra delle azioni. Applica le modifiche e seleziona **Esegui** per iniziare l'elaborazione.

## <a name="delete-a-similar-segment"></a>Eliminare un segmento simile

Seleziona il segmento nella pagina **Segmenti** e seleziona **Elimina** nella barra delle azioni. Quindi, conferma l'eliminazione.

## <a name="about-similarity-scores"></a>Informazioni sui punteggi di somiglianza

La classificazione binaria del modello apprendimento automatico assegna un punteggio ai clienti del segmento simile. Il punteggio si basa sulla somiglianza con i clienti nel segmento di origine.

- I punteggi di somiglianza inferiori a 0,55 sono i clienti classificati dal sistema come *non simili* ai clienti nel segmento di origine
- I punteggi di somiglianza tra 0,55 e 0,7 sono classificati come *in qualche modo simili*
- I punteggi di somiglianza tra 0,7 e 0,85 sono classificati come *simili*
- I punteggi di somiglianza tra 0,85 e 1 sono i clienti classificati dal sistema come *molto simili*

I clienti con punteggi di somiglianza inferiori a 0,4 non sono inclusi nell'output del modello. Il sistema non li considera abbastanza simili al segmento di origine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]