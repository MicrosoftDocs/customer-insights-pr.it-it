---
title: Attività condivise per scenari di previsione
description: Scopri come gestire, risolvere i problemi e perfezionare le previsioni.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315883"
---
# <a name="manage-predictions"></a><span data-ttu-id="6d96b-103">Gestisci previsioni</span><span class="sxs-lookup"><span data-stu-id="6d96b-103">Manage predictions</span></span>

<span data-ttu-id="6d96b-104">Questo articolo illustra alcune attività condivise dalla maggior parte degli scenari di previsione.</span><span class="sxs-lookup"><span data-stu-id="6d96b-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="6d96b-105">Risolvere i problemi relativi a una previsione non riuscita</span><span class="sxs-lookup"><span data-stu-id="6d96b-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="6d96b-106">Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.</span><span class="sxs-lookup"><span data-stu-id="6d96b-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="6d96b-107">Seleziona i puntini di sospensione verticali accanto alla previsione di cui desideri visualizzare i log degli errori.</span><span class="sxs-lookup"><span data-stu-id="6d96b-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="6d96b-108">Seleziona **Log**.</span><span class="sxs-lookup"><span data-stu-id="6d96b-108">Select **Logs**.</span></span>

1. <span data-ttu-id="6d96b-109">Esamina tutti gli errori.</span><span class="sxs-lookup"><span data-stu-id="6d96b-109">Review all the errors.</span></span> <span data-ttu-id="6d96b-110">Esistono diversi tipi di errori che possono verificarsi e descrivono quale condizione ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="6d96b-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="6d96b-111">Ad esempio, un errore che non contiene dati sufficienti per eseguire una previsione accurata viene in genere risolto caricando dati aggiuntivi in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6d96b-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="6d96b-112">Report usabilità dati di input</span><span class="sxs-lookup"><span data-stu-id="6d96b-112">Input data usability report</span></span>

<span data-ttu-id="6d96b-113">Il report sull'usabilità dei dati di input fornisce una visualizzazione consolidata degli errori e degli avvisi che potrebbero essere generati dalle previsioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="6d96b-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="6d96b-114">Fornisce inoltre consigli su come migliorare le prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="6d96b-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="6d96b-115">Il report è disponibile dopo che un modello ha completato il processo di addestramento.</span><span class="sxs-lookup"><span data-stu-id="6d96b-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="6d96b-116">Viene creato separatamente per ogni modello, indipendentemente dal fatto che sia stato completato correttamente o meno.</span><span class="sxs-lookup"><span data-stu-id="6d96b-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="6d96b-117">Visualizza il report sull'usabilità dei dati di input</span><span class="sxs-lookup"><span data-stu-id="6d96b-117">View the input data usability report</span></span>

<span data-ttu-id="6d96b-118">Dopo che un modello predefinito ha completato la fase di addestramento, visualizza il report:</span><span class="sxs-lookup"><span data-stu-id="6d96b-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="6d96b-119">Seleziona i puntini di sospensione accanto al nome del modello e scegli **Report sull'usabilità dei dati di input**.</span><span class="sxs-lookup"><span data-stu-id="6d96b-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="6d96b-120">Seleziona lo stato di un modello, seleziona **Visualizza il report sull'usabilità dei dati di input** nel riquadro laterale.</span><span class="sxs-lookup"><span data-stu-id="6d96b-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="6d96b-121">Selezionando uno dei modelli nell'elenco, seleziona **Report usabilità dati di input** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6d96b-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="6d96b-122">Apri la pagina dei risultati del modello, seleziona **Report usabilità dati di input** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6d96b-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="6d96b-123">Informazioni nel report sull'usabilità dei dati di input</span><span class="sxs-lookup"><span data-stu-id="6d96b-123">Information in the input data usability report</span></span>

<span data-ttu-id="6d96b-124">Le seguenti colonne del report contengono informazioni utili per migliorare i dati per il modello.</span><span class="sxs-lookup"><span data-stu-id="6d96b-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Esempio di un report sull'usabilità dei dati di input che mostra una tabella con errori, avvisi ed elementi consigliati.":::

- <span data-ttu-id="6d96b-126">Nome: nome descrittivo dell'errore, dell'avviso o dell'elemento consigliato.</span><span class="sxs-lookup"><span data-stu-id="6d96b-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="6d96b-127">Passaggio: fase del modello, treno o punteggio, a cui si riferiscono le informazioni.</span><span class="sxs-lookup"><span data-stu-id="6d96b-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="6d96b-128">Stato: gravità delle informazioni (errore, avviso, elemento consigliato).</span><span class="sxs-lookup"><span data-stu-id="6d96b-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="6d96b-129">Nome colonna: colonna in un'entità che deve essere modificata per migliorare le prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="6d96b-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="6d96b-130">Nome entità: nome dell'entità che deve essere modificata per migliorare le prestazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="6d96b-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="6d96b-131">Dettagli: dettagli sull'errore, l'avviso o l'elemento consigliato.</span><span class="sxs-lookup"><span data-stu-id="6d96b-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="6d96b-132">Aggiornare una previsione</span><span class="sxs-lookup"><span data-stu-id="6d96b-132">Refresh a prediction</span></span>

<span data-ttu-id="6d96b-133">Le previsioni si aggiorneranno automaticamente in base alla stessa [pianificazione di aggiornamento dei dati](system.md#schedule-tab) come configurato nelle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6d96b-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="6d96b-134">Puoi anche aggiornarli manualmente.</span><span class="sxs-lookup"><span data-stu-id="6d96b-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="6d96b-135">Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.</span><span class="sxs-lookup"><span data-stu-id="6d96b-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="6d96b-136">Seleziona i puntini di sospensione verticali accanto alla previsione che vuoi aggiornare.</span><span class="sxs-lookup"><span data-stu-id="6d96b-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="6d96b-137">Seleziona **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="6d96b-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="6d96b-138">Eliminare una previsione</span><span class="sxs-lookup"><span data-stu-id="6d96b-138">Delete a prediction</span></span>

<span data-ttu-id="6d96b-139">L'eliminazione di un previsione rimuove anche la relativa entità di output.</span><span class="sxs-lookup"><span data-stu-id="6d96b-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="6d96b-140">Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.</span><span class="sxs-lookup"><span data-stu-id="6d96b-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="6d96b-141">Seleziona i puntini di sospensione verticali accanto alla previsione che vuoi eliminare.</span><span class="sxs-lookup"><span data-stu-id="6d96b-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="6d96b-142">Seleziona **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="6d96b-142">Select **Delete**.</span></span>
