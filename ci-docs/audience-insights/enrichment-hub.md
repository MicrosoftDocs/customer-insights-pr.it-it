---
title: Arricchire profili cliente unificati
description: Usa specifiche funzionalità per arricchire i tuoi dati cliente.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954492"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="ee65c-103">Arricchimento per i profili cliente (anteprima)</span><span class="sxs-lookup"><span data-stu-id="ee65c-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="ee65c-104">Utilizza i dati provenienti da origini come Microsoft e altri partner per arricchire i dati dei tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="ee65c-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina dell'hub di arricchimento":::

<span data-ttu-id="ee65c-106">In Audience Insights, vai a **Dati** > **Arricchimento** per utilizzare le opzioni di arricchimento.</span><span class="sxs-lookup"><span data-stu-id="ee65c-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="ee65c-107">Devi disporre delle autorizzazioni come Collaboratore o Amministratore per creare o modificare gli arricchimenti.</span><span class="sxs-lookup"><span data-stu-id="ee65c-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="ee65c-108">Per ulteriori informazioni, vedi [Autorizzazioni](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ee65c-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="ee65c-109">Nella scheda **Scopri**, troverai i seguenti arricchimenti:</span><span class="sxs-lookup"><span data-stu-id="ee65c-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="ee65c-110">[Marchi](enrichment-microsoft.md) forniti da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee65c-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="ee65c-111">[Interessi](enrichment-microsoft.md) forniti da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee65c-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="ee65c-112">[Indirizzi avanzati](enrichment-enhanced-addresses.md) forniti da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee65c-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="ee65c-113">[Dati aziendali](enrichment-leadspace.md) forniti da Leadspace</span><span class="sxs-lookup"><span data-stu-id="ee65c-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="ee65c-114">[Dati demografici](enrichment-experian.md) forniti da Experian</span><span class="sxs-lookup"><span data-stu-id="ee65c-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="ee65c-115">[Dati di localizzazione](enrichment-here.md) forniti da HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="ee65c-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="ee65c-116">[Personalizzare i dati](enrichment-SFTP-custom-import.md) mediante Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="ee65c-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="ee65c-117">Nella scheda **I miei arricchimenti**, puoi vedere gli arricchimenti che hai configurato e modificarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="ee65c-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="ee65c-118">Gestire gli arricchimenti esistenti</span><span class="sxs-lookup"><span data-stu-id="ee65c-118">Manage existing enrichments</span></span>

<span data-ttu-id="ee65c-119">Vai a **Arricchimenti personali** per vedere tutti gli arricchimenti configurati.</span><span class="sxs-lookup"><span data-stu-id="ee65c-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="ee65c-120">Ogni arricchimento è rappresentato come una riga che include informazioni aggiuntive sull'arricchimento.</span><span class="sxs-lookup"><span data-stu-id="ee65c-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="ee65c-121">Seleziona un arricchimento per vedere le opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="ee65c-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="ee65c-122">È inoltre possibile selezionare i puntini di sospensione (...) di un elemento dell'elenco per visualizzare le opzioni.</span><span class="sxs-lookup"><span data-stu-id="ee65c-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opzioni per gestire gli arricchimenti nell'elenco degli arricchimenti":::

- <span data-ttu-id="ee65c-124">**Visualizza** i dettagli dell'arricchimento con il numero di profili cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="ee65c-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="ee65c-125">**Modifica** la configurazione dell'arricchimento.</span><span class="sxs-lookup"><span data-stu-id="ee65c-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="ee65c-126">**Eseguire** l'arricchimento per aggiornare i profili cliente con i dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="ee65c-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="ee65c-127">**Disattiva** un arricchimento esistente per impedirne l'aggiornamento automatico a ogni aggiornamento pianificato.</span><span class="sxs-lookup"><span data-stu-id="ee65c-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="ee65c-128">I dati dell'ultimo aggiornamento riuscito continueranno a essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="ee65c-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="ee65c-129">**Attiva** un arricchimento inattivo per riavviare l'aggiornamento automatico con ogni aggiornamento pianificato.</span><span class="sxs-lookup"><span data-stu-id="ee65c-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="ee65c-130">**Elimina** un arricchimento.</span><span class="sxs-lookup"><span data-stu-id="ee65c-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="ee65c-131">Puoi eseguire o disattivare più arricchimenti contemporaneamente selezionandoli nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ee65c-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="ee65c-132">Le opzioni di visualizzazione e modifica non sono disponibili come azione in blocco e funzionano solo per un arricchimento alla volta.</span><span class="sxs-lookup"><span data-stu-id="ee65c-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="ee65c-133">Arricchimenti e connessioni</span><span class="sxs-lookup"><span data-stu-id="ee65c-133">Enrichments and connections</span></span>

<span data-ttu-id="ee65c-134">Gli arricchimenti di terze parti vengono configurati utilizzando le [connessioni](connections.md), che un amministratore imposta con le credenziali e fornisce il consenso per il trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="ee65c-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="ee65c-135">La connessione può essere utilizzata da amministratori e collaboratori per configurare gli arricchimenti.</span><span class="sxs-lookup"><span data-stu-id="ee65c-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="ee65c-136">Più arricchimenti dello stesso tipo</span><span class="sxs-lookup"><span data-stu-id="ee65c-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="ee65c-137">L'entità da arricchire viene specificata durante la configurazione dell'arricchimento, che ti consente di arricchire solo un sottoinsieme dei tuoi profili.</span><span class="sxs-lookup"><span data-stu-id="ee65c-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="ee65c-138">Ad esempio, arricchisci i dati solo per un segmento specifico.</span><span class="sxs-lookup"><span data-stu-id="ee65c-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="ee65c-139">Puoi configurare diversi arricchimenti dello stesso tipo e riutilizzare la stessa connessione.</span><span class="sxs-lookup"><span data-stu-id="ee65c-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="ee65c-140">Alcuni arricchimenti avranno dei limiti al numero di arricchimenti dello stesso tipo che possono essere creati.</span><span class="sxs-lookup"><span data-stu-id="ee65c-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="ee65c-141">I limiti e l'uso corrente possono essere visualizzati nella pagina **Arricchimento**.</span><span class="sxs-lookup"><span data-stu-id="ee65c-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
