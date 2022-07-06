---
title: Utilizzare le API di Customer Insights
description: Utilizzare le API e comprendere le limitazioni
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 8e8bd590d3bba9dc7b1644b6ff42b9fc53237ca9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054069"
---
# <a name="work-with-customer-insights-apis"></a>Utilizzare le API di Customer Insights

Dynamics 365 Customer Insights fornisce API per creare le tue applicazioni in base ai tuoi dati in Customer Insights.

> [!IMPORTANT]
> I dettagli di queste API sono elencati nel [Riferimento API di Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Includono informazioni aggiuntive su operazioni, parametri e risposte.

Questo articolo descrive come accedere alle API di Customer Insights, come creare una registrazione di app Azure e come iniziare a utilizzare le librerie client.

## <a name="get-started-trying-the-customer-insights-apis"></a>Iniziare a utilizzare le API di Customer Insights

1. [Accedi](https://home.ci.ai.dynamics.com) a Customer Insights. Se non hai ancora una sottoscrizione, [registrati per una versione di valutazione di Customer Insights](https://aka.ms/tryci).

1. Per abilitare le API nel tuo ambiente Customer Insights, vai ad **Amministratore** > **Sicurezza**. Per farlo devi disporre delle autorizzazioni di amministratore.

1. Vai alla scheda **API** e seleziona il pulsante **Abilita**.    
 
   L'abilitazione delle API crea una chiave di sottoscrizione primaria e secondaria per l'istanza che viene utilizzata nelle richieste API. È possibile rigenerare le chiavi selezionando le opzioni **Rigenera primaria** o **Rigenera secondaria** in **Amministratore** > **Sicurezza** > **API**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Seleziona **Esplora le nostre API** per [provare le API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Scegli un'operazione API e seleziona **Prova**.

1. Nel riquadro laterale imposta il valore nel menu a discesa **Autorizzazione** su **implicito**. L'intestazione `Authorization` viene aggiunta con un token di connessione. La chiave di sottoscrizione verrà popolata automaticamente.
  
1. Se lo si desideri, aggiungi tutti i parametri di query necessari.

1. Scorri fino alla fine del riquadro laterale e seleziona **Invia**.

La risposta HTTP apparirà sotto dopo alcuni secondi.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Creare una nuova registrazione di app nel portale di Azure

Questi passaggi ti aiutano a iniziare a utilizzare le API di Customer Insights in un'applicazione di Azure usando le autorizzazioni delegate. Assicurati di completare prima la [Sezione introduttiva](#get-started-trying-the-customer-insights-apis).

1. Accedi al [portale di Azure](https://portal.azure.com) con l'account che può accedere ai dati di Customer Insights.

1. A sinistra, seleziona **Registrazioni app**.

1. Seleziona **Nuova registrazione**, immetti un nome per l'applicazione e scegli il tipo di account.

   Se lo desideri, aggiungi un URL di reindirizzamento. http://localhost è sufficiente per sviluppare un'applicazione nel computer locale.

1. Nella nuova registrazione, seleziona **Autorizzazioni API**.

1. Seleziona **Aggiungi un'autorizzazione** e seleziona **Dynamics 365 AI per Customer Insights** nel riquadro laterale.

1. Per **Tipo di autorizzazione** seleziona **Autorizzazioni delegate**, quindi l'autorizzazione **user_impersonation**.

1. Seleziona **Aggiungi autorizzazioni**. Se devi all'API senza che un utente abbia effettuato l'accesso, vedi la sezione [Autorizzazioni tra server](#server-to-server-application-permissions).

1. Seleziona **Concedi consenso amministratore per...** per completare la registrazione.

Puoi utilizzare l'ID applicazione/client per questa registrazione con la libreria MSAL (Microsoft Authentication Library) per ottenere un token di connessione da inviare con la richiesta all'API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Per ulteriori informazioni sulla libreria MSAL, vedi [Panoramica della libreria MSAL](/azure/active-directory/develop/msal-overview).

Per ulteriori informazioni sulla registrazione dell'app in Azure, vedi [Registrare un'applicazione](/graph/auth-register-app-v2).

Per informazioni sull'utilizzo delle API nelle librerie client, vedi [Librerie client di Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Autorizzazioni delle applicazioni da server a server

La [sezione sulla registrazione di app](#create-a-new-app-registration-in-the-azure-portal) descrive come registrare un'app che richiede l'accesso di un utente per l'autenticazione. Scopri come creare una registrazione di un'app che non richiede l'interazione dell'utente e che può essere eseguita su un server.

1. Nella registrazione dell'app nel portale di Azure, seleziona **Autorizzazioni API**.

1. Seleziona **Aggiungi autorizzazione**. 

1. Seleziona la scheda **API utilizzate dall'organizzazione** e scegli **Dynamics 365 AI for Customer Insights** dall'elenco. 

1. Per **Tipo di autorizzazione** seleziona **Autorizzazione dell'applicazione**, quindi l'autorizzazione **CustomerInsights.Api.All**.

1. Seleziona **Aggiungi autorizzazioni**.

1. Torna a **Autorizzazioni API** per la registrazione dell'app.

1. Seleziona **Concedi consenso amministratore per...** per completare la registrazione.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Infine, dobbiamo aggiungere il nome della registrazione dell'app come utente in Customer Insights.  
   
   Apri Customer Insights, vai ad **Amministratore** > **Sicurezza** e seleziona **Aggiungi utente**.

1. Cerca il nome della registrazione dell'app, selezionalo nei risultati della ricerca e seleziona **Salva**.

## <a name="sample-queries"></a>Query di esempio

Abbiamo compilato un breve elenco di query di esempio OData per usare le API :[Esempi di query OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Librerie client di Customer Insights

Questa sezione ti consente di iniziare a utilizzare le librerie client disponibili per le API Customer Insights. Tutto il codice sorgente della libreria e le applicazioni di esempio sono disposponibili nella [pagina GitHub di Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Scopri come iniziare a utilizzare le librerie client C# in NuGet.org. Per ulteriori informazioni sul pacchetto NuGet, vedi [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Attualmente, questo pacchetto è per i framework netstandard2.0 e netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Aggiungi la libreria client C# a un progetto C#

1. In Visual Studio, apri la **Gestione pacchetti NuGet** per il progetto.

1. Cerca **Microsoft.Dynamics.CustomerInsights.Api**.

1. Seleziona **Installa** per aggiungere il pacchetto al progetto.
 
   In alternativa, esegui questo comando nella **console di Gestione pacchetti NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Usare la libreria client C#

1. Utilizza la [libreria MSAL](/azure/active-directory/develop/msal-overview) per ottenere un `AccessToken` usando la [registrazione dell'app Azure](#create-a-new-app-registration-in-the-azure-portal) esistente.

1. Dopo aver eseguito correttamente l'autenticazione e l'acquisizione di un token, costruisci un nuovo `HttpClient` o utilizzane uno esistente con l'**"Autorizzazione" DefaultRequestHeaders** impostata su **"Token di accesso" portante** e **Ocp-Apim-Subscription-Key** impostato sulla [**chiave di sottoscrizione** del tuo ambiente Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Reimposta l'intestazione **Autorizzazione** quando appropriato. Ad esempio, alla scadenza del token.

1. Passa `HttpClient` nella costruzione del client `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Effettua chiamate con il client ai "metodi di estensione", ad esempio `GetAllInstancesAsync`. Se l'accesso al `Microsoft.Rest.HttpOperationResponse` sottostante è preferibile, utilizza i "metodi di messaggio http", ad esempio `GetAllInstancesWithHttpMessagesAsync`.

1. La risposta sarà probabilmente di tipo `object` poiché il metodo può restituire più tipi (ad esempio, `IList<InstanceInfo>` e `ApiErrorResult`). Per controllare il tipo restituito, utilizza gli oggetti nei tipi di risposta specificati in [Pagina dei dettagli dell'API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) per quell'operazione.    
   
   Se sono necessarie ulteriori informazioni sulla richiesta, utilizza i **metodi di messaggio http** per accedere all'oggetto risposta non elaborato.

### <a name="nodejs-package"></a>Pacchetto NodeJS

Utilizza le librerie client NodeJS disponibili tramite NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pacchetto Python

Utilizza le librerie client Python disponibili tramite PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
