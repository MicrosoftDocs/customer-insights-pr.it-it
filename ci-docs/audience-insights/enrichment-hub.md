---
title: Arricchire profili cliente unificati
description: Usa specifiche funzionalità per arricchire i tuoi dati cliente.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667099"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="c9024-103">Arricchimento per i profili cliente (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c9024-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="c9024-104">Utilizza i dati provenienti da origini come Microsoft e altri partner per arricchire i dati dei tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="c9024-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina dell'hub di arricchimento":::

<span data-ttu-id="c9024-106">In Audience Insights, vai a **Dati** > **Arricchimento** per utilizzare le opzioni di arricchimento.</span><span class="sxs-lookup"><span data-stu-id="c9024-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="c9024-107">Devi disporre delle autorizzazioni come Collaboratore o Amministratore per creare o modificare gli arricchimenti.</span><span class="sxs-lookup"><span data-stu-id="c9024-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="c9024-108">Per ulteriori informazioni, vedi [Autorizzazioni](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c9024-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="c9024-109">Nella scheda **Scopri**, troverai i seguenti arricchimenti:</span><span class="sxs-lookup"><span data-stu-id="c9024-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="c9024-110">[Marchi](enrichment-microsoft-graph.md) forniti da Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="c9024-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="c9024-111">[Interessi](enrichment-microsoft-graph.md) forniti da Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="c9024-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="c9024-112">[Dati aziendali](enrichment-leadspace.md) forniti da Leadspace</span><span class="sxs-lookup"><span data-stu-id="c9024-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="c9024-113">[Dati demografici](enrichment-experian.md) forniti da Experian</span><span class="sxs-lookup"><span data-stu-id="c9024-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="c9024-114">[Dati di localizzazione](enrichment-here.md) forniti da HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="c9024-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="c9024-115">[Personalizzare i dati](enrichment-SFTP-custom-import.md) mediante Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="c9024-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="c9024-116">Nella scheda **I miei arricchimenti**, puoi vedere gli arricchimenti che hai configurato e modificarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="c9024-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="c9024-117">Gestire gli arricchimenti esistenti</span><span class="sxs-lookup"><span data-stu-id="c9024-117">Manage existing enrichments</span></span>

<span data-ttu-id="c9024-118">Vai a **Arricchimenti personali** per vedere tutti gli arricchimenti configurati.</span><span class="sxs-lookup"><span data-stu-id="c9024-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="c9024-119">Ogni arricchimento è rappresentato come una riga che include informazioni aggiuntive sull'arricchimento.</span><span class="sxs-lookup"><span data-stu-id="c9024-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="c9024-120">Seleziona un arricchimento per vedere le opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="c9024-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="c9024-121">In alternativa, puoi selezionare i puntini di sospensione (...) su un elemento dell'elenco per visualizzare le opzioni.</span><span class="sxs-lookup"><span data-stu-id="c9024-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opzioni per gestire gli arricchimenti nell'elenco degli arricchimenti":::

- <span data-ttu-id="c9024-123">**Visualizza** i dettagli dell'arricchimento con il numero di profili cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="c9024-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="c9024-124">**Modifica** la configurazione dell'arricchimento.</span><span class="sxs-lookup"><span data-stu-id="c9024-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="c9024-125">**Eseguire** l'arricchimento per aggiornare i profili cliente con i dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="c9024-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="c9024-126">**Disattiva** un arricchimento esistente per impedirne l'aggiornamento automatico a ogni aggiornamento pianificato.</span><span class="sxs-lookup"><span data-stu-id="c9024-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="c9024-127">I dati dell'ultimo aggiornamento riuscito continueranno a essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="c9024-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="c9024-128">**Attiva** un arricchimento inattivo per riavviare l'aggiornamento automatico con ogni aggiornamento pianificato.</span><span class="sxs-lookup"><span data-stu-id="c9024-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="c9024-129">**Elimina** un arricchimento.</span><span class="sxs-lookup"><span data-stu-id="c9024-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="c9024-130">Puoi eseguire o disattivare più arricchimenti contemporaneamente selezionandoli nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c9024-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="c9024-131">Le opzioni di visualizzazione e modifica non sono disponibili come azione in blocco e funzionano solo per un arricchimento alla volta.</span><span class="sxs-lookup"><span data-stu-id="c9024-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>