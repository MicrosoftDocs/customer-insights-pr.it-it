---
title: Guida di esempio previsione di Customer Lifetime Value (CLV)
description: Usa questa guida di esempio per provare il modello di previsione di Customer Lifetime Value (CLV).
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609643"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guida di esempio previsione di Customer Lifetime Value (CLV)

Questa guida ti spiegherà un esempio end-to-end della previsione Customer Lifetime Value (CLV) in Customer Insights usando dati di esempio. Ti consigliamo di testare questa previsione [in un nuovo ambiente](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso è un'azienda che produce caffè e macchine per caffè di alta qualità. Vende i prodotti tramite il sito Web di Contoso Coffee. L'azienda vuole capire il valore (ricavo) che i propri clienti possono generare nei prossimi 12 mesi. Conoscere il valore atteso dei loro clienti nei prossimi 12 mesi li aiuterà a dirigere le loro iniziative di marketing su clienti di alto valore.

## <a name="prerequisites"></a>Prerequisiti

- [Autorizzazioni di collaboratore](permissions.md) come minimo.

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

1. **Salva** l'origine dati.

### <a name="ingest-online-purchase-data"></a>Inserire dati sugli acquisti online

1. Aggiungi un altro set di dati alla stessa origine dati **eCommerce**. Scegli di nuovo il connettore **Testo/CSV**.

1. Immetti l'URL per i dati degli **Acquisti online** https://aka.ms/ciadclassonline.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazione**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **PurchasedOn**: data/ora
   - **TotalPrice**: valuta

1. Nel campo **Nome** nel riquadro laterale, rinomina l'origine dati in **eCommercePurchases**.

1. **Salva** l'origine dati.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inserire dati cliente dallo schema di fidelizzazione

1. Crea un origine dati denominata **LoyaltyScheme** e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per i clienti fedeli https://aka.ms/ciadclasscustomerloyalty.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazione**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **DateOfBirth**: data
   - **RewardsPoints**: numero intero
   - **CreatedOn**: date/ora

1. Nel campo **Nome** nel riquadro a destra, rinomina l'origine dati in **loyCustomers**.

1. **Salva** l'origine dati.

### <a name="ingest-customer-data-from-website-reviews"></a>Inserire dati cliente delle recensioni sul sito web

1. Crea un origine dati denominata **Website** e seleziona il connettore **Testo/CSV**.

1. Immetti l'URL per le recensioni del sito Web https://aka.ms/CI-ILT/WebReviews.

1. Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazione**.

1. Aggiorna il tipo di dati per le colonne elencate di seguito:
   - **ReviewRating**: numero decimale
   - **ReviewDate**: data

1. Nel campo **Nome** nel riquadro di destra, rinomina la tua origine dati in **Recensioni**.

1. **Salva** l'origine dati.

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

1. Aggiungi un'altra attività e mappa i nomi dei suoi campi ai campi corrispondenti:
   - **Entità attività**: Reviews:Website
   - **Chiave primaria**: ReviewId
   - **Timestamp**: ReviewDate
   - **Attività evento**: ActivityTypeDisplay
   - **Dettagli aggiuntivi**: ReviewRating
   - **Tipo attività**: Review

1. Esegui l'attività.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Attività 4: configurare la previsione di Customer Lifetime Value

Con i profili cliente unificati definiti e l'attività creata, ora possiamo eseguire la previsione Customer Lifetime Value (CLV). Per i passaggi dettagliati, vedi [Previsione del valore durata cliente](predict-customer-lifetime-value.md).

1. Vai a **Intelligence** > **Previsioni**.

1. Nella scheda **Crea** seleziona **Usa modello** nel riquadro **Valore di durata del cliente**.

1. Seleziona **Richiedi una demo**.

1. Dai un nome al modello **Previsione OOB eCommerce CLV** e l'entità di output **OOBeCommerceCLVPrediction**.

1. Definisci le preferenze del modello:
   - **Periodo di tempo della previsione**: **12 mesi o 1 anno** per definire quanto lontano nel futuro prevedere il CLV.
   - **Clienti attivi**: **Consenti al modello di calcolare l'intervallo di acquisto** permette al modello di calcolare l'intervallo di tempo in cui un cliente deve aver avuto almeno una transazione per essere considerato attivo.
   - **Cliente di valore elevato**: definire manualmente i clienti di valore elevato come **primo 30% di clienti attivi**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Passaggio delle preferenze nell'esperienza guidata per il modello CLV.":::

1. Selezionare **Avanti**.

1. Nel passaggio **Dati richiesti**, seleziona **Aggiungi dati** per fornire i dati della cronologia delle transazioni.

    :::image type="content" source="media/clv-model-required.png" alt-text="Aggiungi il passaggio per i dati obbligatori nell'esperienza guidata per il modello CLV.":::

1. Seleziona **SalesOrderLine** e l'entità eCommercePurchases, quindi seleziona **Avanti**. I dati richiesti vengono compilati automaticamente dall'attività. Seleziona **Salva** e quindi **Avanti**.

1. Il passaggio **Dati aggiuntivi (facoltativo)** consente di aggiungere più dati sull'attività del cliente per ottenere un maggior numero di informazioni dettagliate per le interazioni dei clienti. Per questo esempio, seleziona **Aggiungi dati** e aggiungi l'attività di recensione Web.

1. Selezionare **Avanti**.

1. Nel passaggio **Aggiornamenti dei dati** seleziona **Mensile** per la pianificazione del modello.

1. Selezionare **Avanti**.

1. Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**.

## <a name="task-5---review-model-results-and-explanations"></a>Attività 5: esaminare i risultati e le spiegazioni del modello

Lascia che il modello termini il training e la valutazione dei dati. Rivedi i [risultati e le spiegazioni del modello CLV](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Attività 6: creare un segmento di clienti di alto valore

L'esecuzione del modello crea una nuova entità, che è elencata in **Dati** > **Entità**. È possibile creare un nuovo segmento di clienti in base all'entità creata dal modello.

1. Nella pagina dei risultati, seleziona **Crea segmento**.

1. Crea una regola usando l'entità **OOBeCommerceCLVPrediction** e definisci il segmento:
   - **Campo**: CLVScore
   - **Operatore**: maggiore di
   - **Valore**: 1500

1. Seleziona **Salva** e quindi **Esegui** il segmento.

Ora hai un segmento che identifica i clienti che si prevede genereranno più di $1.500 di entrate nei prossimi 12 mesi. Questo segmento viene aggiornato dinamicamente se vengono inseriti più dati. Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).

> [!TIP]
> Puoi anche creare un segmento per un modello previsione dalla pagina **Segmenti** selezionando **Nuovo** e scegliendo **Crea da** > **Intelligence**. Per maggiori informazioni, vedi [Creare un nuovo segmento con segmenti rapidi](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
