---
title: Segmenti suggeriti in base alle misure (anteprima)
description: Lascia che l'apprendimento automatico ti aiuti a trovare segmenti nuovi e interessanti in base agli attributi dei clienti.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170962"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Segmenti suggeriti in base alle misure (anteprima)

Scopri segmenti interessanti dei tuoi clienti con l'aiuto di un modello di intelligenza artificiale. Questa funzionalità potenziata da apprendimento automatico suggerisce i segmenti in base alle misure o agli attributi dei clienti. Può aiutarti a migliorare i tuoi indicatori KIP o a comprendere meglio l'impatto degli attributi nel contesto di altri attributi.

> [!NOTE]
> La funzionalità dei segmenti suggeriti utilizza strumenti automatizzati per valutare i dati ed elaborare previsioni basate su tali dati. Pertanto può essere utilizzata come metodo di profilatura, come definito dal Regolamento generale sulla protezione dei dati ("GDPR"). L'utilizzo di questa funzionalità per elaborare i dati può essere soggetto al GDPR o ad altre leggi o regolamenti. Devi assicurarti che il tuo utilizzo di Dynamics 365 Customer Insights, compresa questa funzionalità, sia conforme a tutte le leggi e le norme applicabili, comprese le leggi relative alla privacy, ai dati personali, ai dati biometrici, alla protezione dei dati e alla riservatezza delle comunicazioni.

:::image type="content" source="media/suggested-segments.png" alt-text="Pagina dei segmenti suggeriti che mostra i dettagli di un suggerimento in un riquadro laterale.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmenti suggeriti per migliorare i tuoi KPI

Se usi [misure create](measures.md) per tenere traccia dei tuoi indicatori KPI, crea segmenti per visualizzare l'impatto sui KPI. Puoi utilizzare queste informazioni per eseguire una campagna altamente mirata.

Ad esempio, si tiene traccia di una misura chiamata *TotalSpendPerCustomer*. Come azienda, ti piacerebbe vedere crescere questo numero. La scelta di una misura come attributo principale consente di selezionare gli attributi di cui intendi valutare l'impatto. Diciamo *livello di appartenenza*, *periodo di appartenenza* e *occupazione*. Customer Insights può quindi suggerire un segmento che indica qual è il maggiore impatto di quella misura. Ad esempio, i *Commercialisti* che sono membri *Gold* e che sono stati con la tua azienda per *almeno cinque anni* sono i principali influencer di *TotalSpendPerCustomer*. Otterrai una dimensione del segmento stimata per ogni suggerimento. È possibile utilizzare queste informazioni per creare campagne per destinatari mirati.

## <a name="understand-what-influences-a-customer-attribute"></a>Comprendere cosa influisce su un attributo dei clienti

È possibile scegliere un attributo dei clienti invece di una misura come attributo principale. In base alla scelta degli attributi di influenza, il modello di intelligenza artificiale crea una serie di suggerimenti che mostrano come gli attributi selezionati influiscono sull'attributo principale.

Ad esempio, scegli *Membro programma fedeltà (Sì/No)* come attributo principale. *Mandato*, *Occupazione* e *Numero di ticket di supporto* sono impostati come altri attributi di influenza. Il modello di intelligenza artificiale potrebbe suggerire segmenti che indicano che per lo più professionisti IT con un mandato superiore a due anni sono membri del programma fedeltà. Un altro suggerimento potrebbe evidenziare che i contabili con un mandato superiore a un anno e meno di tre ticket di supporto sono membri del programma fedeltà.

## <a name="artificial-intelligence-usage"></a>Uso dell'intelligenza artificiale

Utilizzando l'attributo principale e gli attributi di influenza, un algoritmo dell'albero decisionale suggerisce segmenti interessanti. I suggerimenti si basano su regole o schemi che sono stati raccolti dall'algoritmo di intelligenza artificiale. Solo i segmenti che differiscono in modo significativo dalla popolazione media vengono visualizzati come suggerimenti. Il confronto con la popolazione media si basa sulla misura o sull'attributo principale selezionato.

### <a name="responsible-ai"></a>IA responsabile

Con i segmenti suggeriti, selezioni gli attributi per creare nuovi segmenti ed elaborare i dati selezionati. Quando scegli attributi, tra cui attributi sensibili come razza, orientamento sessuale o sesso, devi assicurarti di poter e dover elaborare tali dati. Sei responsabile del rispetto delle leggi applicabili alla tua organizzazione e dei principi e delle politiche sulla privacy della tua organizzazione.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Risultati diversi per attributi principali con valori categorici e numerici

I suggerimenti di segmento sono diversi se scegli un attributo numerico o un attributo categorico come attributo principale. I valori in un attributo categorico contengono due o più categorie o tipi. Un attributo numerico contiene dati quantitativi e ha un senso di misurazione ad esso associato.

Con un attributo numerico come *reddito annuo* o *periodo di appartenenza* come attributo principale, il sistema suggerisce segmenti che hanno un valore medio più alto o più basso dell'attributo numerico rispetto a tutti i clienti.

Un attributo categorico come *soddisfazione del cliente* come attributo principale determina segmenti suggeriti che hanno una percentuale maggiore o minore di clienti appartenenti a una particolare categoria rispetto alla percentuale di tutti i clienti appartenenti a quella stessa categoria. Ad esempio, *soddisfazione del cliente* viene scelto come attributo principale e si compone di tre categorie (*Bassa*, *Media* e *Alta*). Per ogni categoria, verranno suggeriti i segmenti che hanno una percentuale maggiore o minore di clienti appartenenti a tale categoria rispetto alla percentuale di tutti i clienti della stessa categoria. Se il 22% di tutti i clienti ha un livello di soddisfazione *Alto*, solo i segmenti con percentuale maggiore o minore di clienti con un livello di soddisfazione *Alto* rispetto al 22% saranno suggeriti per tale categoria. Allo stesso modo, i segmenti verranno suggeriti per ciascuna delle altre categorie (*Bassa* e *Media*) se sono statisticamente significativi.

> [!NOTE]
> Al momento, supportiamo solo attributi categorici principali che hanno fino a 10 categorie. Se desideri visualizzare i suggerimenti di segmenti basati su un attributo principale con più di 10 categorie, ti consigliamo di raggruppare alcune delle categorie per ridurre il numero di categorie a 10 o meno. Questa limitazione si applica solo agli attributi principali. Per gli attributi categorici di influenza, attualmente supportiamo un massimo di 100 categorie.

## <a name="generate-suggested-segments"></a>Generare segmenti suggeriti

1. Vai a **Segmenti** e seleziona la scheda **Suggerimenti (anteprima)**.

1. Seleziona **Trova nuovi suggerimenti** e scegli **Migliora una misura/metrica**. Selezionare **Avvia**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Scegliere di migliorare una misura per i segmenti suggeriti.":::

1. Scegli una misura o un attributo dei clienti come attributo principale e seleziona **Avanti**.

1. Seleziona gli attributi di influenza e seleziona **Esegui**.

   > [!TIP]
   > La selezione di più attributi di influenza migliora le possibilità di valutare come influiscono sull'attributo principale. Non includere attributi che non influiscono sull'attributo principale. Ad esempio, se tutti i tuoi clienti provengono da un paese specifico, non includere l'attributo *paese/area geografica* perché non avrà alcun impatto sull'output.

A seconda del numero di profili cliente e degli attributi selezionati, possono essere necessari alcuni minuti per elaborare gli attributi selezionati.

## <a name="manage-suggested-segments"></a>Gestire segmenti suggeriti

Vai a **Segmenti** e seleziona la scheda **Suggerimenti (anteprima)**. Nella sezione **Suggerimenti di segmenti basati su attributo**, seleziona un segmento suggerito per visualizzare le azioni disponibili.

- **Visualizza** i dettagli del segmento suggerito e le regole o i valori degli attributi che il modello di intelligenza artificiale ha appreso.
- Salva il suggerimento come segmento utilizzando **Salva come segmento**. Viene visualizzato nella scheda **Tutti i segmenti** e può essere [aggiornato, modificato o eliminato](segments.md).
- Scegli **Modifica attributi** e modifica gli attributi configurati che sostituiranno i suggerimenti correnti.
- **Aggiorna suggerimenti** per aggiornare i suggerimenti mantenendo gli attributi configurati.

## <a name="limitations"></a>Limiti

1. Dimensione stimata del segmento non corrispondente: se scegli un attributo principale che contiene valori vuoti, ciò può influire sulla dimensione del segmento stimata nei suggerimenti del segmento. Quando si salva tale segmento, la dimensione effettiva del segmento può essere diversa dalla stima originale.

2. Gli attributi principali di tipo booleano non funzionano: attualmente, supportiamo solo tipi di dati numerici e stringa come attributo principale.

3. I segmenti suggeriti non sono abbastanza distinti: tieni presente che gli attributi selezionati e la distribuzione dei valori di tali attributi influiscono sui risultati. Puoi modificare i tuoi attributi di influenza o anche il tuo attributo principale per ottenere risultati diversi.

[!INCLUDE [footer-include](includes/footer-banner.md)]