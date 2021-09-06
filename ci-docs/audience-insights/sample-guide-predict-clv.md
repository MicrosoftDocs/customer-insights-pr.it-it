---
title: Guida di esempio previsione valore di durata del cliente
description: Usa questa guida di esempio per provare il modello di previsione di Customer Lifetime Value (CLV).
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 705e159f348e876f8a2a0ad3481608c6dd380df3dd74d7e5dba9dd3bebe25e52
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029496"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guida di esempio previsione di Customer Lifetime Value (CLV)

Questa guida ti spiegherà un esempio end-to-end della previsione Customer Lifetime Value (CLV) in Customer Insights utilizzando dati di esempio.

## <a name="scenario"></a>Scenario

Contoso è un'azienda che produce caffè e macchine da caffè di alta qualità. Vendono i prodotti attraverso il proprio sito Web Contoso di vendita di caffè. L'azienda vuole capire il valore (ricavo) che i propri clienti possono generare nei prossimi 12 mesi. Conoscere il valore atteso dei loro clienti nei prossimi 12 mesi li aiuterà a dirigere le loro iniziative di marketing su clienti di alto valore.

## <a name="prerequisites"></a>Prerequisiti

- Almeno [Autorizzazioni di tipo Collaboratore](permissions.md) nelle informazioni dettagliate.
- Ti consigliamo di implementare i seguenti passaggi [in un nuovo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Attività 1: inserire dati

Rivedere gli articoli [sull'inserimento dati](data-sources.md) e [l'importazione di origini dati utilizzando i connettori Power Query](connect-power-query.md). Le seguenti informazioni presuppongono che tu conosca l'inserimento dati in generale.

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

Dopo aver importato i dati, iniziamo il processo di unificazione dei dati per creare un profilo cliente unificato. Per ulteriori informazioni, vedi [Unificazione dei dati](data-unification.md).

### <a name="map"></a>Mapping

1. Dopo l'inserimento dei dati, esegui il mapping dei dati di eCommerce e Fedeltà ai tipi di dati comuni. Vai a **Dati** > **Unifica** > **Mapping**.

1. Seleziona le entità che rappresentano il profilo cliente, ovvero **eCommerceContacts** e **loyCustomers**. Selezionare quindi **Applica**.

   ![Unificare le origini dati di e-commerce e fedeltà.](media/unify-ecommerce-loyalty.png)

1. Seleziona **ContactId** come chiave primaria per **eCommerceContacts** e **LoyaltyID** come chiave primaria per **loyCustomers**.

   ![Unifica LoyaltyId come chiave primaria.](media/unify-loyaltyid.png)

1. Seleziona **Salva**.

### <a name="match"></a>Corrispondenza

1. Passa alla scheda **Corrispondenza** e seleziona **Imposta ordine**.

1. Nell'elenco a discesa **Principale** scegli **eCommerceContacts : eCommerce** come fonte primaria e includi tutti i record.

1. Nell'elenco a discesa **Entità 2** scegli **loyCustomers : LoyaltyScheme** e includi tutti i record.

   ![Unificare la corrispondenza di eCommerce e Fedeltà.](media/unify-match-order.png)

1. Seleziona **Aggiungi regola**

1. Aggiungi la prima condizione utilizzando FullName.

   - Per eCommerceContacts seleziona **FullName** nel menu a discesa.
   - Per loyCustomers seleziona **FullName** nel menu a discesa.
   - Seleziona il menu a discesa **Normalizza** e scegli **Tipo (telefono, nome, indirizzo, ...)**.
   - Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.

1. Immetti il nome **FullName, Email** per la nuova regola.

   - Aggiungi una seconda condizione per l'indirizzo e-mail selezionado **Aggiungi condizione**
   - Per l'entità eCommerceContacts, scegli **E-mail** nell'elenco a discesa.
   - Per l'entità loyCustomers, scegli **E-mail** nell'elenco a discesa.
   - Lascia vuoto il campo Normalizza.
   - Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.

   ![Unificare la regola di corrispondenza per nome ed e-mail.](media/unify-match-rule.png)

1. Seleziona **Fatto**.

1. Seleziona **Salva** ed **Esegui**.

### <a name="merge"></a>Unione

1. Vai alla scheda **Unione**.

1. In **ContactId** per l'entità **loyCustomers**, cambia il nome visualizzato in **ContactIdLOYALTY** per differenziarlo dagli altri ID inseriti.

   ![Rinominare contactid dall'ID del programma di fedeltà.](media/unify-merge-contactid.png)

1. Seleziona **Salva** ed **Esegui processi di unione e downstream**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Attività 3 - Configurare la previsione di Customer Lifetime Value

Con i profili cliente unificati in atto, ora possiamo eseguire la previsione Customer Lifetime Value. Per informazioni dettagliate, vedere [Previsione di Customer Lifetime Value (anteprima)](predict-customer-lifetime-value.md).

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
