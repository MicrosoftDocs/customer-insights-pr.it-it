---
title: Guida di esempio per una previsione di abbandono dell'abbonamento
description: Usa questa guida di esempio per provare il modello di previsione di abbandono dell'abbonamento predefinito.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610011"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Guida di esempio per una previsione di abbandono dell'abbonamento

Questa guida illustra un esempio completo di previsione di abbandono dell'abbonamento utilizzando i dati di esempio. Ti consigliamo di testare questa previsione [in un nuovo ambiente](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso è un'azienda che produce caffè e macchine per caffè di alta qualità. Vende i prodotti tramite il sito Web di Contoso Coffee. Recentemente ha lanciato un sistema di abbonamento affinché i suoi clienti acquistino regolarmente del caffè. L'obiettivo dell'azienda è capire quali clienti abbonati potrebbero annullare l'abbonamento nei mesi successivi. Sapere quali dei loro clienti **rischiano di essere persi**, può aiutarli a ridurre gli sforzi di marketing concentrandosi sulla fidelizzazione degli stessi.

## <a name="prerequisites"></a>Prerequisiti

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.

## <a name="task-1---ingest-data"></a>Attività 1: inserire dati

Rivedi gli articoli sull'[inserimento dati](data-sources.md) e sulla [connessione a un'origine dati Power Query](connect-power-query.md). Le seguenti informazioni presuppongono che tu abbia familiarità con l'inserimento dati in generale.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inserire dati cliente dalla piattaforma di eCommerce

1. Crea un origine dati Power Query denominata **eCommerce** e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscontacts.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazione**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **DateOfBirth**: data
   - **CreatedOn**: data/ora/fuso orario

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Trasformare la data di nascita in data.":::

1. Nel campo **Nome** nel riquadro a destra, rinomina l'origine dati in **eCommerceContacts**

1. Salva l'origine dati.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inserire dati cliente dallo schema di fidelizzazione

1. Crea un origine dati denominata **LoyaltyScheme** e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i clienti fedeli https://aka.ms/ciadclasscustomerloyalty.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazione**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **DateOfBirth**: data
   - **RewardsPoints**: numero intero
   - **CreatedOn**: date/ora

1. Nel campo **Nome** nel riquadro a destra, rinomina l'origine dati in **loyCustomers**.

1. Salva l'origine dati.

### <a name="ingest-subscription-information"></a>Inserire le informazioni sull'abbonamento

1. Crea un origine dati denominata **SubscriptionHistory** e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per gli abbonamenti https://aka.ms/ciadchurnsubscriptionhistory.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazione**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **SubscriptioID**: numero intero
   - **SubscriptionAmount**: valuta
   - **SubscriptionEndDate**: data/ora
   - **SubscriptionStartDate**: data/ora
   - **TransactionDate**: data/ora
   - **IsRecurring**: vero/falso
   - **Is_auto_renew**: vero/falso
   - **RecurringFrequencyInMonths**: numero intero

1. Nel campo **Nome** nel riquadro di destra, rinomina la tua origine dati in **SubscriptionHistory**.

1. Salva l'origine dati.

### <a name="ingest-customer-data-from-website-reviews"></a>Inserire dati cliente delle recensioni sul sito web

1. Crea un origine dati denominata **Website** e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per le recensioni del sito Web https://aka.ms/ciadclasswebsite.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazione**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **ReviewRating**: numero intero
   - **ReviewDate**: data

1. Nel campo **Nome** nel riquadro di destra, rinomina la tua origine dati in **webReviews**.

## <a name="task-2---data-unification"></a>Attività 2: unificare i dati

Esamina l'articolo [sull'unificazione dei dati](data-unification.md). Le seguenti informazioni presuppongono che tu abbia familiarità con l'unificazione dei dati in generale.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Attività 3: creare un'attività di cronologia delle transazioni

Rivedi l'articolo [sulle attività dei clienti](activities.md). Le seguenti informazioni presuppongono che tu abbia familiarità con la creazione di attività in generale.

1. Crea un'attività denominata **SubscriptionHistory** con l'entità *Subscription* e la relativa chiave primaria,**CustomerId**.

1. Crea una relazione tra *SubscriptionHistory:Subscription* ed *eCommerceContacts:eCommerce* con **CustomerID** come chiave esterna per collegare le due entità.

1. Seleziona **SubscriptionType** per **EventActivity** e **SubscriptionEndDate** per **TimeStamp**.

1. Seleziona **Subscription** per **Tipo attività** e mappa a livello semantico i dati sull'attività.

1. Esegui l'attività.

1. Aggiungi un'altra attività e mappa i nomi dei suoi campi ai campi corrispondenti:
   - Entità dell'attività del cliente: Recensioni: Sito Web
   - Chiave primaria: Website.Reviews.ReviewId
   - Timestamp: Website.Reviews.ReviewDate
   - Evento (nome attività): Website.Reviews.ActivityTypeDisplay
   - Dettagli (importo o valore): Website.Reviews.ReviewRating

1. Esegui l'attività.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Attività 4: configurare la previsione di abbandono dell'abbonamento

Dopo aver unificato i profili cliente e creato l'attività, possiamo eseguire la previsione dell'abbandono dell'abbonamento. Per i passaggi dettagliati, vedi [Previsione dell'abbandono dell'abbonamento](predict-subscription-churn.md).

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Crea** seleziona **Usa modello** nel riquadro **Modello di abbandono dei clienti**.

1. Seleziona **Abbonamento** per il tipo di abbandono, quindi seleziona **Operazioni preliminari**.

1. Assegna al modello il nome **Previsione abbandono abbonamento OOB** e all'entità di output il nome **OOBSubscriptionChurnPrediction**.

1. Definisci le preferenze del modello:
   - **Giorni dalla fine dell'abbonamento**: **60** giorni per indicare che un cliente viene considerato perso se non rinnova l'abbonamento in questo periodo successivo alla scadenza dell'abbonamento.
   - **Giorni da esaminare nel futuro per prevedere l'abbandono**: **93** giorni, che è la durata prevista dal modello per l'abbandono da parte dei clienti. Maggiore è la durata, meno precisi saranno i risultati.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Seleziona le preferenze per il modello e la definizione di abbandono.":::

1. Selezionare **Avanti**.

1. Nel passaggio **Dati richiesti**, seleziona **Aggiungi dati** per fornire i dati della cronologia degli abbonamenti.

1. Seleziona **Subscription** e l'entità SubscriptionHistory, quindi seleziona **Avanti**. I dati richiesti vengono compilati automaticamente dall'attività. Seleziona **Salva**.

1. In Attività cliente, seleziona **Aggiungi dati**.

1. Per questo esempio, aggiungi l'attività Recensione Web.

1. Selezionare **Avanti**.

1. Nel passaggio **Aggiornamenti dei dati** seleziona **Mensile** per la pianificazione del modello.

1. Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**.

## <a name="task-5---review-model-results-and-explanations"></a>Attività 5: esaminare i risultati e le spiegazioni del modello

Lascia che il modello termini il training e la valutazione dei dati. Rivedi le spiegazioni del modello di abbandono dell'abbonamento. Per maggiori informazioni, vedi [Visualizzare i risultati della previsione](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Attività 6: creare un segmento di clienti ad alto rischio di abbandono

L'esecuzione del modello crea una nuova entità, che è elencata in **Dati** > **Entità**. Puoi creare un nuovo segmento basato sull'entità creata dal modello.

1. Nella pagina dei risultati, seleziona **Crea segmento**.

1. Crea una regola usando l'entità **OOBSubscriptionChurnPrediction** e definisci il segmento:
   - **Campo**: ChurnScore
   - **Operatore**: maggiore di
   - **Valore**: 0,6

1. Seleziona **Salva** e quindi **Esegui** il segmento.

Ora hai un segmento che viene aggiornato dinamicamente e che identifica i clienti ad alto rischio di abbandono per questa attività di abbonamento. Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).

> [!TIP]
> Puoi anche creare un segmento per un modello previsione dalla pagina **Segmenti** selezionando **Nuovo** e scegliendo **Crea da** > **Intelligence**. Per maggiori informazioni, vedi [Creare un nuovo segmento con segmenti rapidi](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
