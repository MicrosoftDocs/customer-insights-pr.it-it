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
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170594"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Segmenti suggeriti in base all'attività (anteprima)

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
Se fornisci assistenza sanitaria pubblica e il tuo obiettivo è ridurre al minimo le spese dei singoli pazienti, potresti provare a ridurre le visite ricorrenti fornendo la migliore assistenza possibile nel minor numero di visite possibile. In questo caso, l'obiettivo è mantenere bassa la frequenza delle visite e ridurre al minimo i costi ricorrenti per i pazienti. Oppure è possibile identificare segmenti di pazienti che hanno appuntamenti frequenti e costi ricorrenti elevati e analizzare questi casi per migliorare il trattamento dell'individuo.

## <a name="required-data"></a>Dati obbligatori

I suggerimenti vengono generati in base ai dati di input selezionati.

- Profili dei clienti: tutti i clienti o membri di un segmento specifico.

- Periodo di tempo: il mese scorso, l'anno scorso o qualsiasi intervallo di tempo personalizzato.

- Tipo di impegno: acquisti, transazioni al dettaglio, transazioni online, casi di assistenza clienti, abbonamenti e così via.  

- Entità in Customer Insights che contiene i dati dell'attività: l'entità UnifiedActivity o l'entità per un impegno specifico.

- Dimensioni da includere: recency, frequenza o dimensione monetaria, a seconda dei requisiti aziendali.

## <a name="generate-suggested-segments"></a>Generare segmenti suggeriti

1. Vai a **Segmenti** e seleziona la scheda **Suggerimenti (anteprima)**.

1. Seleziona **Trova nuovi suggerimenti** e scegli **Visualizza o prevedi il comportamento del cliente**. Selezionare **Avvia**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primo passaggio della configurazione guidata per un segmento suggerito in base all'impegno.":::

1. Fornisci i dati di input richiesti e seleziona **Avanti**.

   - Scegli i clienti: includi tutti i clienti o un segmento specifico.
   - Scegli impegno: seleziona il tipo di impegno e le entità che descrivono l'impegno.
   - Preferenze: imposta il periodo di tempo da considerare, i fattori per i suggerimenti e mappa gli attributi.

1. Rivedi il tuo input e seleziona **Esegui** per eseguire il modello e generare suggerimenti.

A seconda del numero di profili dei clienti e delle attività selezionate, il completamento può richiedere alcuni minuti.

Dopo aver generato i suggerimenti, puoi filtrarli in base alla dimensione o al valore che ti interessa di più.

## <a name="manage-suggested-segments"></a>Gestire segmenti suggeriti

Vai a **Segmenti** e seleziona la scheda **Suggerimenti (anteprima)**. Nella sezione **Suggerimenti di segmenti basati su attività**, seleziona un segmento suggerito per visualizzare le azioni disponibili.

- **Vedi suggerimento** per visualizzare i dettagli di quel segmento come estensione di ogni dimensione rispetto al gruppo di destinazione. Evidenzia inoltre il numero di potenziali membri del segmento e la corrispondente percentuale del totale dei clienti.
- **Crea segmento** per salvare il suggerimento come segmento. È visualizzato nella scheda **Tutti i segmenti** e può essere [aggiornato o eliminato](segments.md). Non puoi modificare i dettagli del segmento. Tuttavia, è possibile modificare i criteri di input per i suggerimenti e generare suggerimenti diversi.
- **Modifica suggerimenti** per modificare gli attributi configurati che sostituiranno i suggerimenti correnti.
- **Aggiorna suggerimenti** per aggiornare i suggerimenti mantenendo gli attributi configurati.

[!INCLUDE [footer-include](includes/footer-banner.md)]
