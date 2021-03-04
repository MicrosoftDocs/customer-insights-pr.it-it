---
title: Guida di esempio per la previsione di raccomandazioni sui prodotti
description: Usa questa guida di esempio per provare il modello di previsione di raccomandazioni sui prodotti predefinito.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270504"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="3294a-103">Guida di esempio per la previsione di raccomandazioni sui prodotti (anteprima)</span><span class="sxs-lookup"><span data-stu-id="3294a-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="3294a-104">In questa guida viene illustrato un esempio completo di previsione di raccomandazioni sui prodotti che utilizza i dati di esempio forniti di seguito.</span><span class="sxs-lookup"><span data-stu-id="3294a-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="3294a-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="3294a-105">Scenario</span></span>

<span data-ttu-id="3294a-106">Contoso è un'azienda che produce caffè e macchine da caffè di alta qualità, in vendita sul sito Web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="3294a-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="3294a-107">Il suo obiettivo è capire quali prodotti dovrebbe consigliare ai clienti ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="3294a-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="3294a-108">Sapere cosa i clienti hanno maggiore **probabilità di acquistare** può aiutare a risparmiare sforzi di marketing concentrandosi su articoli specifici.</span><span class="sxs-lookup"><span data-stu-id="3294a-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3294a-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3294a-109">Prerequisites</span></span>

- <span data-ttu-id="3294a-110">Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3294a-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="3294a-111">Ti consigliamo di implementare i seguenti passaggi [in un nuovo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="3294a-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="3294a-112">Attività 1: inserire dati</span><span class="sxs-lookup"><span data-stu-id="3294a-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="3294a-113">Consulta in particolare gli articoli [sull'inserimento dati](data-sources.md) e sull'[importazione di origini dati utilizzando i connettori Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="3294a-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="3294a-114">Le seguenti informazioni presuppongono che tu conosca l'inserimento dati in generale.</span><span class="sxs-lookup"><span data-stu-id="3294a-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="3294a-115">Inserire dati cliente dalla piattaforma di eCommerce</span><span class="sxs-lookup"><span data-stu-id="3294a-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="3294a-116">Crea un origine dati denominata **eCommerce**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="3294a-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3294a-117">Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="3294a-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="3294a-118">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="3294a-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3294a-119">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="3294a-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3294a-120">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="3294a-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="3294a-121">**CreatedOn**: data/ora/fuso orario</span><span class="sxs-lookup"><span data-stu-id="3294a-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Trasformare la data di nascita in data.":::

5. <span data-ttu-id="3294a-123">Nel campo "Nome" nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="3294a-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="3294a-124">**Salva** l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3294a-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="3294a-125">Inserire dati sugli acquisti online</span><span class="sxs-lookup"><span data-stu-id="3294a-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="3294a-126">Aggiungi un altro set di dati alla stessa origine dati **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="3294a-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="3294a-127">Scegli di nuovo il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="3294a-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="3294a-128">Immetti l'URL per i dati degli **Acquisti online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="3294a-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="3294a-129">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="3294a-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3294a-130">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="3294a-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3294a-131">**PurchasedOn**: data/ora</span><span class="sxs-lookup"><span data-stu-id="3294a-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="3294a-132">**TotalPrice**: valuta</span><span class="sxs-lookup"><span data-stu-id="3294a-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="3294a-133">Nel campo **Nome** nel riquadro laterale, cambia il nome dell'origine dati da **Query** a **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="3294a-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="3294a-134">Salva l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3294a-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="3294a-135">Inserire dati cliente dallo schema di fidelizzazione</span><span class="sxs-lookup"><span data-stu-id="3294a-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="3294a-136">Crea un origine dati denominata **LoyaltyScheme**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="3294a-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3294a-137">Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="3294a-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="3294a-138">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="3294a-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3294a-139">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="3294a-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3294a-140">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="3294a-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="3294a-141">**RewardsPoints**: numero intero</span><span class="sxs-lookup"><span data-stu-id="3294a-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="3294a-142">**CreatedOn**: date/ora</span><span class="sxs-lookup"><span data-stu-id="3294a-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="3294a-143">Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3294a-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="3294a-144">Salva l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3294a-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="3294a-145">Attività 2: unificare i dati</span><span class="sxs-lookup"><span data-stu-id="3294a-145">Task 2 - Data unification</span></span>

<span data-ttu-id="3294a-146">Dopo aver inserito i dati, iniziamo il processo di **Mapping, corrispondenza, unione** per creare un profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="3294a-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="3294a-147">Per ulteriori informazioni, vedi [Unificazione dei dati](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="3294a-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="3294a-148">Mapping</span><span class="sxs-lookup"><span data-stu-id="3294a-148">Map</span></span>

1. <span data-ttu-id="3294a-149">Dopo l'inserimento dei dati, esegui il mapping dei dati di eCommerce e Fedeltà ai tipi di dati comuni.</span><span class="sxs-lookup"><span data-stu-id="3294a-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="3294a-150">Vai a **Dati** > **Unifica** > **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="3294a-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="3294a-151">Seleziona le entità che rappresentano il profilo cliente, ovvero **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3294a-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![Unificare le origini dati di e-commerce e fedeltà.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="3294a-153">Seleziona **ContactId** come chiave primaria per **eCommerceContacts** e **LoyaltyID** come chiave primaria per **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3294a-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unifica LoyaltyId come chiave primaria.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="3294a-155">Corrispondenza</span><span class="sxs-lookup"><span data-stu-id="3294a-155">Match</span></span>

1. <span data-ttu-id="3294a-156">Passa alla scheda **Corrispondenza** e seleziona **Imposta ordine**.</span><span class="sxs-lookup"><span data-stu-id="3294a-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="3294a-157">Nell'elenco a discesa **Primaria**, scegli **eCommerceContacts : eCommerce** come origine primaria e includi tutti i record.</span><span class="sxs-lookup"><span data-stu-id="3294a-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="3294a-158">Nell'elenco a discesa **Entità 2**, scegli **loyCustomers : LoyaltyScheme** e includi tutti i record.</span><span class="sxs-lookup"><span data-stu-id="3294a-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unificare la corrispondenza di eCommerce e Fedeltà.](media/unify-match-order.png)

4. <span data-ttu-id="3294a-160">Seleziona **Crea una nuova regola**</span><span class="sxs-lookup"><span data-stu-id="3294a-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="3294a-161">Aggiungi la prima condizione utilizzando FullName.</span><span class="sxs-lookup"><span data-stu-id="3294a-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="3294a-162">Per eCommerceContacts seleziona **FullName** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3294a-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="3294a-163">Per loyCustomers seleziona **FullName** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3294a-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="3294a-164">Seleziona l'elenco a discesa **Normalizza** e scegli **Tipo (telefono, nome, indirizzo...)**.</span><span class="sxs-lookup"><span data-stu-id="3294a-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="3294a-165">Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.</span><span class="sxs-lookup"><span data-stu-id="3294a-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="3294a-166">Immetti il nome **FullName, Email** per la nuova regola.</span><span class="sxs-lookup"><span data-stu-id="3294a-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="3294a-167">Aggiungi una seconda condizione per l'indirizzo e-mail selezionado **Aggiungi condizione**</span><span class="sxs-lookup"><span data-stu-id="3294a-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="3294a-168">Per l'entità eCommerceContacts, scegli **E-mail** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="3294a-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="3294a-169">Per l'entità loyCustomers, scegli **E-mail** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="3294a-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="3294a-170">Lascia vuoto il campo Normalizza.</span><span class="sxs-lookup"><span data-stu-id="3294a-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="3294a-171">Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.</span><span class="sxs-lookup"><span data-stu-id="3294a-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unificare la regola di corrispondenza per nome ed e-mail.](media/unify-match-rule.png)

7. <span data-ttu-id="3294a-173">Seleziona **Salva** ed **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="3294a-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="3294a-174">Unione</span><span class="sxs-lookup"><span data-stu-id="3294a-174">Merge</span></span>

1. <span data-ttu-id="3294a-175">Vai alla scheda **Unione**.</span><span class="sxs-lookup"><span data-stu-id="3294a-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="3294a-176">In **ContactId** per l'entità **loyCustomers**, cambia il nome visualizzato in **ContactIdLOYALTY** per differenziarlo dagli altri ID inseriti.</span><span class="sxs-lookup"><span data-stu-id="3294a-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Rinominare contactid dall'ID del programma di fedeltà.](media/unify-merge-contactid.png)

1. <span data-ttu-id="3294a-178">Seleziona **Salva** ed **Esegui** per avviare il processo di unione.</span><span class="sxs-lookup"><span data-stu-id="3294a-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="3294a-179">Attività 3: configurare la previsione di raccomandazioni sui prodotti</span><span class="sxs-lookup"><span data-stu-id="3294a-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="3294a-180">Dopo aver unificato i profili cliente, possiamo eseguire la previsione dell'abbandono dell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="3294a-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="3294a-181">Vai a **Intelligenza** > **Previsione** e scegli **Raccomandazioni prodotto**.</span><span class="sxs-lookup"><span data-stu-id="3294a-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="3294a-182">Seleziona **Operazioni preliminari**.</span><span class="sxs-lookup"><span data-stu-id="3294a-182">Select **Get started**.</span></span>

1. <span data-ttu-id="3294a-183">Nomina il modello **Modello di previsione di raccomandazioni sui prodotti predefinito** e l'entità di output **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="3294a-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="3294a-184">Definisci tre condizioni per il modello:</span><span class="sxs-lookup"><span data-stu-id="3294a-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="3294a-185">**Numero di prodotti** : Imposta questo valore su **5**.</span><span class="sxs-lookup"><span data-stu-id="3294a-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="3294a-186">Questa impostazione definisce quanti prodotti desideri consigliare ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="3294a-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="3294a-187">**Suggerire prodotti acquistati di recente dai clienti** : Seleziona **Sì** per indicare che desideri includere prodotti nella raccomandazione che i tuoi clienti hanno acquistato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3294a-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="3294a-188">**Finestra per guardare indietro:** Seleziona almeno **365 giorni**.</span><span class="sxs-lookup"><span data-stu-id="3294a-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="3294a-189">Questa impostazione definisce fino a quanto tempo indietro il modello esaminerà l'impegno del cliente per utilizzarlo come input per le raccomandazioni.</span><span class="sxs-lookup"><span data-stu-id="3294a-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferenze del modello di raccomandazione sui prodotti.":::

1. <span data-ttu-id="3294a-191">Seleziona **Dati obbligatori** e seleziona **Aggiungi dati** per la cronologia degli acquisti.</span><span class="sxs-lookup"><span data-stu-id="3294a-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="3294a-192">Aggiungi l'entità **eCommercePurchases : eCommerce** ed esegui il mapping dei campi di eCommerce ai campi corrispondenti richiesti dal modello.</span><span class="sxs-lookup"><span data-stu-id="3294a-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="3294a-193">Associa l'entità **eCommercePurchases : eCommerce** a **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="3294a-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Associare le entità di e-Commerce.](media/model-purchase-join.png)

1. <span data-ttu-id="3294a-195">Seleziona **Avanti** per impostare la pianificazione del modello.</span><span class="sxs-lookup"><span data-stu-id="3294a-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="3294a-196">È necessario eseguire regolarmente il training del modello affinché apprenda nuovi modelli quando vengono inseriti nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="3294a-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="3294a-197">Per questo esempio, seleziona **Mensile**.</span><span class="sxs-lookup"><span data-stu-id="3294a-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="3294a-198">Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**.</span><span class="sxs-lookup"><span data-stu-id="3294a-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="3294a-199">Attività 4: esaminare i risultati e le spiegazioni del modello</span><span class="sxs-lookup"><span data-stu-id="3294a-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="3294a-200">Lascia che il modello termini il training e la valutazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3294a-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="3294a-201">Ora puoi esaminare le spiegazioni del modello di raccomandazione dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="3294a-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="3294a-202">Per ulteriori informazioni, vedi [Esaminare lo stato e i risultati di una previsione](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="3294a-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="3294a-203">Attività 5: creare un segmento di prodotti ad acquisto elevato</span><span class="sxs-lookup"><span data-stu-id="3294a-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="3294a-204">L'esecuzione del modello di produzione crea una nuova entità visibile in **Dati** > **Entità**.</span><span class="sxs-lookup"><span data-stu-id="3294a-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="3294a-205">Puoi creare un nuovo segmento basato sull'entità creata dal modello.</span><span class="sxs-lookup"><span data-stu-id="3294a-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="3294a-206">Vai a **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="3294a-206">Go to **Segments**.</span></span> <span data-ttu-id="3294a-207">Seleziona **Nuovo** e scegli **Crea a partire da** > **Intelligenza**.</span><span class="sxs-lookup"><span data-stu-id="3294a-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Creazione di un segmento con l'output del modello.](media/segment-intelligence.png)

1. <span data-ttu-id="3294a-209">Seleziona l'endpoint **OOBProductRecommendationModelPrediction** e definisci il segmento:</span><span class="sxs-lookup"><span data-stu-id="3294a-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="3294a-210">Campo: ProductID</span><span class="sxs-lookup"><span data-stu-id="3294a-210">Field: ProductID</span></span>
   - <span data-ttu-id="3294a-211">Operatore: Valore</span><span class="sxs-lookup"><span data-stu-id="3294a-211">Operator: Value</span></span>
   - <span data-ttu-id="3294a-212">Valore: seleziona i primi tre ID prodotto</span><span class="sxs-lookup"><span data-stu-id="3294a-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Crea un segmento dai risultati del modello.":::

<span data-ttu-id="3294a-214">Ora hai un segmento che viene aggiornato dinamicamente che identifica i clienti che sono più disposti ad acquistare i tre prodotti più consigliati</span><span class="sxs-lookup"><span data-stu-id="3294a-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="3294a-215">Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3294a-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]