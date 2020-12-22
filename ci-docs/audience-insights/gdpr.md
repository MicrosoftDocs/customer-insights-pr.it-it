---
title: Richieste diritti dell'interessato (DSR) ai sensi del GDPR | Microsoft Docs
description: Rispondere alle richieste diritti dell'interessato per la funzionalità Audience Insights di Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406123"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="99c84-103">Richieste diritti dell'interessato ai sensi del GDPR</span><span class="sxs-lookup"><span data-stu-id="99c84-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="99c84-104">Risposta alle richieste di eliminazione dell'interessato ai sensi del GDPR per la funzionalità Audience Insights di Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="99c84-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="99c84-105">Il "diritto alla cancellazione" mediante rimozione dei dati personali dai dati cliente di un'organizzazione è una protezione chiave del Regolamento generale sulla protezione dei dati (GDPR).</span><span class="sxs-lookup"><span data-stu-id="99c84-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="99c84-106">La rimozione dei dati personali include la rimozione di tutti i dati personali e di registri generati dal sistema, ad eccezione di informazioni del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="99c84-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="99c84-107">Gestire le richieste di eliminazione dell'interessato</span><span class="sxs-lookup"><span data-stu-id="99c84-107">Manage data subject delete requests</span></span>

<span data-ttu-id="99c84-108">Audience Insights offre le seguenti esperienze nel prodotto per eliminare i dati personali per un cliente specifico o un utente di Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="99c84-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="99c84-109">**Gestisci le richieste di eliminazione di dati cliente**: i dati cliente in Customer Insights vengono inseriti dalle origini dati originali esterne a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="99c84-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="99c84-110">Tutte le richieste di eliminazione ai sensi del GDPR devono essere eseguite nell'origine dati originale.</span><span class="sxs-lookup"><span data-stu-id="99c84-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="99c84-111">**Gestisci le richieste di eliminazione di dati utente per Customer Insights**: i dati per gli utenti vengono creati da Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="99c84-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="99c84-112">Tutte le richieste di eliminazione ai sensi del GDPR devono essere eseguite in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="99c84-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="99c84-113">Gestire le richieste di eliminazione di dati cliente</span><span class="sxs-lookup"><span data-stu-id="99c84-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="99c84-114">Un amministratore di Customer Insights può seguire questi passaggi per rimuovere i dati cliente che sono stati eliminati nell'origine dati:</span><span class="sxs-lookup"><span data-stu-id="99c84-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="99c84-115">Accedere a Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="99c84-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="99c84-116">In Audience Insights, vai a **Dati** > **Origini dati**</span><span class="sxs-lookup"><span data-stu-id="99c84-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="99c84-117">Per ogni origine dati nell'elenco che contiene i dati cliente eliminati:</span><span class="sxs-lookup"><span data-stu-id="99c84-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="99c84-118">Seleziona (...) e quindi **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="99c84-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="99c84-119">Controlla lo stato dell'origine dati in **Stato**.</span><span class="sxs-lookup"><span data-stu-id="99c84-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="99c84-120">Un segno di spunta indica che l'aggiornamento è stato completato.</span><span class="sxs-lookup"><span data-stu-id="99c84-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="99c84-121">Un triangolo di avviso significa che si è verificato un problema.</span><span class="sxs-lookup"><span data-stu-id="99c84-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="99c84-122">Se viene visualizzato un triangolo di avviso, contatta D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="99c84-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="99c84-123">![Gestione delle richieste di eliminazione di dati cliente ai sensi del GDPR](media/gdpr-data-sources.png "Gestione delle richieste di eliminazione di dati cliente ai sensi del GDPR")</span><span class="sxs-lookup"><span data-stu-id="99c84-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="99c84-124">Gestire le richieste di eliminazione di dati utente</span><span class="sxs-lookup"><span data-stu-id="99c84-124">Manage delete requests for user data</span></span>

<span data-ttu-id="99c84-125">Un amministratore di Customer Insights può seguire questi passaggi per eliminare i dati utente di Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="99c84-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="99c84-126">Accedere a Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="99c84-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="99c84-127">In Audience Insights, vai a **Amministratore** > **Autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="99c84-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="99c84-128">Seleziona la casella di controllo corrispondente all'utente che vuoi eliminare.</span><span class="sxs-lookup"><span data-stu-id="99c84-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="99c84-129">Seleziona **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="99c84-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="99c84-130">![Gestire le richieste di eliminazione di dati utente ai sensi del GPDR](media/gdpr-permissions.png "Gestire le richieste di eliminazione di dati utente ai sensi del GDPR")</span><span class="sxs-lookup"><span data-stu-id="99c84-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="99c84-131">Rispondere alle richieste di esportazione dell'interessato ai sensi del GDPR</span><span class="sxs-lookup"><span data-stu-id="99c84-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="99c84-132">Nell'ambito del nostro impegno a collaborare con gli utenti per il loro percorso verso il regolamento generale sulla protezione dei dati (GDPR), abbiamo elaborato la documentazione che ti assiste nella preparazione.</span><span class="sxs-lookup"><span data-stu-id="99c84-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="99c84-133">Questa documentazione descrive i passaggi che puoi eseguire per supportare la conformità al GDPR quando utilizzi Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="99c84-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="99c84-134">Gestire le richieste di esportazione e visualizzazione</span><span class="sxs-lookup"><span data-stu-id="99c84-134">Manage export and view requests</span></span>

<span data-ttu-id="99c84-135">Il diritto della trasferibilità dei dati consente a un interessato di richiedere una copia dei dati personali in formato elettronico (definito come un "formato interoperativo, leggibile su PC, comunemente utilizzato e strutturato") che possa essere trasmesso a un altro controller di dati.</span><span class="sxs-lookup"><span data-stu-id="99c84-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="99c84-136">Esportare dati cliente (amministratore del tenant)</span><span class="sxs-lookup"><span data-stu-id="99c84-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="99c84-137">L'amministratore di un tenant può seguire questa procedura per esportare i dati:</span><span class="sxs-lookup"><span data-stu-id="99c84-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="99c84-138">Invia un messaggio e-mail a D365CI@microsoft.com specificando l'indirizzo e-mail del cliente nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="99c84-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="99c84-139">Il team di Customer Insights invierà un messaggio e-mail all'indirizzo di posta elettronica dell'amministratore del tenant registrato, chiedendo la conferma per esportare i dati.</span><span class="sxs-lookup"><span data-stu-id="99c84-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="99c84-140">Accetta la conferma di esportazione dei dati per il cliente che ha effettuato la richiesta.</span><span class="sxs-lookup"><span data-stu-id="99c84-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="99c84-141">Ricevi i dati esportati tramite l'indirizzo e-mail dell'amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="99c84-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="99c84-142">Esportare dati utente (amministratore del tenant)</span><span class="sxs-lookup"><span data-stu-id="99c84-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="99c84-143">Invia un messaggio e-mail a D365CI@microsoft.com specificando l'indirizzo e-mail dell'utente nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="99c84-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="99c84-144">Il team di Customer Insights invierà un messaggio e-mail all'indirizzo di posta elettronica dell'amministratore del tenant registrato, chiedendo la conferma per esportare i dati.</span><span class="sxs-lookup"><span data-stu-id="99c84-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="99c84-145">Accetta la conferma di esportazione dei dati per l'utente che ha effettuato la richiesta.</span><span class="sxs-lookup"><span data-stu-id="99c84-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="99c84-146">Ricevi i dati esportati tramite l'indirizzo e-mail dell'amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="99c84-146">Receive the exported data through the tenant admin email address.</span></span>
