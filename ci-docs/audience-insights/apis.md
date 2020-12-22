---
title: Utilizzare le API
description: Utilizzare le API e comprendere le limitazioni
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689135"
---
# <a name="work-with-customer-insights-apis"></a>Utilizzare le API di Customer Insights

Dynamics 365 Customer Insights fornisce API per creare applicazioni basate su dati in Customer Insights.

> [!IMPORTANT]
> I dettagli di queste API sono elencati nel [Riferimento API di Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Includono informazioni aggiuntive su operazioni, parametri e risposte.

Questo articolo illustra come accedere alle API di Customer Insights, creare una registrazione di app Azure e iniziare a utilizzare le librerie client disponibili.

## <a name="get-started-trying-the-customer-insights-apis"></a>Iniziare a utilizzare le API di Customer Insights

1. [Accedi](https://home.ci.ai.dynamics.com) a Customer Insights. Se non hai ancora una sottoscrizione, [registrati per una versione di valutazione di Customer Insights](https://aka.ms/tryci).

1. Per abilitare le API nel tuo ambiente Customer Insights, seleziona **Amministratore** > **Autorizzazioni**. Per farlo devi disporre delle autorizzazioni di amministratore.

1. Vai alla scheda **API** e seleziona il pulsante **Abilita**.    
   L'abilitazione delle API crea una chiave di sottoscrizione primaria e secondaria per l'istanza che viene utilizzata nelle richieste API. Puoi rigenerare le chiavi selezionando **Rigenera primaria** o **Rigenera secondaria** in **Amministratore** > **Autorizzazioni** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Abilitare le API di Customer Insights":::.

1. Seleziona **Esplora le nostre API** per provare le API.

1. Scegli un'operazione API e seleziona **Prova**.

1. Nel riquadro laterale, imposta il valore **implicito** nel menu a discesa **Autorizzazione**. All'intestazione `Authorization` viene aggiunto un token di connessione. La chiave di sottoscrizione verrà popolata automaticamente.
  
1. Se lo si desideri, aggiungi tutti i parametri di query necessari.

1. Scorri fino alla fine del riquadro laterale e seleziona **Invia**.

La risposta HTTP apparirà sotto dopo alcuni secondi.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Creare una nuova registrazione di app nel portale di Azure

Questi passaggi ti consentono di iniziare a usare le API di Customer Insights in un'applicazione Azure utilizzando autorizzazioni delegate. Assicurati di aver completato la [sezione precedente](#get-started-trying-the-customer-insights-apis).

1. Accedi al [portale di Azure](https://portal.azure.com) con l'account che può accedere ai dati di Customer Insights.

1. A sinistra, seleziona **Registrazioni app**.

1. Seleziona **Nuova registrazione** per immettere un nome per l'applicazione e scegliere il tipo di account.
   Se lo desideri, aggiungi un URL di reindirizzamento. http://localhost è sufficiente per sviluppare un'applicazione nel computer locale.

1. Nella nuova registrazione, seleziona **Autorizzazioni API**.

1. Seleziona **Aggiungi un'autorizzazione** e seleziona **Customer Insights** nel pannello laterale.

1. Per **Tipo di autorizzazione**, selezionare **Autorizzazioni delegate** e seleziona l'autorizzazione **user_impersonation**.

1. Seleziona **Aggiungi autorizzazioni**. Se devi all'API senza che un utente abbia effettuato l'accesso, vedi la sezione [Autorizzazioni tra server](#server-to-server-application-permissions).

1. Seleziona **Concedi consenso amministratore per...** per completare la registrazione.

Puoi utilizzare l'ID applicazione/client per questa registrazione con la libreria MSAL (Microsoft Authentication Library) per ottenere un token di connessione da inviare con la richiesta all'API.

Per ulteriori informazioni sulla libreria MSAL, vedi [Panoramica della libreria MSAL](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Per altre informazioni sulla registrazione di app in Azure, vedi [La nuova esperienza di registrazione di app nel portale di Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Per informazioni sull'utilizzo delle API delle nostre librerie client, vedi [Librerie client di Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Autorizzazioni delle applicazioni da server a server

La [sezione sulla registrazione di app](#create-a-new-app-registration-in-the-azure-portal) descrive come registrare un'app che richiede l'accesso di un utente per l'autenticazione. Scopri come creare una registrazione di app che non richiede l'interazione dell'utente e può essere eseguita su un server.

1. Nella registrazione dell'app nel portale di Azure, seleziona **Autorizzazioni API**.

1. Seleziona **Aggiungi un'autorizzazione** e seleziona **Customer Insights** nel pannello laterale.

1. Per **Tipo di autorizzazione**, seleziona **Autorizzazioni applicazione** e seleziona l'autorizzazione **CustomerInsights.Api.All**.

1. Seleziona **Aggiungi autorizzazioni**.

1. Per concedere il consenso amministratore a questa autorizzazione, devi aggiungere un'entità servizio.

   1. Installa il moduli Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Connettiti all'account AD: `Connect-AzureAD -TenantId <your tenant id>`. Puoi trovare l'ID tenant in **Panoramica** > **Azure Active Directory**.
   1. Esegui il comando seguente per aggiungere un'entità di sicurezza Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Il parametro AppId riguarda l'app API di Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Esempio di entità servizio":::

1. Torna a **Autorizzazioni API** per la registrazione dell'app.

1. Seleziona **Concedi consenso amministratore per...** per completare la registrazione.

1. Infine, dobbiamo aggiungere il nome della registrazione dell'app come utente in Customer Insights.    
   Apri Customer Insights, seleziona **Amministratore** > **Autorizzazioni** e **Aggiungi utente**.

1. Cerca il nome della registrazione dell'app, selezionalo nei risultati della ricerca e seleziona **Salva**.

## <a name="customer-insights-client-libraries"></a>Librerie client di Customer Insights

Questa sezione ti consente di iniziare a utilizzare le librerie client disponibili per le API Customer Insights.

### <a name="c-nuget"></a>C# NuGet

Scopri come iniziare a utilizzare le librerie client C# in NuGet.org. Per ulteriori informazioni sul pacchetto NuGet, vedi [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Attualmente, questo pacchetto è per i framework netstandard2.0 e netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Aggiungi la libreria client C# a un progetto C#

1. In Visual Studio, apri la **Gestione pacchetti NuGet** per il progetto.

1. Cerca **Microsoft.Dynamics.CustomerInsights.Api**.

1. Seleziona **Installa** per aggiungere il pacchetto al progetto.
   In alternativa, esegui questo comando nella **console di Gestione pacchetti NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Aggiungere il pacchetto NuGet al progetto Visual Studio":::

#### <a name="use-the-c-client-library"></a>Usare la libreria client C#

1. Utilizza la [libreria MSAL](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) per ottenere un `AccessToken` usando la [registrazione dell'app Azure](#create-a-new-app-registration-in-the-azure-portal) esistente.

1. Dopo aver autenticato e acquisito un token, creane uno o utilizza un `HttpClient` esistente con il **DefaultRequestHeaders "Autorizzazione"** aggiuntivo impostato su **<access token> di connessione** e **Ocp-Apim-Subscription-Key** impostato su [**chiave di sottoscrizione** nell'ambiente Customer Insights ](#get-started-trying-the-customer-insights-apis).    
   Reimposta l'intestazione **Autorizzazione** quando appropriato. Ad esempio, alla scadenza del token.

1. Passa `HttpClient` nella costruzione del client `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Esempio di httpclient":::

1. Effettua chiamate con il client ai "metodi di estensione", ad esempio, `GetAllInstancesAsync`. Se l'accesso al `Microsoft.Rest.HttpOperationResponse` sottostante è preferibile, utilizza i "metodi di messaggio http", ad esempio `GetAllInstancesWithHttpMessagesAsync`.

1. La risposta sarà probabilmente di tipo `object` poiché il metodo può restituire più tipi (ad esempio, `IList<InstanceInfo>` e `ApiErrorResult`). Per controllare il tipo restituito, puoi eseguire il cast degli oggetti in modo sicuro nei tipi di risposta specificati nella [pagina dei dettagli dell'API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) per quell'operazione.    
   Se sono necessarie ulteriori informazioni sulla richiesta, utilizza i **metodi di messaggio http** per accedere all'oggetto risposta non elaborato.
