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
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129950"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="4b850-103">Guida di esempio previsione di Customer Lifetime Value (CLV)</span><span class="sxs-lookup"><span data-stu-id="4b850-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="4b850-104">Questa guida ti spiegherà un esempio end-to-end della previsione Customer Lifetime Value (CLV) in Customer Insights utilizzando dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="4b850-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="4b850-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="4b850-105">Scenario</span></span>

<span data-ttu-id="4b850-106">Contoso è un'azienda che produce caffè e macchine da caffè di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="4b850-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="4b850-107">Vendono i prodotti attraverso il proprio sito Web Contoso di vendita di caffè.</span><span class="sxs-lookup"><span data-stu-id="4b850-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="4b850-108">L'azienda vuole capire il valore (ricavo) che i propri clienti possono generare nei prossimi 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="4b850-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="4b850-109">Conoscere il valore atteso dei loro clienti nei prossimi 12 mesi li aiuterà a dirigere le loro iniziative di marketing su clienti di alto valore.</span><span class="sxs-lookup"><span data-stu-id="4b850-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4b850-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4b850-110">Prerequisites</span></span>

- <span data-ttu-id="4b850-111">Almeno [Autorizzazioni di tipo Collaboratore](permissions.md) nelle informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="4b850-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="4b850-112">Ti consigliamo di implementare i seguenti passaggi [in un nuovo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="4b850-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="4b850-113">Attività 1: inserire dati</span><span class="sxs-lookup"><span data-stu-id="4b850-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="4b850-114">Rivedere gli articoli [sull'inserimento dati](data-sources.md) e [l'importazione di origini dati utilizzando i connettori Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="4b850-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="4b850-115">Le seguenti informazioni presuppongono che tu conosca l'inserimento dati in generale.</span><span class="sxs-lookup"><span data-stu-id="4b850-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="4b850-116">Inserire dati cliente dalla piattaforma di eCommerce</span><span class="sxs-lookup"><span data-stu-id="4b850-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="4b850-117">Crea un'origine dati denominata **eCommerce**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4b850-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4b850-118">Immetti l'URL per i contatti di eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="4b850-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="4b850-119">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="4b850-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4b850-120">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="4b850-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="4b850-121">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="4b850-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="4b850-122">**CreatedOn**: data/ora/fuso orario</span><span class="sxs-lookup"><span data-stu-id="4b850-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Trasformare la data di nascita in data.":::

1. <span data-ttu-id="4b850-124">Nel campo "Nome" nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="4b850-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="4b850-125">**Salva** l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4b850-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="4b850-126">Inserire dati sugli acquisti online</span><span class="sxs-lookup"><span data-stu-id="4b850-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="4b850-127">Aggiungi un altro set di dati alla stessa origine dati **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="4b850-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="4b850-128">Scegli di nuovo il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4b850-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="4b850-129">Immetti l'URL per i dati degli **Acquisti online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="4b850-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="4b850-130">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="4b850-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4b850-131">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="4b850-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="4b850-132">**PurchasedOn**: data/ora</span><span class="sxs-lookup"><span data-stu-id="4b850-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="4b850-133">**TotalPrice**: valuta</span><span class="sxs-lookup"><span data-stu-id="4b850-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="4b850-134">Nel campo **Nome** nel riquadro laterale, cambia il nome dell'origine dati da **Query** a **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="4b850-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="4b850-135">**Salva** l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4b850-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="4b850-136">Inserire dati cliente dallo schema di fidelizzazione</span><span class="sxs-lookup"><span data-stu-id="4b850-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="4b850-137">Crea un origine dati denominata **LoyaltyScheme**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4b850-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4b850-138">Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="4b850-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="4b850-139">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="4b850-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4b850-140">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="4b850-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="4b850-141">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="4b850-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="4b850-142">**RewardsPoints**: numero intero</span><span class="sxs-lookup"><span data-stu-id="4b850-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="4b850-143">**CreatedOn**: date/ora</span><span class="sxs-lookup"><span data-stu-id="4b850-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="4b850-144">Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4b850-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="4b850-145">**Salva** l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4b850-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="4b850-146">Inserire dati cliente delle recensioni sul sito web</span><span class="sxs-lookup"><span data-stu-id="4b850-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="4b850-147">Crea un origine dati denominata **Website**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4b850-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4b850-148">Immetti l'URL per i contatti di eCommerce https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="4b850-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="4b850-149">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="4b850-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4b850-150">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="4b850-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="4b850-151">**ReviewRating**: numero decimale</span><span class="sxs-lookup"><span data-stu-id="4b850-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="4b850-152">**ReviewDate**: data</span><span class="sxs-lookup"><span data-stu-id="4b850-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="4b850-153">Nel campo "Nome" nel riquadro di destra, rinomina la tua origine dati da **Query** a **Recensioni**.</span><span class="sxs-lookup"><span data-stu-id="4b850-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="4b850-154">**Salva** l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4b850-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="4b850-155">Attività 2: unificare i dati</span><span class="sxs-lookup"><span data-stu-id="4b850-155">Task 2 - Data unification</span></span>

<span data-ttu-id="4b850-156">Dopo aver importato i dati, iniziamo il processo di unificazione dei dati per creare un profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="4b850-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="4b850-157">Per ulteriori informazioni, vedi [Unificazione dei dati](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="4b850-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="4b850-158">Mapping</span><span class="sxs-lookup"><span data-stu-id="4b850-158">Map</span></span>

1. <span data-ttu-id="4b850-159">Dopo l'inserimento dei dati, esegui il mapping dei dati di eCommerce e Fedeltà ai tipi di dati comuni.</span><span class="sxs-lookup"><span data-stu-id="4b850-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="4b850-160">Vai a **Dati** > **Unifica** > **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="4b850-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="4b850-161">Seleziona le entità che rappresentano il profilo cliente, ovvero **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4b850-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="4b850-162">Selezionare quindi **Applica**.</span><span class="sxs-lookup"><span data-stu-id="4b850-162">Then, select **Apply**.</span></span>

   ![Unificare le origini dati di e-commerce e fedeltà.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="4b850-164">Seleziona **ContactId** come chiave primaria per **eCommerceContacts** e **LoyaltyID** come chiave primaria per **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4b850-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unifica LoyaltyId come chiave primaria.](media/unify-loyaltyid.png)

1. <span data-ttu-id="4b850-166">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4b850-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="4b850-167">Corrispondenza</span><span class="sxs-lookup"><span data-stu-id="4b850-167">Match</span></span>

1. <span data-ttu-id="4b850-168">Passa alla scheda **Corrispondenza** e seleziona **Imposta ordine**.</span><span class="sxs-lookup"><span data-stu-id="4b850-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="4b850-169">Nell'elenco a discesa **Primaria**, scegli **eCommerceContacts : eCommerce** come origine primaria e includi tutti i record.</span><span class="sxs-lookup"><span data-stu-id="4b850-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="4b850-170">Nell'elenco a discesa **Entità 2**, scegli **loyCustomers : LoyaltyScheme** e includi tutti i record.</span><span class="sxs-lookup"><span data-stu-id="4b850-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unificare la corrispondenza di eCommerce e Fedeltà.](media/unify-match-order.png)

1. <span data-ttu-id="4b850-172">Seleziona **Aggiungi regola**</span><span class="sxs-lookup"><span data-stu-id="4b850-172">Select **Add rule**</span></span>

1. <span data-ttu-id="4b850-173">Aggiungi la prima condizione utilizzando FullName.</span><span class="sxs-lookup"><span data-stu-id="4b850-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="4b850-174">Per eCommerceContacts seleziona **FullName** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="4b850-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="4b850-175">Per loyCustomers seleziona **FullName** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="4b850-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="4b850-176">Seleziona l'elenco a discesa **Normalizza** e scegli **Tipo (telefono, nome, indirizzo...)**.</span><span class="sxs-lookup"><span data-stu-id="4b850-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="4b850-177">Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.</span><span class="sxs-lookup"><span data-stu-id="4b850-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="4b850-178">Immetti il nome **FullName, Email** per la nuova regola.</span><span class="sxs-lookup"><span data-stu-id="4b850-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="4b850-179">Aggiungi una seconda condizione per l'indirizzo e-mail selezionado **Aggiungi condizione**</span><span class="sxs-lookup"><span data-stu-id="4b850-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="4b850-180">Per l'entità eCommerceContacts, scegli **E-mail** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="4b850-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="4b850-181">Per l'entità loyCustomers, scegli **E-mail** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="4b850-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="4b850-182">Lascia vuoto il campo Normalizza.</span><span class="sxs-lookup"><span data-stu-id="4b850-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="4b850-183">Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.</span><span class="sxs-lookup"><span data-stu-id="4b850-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unificare la regola di corrispondenza per nome ed e-mail.](media/unify-match-rule.png)

1. <span data-ttu-id="4b850-185">Seleziona **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="4b850-185">Select **Done**.</span></span>

1. <span data-ttu-id="4b850-186">Seleziona **Salva** ed **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4b850-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="4b850-187">Unione</span><span class="sxs-lookup"><span data-stu-id="4b850-187">Merge</span></span>

1. <span data-ttu-id="4b850-188">Vai alla scheda **Unione**.</span><span class="sxs-lookup"><span data-stu-id="4b850-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="4b850-189">In **ContactId** per l'entità **loyCustomers**, cambia il nome visualizzato in **ContactIdLOYALTY** per differenziarlo dagli altri ID inseriti.</span><span class="sxs-lookup"><span data-stu-id="4b850-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Rinominare contactid dall'ID del programma di fedeltà.](media/unify-merge-contactid.png)

1. <span data-ttu-id="4b850-191">Seleziona **Salva** ed **Esegui processi di unione e downstream**.</span><span class="sxs-lookup"><span data-stu-id="4b850-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="4b850-192">Attività 3 - Configurare la previsione di Customer Lifetime Value</span><span class="sxs-lookup"><span data-stu-id="4b850-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="4b850-193">Con i profili cliente unificati in atto, ora possiamo eseguire la previsione Customer Lifetime Value.</span><span class="sxs-lookup"><span data-stu-id="4b850-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="4b850-194">Per informazioni dettagliate, vedere [Previsione di Customer Lifetime Value (anteprima)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="4b850-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="4b850-195">Vai a **Intelligenza**  > **Previsioni** e seleziona **Modello di Valore durata cliente**.</span><span class="sxs-lookup"><span data-stu-id="4b850-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="4b850-196">Scorri le informazioni nel riquadro laterale e seleziona **Attività iniziali**.</span><span class="sxs-lookup"><span data-stu-id="4b850-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="4b850-197">Dai un nome al modello **Previsione OOB eCommerce CLV** e l'entità di output **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="4b850-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="4b850-198">Definire le preferenze del modello per il modello CLV:</span><span class="sxs-lookup"><span data-stu-id="4b850-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="4b850-199">**Periodo di tempo della previsione**: **12 mesi o 1 anno**.</span><span class="sxs-lookup"><span data-stu-id="4b850-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="4b850-200">Questa impostazione definisce quanto lontano nel futuro prevedere il valore della durata del cliente.</span><span class="sxs-lookup"><span data-stu-id="4b850-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="4b850-201">**Clienti attivi**: specifica cosa significano i clienti attivi per la tua attività.</span><span class="sxs-lookup"><span data-stu-id="4b850-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="4b850-202">Imposta l'intervallo di tempo storico in cui un cliente deve aver avuto almeno una transazione per essere considerato attivo.</span><span class="sxs-lookup"><span data-stu-id="4b850-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="4b850-203">Il modello prevede il CLV solo per i clienti attivi.</span><span class="sxs-lookup"><span data-stu-id="4b850-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="4b850-204">Scegli tra lasciare che il modello calcoli il periodo di tempo in base ai dati storici delle transazioni o fornire un intervallo di tempo specifico.</span><span class="sxs-lookup"><span data-stu-id="4b850-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="4b850-205">In questa guida di esempio, noi **lasciamo che il modello calcoli l'intervallo di acquisto**, che è l'opzione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4b850-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="4b850-206">**Clienti di alto valore**: definire i clienti di alto valore come percentile dei clienti più paganti.</span><span class="sxs-lookup"><span data-stu-id="4b850-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="4b850-207">Il modello utilizza questo input per fornire risultati che si adattano alla tua definizione aziendale di clienti di alto valore.</span><span class="sxs-lookup"><span data-stu-id="4b850-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="4b850-208">Puoi scegliere di far definire al modello i clienti di valore elevato.</span><span class="sxs-lookup"><span data-stu-id="4b850-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="4b850-209">Utilizza una regola euristica che derivi il percentile.</span><span class="sxs-lookup"><span data-stu-id="4b850-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="4b850-210">Puoi inoltre definire i clienti di alto valore come percentile dei clienti più paganti in futuro.</span><span class="sxs-lookup"><span data-stu-id="4b850-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="4b850-211">In questa guida di esempio, definiamo manualmente i clienti di alto valore come **top 30% dei clienti paganti attivi** e selezioniamo **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4b850-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Passaggio delle preferenze nell'esperienza guidata per il modello CLV.":::

1. <span data-ttu-id="4b850-213">Nel passaggio **Dati richiesti**, seleziona **Aggiungi dati** per fornire i dati della cronologia delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4b850-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="4b850-214">Aggiungi l'entità **eCommercePurchases: eCommerce** e mappa gli attributi richiesti dal modello:</span><span class="sxs-lookup"><span data-stu-id="4b850-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="4b850-215">ID transazione: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="4b850-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="4b850-216">Data transazione: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="4b850-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="4b850-217">Importo della transazione: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="4b850-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="4b850-218">ID prodotto: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="4b850-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="4b850-219">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4b850-219">Select **Next**.</span></span>

1. <span data-ttu-id="4b850-220">Stabilire la relazione tra l'entità **eCommercePurchases: eCommerce** e **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="4b850-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="4b850-221">Il passaggio **Dati aggiuntivi (facoltativo)** consente di aggiungere più dati sull'attività del cliente.</span><span class="sxs-lookup"><span data-stu-id="4b850-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="4b850-222">Questi dati possono aiutare a ottenere maggiori informazioni sulle interazioni dei clienti con la tua attività, che possono contribuire al CLV.</span><span class="sxs-lookup"><span data-stu-id="4b850-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="4b850-223">L'aggiunta di interazioni chiave con i clienti come i registri web, i registri servizio clienti o la cronologia dei programmi a premi può migliorare l'accuratezza delle previsioni.</span><span class="sxs-lookup"><span data-stu-id="4b850-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="4b850-224">Seleziona **Aggiungi dati** per includere più dati sull'attività del cliente.</span><span class="sxs-lookup"><span data-stu-id="4b850-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="4b850-225">Aggiungi l'entità dell'attività del cliente e mappa i nomi dei suoi campi ai campi corrispondenti richiesti dal modello:</span><span class="sxs-lookup"><span data-stu-id="4b850-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="4b850-226">Entità dell'attività del cliente: Recensioni: Sito Web</span><span class="sxs-lookup"><span data-stu-id="4b850-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="4b850-227">Chiave primaria: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="4b850-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="4b850-228">Timestamp: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="4b850-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="4b850-229">Evento (nome attività): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="4b850-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="4b850-230">Dettagli (importo o valore): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="4b850-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="4b850-231">Seleziona **Avanti** e configura l'attività e la relazione tra i dati della transazione e i dati del cliente:</span><span class="sxs-lookup"><span data-stu-id="4b850-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="4b850-232">Tipo di impegno: scegli esistente</span><span class="sxs-lookup"><span data-stu-id="4b850-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="4b850-233">Etichetta impegno: Recensione</span><span class="sxs-lookup"><span data-stu-id="4b850-233">Activity label: Review</span></span>
   - <span data-ttu-id="4b850-234">Etichetta corrispondente: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="4b850-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="4b850-235">Entità cliente: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="4b850-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="4b850-236">Relazione: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="4b850-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="4b850-237">Seleziona **Avanti** per impostare la pianificazione del modello.</span><span class="sxs-lookup"><span data-stu-id="4b850-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="4b850-238">Il modello deve essere addestrato regolarmente per apprendere nuovi modelli quando vengono inseriti nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="4b850-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="4b850-239">Per questo esempio, scegli **Mensile**.</span><span class="sxs-lookup"><span data-stu-id="4b850-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="4b850-240">Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**.</span><span class="sxs-lookup"><span data-stu-id="4b850-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="4b850-241">Attività 4: esaminare i risultati e le spiegazioni del modello</span><span class="sxs-lookup"><span data-stu-id="4b850-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="4b850-242">Lascia che il modello termini il training e la valutazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="4b850-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="4b850-243">Successivamente, puoi rivedere i risultati e le spiegazioni del modello CLV.</span><span class="sxs-lookup"><span data-stu-id="4b850-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="4b850-244">Per ulteriori informazioni, vedi [Esaminare lo stato e i risultati di una previsione](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="4b850-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="4b850-245">Attività 5 - Creare un segmento di clienti di alto valore</span><span class="sxs-lookup"><span data-stu-id="4b850-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="4b850-246">L'esecuzione del modello crea una nuova entità, che è elencata in **Dati** > **Entità**.</span><span class="sxs-lookup"><span data-stu-id="4b850-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="4b850-247">È possibile creare un nuovo segmento di clienti in base all'entità creata dal modello.</span><span class="sxs-lookup"><span data-stu-id="4b850-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="4b850-248">Vai a **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="4b850-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="4b850-249">Seleziona **Nuovo** e scegli **Crea a partire da** > **Intelligenza**.</span><span class="sxs-lookup"><span data-stu-id="4b850-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Creazione di un segmento con l'output del modello.](media/segment-intelligence.png)

1. <span data-ttu-id="4b850-251">Seleziona l'entità **OOBeCommerceCLVPrediction** e definisci il segmento:</span><span class="sxs-lookup"><span data-stu-id="4b850-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="4b850-252">Campo: CLVScore</span><span class="sxs-lookup"><span data-stu-id="4b850-252">Field: CLVScore</span></span>
  - <span data-ttu-id="4b850-253">Operatore: maggiore di</span><span class="sxs-lookup"><span data-stu-id="4b850-253">Operator: greater than</span></span>
  - <span data-ttu-id="4b850-254">Valore: 1500</span><span class="sxs-lookup"><span data-stu-id="4b850-254">Value: 1500</span></span>

1. <span data-ttu-id="4b850-255">Seleziona **Recensione** e **Salva** il segmento.</span><span class="sxs-lookup"><span data-stu-id="4b850-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="4b850-256">Ora hai un segmento che identifica i clienti che si prevede genereranno più di $1.500 di entrate nei prossimi 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="4b850-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="4b850-257">Questo segmento viene aggiornato dinamicamente se vengono inseriti più dati.</span><span class="sxs-lookup"><span data-stu-id="4b850-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="4b850-258">Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4b850-258">For more information, see [Create and manage segments](segments.md).</span></span>
