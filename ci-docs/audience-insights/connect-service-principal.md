---
title: Connettersi a un account Azure Data Lake Storage Gen2 con un'entità servizio
description: Utilizza un'entità servizio di Azure per Audience Insights per connetterti al tuo data lake quando lo associ a Audience Insights.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644093"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="9a0fd-103">Connettersi a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure per Audience Insights</span><span class="sxs-lookup"><span data-stu-id="9a0fd-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="9a0fd-104">Gli strumenti automatizzati che usano i servizi di Azure deve avere sempre autorizzazioni limitate.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="9a0fd-105">Anziché avere applicazioni che accedono come utente con privilegi completi, Azure fornisce entità servizio.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="9a0fd-106">Leggi questo articolo per scoprire come connettere Audience Insights con un account di Azure Data Lake Storage Gen2 utilizzando un'entità servizio di Azure anziché chiavi di account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="9a0fd-107">Puoi utilizzare l'entità servizio per [aggiungere o modificare in modo sicuro una cartella di Common Data Model come origine dati](connect-common-data-model.md) o per [creare un ambiente o aggiornarne uno esistente](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="9a0fd-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="9a0fd-108">Per creare l'entità servizio, sono necessarie autorizzazioni di amministratore per la sottoscrizione di Azure.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="9a0fd-109">Creare un'entità servizio di Azure per Audience Insights</span><span class="sxs-lookup"><span data-stu-id="9a0fd-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="9a0fd-110">Prima di creare una nuova entità servizio per Audience Insights, controlla se esiste già nella tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="9a0fd-111">Cercare un'entità servizio esistente</span><span class="sxs-lookup"><span data-stu-id="9a0fd-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="9a0fd-112">Vai al [portale di amministrazione di Azure](https://portal.azure.com) e accedi alla tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="9a0fd-113">Seleziona **Azure Active Directory** nei servizi di Azure.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="9a0fd-114">Sotto **Gestisci**, seleziona **Applicazioni aziendali**.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="9a0fd-115">Cerca l'ID applicazione di prima parte `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` di Audience Insights o il nome `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="9a0fd-116">Se trovi un record corrispondente, significa che l'entità servizio per Audience Insights esiste.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="9a0fd-117">Non devi quindi crearla.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot che mostra l'entità servizio esistente.":::
   
6. <span data-ttu-id="9a0fd-119">Se non vengono restituiti risultati, crea una entità servizio.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="9a0fd-120">Creare un'entità servizio</span><span class="sxs-lookup"><span data-stu-id="9a0fd-120">Create a new service principal</span></span>

1. <span data-ttu-id="9a0fd-121">Installa l'ultima versione di **Azure Active Directory PowerShell per Graph**.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="9a0fd-122">Per ulteriori informazioni, vedi [Installare Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="9a0fd-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="9a0fd-123">Nel PC, seleziona il tasto Windows sulla tastiera e cerca **Windows PowerShell**, quindi seleziona **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="9a0fd-124">Nella finestra di PowerShell che si apre, immetti `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="9a0fd-125">Crea l'entità servizio per Audience Insights con il modulo Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="9a0fd-126">Nella finestra di PowerShell, immetti `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="9a0fd-127">Sostituisci "l'ID tenant" con l'ID effettivo del tenant in cui desideri creare l'entità servizio.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="9a0fd-128">Il parametro del nome dell'ambiente `AzureEnvironmentName` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="9a0fd-129">Immetti `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="9a0fd-130">Questo comando crea l'entità servizio per Audience Insights nel tenant selezionato.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="9a0fd-131">Concedere autorizzazioni all'entità servizio per accedere all'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="9a0fd-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="9a0fd-132">Vai al portale di Azure per concedere le autorizzazioni all'entità servizio per l'account di archiviazione che intendi usare in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="9a0fd-133">Vai al [portale di amministrazione di Azure](https://portal.azure.com) e accedi alla tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="9a0fd-134">Apri l'account di archiviazione a cui l'entità servizio per Audience Insight deve avere accesso.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="9a0fd-135">Seleziona **Controllo di accesso (IAM)** nel riquadro di spostamento e seleziona **Aggiungi** > **Aggiungi assegnazione ruolo**.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot che mostra il portale di Azure durante l'aggiunta di un'assegnazione di ruolo.":::
   
1. <span data-ttu-id="9a0fd-137">Nel riquadro **Aggiungi assegnazione ruolo**, imposta le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="9a0fd-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="9a0fd-138">Ruolo: *Collaboratore dati BLOB di archiviazione*</span><span class="sxs-lookup"><span data-stu-id="9a0fd-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="9a0fd-139">Assegna accesso a: *Utente, gruppo o entità servizio*</span><span class="sxs-lookup"><span data-stu-id="9a0fd-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="9a0fd-140">Seleziona: *Dynamics 365 AI for Customer Insights* (l'[entità servizio creata](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="9a0fd-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="9a0fd-141">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-141">Select **Save**.</span></span>

<span data-ttu-id="9a0fd-142">La propagazione delle modifiche può durare fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="9a0fd-143">Immetti l'ID risorsa di Azure o i dettagli della sottoscrizione di Azure nell'allegato dell'account di archiviazione di Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="9a0fd-144">Associa un account di archiviazione di Azure Data Lake in Audience Insights per [memorizzare i dati di output](manage-environments.md) o [usalo come origine dati](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="9a0fd-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="9a0fd-145">La scelta dell'opzione Azure Data Lake ti consente di scegliere tra un approccio basato sulle risorse e un approccio basato sulla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="9a0fd-146">Segui i passaggi seguenti per fornire le informazioni necessarie sull'approccio selezionato.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="9a0fd-147">Connessione dell'account di archiviazione basata sulle risorse</span><span class="sxs-lookup"><span data-stu-id="9a0fd-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="9a0fd-148">Vai al [portale di amministrazione di Azure](https://portal.azure.com), accedi alla tua sottoscrizione e apri l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="9a0fd-149">Vai a **Impostazioni** > **Proprietà** nel riquadro di navigazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="9a0fd-150">Copia il valore dell'ID risorsa dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiare il valore dell'ID risorsa dell'account di archiviazione.":::

1. <span data-ttu-id="9a0fd-152">In Audience Insights, inserisci l'ID risorsa nel campo della risorsa visualizzato nella schermata di connessione dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Immettere le informazioni dell'ID risorsa dell'account di archiviazione.":::   
   
1. <span data-ttu-id="9a0fd-154">Continua con i passaggi rimanenti in Audience Insights per associare l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="9a0fd-155">Connessione dell'account di archiviazione basata sulla sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="9a0fd-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="9a0fd-156">Vai al [portale di amministrazione di Azure](https://portal.azure.com), accedi alla tua sottoscrizione e apri l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="9a0fd-157">Vai a **Impostazioni** > **Proprietà** nel riquadro di navigazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="9a0fd-158">Esamina la **Sottoscrizione**, il **Gruppo di risorse** e il **Nome** dell'account di archiviazione per assicurarti di selezionare i valori corretti in Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="9a0fd-159">In Audience Insights, scegli i valori dei campi corrispondenti quando associ l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Immettere le informazioni dell'ID risorsa dell'account di archiviazione.":::
   
1. <span data-ttu-id="9a0fd-161">Continua con i passaggi rimanenti in Audience Insights per associare l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9a0fd-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
