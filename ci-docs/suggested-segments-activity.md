---
title: Segmenti suggeriti in base all'attività (anteprima)
description: Lascia che l'apprendimento automatico ti aiuti a trovare segmenti nuovi e interessanti in base all'impegno dei clienti.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e98aea3b3f3a2c4788346deab1b7ad7d1167110d
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054345"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segmenti suggeriti in base ai dati dell'impegno (anteprima)

Scopri i segmenti interessanti dei tuoi clienti in base ai dati dell'impegno dei clienti inseriti in Customer Insights. Esempi di dati dell'impegno sono transazioni, durata della chiamata di assistenza, acquisti o resi. Per suggerire i segmenti, i dati dell'impegno vengono analizzati per recency, frequenza e valore monetario (o durata). In alternativa, puoi generare i [segmenti suggeriti per migliorare una misura o capire meglio cosa influenza un attributo](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Scheda Segmenti suggeriti che mostra i suggerimenti per i segmenti basati sull'impegno e sull'attributo.":::

## <a name="categorize-customers-by-activity"></a>Classificare i clienti per impegno

Con i [dati dell'impegno](activities.md) disponibili in Customer Insights, possiamo generare suggerimenti che rappresentano i gruppi di clienti:

- i clienti più attivi 
- i clienti che hanno effettuato il maggior numero di acquisti 
- i clienti che hanno generato il maggior numero di ricavi 
- i clienti che non sono stati attivi di recente 
- i clienti che interagiscono frequentemente con la tua azienda  

Se hai un'attività di vendita al dettaglio, potresti scoprire quali clienti generano il maggior numero di ricavi e premiarli con un coupon. Oppure puoi identificare i clienti occasionali e offrire loro di partecipare a un programma a premi in modo che visitino la tua attività più spesso.
Se operi nel settore sanitario che fornisce assistenza sanitaria pubblica e il tuo obiettivo è ridurre al minimo le spese per i singoli pazienti. Un modo per farlo potrebbe essere quello di ridurre le visite ricorrenti fornendo la migliore assistenza possibile nel minor numero di visite possibile. In questo caso, l'obiettivo è mantenere bassa la frequenza delle visite e ridurre al minimo i costi ricorrenti per i pazienti. Oppure è possibile identificare segmenti di pazienti che hanno appuntamenti frequenti e costi ricorrenti elevati e analizzare questi casi per migliorare il trattamento dell'individuo. 

## <a name="required-data"></a>Dati obbligatori

I suggerimenti vengono generati in base ai dati di input selezionati. 

- Profili dei clienti: tutti i clienti o membri di un segmento specifico. 

- Periodo di tempo: il mese scorso, l'anno scorso o qualsiasi intervallo di tempo personalizzato.

- Tipo di impegno: acquisti, transazioni al dettaglio, transazioni online, casi di assistenza clienti, abbonamenti e così via.  

- Entità in Customer Insights che contiene i dati dell'attività: l'entità UnifiedActivity o l'entità per un impegno specifico. 

- Dimensioni da includere: recency, frequenza o dimensione monetaria, a seconda dei requisiti aziendali.

## <a name="generate-suggested-segments"></a>Generare segmenti suggeriti

1. Vai a **Segmenti**.

1. Seleziona la scheda **Suggerimenti (anteprima)**.

1. Seleziona **Trova nuovi suggerimenti** e scegli **Visualizza o prevedi il comportamento del cliente**. Seleziona **Avvia** per eseguire l'esperienza guidata.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primo passaggio della configurazione guidata per un segmento suggerito in base all'impegno.":::

1. Fornisci i dati di input richiesti e seleziona **Avanti** per procedere.

   - Scegli i clienti: includi tutti i clienti o un segmento specifico.
   - Scegli impegno: seleziona il tipo di impegno e le entità che descrivono l'impegno.
   - Preferenze: imposta il periodo di tempo da considerare, i fattori per i suggerimenti e mappa gli attributi.

1. Rivedi il tuo input e seleziona **Esegui** per eseguire il modello e generare suggerimenti.

1. A seconda del numero di profili dei clienti e delle attività selezionate, il completamento può richiedere alcuni minuti. 

Dopo aver generato i suggerimenti, puoi filtrarli in base alla dimensione o al valore che ti interessa di più. 

## <a name="view-details-of-a-suggested-segment"></a>Visualizzare i dettagli di un segmento suggerito

Una volta generati i suggerimenti, li troverai elencati in **Segmenti** > **Suggerimenti (anteprima)** nella sezione **Suggerimenti basati su impegno**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Riquadro laterale espanso che mostra i dati dettagliati di un segmento suggerito.":::

Seleziona **Vedi suggerimento** su un segmento suggerito per visualizzare i dettagli di quel segmento. Il riquadro laterale fornisce dettagli come l'estensione di ciascuna dimensione rispetto al gruppo di destinazione. Evidenzia inoltre il numero di potenziali membri del segmento e la corrispondente percentuale del totale dei clienti. Se desideri mantenere il suggerimento come segmento, seleziona **Crea segmento**.    

## <a name="save-a-suggestion-as-a-segment"></a>Salvare un suggerimento come segmento

1. Vai a **Segmenti** > **Suggerimenti (anteprima)**.

1. Seleziona il segmento da salvare 

1. Nel riquadro laterale seleziona **Crea segmento**. 

1. Dopo aver salvato il segmento, verrà visualizzato nell'elenco dei segmenti nella scheda **Tutti i segmenti**. Ora può essere [aggiornato o eliminato come qualsiasi altro segmento](segments.md). Non puoi modificare i dettagli del segmento. Tuttavia, è possibile modificare i criteri di input per i suggerimenti e generare suggerimenti diversi.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Aggiornare o modificare una serie di suggerimenti

1. Vai a **Segmenti** > **Suggerimenti (anteprima)** e cerca il segmento nella sezione **Suggerimenti basati su impegno**.

1. Seleziona **Aggiorna suggerimenti** per aggiornare i suggerimenti mantenendo gli attributi configurati. Oppure seleziona **Modifica suggerimenti** per modificare gli attributi configurati. Il sistema eseguirà nuovamente il processo, genererà suggerimenti di segmento in base ai dati più recenti e sostituirà i suggerimenti correnti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
