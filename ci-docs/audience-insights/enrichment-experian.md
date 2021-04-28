---
title: Arricchimento con l'arricchimento di terze parti Experian
description: Informazioni generali sull'arricchimento di terze parti Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896378"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="fdfbc-103">Arricchisci i profili cliente con i dati demografici di Experian (anteprima)</span><span class="sxs-lookup"><span data-stu-id="fdfbc-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="fdfbc-104">Experian è un leader globale nei servizi di marketing e reporting del credito al consumo e alle imprese.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="fdfbc-105">Con Servizi di arricchimento dei dati di Experian, puoi acquisire una conoscenza più approfondita dei tuoi clienti arricchendo i tuoi profili cliente con dati demografici come le dimensioni del nucleo familiare, il reddito e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fdfbc-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fdfbc-106">Prerequisites</span></span>

<span data-ttu-id="fdfbc-107">Per configurare Experian, devono essere rispettati i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="fdfbc-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fdfbc-108">Hai un abbonamento Experian attivo.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-108">You have an active Experian subscription.</span></span> <span data-ttu-id="fdfbc-109">Per ottenere un abbonamento, [contatta Experian](https://www.experian.com/marketing-services/contact) direttamente.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="fdfbc-110">[Altre informazioni sull'arricchimento dei dati Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="fdfbc-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="fdfbc-111">Una connessione Experian è già stata configurata da un amministratore *o* hai le autorizzazioni di [amministratore](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="fdfbc-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="fdfbc-112">È inoltre necessario l'ID utente, l'ID parte e il numero di modello per l'account SSH-enabled Secure Transport (ST) che Experian ha creato per te.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="fdfbc-113">Configurare l'arricchimento</span><span class="sxs-lookup"><span data-stu-id="fdfbc-113">Configure the enrichment</span></span>

1. <span data-ttu-id="fdfbc-114">Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="fdfbc-115">Seleziona **Arricchisci i miei dati** nel riquadro Experian.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fdfbc-116">![Riquadro Experian](media/experian-tile.png "Riquadro Experian")</span><span class="sxs-lookup"><span data-stu-id="fdfbc-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="fdfbc-117">Seleziona una [connessione](connections.md) nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="fdfbc-118">Contatta un amministratore se non è disponibile alcuna connessione.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="fdfbc-119">Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione** e scegliendo Experian dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="fdfbc-120">Seleziona **Connettiti a Experian** per confermare la selezione della connessione.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="fdfbc-121">Seleziona **Avanti** e scegli il **set di dati del cliente** che desideri arricchire con i dati demografici di Experian.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="fdfbc-122">Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. <span data-ttu-id="fdfbc-124">Seleziona **Avanti** e definisci quale tipo di campi dei profili unificati devono essere utilizzati per cercare i dati demografici corrispondenti di Experian.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="fdfbc-125">Almeno uno dei campi **Nome e indirizzo**, **Telefono**, o **E-mail** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="fdfbc-126">Per una maggiore precisione della corrispondenza, è possibile aggiungere fino a due altri campi.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="fdfbc-127">Questa selezione influenzerà i campi di mapping a cui hai accesso nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="fdfbc-128">Più attributi dell'identificatore chiave inviati a Experian probabilmente producono un tasso di corrispondenza più elevato.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="fdfbc-129">Seleziona **Avanti** per iniziare il mapping del campo.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="fdfbc-130">Definisci quali campi dei profili unificati devono essere utilizzati per cercare i dati demografici corrispondenti di Experian.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="fdfbc-131">I campi obbligatori sono contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-131">Required fields are marked.</span></span>

1. <span data-ttu-id="fdfbc-132">Fornisci un nome per l'arricchimento e un nome per l'entità di output.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="fdfbc-133">Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="fdfbc-134">Configurare la connessione per Experian</span><span class="sxs-lookup"><span data-stu-id="fdfbc-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="fdfbc-135">Devi essere un amministratore per configurare le connessioni.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="fdfbc-136">Seleziona **Aggiungi connessione** quando si configura un arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Experian.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="fdfbc-137">Seleziona **Inizia subito**.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="fdfbc-138">Immetti un nome per la connessione nella casella **nome visualizzato**.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="fdfbc-139">Inserisci un ID utente, un ID parte e un numero di modello validi per il tuo account Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="fdfbc-140">Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**</span><span class="sxs-lookup"><span data-stu-id="fdfbc-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="fdfbc-141">Seleziona **Verifica** per convalidare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="fdfbc-142">Dopo aver completato la verifica, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Riquadro di configurazione della connessione Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="fdfbc-144">Risultati dell'arricchimento</span><span class="sxs-lookup"><span data-stu-id="fdfbc-144">Enrichment results</span></span>

<span data-ttu-id="fdfbc-145">Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="fdfbc-146">Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fdfbc-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fdfbc-147">Il tempo di elaborazione dipenderà dalle dimensioni dei tuoi dati cliente e dai processi di arricchimento impostati per il tuo account da Experian.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="fdfbc-148">Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="fdfbc-149">Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fdfbc-150">Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fdfbc-151">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fdfbc-151">Next steps</span></span>

<span data-ttu-id="fdfbc-152">Crea sulla base dei tuoi dati cliente arricchiti.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fdfbc-153">Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fdfbc-154">Conformità e privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="fdfbc-154">Data privacy and compliance</span></span>

<span data-ttu-id="fdfbc-155">Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Experian, consenti il trasferimento di dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fdfbc-156">Microsoft trasferirà tali dati secondo le tue istruzioni, ma hai la responsabilità di assicurarti che Experian rispetti gli obblighi di privacy o sicurezza che potresti avere.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fdfbc-157">Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fdfbc-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fdfbc-158">L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="fdfbc-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
