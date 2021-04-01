---
title: Segmenti suggertiti in base all'apprendimento automatico
description: Lascia che l'apprendimento automatico ti aiuti a trovare segmenti nuovi e interessanti in base agli attributi dei clienti.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: bbc22adcd7b6e756fa6128abd855795de7480f2d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597101"
---
# <a name="suggested-segments-preview"></a>Segmenti suggeriti (anteprima)

Scopri segmenti interessanti dei tuoi clienti con l'aiuto di un modello di intelligenza artificiale. Questa funzionalità potenziata da apprendimento automatico suggerisce i segmenti in base alle misure o agli attributi dei clienti. Può aiutarti a migliorare i tuoi KPI o a comprendere meglio l'influenza degli attributi nel contesto di altri attributi. 

> [!NOTE]
> La funzionalità dei segmenti suggeriti utilizza mezzi automatizzati per valutare i dati e fare previsioni basate sui dati e quindi può essere utilizzata come metodo di profilazione, secondo la definizione del termine nel Regolamento generale sulla protezione dei dati ("GDPR"). L'utilizzo di questa funzionalità per elaborare i dati può essere soggetto al GDPR o ad altre leggi o regolamenti. Devi assicurarti che il tuo utilizzo di Dynamics 365 Customer Insights, compresa questa funzionalità, sia conforme a tutte le leggi e le norme applicabili, comprese le leggi relative alla privacy, ai dati personali, ai dati biometrici, alla protezione dei dati e alla riservatezza delle comunicazioni.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Pagina dei segmenti suggeriti in Customer Insights che mostra i dettagli di un suggerimento in un riquadro laterale.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmenti suggeriti per migliorare i tuoi KPI

Come utente di Audience Insights, probabilmente hai una serie di [misure create](measures.md) che aiutano a tenere traccia dei tuoi indicatori di prestazioni chiave (KPI). È importante capire come determinati attributi influenzano questi KPI per creare segmenti ed eseguire una campagna altamente mirata.   
Ad esempio, si tiene traccia di una misura chiamata *TotalSpendPerCustomer*. Come azienda, ti piacerebbe vedere crescere questo numero. La scelta di una misura come attributo principale consente di selezionare gli attributi di cui si desidera valutare l'influenza. Diciamo *livello di appartenenza*, *periodo di appartenenza* e *occupazione*. Customer Insights può quindi suggerire un segmento che ti dice chi è la maggiore influenza di quella misura. Ad esempio, i *Commercialisti* che sono membri *Gold* e che sono stati con la tua azienda per *almeno cinque anni* sono i principali influencer di *TotalSpendPerCustomer*. Otterrai una dimensione del segmento stimata per ogni suggerimento. È possibile utilizzare queste informazioni per creare campagne per destinatari mirati.

## <a name="understand-what-influences-a-customer-attribute"></a>Comprendere cosa influenza un attributo dei clienti

È possibile scegliere un attributo dei clienti invece di una misura come attributo principale. In base alla scelta degli attributi di influenza, il modello di intelligenza artificiale crea una serie di suggerimenti che mostrano come gli attributi selezionati influenzano l'attributo principale.   
Ad esempio, scegli *Membro programma fedeltà (Sì/No)* come attributo principale. *Mandato*, *Occupazione* e *Numero di ticket di supporto* sono impostati come altri attributi di influenza. Il modello di intelligenza artificiale potrebbe suggerire segmenti che indicano che per lo più professionisti IT con un mandato superiore a due anni sono membri del programma fedeltà. Un altro suggerimento potrebbe evidenziare che i contabili con un mandato superiore a un anno e meno di tre ticket di supporto sono membri del programma fedeltà. 

## <a name="artificial-intelligence-usage"></a>Uso dell'intelligenza artificiale

Utilizzando l'attributo principale e gli attributi di influenza, un algoritmo dell'albero decisionale suggerisce segmenti interessanti. I suggerimenti si basano su regole o schemi che sono stati raccolti dall'algoritmo di intelligenza artificiale. Solo i segmenti che differiscono in modo significativo dalla popolazione media vengono visualizzati come suggerimenti. Il confronto con la popolazione media si basa sulla misura o sull'attributo principale selezionato.

### <a name="responsible-ai"></a>IA responsabile

I segmenti suggeriti ti consentono di selezionare gli attributi per creare nuovi segmenti ed elaborare i dati selezionati. Quando scegli attributi, tra cui attributi sensibili come razza, orientamento sessuale o sesso, devi assicurarti di poter e dover elaborare tali dati. Sei responsabile del rispetto delle leggi applicabili alla tua organizzazione e dei principi e delle politiche sulla privacy della tua organizzazione.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Risultati diversi per attributi principali con valori categorici e numerici

I suggerimenti di segmento sono diversi se scegli un attributo numerico o un attributo categorico come attributo principale. I valori in un attributo categorico contengono due o più categorie o tipi. Un attributo numerico contiene dati quantitativi e ha un senso di misurazione ad esso associato.

Con un attributo numerico come *reddito annuo* o *periodo di appartenenza* come attributo principale, il sistema suggerisce segmenti che hanno un valore medio più alto o più basso dell'attributo numerico rispetto a tutti i clienti.

Un attributo categorico come *soddisfazione del cliente* come attributo principale determina segmenti suggeriti che hanno una percentuale maggiore o minore di clienti appartenenti a una particolare categoria rispetto alla percentuale di tutti i clienti appartenenti a quella stessa categoria. Ad esempio, *soddisfazione del cliente* viene scelto come attributo principale e si compone di tre categorie (*Bassa*, *Media* e *Alta*). Per ciascuna categoria, verranno suggeriti segmenti che hanno una percentuale di clienti appartenenti a quella categoria significativamente più alta o più bassa rispetto alla proporzione di tutti i clienti nella stessa categoria. Se il 22% di tutti i clienti ha una soddisfazione *Alta*, solo i segmenti che hanno una percentuale significativamente maggiore o minore di clienti con soddisfazione *Alta* rispetto al 22% verranno suggeriti per quella categoria. Allo stesso modo, i segmenti verranno suggeriti per ciascuna delle altre categorie (*Bassa* e *Media*) se sono statisticamente significativi.

> [!NOTE]
> Al momento, supportiamo solo attributi categorici principali che hanno fino a 10 categorie. Se desideri visualizzare i suggerimenti di segmenti basati su un attributo principale con più di 10 categorie, ti consigliamo di raggruppare alcune delle categorie per ridurre il numero di categorie a 10 o meno. Questa limitazione si applica solo agli attributi principali. Per gli attributi categorici di influenza, attualmente supportiamo un massimo di 100 categorie.

## <a name="generate-suggested-segments"></a>Generare segmenti suggeriti

1. Vai a **Segmenti**.

1. Seleziona la scheda **Suggerimenti (anteprima)**.

1. Seleziona **Ottieni nuovi suggerimenti** per iniziare l'esperienza guidata.

1. Scegli una misura o un attributo dei clienti come attributo principale e seleziona **Avanti**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Scelta dell'attributo principale per suggerimenti sui segmenti suggeriti.":::

1. Seleziona gli attributi di influenza e seleziona **Salva**.
   
   > [!TIP]
   > La selezione di più attributi di influenza migliora le possibilità di valutare come influenzano l'attributo principale. Non includere attributi che non influiscono sull'attributo principale. Ad esempio, se tutti i tuoi clienti provengono da un paese specifico, non includere l'attributo *paese/area geografica* perché non avrà alcun impatto sull'output.

1. A seconda del numero di profili cliente e degli attributi selezionati, possono essere necessari alcuni minuti per elaborare gli attributi selezionati. 

## <a name="view-details-of-a-suggested-segment"></a>Visualizzare i dettagli di un segmento suggerito

Una volta che il modello di intelligenza artificiale ha generato i suggerimenti, li troverai elencati in **Segmenti** > **Suggerimenti (anteprima)**.
 
Seleziona un segmento suggerito per rivedere i dettagli di quel suggerimento, incluso un confronto tra il valore medio e il numero di membri del segmento. Puoi anche rivedere i valori degli attributi o le regole che il modello di intelligenza artificiale ha appreso per suggerire il segmento selezionato.

## <a name="save-a-suggestion-as-a-segment"></a>Salvare un suggerimento come segmento

1. Vai a **Segmenti** > **Suggerimenti (anteprima)**.

1. Seleziona il segmento da salvare 

1. Nel riquadro laterale seleziona **Salva come segmento**. 

1. Dopo aver salvato il segmento, verrà visualizzato nell'elenco dei segmenti nella scheda **Tutti i segmenti**. Ora può essere [aggiornato, modificato o eliminato come qualsiasi altro segmento](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Aggiornare o modificare una serie di suggerimenti

1. Vai a **Segmenti** > **Suggerimenti (anteprima)**.

1. Seleziona **Aggiorna suggerimenti** per aggiornare i suggerimenti mantenendo gli attributi configurati. Oppure seleziona **Modifica attributi** per modificare gli attributi configurati. Il sistema eseguirà nuovamente il modello di intelligenza artificiale, genererà suggerimenti di segmenti basati sui dati più recenti e sostituirà i suggerimenti correnti.

## <a name="limitations"></a>Limiti

1. Dimensione stimata del segmento non corrispondente: se scegli un attributo principale che contiene valori vuoti, ciò può influire sulla dimensione del segmento stimata nei suggerimenti del segmento. Quando si salva tale segmento, la dimensione effettiva del segmento può essere diversa dalla stima originale.
 
2. Gli attributi principali di tipo booleano non funzionano: attualmente, supportiamo solo tipi di dati numerici e stringa come attributo principale.

3. I segmenti suggeriti non sono abbastanza distinti: tieni presente che gli attributi selezionati e la distribuzione dei valori di tali attributi influenzano i risultati. Puoi modificare i tuoi attributi di influenza o anche il tuo attributo principale per ottenere risultati diversi.



[!INCLUDE[footer-include](../includes/footer-banner.md)]