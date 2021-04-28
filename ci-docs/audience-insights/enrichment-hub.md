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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896010"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="c0459-103">Arricchimento per i profili cliente (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c0459-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="c0459-104">Utilizza i dati provenienti da origini come Microsoft e altri partner per arricchire i dati dei tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="c0459-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina dell'hub di arricchimento":::

<span data-ttu-id="c0459-106">In Audience Insights, vai a **Dati** > **Arricchimento** per utilizzare le opzioni di arricchimento.</span><span class="sxs-lookup"><span data-stu-id="c0459-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="c0459-107">Devi disporre delle autorizzazioni come Collaboratore o Amministratore per creare o modificare gli arricchimenti.</span><span class="sxs-lookup"><span data-stu-id="c0459-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="c0459-108">Per ulteriori informazioni, vedi [Autorizzazioni](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c0459-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="c0459-109">Nella scheda **Scopri**, troverai i seguenti arricchimenti:</span><span class="sxs-lookup"><span data-stu-id="c0459-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="c0459-110">[Marchi](enrichment-microsoft.md) forniti da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0459-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="c0459-111">[Interessi](enrichment-microsoft.md) forniti da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0459-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="c0459-112">[Dati aziendali](enrichment-leadspace.md) forniti da Leadspace</span><span class="sxs-lookup"><span data-stu-id="c0459-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="c0459-113">[Dati demografici](enrichment-experian.md) forniti da Experian</span><span class="sxs-lookup"><span data-stu-id="c0459-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="c0459-114">[Dati di localizzazione](enrichment-here.md) forniti da HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="c0459-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="c0459-115">[Personalizzare i dati](enrichment-SFTP-custom-import.md) mediante Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="c0459-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="c0459-116">Nella scheda **I miei arricchimenti**, puoi vedere gli arricchimenti che hai configurato e modificarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="c0459-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="c0459-117">Gestire gli arricchimenti esistenti</span><span class="sxs-lookup"><span data-stu-id="c0459-117">Manage existing enrichments</span></span>

<span data-ttu-id="c0459-118">Vai a **Arricchimenti personali** per vedere tutti gli arricchimenti configurati.</span><span class="sxs-lookup"><span data-stu-id="c0459-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="c0459-119">Ogni arricchimento è rappresentato come una riga che include informazioni aggiuntive sull'arricchimento.</span><span class="sxs-lookup"><span data-stu-id="c0459-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="c0459-120">Seleziona un arricchimento per vedere le opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="c0459-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="c0459-121">È inoltre possibile selezionare i puntini di sospensione (...) di un elemento dell'elenco per visualizzare le opzioni.</span><span class="sxs-lookup"><span data-stu-id="c0459-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opzioni per gestire gli arricchimenti nell'elenco degli arricchimenti":::

- <span data-ttu-id="c0459-123">**Visualizza** i dettagli dell'arricchimento con il numero di profili cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="c0459-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="c0459-124">**Modifica** la configurazione dell'arricchimento.</span><span class="sxs-lookup"><span data-stu-id="c0459-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="c0459-125">**Eseguire** l'arricchimento per aggiornare i profili cliente con i dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="c0459-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="c0459-126">**Disattiva** un arricchimento esistente per impedirne l'aggiornamento automatico a ogni aggiornamento pianificato.</span><span class="sxs-lookup"><span data-stu-id="c0459-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="c0459-127">I dati dell'ultimo aggiornamento riuscito continueranno a essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="c0459-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="c0459-128">**Attiva** un arricchimento inattivo per riavviare l'aggiornamento automatico con ogni aggiornamento pianificato.</span><span class="sxs-lookup"><span data-stu-id="c0459-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="c0459-129">**Elimina** un arricchimento.</span><span class="sxs-lookup"><span data-stu-id="c0459-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="c0459-130">Puoi eseguire o disattivare più arricchimenti contemporaneamente selezionandoli nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c0459-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="c0459-131">Le opzioni di visualizzazione e modifica non sono disponibili come azione in blocco e funzionano solo per un arricchimento alla volta.</span><span class="sxs-lookup"><span data-stu-id="c0459-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="c0459-132">Arricchimenti e connessioni</span><span class="sxs-lookup"><span data-stu-id="c0459-132">Enrichments and connections</span></span>

<span data-ttu-id="c0459-133">Gli arricchimenti di terze parti vengono configurati utilizzando le [connessioni](connections.md), che un amministratore imposta con le credenziali e fornisce il consenso per il trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="c0459-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="c0459-134">La connessione può essere utilizzata da amministratori e collaboratori per configurare gli arricchimenti.</span><span class="sxs-lookup"><span data-stu-id="c0459-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="c0459-135">Più arricchimenti dello stesso tipo</span><span class="sxs-lookup"><span data-stu-id="c0459-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="c0459-136">L'entità da arricchire viene specificata durante la configurazione dell'arricchimento, che ti consente di arricchire solo un sottoinsieme dei tuoi profili.</span><span class="sxs-lookup"><span data-stu-id="c0459-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="c0459-137">Ad esempio, arricchisci i dati solo per un segmento specifico.</span><span class="sxs-lookup"><span data-stu-id="c0459-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="c0459-138">Puoi configurare diversi arricchimenti dello stesso tipo e riutilizzare la stessa connessione.</span><span class="sxs-lookup"><span data-stu-id="c0459-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="c0459-139">Alcuni arricchimenti avranno dei limiti al numero di arricchimenti dello stesso tipo che possono essere creati.</span><span class="sxs-lookup"><span data-stu-id="c0459-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="c0459-140">I limiti e l'uso corrente possono essere visualizzati nella pagina **Arricchimento**.</span><span class="sxs-lookup"><span data-stu-id="c0459-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
