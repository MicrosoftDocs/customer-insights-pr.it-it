---
title: Guida di esempio per la previsione di raccomandazioni sui prodotti
description: Usa questa guida di esempio per provare il modello di previsione di raccomandazioni sui prodotti predefinito.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306171"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Guida di esempio per la previsione di raccomandazioni sui prodotti (anteprima)

In questa guida viene illustrato un esempio completo di previsione di raccomandazioni sui prodotti che utilizza i dati di esempio forniti di seguito.

## <a name="scenario"></a>Scenario

Contoso è un'azienda che produce caffè e macchine da caffè di alta qualità, che vendono attraverso il sito Web Contoso per il caffè. Il suo obiettivo è capire quali prodotti dovrebbe consigliare ai clienti ricorrenti. Sapere cosa i clienti hanno maggiore **probabilità di acquistare** può aiutare a risparmiare sforzi di marketing concentrandosi su articoli specifici.

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

5. Nel campo "Nome" nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **eCommerceContacts**

6. **Salva** l'origine dati.

### <a name="ingest-online-purchase-data"></a>Inserire dati sugli acquisti online

1. Aggiungi un altro set di dati alla stessa origine dati **eCommerce**. Scegli di nuovo il connettore **Testo/CSV**.

1. Immetti l'URL per i dati degli **Acquisti online** https://aka.ms/ciadclassonline.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **PurchasedOn**: data/ora
   - **TotalPrice**: valuta

1. Nel campo **Nome** nel riquadro laterale, cambia il nome dell'origine dati da **Query** a **eCommercePurchases**.

1. **Salva** l'origine dati.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Inserire dati cliente dallo schema di fidelizzazione

1. Crea un origine dati denominata **LoyaltyScheme**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **DateOfBirth**: data
   - **RewardsPoints**: numero intero
   - **CreatedOn**: date/ora

1. Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **loyCustomers**.

1. **Salva** l'origine dati.

## <a name="task-2---data-unification"></a>Attività 2: unificare i dati

Dopo aver importato i dati, iniziamo il processo di unificazione dei dati per creare un profilo cliente unificato. Per ulteriori informazioni, vedi [Unificazione dei dati](data-unification.md).

### <a name="map"></a>Mapping

1. Dopo l'inserimento dei dati, esegui il mapping dei dati di eCommerce e Fedeltà ai tipi di dati comuni. Vai a **Dati** > **Unifica** > **Mapping**.

2. Seleziona le entità che rappresentano il profilo cliente, ovvero **eCommerceContacts** e **loyCustomers**.

   ![Unificare le origini dati di e-commerce e fedeltà.](media/unify-ecommerce-loyalty.png)

3. Seleziona **ContactId** come chiave primaria per **eCommerceContacts** e **LoyaltyID** come chiave primaria per **loyCustomers**.

   ![Unifica LoyaltyId come chiave primaria.](media/unify-loyaltyid.png)

### <a name="match"></a>Corrispondenza

1. Passa alla scheda **Corrispondenza** e seleziona **Imposta ordine**.

2. Nell'elenco a discesa **Principale** scegli **eCommerceContacts : eCommerce** come fonte primaria e includi tutti i record.

3. Nell'elenco a discesa **Entità 2** scegli **loyCustomers : LoyaltyScheme** e includi tutti i record.

   ![Unificare la corrispondenza di eCommerce e Fedeltà.](media/unify-match-order.png)

4. Seleziona **Crea una nuova regola**

5. Aggiungi la prima condizione utilizzando FullName.

   - Per eCommerceContacts seleziona **FullName** nel menu a discesa.
   - Per loyCustomers seleziona **FullName** nel menu a discesa.
   - Seleziona l'elenco a discesa **Normalizza** e scegli **Tipo (telefono, nome, indirizzo...)**.
   - Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.

6. Immetti il nome **FullName, Email** per la nuova regola.

   - Aggiungi una seconda condizione per l'indirizzo e-mail selezionado **Aggiungi condizione**
   - Per l'entità eCommerceContacts, scegli **E-mail** nell'elenco a discesa.
   - Per l'entità loyCustomers, scegli **E-mail** nell'elenco a discesa.
   - Lascia vuoto il campo Normalizza.
   - Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.

   ![Unificare la regola di corrispondenza per nome ed e-mail.](media/unify-match-rule.png)

7. Seleziona **Salva** ed **Esegui**.

### <a name="merge"></a>Unione

1. Vai alla scheda **Unione**.

1. In **ContactId** per l'entità **loyCustomers**, cambia il nome visualizzato in **ContactIdLOYALTY** per differenziarlo dagli altri ID inseriti.

   ![Rinominare contactid dall'ID del programma di fedeltà.](media/unify-merge-contactid.png)

1. Seleziona **Salva** ed **Esegui** per avviare il processo di unione.

## <a name="task-3---configure-product-recommendation-prediction"></a>Attività 3: configurare la previsione di raccomandazioni sui prodotti

Dopo aver unificato i profili cliente, possiamo eseguire la previsione dell'abbandono dell'abbonamento.

1. Vai a **Intelligenza** > **Previsione** e scegli **Raccomandazioni prodotto**.

1. Seleziona **Operazioni preliminari**.

1. Nomina il modello **Modello di previsione di raccomandazioni sui prodotti predefinito** e l'entità di output **OOBProductRecommendationModelPrediction**.

1. Definisci tre condizioni per il modello:

   - **Numero di prodotti**: imposta questo valore su **5**. Questa impostazione definisce quanti prodotti desideri consigliare ai tuoi clienti.

   - **Ripetizione degli acquisti prevista**: seleziona **Sì** per indicare che desideri includere i prodotti nella raccomandazione che i tuoi clienti hanno acquistato in precedenza.

   - **Finestra per guardare indietro:** Seleziona almeno **365 giorni**. Questa impostazione definisce fino a quanto tempo indietro il modello esaminerà l'impegno del cliente per utilizzarlo come input per le raccomandazioni.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferenze del modello di raccomandazione sui prodotti.":::

1. Seleziona **Dati obbligatori** e seleziona **Aggiungi dati** per la cronologia degli acquisti.

1. Aggiungi l'entità **eCommercePurchases : eCommerce** ed esegui il mapping dei campi di eCommerce ai campi corrispondenti richiesti dal modello.

1. Associa l'entità **eCommercePurchases : eCommerce** a **eCommerceContacts : eCommerce**.

   ![Associare le entità di e-Commerce.](media/model-purchase-join.png)

1. Seleziona **Avanti** per impostare la pianificazione del modello.

   È necessario eseguire regolarmente il training del modello affinché apprenda nuovi modelli quando vengono inseriti nuovi dati. Per questo esempio, seleziona **Mensile**.

1. Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**.


## <a name="task-4---review-model-results-and-explanations"></a>Attività 4: esaminare i risultati e le spiegazioni del modello

Lascia che il modello termini il training e la valutazione dei dati. Ora puoi esaminare le spiegazioni del modello di raccomandazione dei prodotti. Per ulteriori informazioni, vedi [Esaminare lo stato e i risultati di una previsione](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Attività 5: creare un segmento di prodotti ad acquisto elevato

L'esecuzione del modello di produzione crea una nuova entità visibile in **Dati** > **Entità**.

Puoi creare un nuovo segmento basato sull'entità creata dal modello.

1. Vai a **Segmenti**. Seleziona **Nuovo** e scegli **Crea a partire da** > **Intelligenza**.

   ![Creazione di un segmento con l'output del modello.](media/segment-intelligence.png)

1. Seleziona l'endpoint **OOBProductRecommendationModelPrediction** e definisci il segmento:

   - Campo: ProductID
   - Operatore: Valore
   - Valore: seleziona i primi tre ID prodotto

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Crea un segmento dai risultati del modello.":::

Ora hai un segmento che viene aggiornato dinamicamente che identifica i clienti che sono più disposti ad acquistare i tre prodotti più consigliati 

Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
