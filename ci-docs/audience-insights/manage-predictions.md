---
title: Attività condivise per scenari di previsione
description: Scopri come gestire, risolvere i problemi e perfezionare le previsioni.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 4e7e21a610564b30463b27ab703c291275725895
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731993"
---
# <a name="manage-predictions"></a>Gestisci previsioni

Questo articolo illustra alcune attività condivise dalla maggior parte degli scenari di previsione.

## <a name="troubleshoot-a-failed-prediction"></a>Risolvere i problemi relativi a una previsione non riuscita

1. Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.

1. Seleziona i puntini di sospensione verticali accanto alla previsione di cui desideri visualizzare i log degli errori.

1. Seleziona **Log**.

1. Esamina tutti gli errori. Esistono diversi tipi di errori che possono verificarsi e descrivono quale condizione ha causato l'errore. Ad esempio, un errore che non contiene dati sufficienti per eseguire una previsione accurata viene in genere risolto caricando dati aggiuntivi in Customer Insights.

## <a name="input-data-usability-report"></a>Report usabilità dati di input

Il report sull'usabilità dei dati di input fornisce una visualizzazione consolidata degli errori e degli avvisi che potrebbero essere generati dalle previsioni predefinite. Fornisce inoltre consigli su come migliorare le prestazioni del modello.

Il report è disponibile dopo che un modello ha completato il processo di addestramento. Viene creato separatamente per ogni modello, indipendentemente dal fatto che sia stato completato correttamente o meno.

### <a name="view-the-input-data-usability-report"></a>Visualizza il report sull'usabilità dei dati di input

Dopo che un modello predefinito ha completato la fase di addestramento, visualizza il report:
- Seleziona i puntini di sospensione accanto al nome del modello e scegli **Report sull'usabilità dei dati di input**.
- Seleziona lo stato di un modello, seleziona **Visualizza il report sull'usabilità dei dati di input** nel riquadro laterale.
- Selezionando uno dei modelli nell'elenco, seleziona **Report usabilità dati di input** nella barra dei comandi.
- Apri la pagina dei risultati del modello, seleziona **Report usabilità dati di input** nella barra dei comandi.

### <a name="information-in-the-input-data-usability-report"></a>Informazioni nel report sull'usabilità dei dati di input

Le seguenti colonne del report contengono informazioni utili per migliorare i dati per il modello.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Esempio di un report sull'usabilità dei dati di input che mostra una tabella con errori, avvisi ed elementi consigliati.":::

- **Nome:** nome descrittivo dell'errore, dell'avviso o dell'elemento consigliato.
- **Passaggio:** fase del modello, treno o punteggio, a cui si riferiscono le informazioni.
- **Stato:** gravità delle informazioni (errore, avviso, elemento consigliato).
- **Nome colonna:** colonna in un'entità che deve essere modificata per migliorare le prestazioni del modello.
- **Nome entità:** nome dell'entità che deve essere modificata per migliorare le prestazioni del modello.
- **Dettagli:** dettagli dell'errore, dell'avviso o dell'elemento consigliato.

## <a name="refresh-a-prediction"></a>Aggiornare una previsione

Le previsioni si aggiorneranno automaticamente in base alla stessa [pianificazione di aggiornamento dei dati](system.md#schedule-tab) come configurato nelle impostazioni. Puoi anche aggiornarli manualmente.

1. Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.

1. Seleziona i puntini di sospensione verticali accanto alla previsione che vuoi aggiornare.

1. Seleziona **Aggiorna**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Eliminare una previsione

L'eliminazione di un previsione rimuove anche la relativa entità di output.

1. Vai a **Intelligenza** > **Predizioni** e seleziona la scheda **Le mie previsioni**.

1. Seleziona i puntini di sospensione verticali accanto alla previsione che vuoi eliminare.

1. Seleziona **Elimina.**
