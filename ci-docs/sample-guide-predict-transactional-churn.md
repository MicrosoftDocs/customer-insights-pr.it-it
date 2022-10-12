---
title: Guida di esempio per una previsione di abbandono transazionale
description: Usa questa guida di esempio per provare il modello di previsione di abbandono transazionale predefinito.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609689"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guida di esempio per una previsione di abbandono transazionale

Questa guida illustra un esempio completo di previsione di abbandono transazionale utilizzando i dati di esempio. Ti consigliamo di testare questa previsione [in un nuovo ambiente](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso è un'azienda che produce caffè e macchine per caffè di alta qualità. Vende i prodotti tramite il sito Web di Contoso Coffee. Lo scopo dell'azienda è sapere quali clienti che acquistano regolarmente i loro prodotti smetteranno di essere clienti attivi nei prossimi 60 giorni. Sapere quali dei loro clienti **rischiano di essere persi**, può aiutarli a ridurre gli sforzi di marketing concentrandosi sulla fidelizzazione degli stessi.

## <a name="prerequisites"></a>Prerequisiti

- [Autorizzazioni di collaboratore](permissions.md) come minimo.

## <a name="task-1---ingest-data"></a>Attività 1: inserire dati

Rivedi gli articoli sull'[inserimento dati](data-sources.md) e sulla [connessione a un'origine dati Power Query](connect-power-query.md). Le seguenti informazioni presuppongono che tu abbia familiarità con l'inserimento dati in generale.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inserire dati cliente dalla piattaforma di eCommerce

1. Crea un origine dati denominata **eCommerce** e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscontacts.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazione**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:

   - **DateOfBirth**: data
   - **CreatedOn**: data/ora/fuso orario

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Trasformare la data di nascita in data.":::

1. Nel campo **Nome** nel riquadro a destra, rinomina l'origine dati in **eCommerceContacts**

1. Salva l'origine dati.

### <a name="ingest-online-purchase-data"></a>Inserire dati sugli acquisti online

1. Aggiungi un altro set di dati alla stessa origine dati **eCommerce**. Scegli di nuovo il connettore **Testo/CSV**.

1. Immetti l'URL per i dati di Acquisti online https://aka.ms/ciadclassonline.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazione**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:

   - **PurchasedOn**: data/ora
   - **TotalPrice**: valuta

1. Nel campo **Nome** nel riquadro a destra, rinomina l'origine dati in **eCommercePurchases**.

1. Salva l'origine dati.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inserire dati cliente dallo schema di fidelizzazione

1. Crea un origine dati denominata **LoyaltyScheme** e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazione**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:

   - **DateOfBirth**: data
   - **RewardsPoints**: numero intero
   - **CreatedOn**: date/ora

1. Nel campo **Nome** nel riquadro a destra, rinomina l'origine dati in **loyCustomers**.

1. Salva l'origine dati.

## <a name="task-2---data-unification"></a>Attività 2: unificare i dati

Esamina l'articolo [sull'unificazione dei dati](data-unification.md). Le seguenti informazioni presuppongono che tu abbia familiarità con l'unificazione dei dati in generale.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Attività 3: creare un'attività di cronologia delle transazioni

Rivedi l'articolo [sulle attività dei clienti](activities.md). Le seguenti informazioni presuppongono che tu abbia familiarità con la creazione di attività in generale.

1. Crea un'attività denominata **eCommercePurchases** con l'entità *eCommercePurchases:eCommerce* e la relativa chiave primaria,**PurchaseId**.

1. Crea una relazione tra *eCommercePurchases:eCommerce* ed *eCommerceContacts:eCommerce* con **ContactID** come chiave esterna per collegare le due entità.

1. Seleziona **TotalPrice** per **EventActivity** e **PurchasedOn** per **TimeStamp**.

1. Seleziona **SalesOrderLine** per **Tipo attività** e mappa a livello semantico i dati sull'attività.

1. Esegui l'attività.

## <a name="task-4---configure-transaction-churn-prediction"></a>Attività 4: configurare la previsione di abbandono transazionale

Con i profili cliente unificati e l'attività impostati, esegui la previsione di abbandono della transazione.

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Crea** seleziona **Usa modello** in **Modello di abbandono dei clienti**.

1. Seleziona **Transazionale** per il tipo di abbandono, quindi seleziona **Operazioni preliminari**.

1. Assegna al modello il nome **Previsione abbandono abbonamento eCommerce OOB** e all'entità il nome **OOBeCommerceChurnPrediction**.

1. Selezionare **Avanti**.

1. Definisci le preferenze del modello:

   - **Finestra di previsione**: **60** giorni per definire la durata del periodo di previsione dell'abbandono dei clienti.

   - **Definizione abbandono**: **60** giorni per indicare la durata senza acquisti trascorsa la quale un cliente è considerato come perso.

     :::image type="content" source="media/model-levers.PNG" alt-text="Selezionare le preferenze per i modelli Finestra di previsione e Definizione abbandono.":::

1. Selezionare **Avanti**.

1. Seleziona **Cronologia acquisti (obbligatoria)** e seleziona **Aggiungi dati** per la cronologia degli acquisti.

1. Seleziona **SalesOrderLine** e l'entità eCommercePurchases, quindi seleziona **Avanti**. I dati richiesti vengono compilati automaticamente dall'attività. Seleziona **Salva** e quindi **Avanti**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Associare le entità di e-Commerce.":::

1. Ignora il passaggio **Dati aggiuntivi (opzionale)**.

1. Nel passaggio **Aggiornamenti dei dati** seleziona **Mensile** per la pianificazione del modello.

1. Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**.

## <a name="task-5---review-model-results-and-explanations"></a>Attività 5: esaminare i risultati e le spiegazioni del modello

Lascia che il modello termini il training e la valutazione dei dati. Rivedi le spiegazioni del modello di abbandono. Per maggiori informazioni, vedi [Visualizzare i risultati della previsione](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Attività 6: creare un segmento di clienti ad alto rischio di abbandono

L'esecuzione del modello di produzione crea una nuova entità, che è elencata in **Dati** > **Entità**. Puoi creare un nuovo segmento basato sull'entità creata dal modello.

1. Nella pagina dei risultati, seleziona **Crea segmento**.

1. Crea una regola usando l'entità **OOBeCommerceChurnPrediction** e definisci il segmento:
   - **Campo**: ChurnScore
   - **Operatore**: maggiore di
   - **Valore**: 0,6

1. Seleziona **Salva** e quindi **Esegui** il segmento.

Ora hai un segmento aggiornato dinamicamente che identifica i clienti ad alto rischio di abbandono. Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).

> [!TIP]
> Puoi anche creare un segmento per un modello previsione dalla pagina **Segmenti** selezionando **Nuovo** e scegliendo **Crea da** > **Intelligence**. Per maggiori informazioni, vedi [Creare un nuovo segmento con segmenti rapidi](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
