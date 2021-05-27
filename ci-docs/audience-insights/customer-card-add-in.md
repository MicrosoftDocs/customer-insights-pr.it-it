---
title: Componente aggiuntivo Customer Card per app Dynamics 365
description: Mostra i dati delle informazioni dettagliate sul gruppo di destinatari nelle app Dynamics 365 con questo componente aggiuntivo.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059593"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="cf9a0-103">Componente aggiuntivo Scheda cliente (anteprima)</span><span class="sxs-lookup"><span data-stu-id="cf9a0-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cf9a0-104">Ottieni una panoramica completa dei tuoi clienti direttamente nelle app Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="cf9a0-105">Con il componente aggiuntivo Customer Card installato in un'app Dynamics 365 supportata, puoi scegliere di visualizzare dati demografici, informazioni dettagliate e cronologie degli impegni.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="cf9a0-106">Il componente aggiuntivo recupera i dati da Customer Insights senza influire sui dati nell'app Dynamics 365 connessa.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="cf9a0-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cf9a0-107">Prerequisites</span></span>

- <span data-ttu-id="cf9a0-108">Il componente aggiuntivo funziona solo con le app Dynamics 365 basate su modello, come Sales o Customer Service, versione 9.0 e successive.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="cf9a0-109">Affinché i dati di Dynamics 365 possano essere mappati ai profili cliente delle informazioni dettagliate sul gruppo di destinatari devono essere [inseriti dall'app Dynamics 365 utilizzando il connettore Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="cf9a0-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="cf9a0-110">Tutti gli utenti Dynamics 365 del componente aggiuntivo Customer Card devono essere [aggiunti come utenti](permissions.md) nelle informazioni dettagliate sul gruppo di destinatari per vedere i dati.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="cf9a0-111">[Le funzionalità di ricerca e filtro configurate](search-filter-index.md) nelle informazioni dettagliate sul gruppo di destinatari sono necessarie affinché la ricerca dei dati funzioni.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="cf9a0-112">Ogni controllo del componente aggiuntivo si basa su dati specifici nelle informazioni dettagliate sul gruppo di destinatari:</span><span class="sxs-lookup"><span data-stu-id="cf9a0-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="cf9a0-113">Controllo delle misure: richiede [misure configurate](measures.md).</span><span class="sxs-lookup"><span data-stu-id="cf9a0-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="cf9a0-114">Controllo intelligente: richiede dati generati utilizzando [previsioni](predictions.md) o [modelli personalizzati](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="cf9a0-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="cf9a0-115">Controllo demografico: i campi demografici, come l'età o il sesso, sono disponibili nel profilo cliente unificato.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="cf9a0-116">Controllo Arricchimento: richiede [arricchimenti](enrichment-hub.md) attivi applicati ai profili cliente.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="cf9a0-117">Controllo della sequenza temporale: richiede [impegni configurati](activities.md).</span><span class="sxs-lookup"><span data-stu-id="cf9a0-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="cf9a0-118">Installare il componente aggiuntivo Scheda cliente</span><span class="sxs-lookup"><span data-stu-id="cf9a0-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="cf9a0-119">Il componente aggiuntivo Scheda cliente è una soluzione per le app di interazione con i clienti in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="cf9a0-120">Per installare la soluzione, vai a AppSource e cerca **Scheda cliente Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="cf9a0-121">Seleziona il [componente aggiuntivo Scheda cliente su AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e seleziona **Prova adesso**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="cf9a0-122">Potrebbe essere necessario accedere con le credenziali di amministratore per l'app Dynamics 365 per installare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="cf9a0-123">L'installazione della soluzione nell'ambiente potrebbe richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="cf9a0-124">Configurare il componente aggiuntivo Scheda cliente</span><span class="sxs-lookup"><span data-stu-id="cf9a0-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="cf9a0-125">In qualità di amministratore, vai alla sezione **Impostazioni** in Dynamics 365 e seleziona **Soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="cf9a0-126">Seleziona il collegamento **Nome visualizzato** per la soluzione **Componente aggiuntivo Scheda cliente di Dynamics 365 Customer Insights (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cf9a0-127">![Selezionare il nome visualizzato](media/select-display-name.png "Selezionare il nome visualizzato")</span><span class="sxs-lookup"><span data-stu-id="cf9a0-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="cf9a0-128">Seleziona **Accedi** e immetti le credenziali per l'account amministratore che utilizzi per configurare Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cf9a0-129">Verifica che il blocco popup del browser non blocchi la finestra di autenticazione quando selezioni il pulsante **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="cf9a0-130">Seleziona l'ambiente di Customer Insights da cui vuoi recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="cf9a0-131">Definisci la mappatura dei campi ai record nell'app Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="cf9a0-132">A seconda dei dati in Customer Insights, puoi scegliere di mappare le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="cf9a0-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="cf9a0-133">Per eseguire il mapping con un contatto, seleziona il campo nell'entità Cliente che corrisponde all'ID dell'entità di contatto.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="cf9a0-134">Per eseguire il mapping con un account, seleziona il campo nell'entità Cliente che corrisponde all'ID dell'entità account.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cf9a0-135">![Campo ID contatto](media/contact-id-field.png "Campo ID contatto")</span><span class="sxs-lookup"><span data-stu-id="cf9a0-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="cf9a0-136">Seleziona **Salva configurazione** per salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="cf9a0-137">Successivamente, devi assegnare ruoli di sicurezza in Dynamics 365 in modo che gli utenti possano personalizzare e visualizzare la scheda cliente.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="cf9a0-138">In Dynamics 365 vai a **Impostazioni** > **Sicurezza** > **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="cf9a0-139">Seleziona gli utenti per modificare i ruoli utente e seleziona **Gestisci ruoli**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="cf9a0-140">Assegna il ruolo **Addetto personalizzazione scheda Customer Insights** agli utenti che personalizzeranno il contenuto mostrato sulla scheda per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="cf9a0-141">Aggiungere i controlli Scheda cliente ai moduli</span><span class="sxs-lookup"><span data-stu-id="cf9a0-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="cf9a0-142">Per aggiungere i controlli della scheda cliente al modulo Contatto, vai a **Impostazioni** > **Personalizzazioni** in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="cf9a0-143">Selezionare **Personalizza il sistema**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="cf9a0-144">Accedi all'entità **Contatto**, espandila e quindi seleziona **Moduli**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="cf9a0-145">Seleziona il modulo del contatto a cui vuoi aggiungere i controlli Scheda cliente.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cf9a0-146">![Selezionare il modulo Contatto](media/contact-active-forms.png "Selezionare il modulo Contatto")</span><span class="sxs-lookup"><span data-stu-id="cf9a0-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="cf9a0-147">Per aggiungere un controllo, nell'editor di moduli trascina qualsiasi campo da **Esplora campi** nel punto in cui vuoi che il controllo venga visualizzato.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="cf9a0-148">Seleziona il campo sul modulo che hai appena aggiunto e scegli **Cambia proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="cf9a0-149">Vai alla scheda **Controlli** e seleziona **Aggiungi controllo**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="cf9a0-150">Scegli uno dei controlli personalizzati disponibili e seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="cf9a0-151">Nella finestra di dialogo **Proprietà campo**, seleziona la casella di controllo **Visualizza etichetta nel modulo**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="cf9a0-152">Seleziona l'opzione **Web** per il controllo.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="cf9a0-153">Per il controllo Arricchimento, seleziona il tipo di arricchimento che vuoi visualizzare configurando il campo **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="cf9a0-154">Aggiungi un controllo arricchimento separato per ogni tipo di arricchimento.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="cf9a0-155">Seleziona **Salva** e **Pubblica** per pubblicare il modulo contatto aggiornato.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="cf9a0-156">Vai al modulo del contatto pubblicato.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-156">Go to the published contact form.</span></span> <span data-ttu-id="cf9a0-157">Vedrai il controllo appena aggiunto.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-157">You'll see the newly added control.</span></span> <span data-ttu-id="cf9a0-158">Potrebbe essere necessario effettuare l'accesso la prima volta che lo si utilizza.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="cf9a0-159">Per personalizzare quello che vuoi visualizzare nel controllo personalizzato, seleziona il pulsante di modifica nell'angolo superiore destro.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="cf9a0-160">Aggiornare il componente aggiuntivo Scheda cliente</span><span class="sxs-lookup"><span data-stu-id="cf9a0-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="cf9a0-161">Il componente aggiuntivo Scheda cliente non si aggiorna automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="cf9a0-162">Per eseguire l'aggiornamento alla versione più recente, segui questa procedura nell'app Dynamics 365 in cui è installato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="cf9a0-163">Nell'app Dynamics 365, vai a **Impostazioni** > **Personalizzazione** e seleziona **Soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="cf9a0-164">Nella tabella dei componenti aggiuntivi cerca **CustomerInsightsCustomerCard** e seleziona la riga.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="cf9a0-165">Seleziona **Applica aggiornamento soluzione** nella barra delle azioni.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Aggiorna la soluzione nell'area Personalizzazione delle app Dynamics 365":::

1. <span data-ttu-id="cf9a0-167">Dopo aver avviato il processo di aggiornamento, vedrai un indicatore di caricamento fino al completamento dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="cf9a0-168">Se non è disponibile una versione più recente, l'aggiornamento mostrerà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="cf9a0-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
