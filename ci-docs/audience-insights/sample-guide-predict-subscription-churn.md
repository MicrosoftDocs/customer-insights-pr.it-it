---
title: Guida di esempio per una previsione di abbandono dell'abbonamento
description: Usa questa guida di esempio per provare il modello di previsione di abbandono dell'abbonamento predefinito.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306308"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="65eac-103">Guida di esempio per una previsione di abbandono dell'abbonamento (anteprima)</span><span class="sxs-lookup"><span data-stu-id="65eac-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="65eac-104">In questa guida viene illustrato un esempio completo di previsione di abbandono dell'abbonamento che utilizza i dati di esempio forniti di seguito.</span><span class="sxs-lookup"><span data-stu-id="65eac-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="65eac-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="65eac-105">Scenario</span></span>

<span data-ttu-id="65eac-106">Contoso è un'azienda che produce caffè e macchine da caffè di alta qualità, che vendono attraverso il sito Web Contoso per il caffè.</span><span class="sxs-lookup"><span data-stu-id="65eac-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="65eac-107">Recentemente ha lanciato un sistema di abbonamento affinché i suoi clienti acquistino regolarmente del caffè.</span><span class="sxs-lookup"><span data-stu-id="65eac-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="65eac-108">L'obiettivo dell'azienda è capire quali clienti abbonati potrebbero annullare l'abbonamento nei mesi successivi.</span><span class="sxs-lookup"><span data-stu-id="65eac-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="65eac-109">Sapere quali dei loro clienti **rischiano di essere persi**, può aiutarli a ridurre gli sforzi di marketing concentrandosi sulla fidelizzazione degli stessi.</span><span class="sxs-lookup"><span data-stu-id="65eac-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65eac-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="65eac-110">Prerequisites</span></span>

- <span data-ttu-id="65eac-111">Almeno le [autorizzazioni di Collaboratore](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="65eac-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="65eac-112">Ti consigliamo di implementare i seguenti passaggi [in un nuovo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="65eac-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="65eac-113">Attività 1: inserire dati</span><span class="sxs-lookup"><span data-stu-id="65eac-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="65eac-114">Consulta in particolare gli articoli [sull'inserimento dati](data-sources.md) e sull'[importazione di origini dati utilizzando i connettori Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="65eac-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="65eac-115">Le seguenti informazioni presuppongono che tu conosca l'inserimento dati in generale.</span><span class="sxs-lookup"><span data-stu-id="65eac-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="65eac-116">Inserire dati cliente dalla piattaforma di eCommerce</span><span class="sxs-lookup"><span data-stu-id="65eac-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="65eac-117">Crea un origine dati denominata **eCommerce**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="65eac-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="65eac-118">Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="65eac-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="65eac-119">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="65eac-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65eac-120">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="65eac-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="65eac-121">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="65eac-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="65eac-122">**CreatedOn**: data/ora/fuso orario</span><span class="sxs-lookup"><span data-stu-id="65eac-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Trasformare la data di nascita in data.":::

1. <span data-ttu-id="65eac-124">Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="65eac-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="65eac-125">Salva l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="65eac-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="65eac-126">Inserire dati cliente dallo schema di fidelizzazione</span><span class="sxs-lookup"><span data-stu-id="65eac-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="65eac-127">Crea un origine dati denominata **LoyaltyScheme**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="65eac-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="65eac-128">Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="65eac-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="65eac-129">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="65eac-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65eac-130">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="65eac-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="65eac-131">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="65eac-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="65eac-132">**RewardsPoints**: numero intero</span><span class="sxs-lookup"><span data-stu-id="65eac-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="65eac-133">**CreatedOn**: date/ora</span><span class="sxs-lookup"><span data-stu-id="65eac-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="65eac-134">Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="65eac-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="65eac-135">Salva l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="65eac-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="65eac-136">Inserire le informazioni sull'abbonamento</span><span class="sxs-lookup"><span data-stu-id="65eac-136">Ingest subscription information</span></span>

1. <span data-ttu-id="65eac-137">Crea un origine dati denominata **SubscriptionHistory**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="65eac-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="65eac-138">Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="65eac-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="65eac-139">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="65eac-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65eac-140">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="65eac-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="65eac-141">**SubscriptioID**: numero intero</span><span class="sxs-lookup"><span data-stu-id="65eac-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="65eac-142">**SubscriptionAmount**: valuta</span><span class="sxs-lookup"><span data-stu-id="65eac-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="65eac-143">**SubscriptionEndDate**: data/ora</span><span class="sxs-lookup"><span data-stu-id="65eac-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="65eac-144">**SubscriptionStartDate**: data/ora</span><span class="sxs-lookup"><span data-stu-id="65eac-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="65eac-145">**TransactionDate**: data/ora</span><span class="sxs-lookup"><span data-stu-id="65eac-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="65eac-146">**IsRecurring**: vero/falso</span><span class="sxs-lookup"><span data-stu-id="65eac-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="65eac-147">**Is_auto_renew**: vero/falso</span><span class="sxs-lookup"><span data-stu-id="65eac-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="65eac-148">**RecurringFrequencyInMonths**: numero intero</span><span class="sxs-lookup"><span data-stu-id="65eac-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="65eac-149">Nel campo **Nome** nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="65eac-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="65eac-150">Salva l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="65eac-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="65eac-151">Inserire dati cliente delle recensioni sul sito web</span><span class="sxs-lookup"><span data-stu-id="65eac-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="65eac-152">Crea un origine dati denominata **Website**, scegli l'opzione di importazione e seleziona il connettore **Testo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="65eac-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="65eac-153">Immetti l'URL per i contatti di eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="65eac-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="65eac-154">Durante la modifica dei dati, seleziona **Trasforma** e quindi **Usa la prima riga come intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="65eac-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65eac-155">Aggiorna il tipo di dati per le colonne elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="65eac-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="65eac-156">**ReviewRating**: numero intero</span><span class="sxs-lookup"><span data-stu-id="65eac-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="65eac-157">**ReviewDate**: data</span><span class="sxs-lookup"><span data-stu-id="65eac-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="65eac-158">Nel campo "Nome" nel riquadro a destra, cambia il nome dell'origine dati da **Query** a **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="65eac-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="65eac-159">Attività 2: unificare i dati</span><span class="sxs-lookup"><span data-stu-id="65eac-159">Task 2 - Data unification</span></span>

<span data-ttu-id="65eac-160">Dopo aver inserito i dati, iniziamo il processo di **Mapping, corrispondenza, unione** per creare un profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="65eac-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="65eac-161">Per ulteriori informazioni, vedi [Unificazione dei dati](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="65eac-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="65eac-162">Mapping</span><span class="sxs-lookup"><span data-stu-id="65eac-162">Map</span></span>

1. <span data-ttu-id="65eac-163">Dopo l'inserimento dei dati, esegui il mapping dei dati di eCommerce e Fedeltà ai tipi di dati comuni.</span><span class="sxs-lookup"><span data-stu-id="65eac-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="65eac-164">Vai a **Dati** > **Unifica** > **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="65eac-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="65eac-165">Seleziona le entità che rappresentano il profilo cliente, ovvero **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="65eac-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Unificare le origini dati di e-commerce e fedeltà.":::

1. <span data-ttu-id="65eac-167">Seleziona **ContactId** come chiave primaria per **eCommerceContacts** e **LoyaltyID** come chiave primaria per **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="65eac-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifica LoyaltyId come chiave primaria.":::

### <a name="match"></a><span data-ttu-id="65eac-169">Corrispondenza</span><span class="sxs-lookup"><span data-stu-id="65eac-169">Match</span></span>

1. <span data-ttu-id="65eac-170">Passa alla scheda **Corrispondenza** e seleziona **Imposta ordine**.</span><span class="sxs-lookup"><span data-stu-id="65eac-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="65eac-171">Nell'elenco a discesa **Principale** scegli **eCommerceContacts : eCommerce** come fonte primaria e includi tutti i record.</span><span class="sxs-lookup"><span data-stu-id="65eac-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="65eac-172">Nell'elenco a discesa **Entità 2** scegli **loyCustomers : LoyaltyScheme** e includi tutti i record.</span><span class="sxs-lookup"><span data-stu-id="65eac-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unificare la corrispondenza di eCommerce e Fedeltà.":::

1. <span data-ttu-id="65eac-174">Seleziona **Crea una nuova regola**</span><span class="sxs-lookup"><span data-stu-id="65eac-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="65eac-175">Aggiungi la prima condizione utilizzando FullName.</span><span class="sxs-lookup"><span data-stu-id="65eac-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="65eac-176">Per eCommerceContacts seleziona **FullName** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="65eac-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="65eac-177">Per loyCustomers seleziona **FullName** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="65eac-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="65eac-178">Seleziona l'elenco a discesa **Normalizza** e scegli **Tipo (telefono, nome, indirizzo...)**.</span><span class="sxs-lookup"><span data-stu-id="65eac-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="65eac-179">Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.</span><span class="sxs-lookup"><span data-stu-id="65eac-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="65eac-180">Immetti il nome **FullName, Email** per la nuova regola.</span><span class="sxs-lookup"><span data-stu-id="65eac-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="65eac-181">Aggiungi una seconda condizione per l'indirizzo e-mail selezionado **Aggiungi condizione**</span><span class="sxs-lookup"><span data-stu-id="65eac-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="65eac-182">Per l'entità eCommerceContacts, scegli **E-mail** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="65eac-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="65eac-183">Per l'entità loyCustomers, scegli **E-mail** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="65eac-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="65eac-184">Lascia vuoto il campo Normalizza.</span><span class="sxs-lookup"><span data-stu-id="65eac-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="65eac-185">Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.</span><span class="sxs-lookup"><span data-stu-id="65eac-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificare la regola di corrispondenza per nome ed e-mail.":::

7. <span data-ttu-id="65eac-187">Seleziona **Salva** ed **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="65eac-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="65eac-188">Unione</span><span class="sxs-lookup"><span data-stu-id="65eac-188">Merge</span></span>

1. <span data-ttu-id="65eac-189">Vai alla scheda **Unione**.</span><span class="sxs-lookup"><span data-stu-id="65eac-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="65eac-190">In **ContactId** per l'entità **loyCustomers**, cambia il nome visualizzato in **ContactIdLOYALTY** per differenziarlo dagli altri ID inseriti.</span><span class="sxs-lookup"><span data-stu-id="65eac-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Rinominare contactid dall'ID del programma di fedeltà.":::

1. <span data-ttu-id="65eac-192">Seleziona **Salva** ed **Esegui** per avviare il processo di unione.</span><span class="sxs-lookup"><span data-stu-id="65eac-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="65eac-193">Attività 3: configurare la previsione di abbandono dell'abbonamento</span><span class="sxs-lookup"><span data-stu-id="65eac-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="65eac-194">Dopo aver unificato i profili cliente, possiamo eseguire la previsione dell'abbandono dell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="65eac-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="65eac-195">Per i passaggi dettagliati, vedi [Previsione di abbandono dell'abbonamento (anteprima)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="65eac-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="65eac-196">Vai a **Intelligenza** > **Scopri** e seleziona per utilizzare il **Modello di abbandono dei clienti**.</span><span class="sxs-lookup"><span data-stu-id="65eac-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="65eac-197">Seleziona l'opzione **Abbonamento** e seleziona **Inizia**.</span><span class="sxs-lookup"><span data-stu-id="65eac-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="65eac-198">Assegna al modello il nome **Previsione abbandono abbonamento OOB** e all'entità di output il nome **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="65eac-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="65eac-199">Definisci due condizioni per il modello di abbandono:</span><span class="sxs-lookup"><span data-stu-id="65eac-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="65eac-200">**Giorni dalla fine dell'abbonamento**: **almeno 60** giorni.</span><span class="sxs-lookup"><span data-stu-id="65eac-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="65eac-201">Se un cliente non rinnova il proprio abbonamento in tale periodo di tempo dopo la scadenza dell'abbonamento, viene considerato come perso.</span><span class="sxs-lookup"><span data-stu-id="65eac-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="65eac-202">**Definizione abbandono**: **almeno 93** giorni.</span><span class="sxs-lookup"><span data-stu-id="65eac-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="65eac-203">La durata della previsione del modello durante la quale i clienti potrebbero disabbonarsi.</span><span class="sxs-lookup"><span data-stu-id="65eac-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="65eac-204">Maggiore è la durata, meno precisi saranno i risultati.</span><span class="sxs-lookup"><span data-stu-id="65eac-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selezionare Finestra di previsione e Definizione abbandono.":::

1. <span data-ttu-id="65eac-206">Seleziona **Aggiungi dati obbligatori** e seleziona **Aggiungi dati** per la cronologia dell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="65eac-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="65eac-207">Aggiungi l'entità **Subscription : SubscriptionHistory** ed esegui il mapping dei campi di eCommerce ai campi corrispondenti richiesti dal modello.</span><span class="sxs-lookup"><span data-stu-id="65eac-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="65eac-208">Associa l'entità **Subscription : SubscriptionHistory** a **eCommerceContacts : eCommerce** e assegna un nome alla relazione **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="65eac-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Associare le entità di e-Commerce.":::

1. <span data-ttu-id="65eac-210">In Impegni cliente, aggiungi l'entità **webReviews: sito web** ed esegui il mapping dei campi di webReviews ai campi corrispondenti richiesti dal modello.</span><span class="sxs-lookup"><span data-stu-id="65eac-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="65eac-211">Chiave primaria: ReviewId</span><span class="sxs-lookup"><span data-stu-id="65eac-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="65eac-212">Timestamp: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="65eac-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="65eac-213">Evento: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="65eac-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="65eac-214">Configura un'attività per recensioni sul sito Web.</span><span class="sxs-lookup"><span data-stu-id="65eac-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="65eac-215">Seleziona l'impegno **Esamina** e associa l'entità **webReviews: sito web** a **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="65eac-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="65eac-216">Seleziona **Avanti** per impostare la pianificazione del modello.</span><span class="sxs-lookup"><span data-stu-id="65eac-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="65eac-217">È necessario eseguire regolarmente il training del modello affinché apprenda nuovi modelli quando vengono inseriti nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="65eac-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="65eac-218">Per questo esempio, seleziona **Mensile**.</span><span class="sxs-lookup"><span data-stu-id="65eac-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="65eac-219">Dopo aver esaminato tutti i dettagli, seleziona **Salva ed esegui**.</span><span class="sxs-lookup"><span data-stu-id="65eac-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="65eac-220">Attività 4: esaminare i risultati e le spiegazioni del modello</span><span class="sxs-lookup"><span data-stu-id="65eac-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="65eac-221">Lascia che il modello termini il training e la valutazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="65eac-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="65eac-222">Ora puoi esaminare le spiegazioni del modello di abbandono dell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="65eac-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="65eac-223">Per ulteriori informazioni, vedi [Esaminare lo stato e i risultati di una previsione](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="65eac-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="65eac-224">Attività 5: creare un segmento di clienti ad alto rischio di abbandono</span><span class="sxs-lookup"><span data-stu-id="65eac-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="65eac-225">L'esecuzione del modello di produzione crea una nuova entità visibile in **Dati** > **Entità**.</span><span class="sxs-lookup"><span data-stu-id="65eac-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="65eac-226">Puoi creare un nuovo segmento basato sull'entità creata dal modello.</span><span class="sxs-lookup"><span data-stu-id="65eac-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="65eac-227">Vai a **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="65eac-227">Go to **Segments**.</span></span> <span data-ttu-id="65eac-228">Seleziona **Nuovo** e scegli **Crea a partire da** > **Intelligenza**.</span><span class="sxs-lookup"><span data-stu-id="65eac-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creazione di un segmento con l'output del modello.":::

1. <span data-ttu-id="65eac-230">Seleziona l'endpoint **OOBSubscriptionChurnPrediction** e definisci il segmento:</span><span class="sxs-lookup"><span data-stu-id="65eac-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="65eac-231">Campo: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="65eac-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="65eac-232">Operatore: maggiore di</span><span class="sxs-lookup"><span data-stu-id="65eac-232">Operator: greater than</span></span>
   - <span data-ttu-id="65eac-233">Valore: 0,6</span><span class="sxs-lookup"><span data-stu-id="65eac-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Impostare il segmento di abbandono dell'abbonamento.":::

<span data-ttu-id="65eac-235">Ora hai un segmento che viene aggiornato dinamicamente e che identifica i clienti ad alto rischio di abbandono per questa attività di abbonamento.</span><span class="sxs-lookup"><span data-stu-id="65eac-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="65eac-236">Per altre informazioni, vedi [Creare e gestire i segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="65eac-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]