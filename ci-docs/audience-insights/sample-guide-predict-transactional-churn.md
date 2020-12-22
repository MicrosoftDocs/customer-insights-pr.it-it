---
title: Guida di esempio per una previsione di abbandono transazionale
description: Usa questa guida di esempio per provare il modello di previsione di abbandono transazionale predefinito.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 055708ed3f9f468cad83ecf976a460814bf05199
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643598"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="1c044-103">Guida di esempio per una previsione di abbandono transazionale (anteprima)</span><span class="sxs-lookup"><span data-stu-id="1c044-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="1c044-104">In questa guida viene illustrato un esempio completo di previsione di abbandono transazionale in Customer Insights che utilizza i dati di esempio forniti di seguito.</span><span class="sxs-lookup"><span data-stu-id="1c044-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="1c044-105">Tutti i dati utilizzati in questa guida non sono dati cliente reali e fanno parte del set di dati di Contoso disponibile nell'ambiente *Demo* dell'abbonamento a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1c044-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="1c044-106">Scenario</span><span class="sxs-lookup"><span data-stu-id="1c044-106">Scenario</span></span>

<span data-ttu-id="1c044-107">Contoso è un'azienda che produce caffè e macchine da caffè di alta qualità, in vendita sul sito Web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="1c044-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="1c044-108">Lo scopo dell'azienda è sapere quali clienti che acquistano regolarmente i loro prodotti smetteranno di essere clienti attivi nei prossimi 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="1c044-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="1c044-109">Sapere quali dei loro clienti **rischiano di essere persi**, può aiutarli a ridurre gli sforzi di marketing concentrandosi sulla fidelizzazione degli stessi.</span><span class="sxs-lookup"><span data-stu-id="1c044-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1c044-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1c044-110">Prerequisites</span></span>

- <span data-ttu-id="1c044-111">Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1c044-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1c044-112">Ti consigliamo di implementare i seguenti passaggi [in un nuovo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="1c044-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="1c044-113">Attività 1: inserire dati</span><span class="sxs-lookup"><span data-stu-id="1c044-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="1c044-114">Consulta in particolare gli articoli [sull'inserimento dati](data-sources.md) e sull'[importazione di origini dati utilizzando i connettori Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1c044-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="1c044-115">Le seguenti informazioni presuppongono che tu conosca l'inserimento dati in generale.</span><span class="sxs-lookup"><span data-stu-id="1c044-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="1c044-116">Inserire dati cliente dalla piattaforma di eCommerce</span><span class="sxs-lookup"><span data-stu-id="1c044-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="1c044-117">Crea un origine dati denominata **eCommerce**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1c044-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1c044-118">Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="1c044-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="1c044-119">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="1c044-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1c044-120">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="1c044-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1c044-121">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="1c044-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1c044-122">**CreatedOn**: data/ora/fuso orario</span><span class="sxs-lookup"><span data-stu-id="1c044-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="1c044-123">![Trasformare la data di nascita in data](media/ecommerce-dob-date.PNG "Trasformare la data di nascita in data")</span><span class="sxs-lookup"><span data-stu-id="1c044-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="1c044-124">Nel campo "Nome" nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="1c044-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="1c044-125">Salva l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1c044-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="1c044-126">Inserire dati sugli acquisti online</span><span class="sxs-lookup"><span data-stu-id="1c044-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="1c044-127">Aggiungi un altro set di dati alla stessa origine dati **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="1c044-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="1c044-128">Scegli di nuovo il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1c044-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="1c044-129">Immetti l'URL per i dati degli **Acquisti online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="1c044-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="1c044-130">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="1c044-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1c044-131">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="1c044-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1c044-132">**PurchasedOn**: data/ora</span><span class="sxs-lookup"><span data-stu-id="1c044-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="1c044-133">**TotalPrice**: valuta</span><span class="sxs-lookup"><span data-stu-id="1c044-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="1c044-134">Nel campo "Nome" nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="1c044-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="1c044-135">Salva l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1c044-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="1c044-136">Inserire dati cliente dallo schema di fidelizzazione</span><span class="sxs-lookup"><span data-stu-id="1c044-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="1c044-137">Crea un origine dati denominata **LoyaltyScheme**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1c044-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1c044-138">Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="1c044-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="1c044-139">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="1c044-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1c044-140">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="1c044-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1c044-141">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="1c044-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1c044-142">**RewardsPoints**: numero intero</span><span class="sxs-lookup"><span data-stu-id="1c044-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="1c044-143">**CreatedOn**: date/ora</span><span class="sxs-lookup"><span data-stu-id="1c044-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="1c044-144">Nel campo "Nome" nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1c044-144">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="1c044-145">Salva l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1c044-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="1c044-146">Attività 2: unificare i dati</span><span class="sxs-lookup"><span data-stu-id="1c044-146">Task 2 - Data unification</span></span>

<span data-ttu-id="1c044-147">Dopo aver inserito i dati, iniziamo il processo di **Mapping, corrispondenza, unione** per creare un profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="1c044-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="1c044-148">Per ulteriori informazioni, vedi [Unificazione dei dati](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1c044-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="1c044-149">Mapping</span><span class="sxs-lookup"><span data-stu-id="1c044-149">Map</span></span>

1. <span data-ttu-id="1c044-150">Dopo l'inserimento dei dati, esegui il mapping dei dati di eCommerce e Fedeltà ai tipi di dati comuni.</span><span class="sxs-lookup"><span data-stu-id="1c044-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="1c044-151">Vai a **Dati** > **Unifica** > **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="1c044-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="1c044-152">Seleziona le entità che rappresentano il profilo cliente, ovvero **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1c044-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Unificare le origini dati di e-commerce e fedeltà.":::

1. <span data-ttu-id="1c044-154">Seleziona **ContactId** come chiave primaria per **eCommerceContacts** e **LoyaltyID** come chiave primaria per **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1c044-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifica LoyaltyId come chiave primaria.":::

### <a name="match"></a><span data-ttu-id="1c044-156">Corrispondenza</span><span class="sxs-lookup"><span data-stu-id="1c044-156">Match</span></span>

1. <span data-ttu-id="1c044-157">Passa alla scheda **Corrispondenza** e seleziona **Imposta ordine**.</span><span class="sxs-lookup"><span data-stu-id="1c044-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="1c044-158">Nell'elenco a discesa **Primaria**, scegli **eCommerceContacts : eCommerce** come origine primaria e includi tutti i record.</span><span class="sxs-lookup"><span data-stu-id="1c044-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="1c044-159">Nell'elenco a discesa **Entità 2**, scegli **loyCustomers : LoyaltyScheme** e includi tutti i record.</span><span class="sxs-lookup"><span data-stu-id="1c044-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unificare la corrispondenza di eCommerce e Fedeltà.":::

1. <span data-ttu-id="1c044-161">Seleziona **Crea una nuova regola**</span><span class="sxs-lookup"><span data-stu-id="1c044-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="1c044-162">Aggiungi la prima condizione utilizzando FullName.</span><span class="sxs-lookup"><span data-stu-id="1c044-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="1c044-163">Per eCommerceContacts seleziona **FullName** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1c044-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1c044-164">Per loyCustomers seleziona **FullName** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1c044-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1c044-165">Seleziona l'elenco a discesa **Normalizza** e scegli **Tipo (telefono, nome, indirizzo...)**.</span><span class="sxs-lookup"><span data-stu-id="1c044-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="1c044-166">Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.</span><span class="sxs-lookup"><span data-stu-id="1c044-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="1c044-167">Immetti il nome **FullName, Email** per la nuova regola.</span><span class="sxs-lookup"><span data-stu-id="1c044-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="1c044-168">Aggiungi una seconda condizione per l'indirizzo e-mail selezionado **Aggiungi condizione**</span><span class="sxs-lookup"><span data-stu-id="1c044-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="1c044-169">Per l'entità eCommerceContacts, scegli **E-mail** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="1c044-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="1c044-170">Per l'entità loyCustomers, scegli **E-mail** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="1c044-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="1c044-171">Lascia vuoto il campo Normalizza.</span><span class="sxs-lookup"><span data-stu-id="1c044-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="1c044-172">Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.</span><span class="sxs-lookup"><span data-stu-id="1c044-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificare la regola di corrispondenza per nome ed e-mail.":::

7. <span data-ttu-id="1c044-174">Seleziona **Salva** ed **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="1c044-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="1c044-175">Unione</span><span class="sxs-lookup"><span data-stu-id="1c044-175">Merge</span></span>

1. <span data-ttu-id="1c044-176">Vai alla scheda **Unione**.</span><span class="sxs-lookup"><span data-stu-id="1c044-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="1c044-177">In **ContactId** per l'entità **loyCustomers**, cambia il nome visualizzato in **ContactIdLOYALTY** per differenziarlo dagli altri ID inseriti.</span><span class="sxs-lookup"><span data-stu-id="1c044-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Rinominare contactid dall'ID del programma di fedeltà.":::

1. <span data-ttu-id="1c044-179">Seleziona **Salva** ed **Esegui** per avviare il processo di unione.</span><span class="sxs-lookup"><span data-stu-id="1c044-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="1c044-180">Attività 3: configurare la previsione di abbandono transazionale</span><span class="sxs-lookup"><span data-stu-id="1c044-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="1c044-181">Dopo aver unificato i profili cliente, possiamo eseguire la previsione dell'abbandono dell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1c044-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="1c044-182">Per i passaggi dettagliati, vedi [Previsione di abbandono dell'abbonamento (anteprima)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="1c044-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="1c044-183">Vai a **Intelligenza** > **Scopri** e seleziona per utilizzare il **Modello di abbandono dei clienti**.</span><span class="sxs-lookup"><span data-stu-id="1c044-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="1c044-184">Seleziona l'opzione **Transazionale** e seleziona **Inizia**.</span><span class="sxs-lookup"><span data-stu-id="1c044-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="1c044-185">Assegna al modello il nome **Previsione abbandono abbonamento eCommerce OOB** e all'entità il nome **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="1c044-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="1c044-186">Definisci due condizioni per il modello di abbandono:</span><span class="sxs-lookup"><span data-stu-id="1c044-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="1c044-187">**Finestra di previsione**: **almeno 60** giorni.</span><span class="sxs-lookup"><span data-stu-id="1c044-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="1c044-188">Questa impostazione definisce la durata del periodo di previsione dell'abbandono dei clienti.</span><span class="sxs-lookup"><span data-stu-id="1c044-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="1c044-189">**Definizione abbandono**: **almeno 60** giorni.</span><span class="sxs-lookup"><span data-stu-id="1c044-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="1c044-190">La durata senza acquisto dopo la quale un cliente è considerato come perso.</span><span class="sxs-lookup"><span data-stu-id="1c044-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Selezionare Finestra di previsione e Definizione abbandono.":::

1. <span data-ttu-id="1c044-192">Seleziona **Cronologia acquisti (obbligatoria)** e seleziona **Aggiungi dati** per la cronologia dell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1c044-192">Select **Purchase History (required)** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="1c044-193">Aggiungi l'entità **eCommercePurchases : eCommerce** ed esegui il mapping dei campi di eCommerce ai campi corrispondenti richiesti dal modello.</span><span class="sxs-lookup"><span data-stu-id="1c044-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="1c044-194">Associa l'entità **eCommercePurchases : eCommerce** a **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="1c044-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Associare le entità di e-Commerce.":::

1. <span data-ttu-id="1c044-196">Seleziona **Avanti** per impostare la pianificazione del modello.</span><span class="sxs-lookup"><span data-stu-id="1c044-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="1c044-197">È necessario eseguire regolarmente il training del modello affinché apprenda nuovi modelli quando vengono inseriti nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="1c044-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="1c044-198">Per questo esempio, seleziona **Mensile**.</span><span class="sxs-lookup"><span data-stu-id="1c044-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="1c044-199">Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**.</span><span class="sxs-lookup"><span data-stu-id="1c044-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="1c044-200">Attività 4: esaminare i risultati e le spiegazioni del modello</span><span class="sxs-lookup"><span data-stu-id="1c044-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="1c044-201">Lascia che il modello termini il training e la valutazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="1c044-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="1c044-202">Ora puoi esaminare le spiegazioni del modello di abbandono dell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1c044-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="1c044-203">Per ulteriori informazioni, vedi [Esaminare lo stato e i risultati di una previsione](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="1c044-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="1c044-204">Attività 5: creare un segmento di clienti ad alto rischio di abbandono</span><span class="sxs-lookup"><span data-stu-id="1c044-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="1c044-205">L'esecuzione del modello di produzione crea una nuova entità visibile in **Dati** > **Entità**.</span><span class="sxs-lookup"><span data-stu-id="1c044-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="1c044-206">Puoi creare un nuovo segmento basato sull'entità creata dal modello.</span><span class="sxs-lookup"><span data-stu-id="1c044-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="1c044-207">Vai a **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="1c044-207">Go to **Segments**.</span></span> <span data-ttu-id="1c044-208">Seleziona **Nuovo** e scegli **Crea a partire da** > **Intelligenza**.</span><span class="sxs-lookup"><span data-stu-id="1c044-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creazione di un segmento con l'output del modello.":::

1. <span data-ttu-id="1c044-210">Seleziona l'endpoint **OOBSubscriptionChurnPrediction** e definisci il segmento:</span><span class="sxs-lookup"><span data-stu-id="1c044-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="1c044-211">Campo: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="1c044-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="1c044-212">Operatore: maggiore di</span><span class="sxs-lookup"><span data-stu-id="1c044-212">Operator: greater than</span></span>
   - <span data-ttu-id="1c044-213">Valore: 0,6</span><span class="sxs-lookup"><span data-stu-id="1c044-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Impostare il segmento di abbandono dell'abbonamento.":::

<span data-ttu-id="1c044-215">Ora hai un segmento che viene aggiornato dinamicamente e che identifica i clienti ad alto rischio di abbandono per questa attività di abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1c044-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="1c044-216">Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1c044-216">For more information, see [Create and manage segments](segments.md).</span></span>
