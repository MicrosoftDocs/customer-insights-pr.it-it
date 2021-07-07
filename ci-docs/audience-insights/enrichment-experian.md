---
title: Arricchimento con l'arricchimento di terze parti Experian
description: Informazioni generali sull'arricchimento di terzi parti Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309825"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="3b0e5-103">Arricchimento dei profili dei clienti con i dati demografici di Experian (anteprima)</span><span class="sxs-lookup"><span data-stu-id="3b0e5-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="3b0e5-104">Experian è leader globale nei servizi di marketing e rendicontazione creditizia dei consumatori e delle imprese.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="3b0e5-105">Con i servizi di arricchimento dei dati di Experian puoi approfondire la conoscenza dei tuoi clienti arricchendo i loro profili con dati demografici come dimensioni del nucleo familiare, reddito e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b0e5-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3b0e5-106">Prerequisites</span></span>

<span data-ttu-id="3b0e5-107">Per configurare Experian, devono essere rispettati i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="3b0e5-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3b0e5-108">Devi disporre di una sottoscrizione attiva di Experian.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-108">You have an active Experian subscription.</span></span> <span data-ttu-id="3b0e5-109">Per ottenere una sottoscrizione, [contatta Experian](https://www.experian.com/marketing-services/contact) direttamente.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="3b0e5-110">[Altre informazioni su Arricchimento dei dati di Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="3b0e5-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="3b0e5-111">Una connessione Experian è già stata configurata da un amministratore *o* hai le autorizzazioni di [amministratore](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="3b0e5-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="3b0e5-112">È inoltre necessario l'ID utente, l'ID parte e il numero modello per l'account Secure Transport (ST) abilitato per SSH che Experian creato per te.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="3b0e5-113">Paesi/aree geografiche supportati</span><span class="sxs-lookup"><span data-stu-id="3b0e5-113">Supported countries/regions</span></span>

<span data-ttu-id="3b0e5-114">Attualmente supportiamo l'arricchimento dei profili dei clienti solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="3b0e5-115">Configurare l'arricchimento</span><span class="sxs-lookup"><span data-stu-id="3b0e5-115">Configure the enrichment</span></span>

1. <span data-ttu-id="3b0e5-116">Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="3b0e5-117">Seleziona **Arricchisci i miei dati** nel riquadro di Experian.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b0e5-118">![Experian riquadri](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="3b0e5-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="3b0e5-119">Seleziona una [connessione](connections.md) dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="3b0e5-120">Contatta un amministratore se non è disponibile alcuna connessione.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="3b0e5-121">Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione** e scegliendo Experian dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="3b0e5-122">Seleziona **Connetti a Experian** per confermare la selezione della connessione.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="3b0e5-123">Seleziona **Avanti** e scegli il **Set di dati cliente** che vuoi arricchire con i dati demografici di Experian.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="3b0e5-124">Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. <span data-ttu-id="3b0e5-126">Seleziona **Avanti** e definisci il tipo di campi dei tuoi profili unificati da utilizzare per cercare i dati demografici corrispondenti in Experian.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="3b0e5-127">Almeno uno dei campi **Nome e indirizzo**, **Telefono**, o **E-mail** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="3b0e5-128">Per una maggiore precisione della corrispondenza, è possibile aggiungere fino a due altri campi.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="3b0e5-129">Questa selezione influenzerà i campi di mapping a cui hai accesso nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="3b0e5-130">Altri attributi identificativi chiave inviati a Experian produrranno probabilmente un tasso di corrispondenza più elevato.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="3b0e5-131">Seleziona **Avanti** per iniziare il mapping del campo.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="3b0e5-132">Definisci quali campi dei tuoi profili unificati utilizzare per cercare i dati demografici corrispondenti in Experian.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="3b0e5-133">I campi obbligatori sono contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-133">Required fields are marked.</span></span>

1. <span data-ttu-id="3b0e5-134">Fornisci un nome per l'arricchimento e un nome per l'entità di output.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="3b0e5-135">Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="3b0e5-136">Configurazione della connessione per Experian</span><span class="sxs-lookup"><span data-stu-id="3b0e5-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="3b0e5-137">Devi essere un amministratore per configurare le connessioni.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="3b0e5-138">Seleziona **Aggiungi connessione** quando configuri un arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Experian.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="3b0e5-139">Seleziona **Inizia subito**.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="3b0e5-140">Immetti un nome per la connessione nella casella **nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="3b0e5-141">Inserisci un ID utente, un ID parte e un numero di modello validi per il tuo account di trasporto sicuro Experian.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="3b0e5-142">Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="3b0e5-143">Seleziona **Verifica** per convalidare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="3b0e5-144">Dopo aver completato la verifica, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Riquadro di configurazione della connessione di Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="3b0e5-146">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="3b0e5-146">Enrichment results</span></span>

<span data-ttu-id="3b0e5-147">Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3b0e5-148">Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3b0e5-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3b0e5-149">Il tempo di elaborazione dipenderà dalle dimensioni dei dati dei tuoi clienti e dai processi di arricchimento impostati per il tuo account da Experian.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="3b0e5-150">Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="3b0e5-151">Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3b0e5-152">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b0e5-153">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3b0e5-153">Next steps</span></span>

<span data-ttu-id="3b0e5-154">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3b0e5-155">Crea [segmenti](segments.md) e [misure](measures.md) e persino [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3b0e5-156">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="3b0e5-156">Data privacy and compliance</span></span>

<span data-ttu-id="3b0e5-157">Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Experian, consenti il trasferimento di dati al di fuori del limite di conformità per Dynamics 365 Customer Insights, inclusi i dati potenzialmente sensibili come i Dati Personali.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3b0e5-158">Microsoft trasferirà tali dati alle tue condizioni ma sei tu a dover garantire che Experian soddisfi tutti gli obblighi di privacy e sicurezza che sei tenuto a rispettare.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3b0e5-159">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3b0e5-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3b0e5-160">L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
