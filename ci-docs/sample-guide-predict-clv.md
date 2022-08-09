---
title: Guida di esempio previsione di Customer Lifetime Value (CLV)
description: Usa questa guida di esempio per provare il modello di previsione di Customer Lifetime Value (CLV).
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 2013533ed225a396d21e51e63297d7608ce58ac6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051642"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guida di esempio previsione di Customer Lifetime Value (CLV)

Questa guida ti spiegherà un esempio end-to-end della previsione Customer Lifetime Value (CLV) in Customer Insights utilizzando dati di esempio.

## <a name="scenario"></a>Scenario

Contoso è un'azienda che produce caffè e macchine per caffè di alta qualità. Vende i prodotti tramite il sito Web di Contoso Coffee. L'azienda vuole capire il valore (ricavo) che i propri clienti possono generare nei prossimi 12 mesi. Conoscere il valore atteso dei loro clienti nei prossimi 12 mesi li aiuterà a dirigere le loro iniziative di marketing su clienti di alto valore.

## <a name="prerequisites"></a>Prerequisiti

- Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.
- Ti consigliamo di implementare i seguenti passaggi [in un nuovo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Attività 1: inserire dati

Rivedi gli articoli [sull'inserimento di dati](data-sources.md) e sull'[importazione delle origini dati utilizzando i connettori Power Query](connect-power-query.md). Le seguenti informazioni presuppongono che tu conosca l'inserimento dati in generale.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inserire dati cliente dalla piattaforma di eCommerce

1. Crea un'origine dati denominata **eCommerce**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **DateOfBirth**: data
   - **CreatedOn**: data/ora/fuso orario

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Trasformare la data di nascita in data.":::

1. Nel campo "Nome" nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **eCommerceContacts**

1. **Salva** l'origine dati.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Inserire dati cliente delle recensioni sul sito web

1. Crea un origine dati denominata **Website**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i contatti di eCommerce https://aka.ms/CI-ILT/WebReviews.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:

   - **ReviewRating**: numero decimale
   - **ReviewDate**: data

1. Nel campo "Nome" nel riquadro di destra, rinomina la tua origine dati da **Query** a **Recensioni**.

1. **Salva** l'origine dati.

## <a name="task-2---data-unification"></a>Attività 2: unificare i dati

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Attività 3 - Configurare la previsione di Customer Lifetime Value

Con i profili cliente unificati in atto, ora possiamo eseguire la previsione Customer Lifetime Value. Per i passaggi dettagliati, vedi [Previsione del valore durata cliente](predict-customer-lifetime-value.md).

1. Vai a **Intelligenza**  > **Previsioni** e seleziona **Modello di Valore durata cliente**.

1. Scorri le informazioni nel riquadro laterale e seleziona **Attività iniziali**.

1. Dai un nome al modello **Previsione OOB eCommerce CLV** e l'entità di output **OOBeCommerceCLVPrediction**.

1. Definire le preferenze del modello per il modello CLV:
   - **Periodo di tempo della previsione**: **12 mesi o 1 anno**. Questa impostazione definisce quanto lontano nel futuro prevedere il valore della durata del cliente.
   - **Clienti attivi**: specifica cosa significano i clienti attivi per la tua attività. Imposta l'intervallo di tempo storico in cui un cliente deve aver avuto almeno una transazione per essere considerato attivo. Il modello prevede il CLV solo per i clienti attivi. Scegli tra lasciare che il modello calcoli il periodo di tempo in base ai dati storici delle transazioni o fornire un intervallo di tempo specifico. In questa guida di esempio, noi **lasciamo che il modello calcoli l'intervallo di acquisto**, che è l'opzione predefinita.
   - **Clienti di alto valore**: definire i clienti di alto valore come percentile dei clienti più paganti. Il modello utilizza questo input per fornire risultati che si adattano alla tua definizione aziendale di clienti di alto valore. Puoi scegliere di far definire al modello i clienti di valore elevato. Utilizza una regola euristica che derivi il percentile. Puoi inoltre definire i clienti di alto valore come percentile dei clienti più paganti in futuro. In questa guida di esempio, definiamo manualmente i clienti di alto valore come **top 30% dei clienti paganti attivi** e selezioniamo **Avanti**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Passaggio delle preferenze nell'esperienza guidata per il modello CLV.":::

1. Nel passaggio **Dati richiesti**, seleziona **Aggiungi dati** per fornire i dati della cronologia delle transazioni.

1. Aggiungi l'entità **eCommercePurchases: eCommerce** e mappa gli attributi richiesti dal modello:
   - ID transazione: eCommerce.eCommercePurchases.PurchaseId
   - Data transazione: eCommerce.eCommercePurchases.PurchasedOn
   - Importo della transazione: eCommerce.eCommercePurchases.TotalPrice
   - ID prodotto: eCommerce.eCommercePurchases.ProductId

1. Seleziona **Avanti**.

1. Stabilire la relazione tra l'entità **eCommercePurchases: eCommerce** e **eCommerceContacts : eCommerce**.

1. Il passaggio **Dati aggiuntivi (facoltativo)** consente di aggiungere più dati sull'attività del cliente. Questi dati possono aiutare a ottenere maggiori informazioni sulle interazioni dei clienti con la tua attività, che possono contribuire al CLV. L'aggiunta di interazioni chiave con i clienti come i registri web, i registri servizio clienti o la cronologia dei programmi a premi può migliorare l'accuratezza delle previsioni. Seleziona **Aggiungi dati** per includere più dati sull'attività del cliente.

1. Aggiungi l'entità dell'attività del cliente e mappa i nomi dei suoi campi ai campi corrispondenti richiesti dal modello:
   - Entità dell'attività del cliente: Recensioni: Sito Web
   - Chiave primaria: Website.Reviews.ReviewId
   - Timestamp: Website.Reviews.ReviewDate
   - Evento (nome attività): Website.Reviews.ActivityTypeDisplay
   - Dettagli (importo o valore): Website.Reviews.ReviewRating

1. Seleziona **Avanti** e configura l'attività e la relazione tra i dati della transazione e i dati del cliente:  
   - Tipo di impegno: scegli esistente
   - Etichetta impegno: Recensione
   - Etichetta corrispondente: Website.Reviews.UserId
   - Entità cliente: eCommerceContacts:eCommerce
   - Relazione: WebsiteReviews

1. Seleziona **Avanti** per impostare la pianificazione del modello.

   Il modello deve essere addestrato regolarmente per apprendere nuovi modelli quando vengono inseriti nuovi dati. Per questo esempio, scegli **Mensile**.

1. Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**.

## <a name="task-4---review-model-results-and-explanations"></a>Attività 4: esaminare i risultati e le spiegazioni del modello

Lascia che il modello termini il training e la valutazione dei dati. Successivamente, puoi rivedere i risultati e le spiegazioni del modello CLV. Per ulteriori informazioni, vedi [Esaminare lo stato e i risultati di una previsione](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Attività 5 - Creare un segmento di clienti di alto valore

L'esecuzione del modello crea una nuova entità, che è elencata in **Dati** > **Entità**. È possibile creare un nuovo segmento di clienti in base all'entità creata dal modello.

1. Vai a **Segmenti**. 

1. Seleziona **Nuovo** e scegli **Crea a partire da** > **Intelligenza**.

   ![Creazione di un segmento con l'output del modello.](media/segment-intelligence.png)

1. Seleziona l'entità **OOBeCommerceCLVPrediction** e definisci il segmento:
  - Campo: CLVScore
  - Operatore: maggiore di
  - Valore: 1500

1. Seleziona **Recensione** e **Salva** il segmento.

Ora hai un segmento che identifica i clienti che si prevede genereranno più di $1.500 di entrate nei prossimi 12 mesi. Questo segmento viene aggiornato dinamicamente se vengono inseriti più dati.

Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).