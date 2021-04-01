---
title: Utilizzare le API
description: Utilizzare le API e comprendere le limitazioni
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710465"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="fc800-103">Utilizzare le API di Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fc800-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="fc800-104">Dynamics 365 Customer Insights fornisce API per creare applicazioni basate su dati in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fc800-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc800-105">I dettagli di queste API sono elencati nel [Riferimento API di Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="fc800-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="fc800-106">Includono informazioni aggiuntive su operazioni, parametri e risposte.</span><span class="sxs-lookup"><span data-stu-id="fc800-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="fc800-107">Questo articolo illustra come accedere alle API di Customer Insights, creare una registrazione di app Azure e iniziare a utilizzare le librerie client disponibili.</span><span class="sxs-lookup"><span data-stu-id="fc800-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="fc800-108">Iniziare a utilizzare le API di Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fc800-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="fc800-109">[Accedi](https://home.ci.ai.dynamics.com) a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fc800-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="fc800-110">Se non hai ancora una sottoscrizione, [registrati per una versione di valutazione di Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="fc800-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="fc800-111">Per abilitare le API nel tuo ambiente Customer Insights, seleziona **Amministratore** > **Autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="fc800-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="fc800-112">Per farlo devi disporre delle autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="fc800-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="fc800-113">Vai alla scheda **API** e seleziona il pulsante **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="fc800-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="fc800-114">L'abilitazione delle API crea una chiave di sottoscrizione primaria e secondaria per l'istanza che viene utilizzata nelle richieste API.</span><span class="sxs-lookup"><span data-stu-id="fc800-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="fc800-115">Puoi rigenerare le chiavi selezionando **Rigenera primaria** o **Rigenera secondaria** in **Amministratore** > **Autorizzazioni** > **API**.</span><span class="sxs-lookup"><span data-stu-id="fc800-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Abilitare le API di Customer Insights":::.

1. <span data-ttu-id="fc800-117">Seleziona **Esplora le nostre API** per [provare le API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="fc800-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="fc800-118">Scegli un'operazione API e seleziona **Prova**.</span><span class="sxs-lookup"><span data-stu-id="fc800-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="fc800-119">Nel riquadro laterale, imposta il valore **implicito** nel menu a discesa **Autorizzazione**.</span><span class="sxs-lookup"><span data-stu-id="fc800-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="fc800-120">All'intestazione `Authorization` viene aggiunto un token di connessione.</span><span class="sxs-lookup"><span data-stu-id="fc800-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="fc800-121">La chiave di sottoscrizione verrà popolata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fc800-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="fc800-122">Se lo si desideri, aggiungi tutti i parametri di query necessari.</span><span class="sxs-lookup"><span data-stu-id="fc800-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="fc800-123">Scorri fino alla fine del riquadro laterale e seleziona **Invia**.</span><span class="sxs-lookup"><span data-stu-id="fc800-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="fc800-124">La risposta HTTP apparirà sotto dopo alcuni secondi.</span><span class="sxs-lookup"><span data-stu-id="fc800-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="GIF animata che mostra come selezionare il test delle API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="fc800-126">Creare una nuova registrazione di app nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="fc800-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="fc800-127">Questi passaggi ti consentono di iniziare a usare le API di Customer Insights in un'applicazione Azure utilizzando autorizzazioni delegate.</span><span class="sxs-lookup"><span data-stu-id="fc800-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="fc800-128">Assicurati di aver completato la [sezione precedente](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="fc800-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="fc800-129">Accedi al [portale di Azure](https://portal.azure.com) con l'account che può accedere ai dati di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fc800-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="fc800-130">A sinistra, seleziona **Registrazioni app**.</span><span class="sxs-lookup"><span data-stu-id="fc800-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="fc800-131">Seleziona **Nuova registrazione** per immettere un nome per l'applicazione e scegliere il tipo di account.</span><span class="sxs-lookup"><span data-stu-id="fc800-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="fc800-132">Se lo desideri, aggiungi un URL di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="fc800-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="fc800-133">http://localhost è sufficiente per sviluppare un'applicazione nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="fc800-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="fc800-134">Nella nuova registrazione, seleziona **Autorizzazioni API**.</span><span class="sxs-lookup"><span data-stu-id="fc800-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="GIF animata per impostare l'autorizzazione API nella registrazione dell'app.":::

1. <span data-ttu-id="fc800-136">Seleziona **Aggiungi un'autorizzazione** e seleziona **Customer Insights** nel pannello laterale.</span><span class="sxs-lookup"><span data-stu-id="fc800-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="fc800-137">Per **Tipo di autorizzazione**, selezionare **Autorizzazioni delegate** e seleziona l'autorizzazione **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="fc800-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="fc800-138">Seleziona **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="fc800-138">Select **Add permissions**.</span></span> <span data-ttu-id="fc800-139">Se devi all'API senza che un utente abbia effettuato l'accesso, vedi la sezione [Autorizzazioni tra server](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="fc800-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="fc800-140">Seleziona **Concedi consenso amministratore per...** per completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="fc800-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="fc800-141">Puoi utilizzare l'ID applicazione/client per questa registrazione con la libreria MSAL (Microsoft Authentication Library) per ottenere un token di connessione da inviare con la richiesta all'API.</span><span class="sxs-lookup"><span data-stu-id="fc800-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="GIF animata per concedere il consenso dell'amministratore.":::

<span data-ttu-id="fc800-143">Per ulteriori informazioni sulla libreria MSAL, vedi [Panoramica della libreria MSAL](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="fc800-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="fc800-144">Per altre informazioni sulla registrazione di app in Azure, vedi [La nuova esperienza di registrazione di app nel portale di Azure](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="fc800-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="fc800-145">Per informazioni sull'utilizzo delle API delle nostre librerie client, vedi [Librerie client di Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="fc800-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="fc800-146">Autorizzazioni delle applicazioni da server a server</span><span class="sxs-lookup"><span data-stu-id="fc800-146">Server-to-server application permissions</span></span>

<span data-ttu-id="fc800-147">La [sezione sulla registrazione di app](#create-a-new-app-registration-in-the-azure-portal) descrive come registrare un'app che richiede l'accesso di un utente per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="fc800-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="fc800-148">Scopri come creare una registrazione di app che non richiede l'interazione dell'utente e può essere eseguita su un server.</span><span class="sxs-lookup"><span data-stu-id="fc800-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="fc800-149">Nella registrazione dell'app nel portale di Azure, seleziona **Autorizzazioni API**.</span><span class="sxs-lookup"><span data-stu-id="fc800-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="fc800-150">Seleziona **Aggiungi un'autorizzazione** e seleziona **Customer Insights** nel pannello laterale.</span><span class="sxs-lookup"><span data-stu-id="fc800-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="fc800-151">Per **Tipo di autorizzazione**, seleziona **Autorizzazioni applicazione** e seleziona l'autorizzazione **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="fc800-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="fc800-152">Seleziona **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="fc800-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="fc800-153">Per concedere il consenso amministratore a questa autorizzazione, devi aggiungere un'entità servizio.</span><span class="sxs-lookup"><span data-stu-id="fc800-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="fc800-154">Installa il moduli Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="fc800-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="fc800-155">Connettiti all'account AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="fc800-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="fc800-156">Puoi trovare l'ID tenant in **Panoramica** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="fc800-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="fc800-157">Esegui il comando seguente per aggiungere un'entità di sicurezza Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Il parametro AppId riguarda l'app API di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fc800-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Esempio di entità servizio":::

1. <span data-ttu-id="fc800-159">Torna a **Autorizzazioni API** per la registrazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="fc800-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="fc800-160">Seleziona **Concedi consenso amministratore per...** per completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="fc800-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="GIF animata per concedere il consenso dell'amministratore.":::

1. <span data-ttu-id="fc800-162">Infine, dobbiamo aggiungere il nome della registrazione dell'app come utente in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fc800-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="fc800-163">Apri Customer Insights, seleziona **Amministratore** > **Autorizzazioni** e **Aggiungi utente**.</span><span class="sxs-lookup"><span data-stu-id="fc800-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="fc800-164">Cerca il nome della registrazione dell'app, selezionalo nei risultati della ricerca e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fc800-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="fc800-165">Librerie client di Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fc800-165">Customer Insights client libraries</span></span>

<span data-ttu-id="fc800-166">Questa sezione ti consente di iniziare a utilizzare le librerie client disponibili per le API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fc800-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="fc800-167">Tutto il codice sorgente della libreria e le applicazioni di esempio sono disposponibili nella [pagina GitHub di Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="fc800-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="fc800-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="fc800-168">C# NuGet</span></span>

<span data-ttu-id="fc800-169">Scopri come iniziare a utilizzare le librerie client C# in NuGet.org. Per ulteriori informazioni sul pacchetto NuGet, vedi [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="fc800-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="fc800-170">Attualmente, questo pacchetto è per i framework netstandard2.0 e netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="fc800-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="fc800-171">Aggiungi la libreria client C# a un progetto C#</span><span class="sxs-lookup"><span data-stu-id="fc800-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="fc800-172">In Visual Studio, apri la **Gestione pacchetti NuGet** per il progetto.</span><span class="sxs-lookup"><span data-stu-id="fc800-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="fc800-173">Cerca **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="fc800-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="fc800-174">Seleziona **Installa** per aggiungere il pacchetto al progetto.</span><span class="sxs-lookup"><span data-stu-id="fc800-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="fc800-175">In alternativa, esegui questo comando nella **console di Gestione pacchetti NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="fc800-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Aggiungere il pacchetto NuGet al progetto Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="fc800-177">Usare la libreria client C#</span><span class="sxs-lookup"><span data-stu-id="fc800-177">Use the C# client library</span></span>

1. <span data-ttu-id="fc800-178">Utilizza la [libreria MSAL](/azure/active-directory/develop/msal-overview) per ottenere un `AccessToken` usando la [registrazione dell'app Azure](#create-a-new-app-registration-in-the-azure-portal) esistente.</span><span class="sxs-lookup"><span data-stu-id="fc800-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="fc800-179">Dopo aver autenticato e acquisito un token, creane uno o utilizza un `HttpClient` esistente con il **DefaultRequestHeaders "Autorizzazione"** aggiuntivo impostato su **<access token> di connessione** e **Ocp-Apim-Subscription-Key** impostato su [**chiave di sottoscrizione** nell'ambiente Customer Insights ](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="fc800-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="fc800-180">Reimposta l'intestazione **Autorizzazione** quando appropriato.</span><span class="sxs-lookup"><span data-stu-id="fc800-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="fc800-181">Ad esempio, alla scadenza del token.</span><span class="sxs-lookup"><span data-stu-id="fc800-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="fc800-182">Passa `HttpClient` nella costruzione del client `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="fc800-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Esempio di httpclient":::

1. <span data-ttu-id="fc800-184">Effettua chiamate con il client ai "metodi di estensione", ad esempio, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="fc800-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="fc800-185">Se l'accesso al `Microsoft.Rest.HttpOperationResponse` sottostante è preferibile, utilizza i "metodi di messaggio http", ad esempio `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="fc800-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="fc800-186">La risposta sarà probabilmente di tipo `object` poiché il metodo può restituire più tipi (ad esempio, `IList<InstanceInfo>` e `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="fc800-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="fc800-187">Per controllare il tipo restituito, puoi eseguire il cast degli oggetti in modo sicuro nei tipi di risposta specificati nella [pagina dei dettagli dell'API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) per quell'operazione.</span><span class="sxs-lookup"><span data-stu-id="fc800-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="fc800-188">Se sono necessarie ulteriori informazioni sulla richiesta, utilizza i **metodi di messaggio http** per accedere all'oggetto risposta non elaborato.</span><span class="sxs-lookup"><span data-stu-id="fc800-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="fc800-189">Pacchetto NodeJS</span><span class="sxs-lookup"><span data-stu-id="fc800-189">NodeJS package</span></span>

<span data-ttu-id="fc800-190">Utilizza le librerie client NodeJS disponibili tramite NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="fc800-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="fc800-191">Pacchetto Python</span><span class="sxs-lookup"><span data-stu-id="fc800-191">Python package</span></span>

<span data-ttu-id="fc800-192">Utilizza le librerie client Python disponibili tramite PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="fc800-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
