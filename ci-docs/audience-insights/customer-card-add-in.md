---
title: Installa e configura il componente aggiuntivo Scheda cliente
description: Installa e configura il componente aggiuntivo Scheda cliente per Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268049"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="65afd-103">Componente aggiuntivo Scheda cliente (anteprima)</span><span class="sxs-lookup"><span data-stu-id="65afd-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="65afd-104">Ottieni una panoramica completa dei tuoi clienti direttamente nelle app Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="65afd-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="65afd-105">Visualizza dati demografici, informazioni dettagliate e sequenze temporali degli impegni con il componente aggiuntivo Scheda cliente.</span><span class="sxs-lookup"><span data-stu-id="65afd-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65afd-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="65afd-106">Prerequisites</span></span>

- <span data-ttu-id="65afd-107">App Dynamics 365 (come Hub delle vendite o Hub del servizio clienti), versione 9.0 e successive con Unified Interface abilitato.</span><span class="sxs-lookup"><span data-stu-id="65afd-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="65afd-108">Profili cliente [inseriti dall'app Dynamics 365 utilizzando Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="65afd-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="65afd-109">Gli utenti del componente aggiuntivo Scheda cliente devono essere [aggiunti come utenti](permissions.md) in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="65afd-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="65afd-110">[Funzionalità di ricerca e filtro configurate](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="65afd-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="65afd-111">Controllo demografico: i campi demografici, come l'età o il sesso, sono disponibili nel profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="65afd-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="65afd-112">Controllo Arricchimento: richiede [arricchimenti](enrichment-hub.md) attivi applicati ai profili cliente.</span><span class="sxs-lookup"><span data-stu-id="65afd-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="65afd-113">Controllo dell'intelligenza: richiede dati generati tramite Azure Machine Learning ([previsioni](predictions.md) o [modelli personalizzati](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="65afd-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="65afd-114">Controllo delle misure: richiede [misure configurate](measures.md).</span><span class="sxs-lookup"><span data-stu-id="65afd-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="65afd-115">Controllo della sequenza temporale: richiede [impegni configurati](activities.md).</span><span class="sxs-lookup"><span data-stu-id="65afd-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="65afd-116">Installare il componente aggiuntivo Scheda cliente</span><span class="sxs-lookup"><span data-stu-id="65afd-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="65afd-117">Il componente aggiuntivo Scheda cliente è una soluzione per le app di interazione con i clienti in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="65afd-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="65afd-118">Per installare la soluzione, vai a AppSource e cerca **Scheda cliente Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="65afd-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="65afd-119">Seleziona il [componente aggiuntivo Scheda cliente su AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e seleziona **Prova adesso**.</span><span class="sxs-lookup"><span data-stu-id="65afd-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="65afd-120">Potrebbe essere necessario accedere con le credenziali di amministratore per l'app Dynamics 365 per installare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="65afd-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="65afd-121">L'installazione della soluzione nell'ambiente potrebbe richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="65afd-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="65afd-122">Configurare il componente aggiuntivo Scheda cliente</span><span class="sxs-lookup"><span data-stu-id="65afd-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="65afd-123">In qualità di amministratore, vai alla sezione **Impostazioni** in Dynamics 365 e seleziona **Soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="65afd-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="65afd-124">Seleziona il collegamento **Nome visualizzato** per la soluzione **Componente aggiuntivo Scheda cliente di Dynamics 365 Customer Insights (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="65afd-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65afd-125">![Selezionare il nome visualizzato](media/select-display-name.png "Selezionare il nome visualizzato")</span><span class="sxs-lookup"><span data-stu-id="65afd-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="65afd-126">Seleziona **Accedi** e immetti le credenziali per l'account amministratore che utilizzi per configurare Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="65afd-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="65afd-127">Verifica che il blocco popup del browser non blocchi la finestra di autenticazione quando selezioni il pulsante **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="65afd-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="65afd-128">Seleziona l'ambiente da cui vuoi recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="65afd-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="65afd-129">Definisci quale campo mappare ai record nell'app Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="65afd-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="65afd-130">Per eseguire il mapping con un contatto, seleziona il campo nell'entità Cliente che corrisponde all'ID dell'entità di contatto.</span><span class="sxs-lookup"><span data-stu-id="65afd-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="65afd-131">Per eseguire il mapping con un account, seleziona il campo nell'entità Cliente che corrisponde all'ID dell'entità account.</span><span class="sxs-lookup"><span data-stu-id="65afd-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65afd-132">![Campo ID contatto](media/contact-id-field.png "Campo ID contatto")</span><span class="sxs-lookup"><span data-stu-id="65afd-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="65afd-133">Seleziona **Salva configurazione** per salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="65afd-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="65afd-134">Successivamente, devi assegnare ruoli di sicurezza in Dynamics 365 in modo che gli utenti possano personalizzare e visualizzare la scheda cliente.</span><span class="sxs-lookup"><span data-stu-id="65afd-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="65afd-135">In Dynamics 365 vai a **Impostazioni** > **Sicurezza** > **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="65afd-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="65afd-136">Seleziona gli utenti per modificare i ruoli utente e seleziona **Gestisci ruoli**.</span><span class="sxs-lookup"><span data-stu-id="65afd-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="65afd-137">Assegna il ruolo **Addetto personalizzazione scheda Customer Insights** agli utenti che personalizzeranno il contenuto mostrato sulla scheda per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65afd-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="65afd-138">Aggiungere i controlli Scheda cliente ai moduli</span><span class="sxs-lookup"><span data-stu-id="65afd-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="65afd-139">Per aggiungere i controlli della scheda cliente al modulo Contatto, vai a **Impostazioni** > **Personalizzazioni** in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="65afd-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="65afd-140">Selezionare **Personalizza il sistema**.</span><span class="sxs-lookup"><span data-stu-id="65afd-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="65afd-141">Accedi all'entità **Contatto**, espandila e quindi seleziona **Moduli**.</span><span class="sxs-lookup"><span data-stu-id="65afd-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="65afd-142">Seleziona il modulo del contatto a cui vuoi aggiungere i controlli Scheda cliente.</span><span class="sxs-lookup"><span data-stu-id="65afd-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="65afd-143">![Selezionare il modulo Contatto](media/contact-active-forms.png "Selezionare il modulo Contatto")</span><span class="sxs-lookup"><span data-stu-id="65afd-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="65afd-144">Per aggiungere un controllo, nell'editor di moduli trascina qualsiasi campo da **Esplora campi** nel punto in cui vuoi che il controllo venga visualizzato.</span><span class="sxs-lookup"><span data-stu-id="65afd-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="65afd-145">Seleziona il campo sul modulo che hai appena aggiunto e scegli **Cambia proprietà**.</span><span class="sxs-lookup"><span data-stu-id="65afd-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="65afd-146">Vai alla scheda **Controlli** e seleziona **Aggiungi controllo**.</span><span class="sxs-lookup"><span data-stu-id="65afd-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="65afd-147">Scegli uno dei controlli personalizzati disponibili e seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="65afd-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="65afd-148">Nella finestra di dialogo **Proprietà campo**, seleziona la casella di controllo **Visualizza etichetta nel modulo**.</span><span class="sxs-lookup"><span data-stu-id="65afd-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="65afd-149">Seleziona l'opzione **Web** per il controllo.</span><span class="sxs-lookup"><span data-stu-id="65afd-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="65afd-150">Per il controllo Arricchimento, seleziona il tipo di arricchimento che vuoi visualizzare configurando il campo **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="65afd-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="65afd-151">Aggiungi un controllo arricchimento separato per ogni tipo di arricchimento.</span><span class="sxs-lookup"><span data-stu-id="65afd-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="65afd-152">Seleziona **Salva** e **Pubblica** per pubblicare il modulo contatto aggiornato.</span><span class="sxs-lookup"><span data-stu-id="65afd-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="65afd-153">Vai al modulo del contatto pubblicato.</span><span class="sxs-lookup"><span data-stu-id="65afd-153">Go to the published contact form.</span></span> <span data-ttu-id="65afd-154">Vedrai il controllo appena aggiunto.</span><span class="sxs-lookup"><span data-stu-id="65afd-154">You'll see the newly added control.</span></span> <span data-ttu-id="65afd-155">Potrebbe essere necessario effettuare l'accesso la prima volta che lo si utilizza.</span><span class="sxs-lookup"><span data-stu-id="65afd-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="65afd-156">Per personalizzare quello che vuoi visualizzare nel controllo personalizzato, seleziona il pulsante di modifica nell'angolo superiore destro.</span><span class="sxs-lookup"><span data-stu-id="65afd-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="65afd-157">Aggiornare il componente aggiuntivo Scheda cliente</span><span class="sxs-lookup"><span data-stu-id="65afd-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="65afd-158">Il componente aggiuntivo Scheda cliente non si aggiorna automaticamente.</span><span class="sxs-lookup"><span data-stu-id="65afd-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="65afd-159">Per eseguire l'aggiornamento alla versione più recente, segui questa procedura nell'app Dynamics 365 in cui è installato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="65afd-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="65afd-160">Nell'app Dynamics 365, vai a **Impostazioni** > **Personalizzazione** e seleziona **Soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="65afd-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="65afd-161">Nella tabella dei componenti aggiuntivi cerca **CustomerInsightsCustomerCard** e seleziona la riga.</span><span class="sxs-lookup"><span data-stu-id="65afd-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="65afd-162">Seleziona **Applica aggiornamento soluzione** nella barra delle azioni.</span><span class="sxs-lookup"><span data-stu-id="65afd-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Aggiorna la soluzione nell'area Personalizzazione delle app Dynamics 365":::

1. <span data-ttu-id="65afd-164">Dopo aver avviato il processo di aggiornamento, vedrai un indicatore di caricamento fino al completamento dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="65afd-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="65afd-165">Se non è disponibile una versione più recente, l'aggiornamento mostrerà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="65afd-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]