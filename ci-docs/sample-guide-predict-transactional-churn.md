---
title: Guida di esempio per una previsione di abbandono transazionale
description: Usa questa guida di esempio per provare il modello di previsione di abbandono transazionale predefinito.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 05c221c634b8e0f582a6c6d3f4d90e971aa9707e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647269"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guida di esempio per una previsione di abbandono transazionale

In questa guida viene illustrato un esempio completo di previsione di abbandono transazionale in Customer Insights che utilizza i dati di esempio forniti di seguito. Tutti i dati utilizzati in questa guida non sono dati cliente reali e fanno parte del set di dati di Contoso disponibile nell'ambiente *Demo* dell'abbonamento a Customer Insights.

## <a name="scenario"></a>Scenario

Contoso è un'azienda che produce caffè e macchine da caffè di alta qualità, in vendita sul sito Web Contoso Coffee. Lo scopo dell'azienda è sapere quali clienti che acquistano regolarmente i loro prodotti smetteranno di essere clienti attivi nei prossimi 60 giorni. Sapere quali dei loro clienti **rischiano di essere persi**, può aiutarli a ridurre gli sforzi di marketing concentrandosi sulla fidelizzazione degli stessi.

## <a name="prerequisites"></a>Prerequisiti

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.
- Ti consigliamo di implementare i seguenti passaggi [in un nuovo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Attività 1: inserire dati

Rivedi gli articoli [sull'inserimento di dati](data-sources.md) e sull'[importazione delle origini dati utilizzando in specifico i connettori Power Query](connect-power-query.md). Le seguenti informazioni presuppongono che tu conosca l'inserimento dati in generale. 

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

### <a name="ingest-online-purchase-data"></a>Inserire dati sugli acquisti online

1. Aggiungi un altro set di dati alla stessa origine dati **eCommerce**. Scegli di nuovo il connettore **Testo/CSV**.

1. Immetti l'URL per i dati degli **Acquisti online** https://aka.ms/ciadclassonline.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:

   - **PurchasedOn**: data/ora
   - **TotalPrice**: valuta
   
1. Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **eCommercePurchases**.

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

1. Nell'elenco a discesa **Principale** scegli **eCommerceContacts : eCommerce** come fonte primaria e includi tutti i record.

1. Nell'elenco a discesa **Entità 2** scegli **loyCustomers : LoyaltyScheme** e includi tutti i record.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unificare la corrispondenza di eCommerce e Fedeltà.":::

1. Seleziona **Crea una nuova regola**

1. Aggiungi la prima condizione utilizzando FullName.

   * Per eCommerceContacts seleziona **FullName** nel menu a discesa.
   * Per loyCustomers seleziona **FullName** nel menu a discesa.
   * Seleziona l'elenco a discesa **Normalizza** e scegli **Tipo (telefono, nome, indirizzo...)**.
   * Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.

1. Immetti il nome **FullName, Email** per la nuova regola.

   * Aggiungi una seconda condizione per l'indirizzo e-mail selezionado **Aggiungi condizione**
   * Per l'entità eCommerceContacts, scegli **E-mail** nell'elenco a discesa.
   * Per l'entità loyCustomers, scegli **E-mail** nell'elenco a discesa. 
   * Lascia vuoto il campo Normalizza. 
   * Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificare la regola di corrispondenza per nome ed e-mail.":::

7. Seleziona **Salva** ed **Esegui**.

### <a name="merge"></a>Unione

1. Vai alla scheda **Unione**.

1. In **ContactId** per l'entità **loyCustomers**, cambia il nome visualizzato in **ContactIdLOYALTY** per differenziarlo dagli altri ID inseriti.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Rinominare contactid dall'ID del programma di fedeltà.":::

1. Seleziona **Salva** ed **Esegui** per avviare il processo di unione.



## <a name="task-3---configure-transaction-churn-prediction"></a>Attività 3: configurare la previsione di abbandono transazionale

Dopo aver unificato i profili cliente, possiamo eseguire la previsione dell'abbandono dell'abbonamento. Per i passaggi dettagliati, vedi l'articolo [Previsione dell'abbandono della sottoscrizione](predict-subscription-churn.md). 

1. Vai a **Intelligenza** > **Scopri** e seleziona per utilizzare il **Modello di abbandono dei clienti**.

1. Seleziona l'opzione **Transazionale** e seleziona **Inizia**.

1. Assegna al modello il nome **Previsione abbandono abbonamento eCommerce OOB** e all'entità il nome **OOBeCommerceChurnPrediction**.

1. Definisci due condizioni per il modello di abbandono:

   * **Finestra di previsione**: **almeno 60** giorni. Questa impostazione definisce la durata del periodo di previsione dell'abbandono dei clienti.

   * **Definizione abbandono**: **almeno 60** giorni. La durata senza acquisto dopo la quale un cliente è considerato come perso.

     :::image type="content" source="media/model-levers.PNG" alt-text="Selezionare Finestra di previsione e Definizione abbandono.":::

1. Seleziona **Cronologia acquisti (obbligatoria)** e seleziona **Aggiungi dati** per la cronologia degli acquisti.

1. Aggiungi l'entità **eCommercePurchases : eCommerce** ed esegui il mapping dei campi di eCommerce ai campi corrispondenti richiesti dal modello.

1. Associa l'entità **eCommercePurchases : eCommerce** a **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Associare le entità di e-Commerce.":::

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
