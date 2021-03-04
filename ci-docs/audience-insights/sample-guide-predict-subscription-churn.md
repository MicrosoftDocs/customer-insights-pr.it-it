---
title: Guida di esempio per una previsione di abbandono dell'abbonamento
description: Usa questa guida di esempio per provare il modello di previsione di abbandono dell'abbonamento predefinito.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269841"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Guida di esempio per una previsione di abbandono dell'abbonamento (anteprima)

In questa guida viene illustrato un esempio completo di previsione di abbandono dell'abbonamento che utilizza i dati di esempio forniti di seguito. 

## <a name="scenario"></a>Scenario

Contoso è un'azienda che produce caffè e macchine da caffè di alta qualità, in vendita sul sito Web Contoso Coffee. Recentemente ha lanciato un sistema di abbonamento affinché i suoi clienti acquistino regolarmente del caffè. L'obiettivo dell'azienda è capire quali clienti abbonati potrebbero annullare l'abbonamento nei mesi successivi. Sapere quali dei loro clienti **rischiano di essere persi**, può aiutarli a ridurre gli sforzi di marketing concentrandosi sulla fidelizzazione degli stessi.

## <a name="prerequisites"></a>Prerequisiti

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.
- Ti consigliamo di implementare i seguenti passaggi [in un nuovo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Attività 1: inserire dati

Consulta in particolare gli articoli [sull'inserimento dati](data-sources.md) e sull'[importazione di origini dati utilizzando i connettori Power Query](connect-power-query.md). Le seguenti informazioni presuppongono che tu conosca l'inserimento dati in generale. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inserire dati cliente dalla piattaforma di eCommerce

1. Crea un origine dati denominata **eCommerce**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscontacts.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:

   - **DateOfBirth**: data
   - **CreatedOn**: data/ora/fuso orario

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Trasformare la data di nascita in data.":::

1. Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **eCommerceContacts**

1. Salva l'origine dati.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inserire dati cliente dallo schema di fidelizzazione

1. Crea un origine dati denominata **LoyaltyScheme**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:

   - **DateOfBirth**: data
   - **RewardsPoints**: numero intero
   - **CreatedOn**: date/ora

1. Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **loyCustomers**.

1. Salva l'origine dati.

### <a name="ingest-subscription-information"></a>Inserire le informazioni sull'abbonamento

1. Crea un origine dati denominata **SubscriptionHistory**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadchurnsubscriptionhistory.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:

   - **SubscriptioID**: numero intero
   - **SubscriptionAmount**: valuta
   - **SubscriptionEndDate**: data/ora
   - **SubscriptionStartDate**: data/ora
   - **TransactionDate**: data/ora
   - **IsRecurring**: vero/falso
   - **Is_auto_renew**: vero/falso
   - **RecurringFrequencyInMonths**: numero intero

1. Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **SubscriptionHistory**.

1. Salva l'origine dati.

### <a name="ingest-customer-data-from-website-reviews"></a>Inserire dati cliente delle recensioni sul sito web

1. Crea un origine dati denominata **Website**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasswebsite.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:

   - **ReviewRating**: numero intero
   - **ReviewDate**: data

1. Nel campo "Nome" nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **webReviews**.

## <a name="task-2---data-unification"></a>Attività 2: unificare i dati

Dopo aver inserito i dati, iniziamo il processo di **Mapping, corrispondenza, unione** per creare un profilo cliente unificato. Per ulteriori informazioni, vedi [Unificazione dei dati](data-unification.md).

### <a name="map"></a>Mapping

1. Dopo l'inserimento dei dati, esegui il mapping dei dati di eCommerce e Fedeltà ai tipi di dati comuni. Vai a **Dati** > **Unifica** > **Mapping**.

1. Seleziona le entità che rappresentano il profilo cliente, ovvero **eCommerceContacts** e **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Unificare le origini dati di e-commerce e fedeltà.":::

1. Seleziona **ContactId** come chiave primaria per **eCommerceContacts** e **LoyaltyID** come chiave primaria per **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifica LoyaltyId come chiave primaria.":::

### <a name="match"></a>Corrispondenza

1. Passa alla scheda **Corrispondenza** e seleziona **Imposta ordine**.

1. Nell'elenco a discesa **Primaria**, scegli **eCommerceContacts : eCommerce** come origine primaria e includi tutti i record.

1. Nell'elenco a discesa **Entità 2**, scegli **loyCustomers : LoyaltyScheme** e includi tutti i record.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unificare la corrispondenza di eCommerce e Fedeltà.":::

1. Seleziona **Crea una nuova regola**

1. Aggiungi la prima condizione utilizzando FullName.

   * Per eCommerceContacts seleziona **FullName** nell'elenco a discesa.
   * Per loyCustomers seleziona **FullName** nell'elenco a discesa.
   * Seleziona l'elenco a discesa **Normalizza** e scegli **Tipo (telefono, nome, indirizzo...)**.
   * Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.

1. Immetti il nome **FullName, Email** per la nuova regola.

   * Aggiungi una seconda condizione per l'indirizzo e-mail selezionado **Aggiungi condizione**
   * Per l'entità eCommerceContacts, scegli **E-mail** nel menu a discesa.
   * Per l'entità loyCustomers, scegli **E-mail** nel menu a discesa. 
   * Lascia vuoto il campo Normalizza. 
   * Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificare la regola di corrispondenza per nome ed e-mail.":::

7. Seleziona **Salva** ed **Esegui**.

### <a name="merge"></a>Unione

1. Vai alla scheda **Unione**.

1. In **ContactId** per l'entità **loyCustomers**, cambia il nome visualizzato in **ContactIdLOYALTY** per differenziarlo dagli altri ID inseriti.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Rinominare contactid dall'ID del programma di fedeltà.":::

1. Seleziona **Salva** ed **Esegui** per avviare il processo di unione.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Attività 3: configurare la previsione di abbandono dell'abbonamento

Dopo aver unificato i profili cliente, possiamo eseguire la previsione dell'abbandono dell'abbonamento. Per i passaggi dettagliati, vedi [Previsione di abbandono dell'abbonamento (anteprima)](predict-subscription-churn.md). 

1. Vai a **Intelligenza** > **Scopri** e seleziona per utilizzare il **Modello di abbandono dei clienti**.

1. Seleziona l'opzione **Abbonamento** e seleziona **Inizia**.

1. Assegna al modello il nome **Previsione abbandono abbonamento OOB** e all'entità di output il nome **OOBSubscriptionChurnPrediction**.

1. Definisci due condizioni per il modello di abbandono:

   * **Giorni dalla fine dell'abbonamento**: **almeno 60** giorni. Se un cliente non rinnova il proprio abbonamento in tale periodo di tempo dopo la scadenza dell'abbonamento, viene considerato come perso. 

   * **Definizione abbandono**: **almeno 93** giorni. La durata della previsione del modello durante la quale i clienti potrebbero disabbonarsi. Maggiore è la durata, meno precisi saranno i risultati.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selezionare Finestra di previsione e Definizione abbandono.":::

1. Seleziona **Aggiungi dati obbligatori** e seleziona **Aggiungi dati** per la cronologia dell'abbonamento.

1. Aggiungi l'entità **Subscription : SubscriptionHistory** ed esegui il mapping dei campi di eCommerce ai campi corrispondenti richiesti dal modello.

1. Associa l'entità **Subscription : SubscriptionHistory** a **eCommerceContacts : eCommerce** e assegna un nome alla relazione **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Associare le entità di e-Commerce.":::

1. In Impegni cliente, aggiungi l'entità **webReviews: sito web** ed esegui il mapping dei campi di webReviews ai campi corrispondenti richiesti dal modello. 
   - Chiave primaria: ReviewId
   - Timestamp: ReviewDate
   - Evento: ReviewRating

1. Configura un'attività per recensioni sul sito Web. Seleziona l'impegno **Esamina** e associa l'entità **webReviews: sito web** a **eCommerceContacts : eCommerce**.

1. Seleziona **Avanti** per impostare la pianificazione del modello.

   È necessario eseguire regolarmente il training del modello affinché apprenda nuovi modelli quando vengono inseriti nuovi dati. Per questo esempio, seleziona **Mensile**.

1. Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**.

## <a name="task-4---review-model-results-and-explanations"></a>Attività 4: esaminare i risultati e le spiegazioni del modello

Lascia che il modello termini il training e la valutazione dei dati. Ora puoi esaminare le spiegazioni del modello di abbandono dell'abbonamento. Per ulteriori informazioni, vedi [Esaminare lo stato e i risultati di una previsione](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Attività 5: creare un segmento di clienti ad alto rischio di abbandono

L'esecuzione del modello di produzione crea una nuova entità visibile in **Dati** > **Entità**.   

Puoi creare un nuovo segmento basato sull'entità creata dal modello.

1.  Vai a **Segmenti**. Seleziona **Nuovo** e scegli **Crea a partire da** > **Intelligenza**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creazione di un segmento con l'output del modello.":::

1. Seleziona l'endpoint **OOBSubscriptionChurnPrediction** e definisci il segmento: 
   - Campo: ChurnScore
   - Operatore: maggiore di
   - Valore: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Impostare il segmento di abbandono dell'abbonamento.":::

Ora hai un segmento che viene aggiornato dinamicamente e che identifica i clienti ad alto rischio di abbandono per questa attività di abbonamento.

Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]