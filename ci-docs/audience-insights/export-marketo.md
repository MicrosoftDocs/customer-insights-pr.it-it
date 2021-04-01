---
title: Esportare dati di Customer Insights in Marketo
description: Scopri come configurare la connessione a Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597976"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="b1c7d-103">Connettore per Marketo (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b1c7d-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="b1c7d-104">Esporta segmenti di profili cliente unificati per generare campagne, fornire e-mail marketing e utilizzare gruppi specifici di clienti con Marketo.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1c7d-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b1c7d-105">Prerequisites</span></span>

-   <span data-ttu-id="b1c7d-106">Devi disporre di un [account Marketo](https://login.marketo.com/) e delle credenziali di amministratore corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b1c7d-107">In Marketo sono presenti elenchi e ID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="b1c7d-108">Per ulteriori informazioni, vedi [Elenchi Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="b1c7d-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="b1c7d-109">Disponi di [segmenti configurati](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b1c7d-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="b1c7d-110">I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="b1c7d-111">Connessione a Marketo</span><span class="sxs-lookup"><span data-stu-id="b1c7d-111">Connect to Marketo</span></span>

1. <span data-ttu-id="b1c7d-112">Passa a **Amministratore** > **Destinazioni di esportazione**.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b1c7d-113">Sotto **Marketo**, seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="b1c7d-114">Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b1c7d-115">Immetti **[ID client Marketo, segreto client e nome host dell'endpoint REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="b1c7d-116">Immetti l'**[ID elenco Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="b1c7d-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="b1c7d-117">Seleziona **Accetto** per confermare **Conformità e privacy dei dati** e seleziona **Connetti** per inizializzare la connessione a Marketo.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="b1c7d-118">Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Screenshot di esportazione per la connessione a Marketo":::

1. <span data-ttu-id="b1c7d-120">Seleziona **Avanti** per configurare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b1c7d-121">Configurare il connettore</span><span class="sxs-lookup"><span data-stu-id="b1c7d-121">Configure the connector</span></span>

1. <span data-ttu-id="b1c7d-122">Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="b1c7d-123">Facoltativamente, puoi esportare **Nome**, **Cognome**, **Città**, **Regione** e **Paese** come campi aggiuntivi per creare messaggi di posta elettronica più personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="b1c7d-124">Seleziona **Aggiungi attributo** per eseguire il mapping di questi campi.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="b1c7d-125">Seleziona i segmenti da esportare.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-125">Select the segments you want to export.</span></span> <span data-ttu-id="b1c7d-126">Puoi esportare in totale fino a 1 milione di profili cliente in Marketo.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Selezionare campi e segmenti da esportare in Marketo":::

1. <span data-ttu-id="b1c7d-128">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b1c7d-129">Esportare i dati</span><span class="sxs-lookup"><span data-stu-id="b1c7d-129">Export the data</span></span>

<span data-ttu-id="b1c7d-130">Puoi [esportare dati su richiesta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b1c7d-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b1c7d-131">L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b1c7d-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b1c7d-132">I tuoi segmenti sono ora visualizzati sotto [Elenchi Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) in Marketo.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b1c7d-133">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="b1c7d-133">Known limitations</span></span>

- <span data-ttu-id="b1c7d-134">Fino a 1 milione di profili per esportazione in Marketo.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="b1c7d-135">L'esportazione in Marketo è limitata ai segmenti.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="b1c7d-136">L'esportazione di segmenti con un totale di 1 milione di profili può richiedere fino a 3 ore.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="b1c7d-137">Il numero di profili che puoi esportare in Marketo dipende ed è limitato dal tuo contratto con Marketo.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b1c7d-138">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="b1c7d-138">Data privacy and compliance</span></span>

<span data-ttu-id="b1c7d-139">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Marketo, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b1c7d-140">Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Marketo rispetti gli obblighi di privacy o sicurezza che ti incombono.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b1c7d-141">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b1c7d-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b1c7d-142">L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b1c7d-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]