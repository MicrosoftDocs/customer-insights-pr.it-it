---
title: Guida di esempio per la previsione di raccomandazioni sui prodotti
description: Usa questa guida di esempio per provare il modello di previsione di raccomandazioni sui prodotti predefinito.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762691"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guida di esempio per la previsione di raccomandazioni sui prodotti

In questa guida viene illustrato un esempio completo di previsione di raccomandazioni sui prodotti che utilizza i dati di esempio forniti di seguito.

## <a name="scenario"></a>Scenario

Contoso è un'azienda che produce caffè e macchine da caffè di alta qualità, in vendita sul sito Web Contoso Coffee. Il suo obiettivo è capire quali prodotti dovrebbe consigliare ai clienti ricorrenti. Sapere cosa i clienti hanno maggiore **probabilità di acquistare** può aiutare a risparmiare sforzi di marketing concentrandosi su articoli specifici.

## <a name="prerequisites"></a>Prerequisiti

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.
- Ti consigliamo di implementare i seguenti passaggi [in un nuovo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Attività 1: inserire dati

Rivedi gli articoli [sull'inserimento di dati](data-sources.md) e sull'[importazione delle origini dati utilizzando in specifico i connettori Power Query](connect-power-query.md). Le seguenti informazioni presuppongono che tu conosca l'inserimento dati in generale.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inserire dati cliente dalla piattaforma di eCommerce

1. Crea un origine dati denominata **eCommerce**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **DateOfBirth**: data
   - **CreatedOn**: data/ora/fuso orario

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Trasformare la data di nascita in data.":::

1. Nel campo "Nome" nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **eCommerceContacts**

1. **Salva** l'origine dati.

### <a name="ingest-online-purchase-data"></a>Inserire dati sugli acquisti online

1. Aggiungi un altro set di dati alla stessa origine dati **eCommerce**. Scegli di nuovo il connettore **Testo/CSV**.

1. Immetti l'URL per i dati di **Acquisti online** [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **PurchasedOn**: data/ora
   - **TotalPrice**: valuta

1. Nel campo **Nome** nel riquadro laterale, cambia il nome dell'origine dati da **Query** a **eCommercePurchases**.

1. **Salva** l'origine dati.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inserire dati cliente dallo schema di fidelizzazione

1. Crea un origine dati denominata **LoyaltyScheme**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **DateOfBirth**: data
   - **RewardsPoints**: numero intero
   - **CreatedOn**: date/ora

1. Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **loyCustomers**.

1. **Salva** l'origine dati.

## <a name="task-2---data-unification"></a>Attività 2: unificare i dati

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Attività 3: configurare la previsione di raccomandazioni sui prodotti

Con i profili cliente unificati, ora possiamo eseguire la previsione di consigli del prodotto.

1. Vai a **Intelligenza** > **Previsione** e scegli **Raccomandazioni prodotto**.

1. Seleziona **Operazioni preliminari**.

1. Nomina il modello **Modello di previsione di raccomandazioni sui prodotti predefinito** e l'entità di output **OOBProductRecommendationModelPrediction**.

1. Definisci tre condizioni per il modello:

   - **Numero di prodotti**: imposta questo valore su **5**. Questa impostazione definisce quanti prodotti desideri consigliare ai tuoi clienti.

   - **Ripetizione degli acquisti prevista**: seleziona **Sì** per indicare che desideri includere i prodotti nella raccomandazione che i tuoi clienti hanno acquistato in precedenza.

   - **Finestra per guardare indietro:** Seleziona almeno **365 giorni**. Questa impostazione definisce fino a quanto tempo indietro il modello esaminerà l'impegno del cliente per utilizzarlo come input per le raccomandazioni.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferenze del modello di raccomandazione sui prodotti.":::

1. Nel passaggio **Aggiungi dati obbligatori** seleziona **Aggiungi dati**.

1. Nel riquadro **Aggiungi dati** scegli **SalesOrderLine** come entità della cronologia degli acquisti. A questo punto, probabilmente non è ancora configurata. Apri il collegamento nel riquadro per creare l'impegno con i seguenti passaggi:
   1. Immetti un valore nel campo **Nome impegno** e scegli *eCommercePurchases:eCommerce* come **Entità impegno**. Il campo **Chiave primaria** è *PurchaseId*.
   1. Definisci e assegna un nome alla relazione con l'entità *eCommerceContacts:eCommerce* e scegli **ContactId** come chiave esterna.
   1. Per Unificazione impegno, imposta **Impegno evento** come *TotalPrice* e Timestamp su *PurchasedOn*. È possibile specificare più campi come indicato in [Impegni cliente](activities.md).
   1. Per **Tipo di impegno** scegli *SalesOrderLine*. Esegui il mapping dei campi di impegno seguenti:
      - ID riga ordine: PurchaseId
      - ID ordine: PurchaseId
      - Dati ordine: PurchasedOn
      - ID prodotto: ProductId
      - Importo: TotalPrice
   1. Rivedi e termina l'impegno prima di tornare alla configurazione del modello.

1. Nel passaggio **Seleziona impegni** scegli l'impegno creato nella sezione **Impegni**. Seleziona **Avanti** e la mappatura degli attributi è già compilata. Seleziona **Salva**.

1. In questa guida di esempio, saltiamo le impostazioni **Aggiungi informazioni sul prodotto** e **Filtri prodotto** perché non disponiamo di dati sulle informazioni sul prodotto.

1. Nel passaggio **Aggiornamenti dei dati** impostare la pianificazione del modello.

   È necessario eseguire regolarmente il training del modello affinché apprenda nuovi modelli quando vengono inseriti nuovi dati. Per questo esempio, seleziona **Mensile**.

1. Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**. Ci vorranno alcuni minuti per eseguire il modello la prima volta.

## <a name="task-4---review-model-results-and-explanations"></a>Attività 4: esaminare i risultati e le spiegazioni del modello

Lascia che il modello termini il training e la valutazione dei dati. Ora puoi esaminare le spiegazioni del modello di raccomandazione dei prodotti. Per ulteriori informazioni, vedi [Esaminare lo stato e i risultati di una previsione](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Attività 5: creare un segmento di prodotti ad acquisto elevato

L'esecuzione del modello di produzione crea una nuova entità visibile in **Dati** > **Entità**.

Puoi creare un nuovo segmento basato sull'entità creata dal modello.

1. Vai a **Segmenti**. Seleziona **Nuovo** e scegli **Crea da intelligence**.

   ![Creazione di un segmento con l'output del modello.](media/segment-intelligence.png)

1. Seleziona l'endpoint **OOBProductRecommendationModelPrediction** e definisci il segmento:

   - Campo: ProductID
   - Valore: seleziona i primi tre ID prodotto

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Crea un segmento dai risultati del modello.":::

Ora hai un segmento aggiornato dinamicamente che identifica i clienti che possono essere interessati ad acquistare i tre prodotti più consigliati.

Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
