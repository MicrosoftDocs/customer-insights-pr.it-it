---
title: Acquisire i dati tramite un connettore Power Query (video)
description: Connettori per origini dati basate su Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4db97ec02eb96662d30a8536ea42372f81f318d2
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800154"
---
# <a name="connect-to-a-power-query-data-source"></a>Connessione a un'origine dati Power Query

Power Query offre un'ampia serie di connettori per l'inserimento dei dati. La maggior parte di questi connettori è supportata da Dynamics 365 Customer Insights. 

L'aggiunta di origini dati basate sui connettori Power Query generalmente segue i passaggi descritti in questa sezione. Tuttavia, a seconda del connettore utilizzato, sono necessarie informazioni diverse. Per saperne di più, vedi la documentazione sui singoli connettori nel [Riferimento del connettore Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crea una nuova origine dati

1. Vai a **Dati** > **Origini dati**.

1. Seleziona **Aggiungi origine dati**.

1. Selezionare **Microsoft Power Query**.

1. Fornisci un **Nome** per l'origine dati e seleziona **Avanti** per creare l'origine dati.

1. Scegli uno dei [connettori disponibili](#available-power-query-data-sources). In questo esempio, selezioniamo il connettore **Testo/CSV**.

1. Immetti i dettagli richiesti in **Impostazioni di connessione** per il connettore selezionato e seleziona **Avanti** per visualizzare un'anteprima dei dati.

1. Seleziona **Trasforma dati**. In questo passaggio, aggiungerai entità alla tua origine dati. Le entità sono set di dati. Se disponi di un database che include più set di dati, ogni set di dati è la propria entità.

1. La finestra di dialogo **Power Query - Modifica query** consente di rivedere e perfezionare i dati. Le entità identificate dai sistemi nell'origine dati selezionata vengono visualizzate nel riquadro di sinistra.

   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo Modifica query.](media/data-manager-configure-edit-queries.png "Finestra di dialogo Modifica query")

1. Puoi anche trasformare i dati. Seleziona un'entità da modificare o trasformare. Usa le opzioni nella finestra Power Query per applicare le trasformazioni. Ogni trasformazione viene elencata in **Passaggi applicati**. Power Query fornisce numerose opzioni di trasformazione predefinite. Per ulteriori informazioni, vedi [Trasformazioni di Power Query](/power-query/power-query-what-is-power-query#transformations).

   Si consiglia di utilizzare le seguenti trasformazioni:

   - Se stai inserendo dati da un file CSV, la prima riga spesso contiene intestazioni. Vai a **Trasforma**, quindi seleziona **Usa la prima riga come intestazione**.
   - Assicurati che il tipo di dati sia impostato in modo appropriato. Ad esempio, per i campi data, seleziona un tipo di data.

1. Per aggiungere ulteriori entità all'origine dati nella finestra **Modifica query** vai a **Home** e seleziona **Ottieni dati**.

1. Seleziona **Salva** nella parte inferiore della finestra di Power Query  per salvare le trasformazioni. Dopo aver salvato, troverai la tua origine dati su **Dati** > **Origini dati**.

1. Nella pagina **Origini dati** noterai che la nuova origine dati è nello stato **Aggiornamento in corso**.

## <a name="available-power-query-data-sources"></a>Origini dati di Power Query disponibili

Vedi il [Riferimento del connettore Power Query](/power-query/connectors/) per un elenco di connettori che è possibile utilizzare per importare dati in Customer Insights. 

I connettori con un segno di spunta nella colonna **Informazioni dettagliate sui clienti (flussi di dati)** sono disponibili per creare nuove origini dati basate su Power Query. Esamina la documentazione di un connettore specifico per ulteriori informazioni su prerequisiti, limitazioni e altri dettagli.

## <a name="edit-power-query-data-sources"></a>Modifica origine dati Power Query

> [!NOTE]
> Potrebbe non essere possibile apportare modifiche alle origini dati attualmente utilizzate in uno dei processi dell'app (*segmentazione*, *corrispondenza* o *unione*, ad esempio). 
>
> Nella pagina **Impostazioni**, puoi tener traccia dell'avanzamento di ciascuno dei processi attivi. Al termine di un processo, puoi tornare alla pagina **Origine dei dati** e apportare le tue modifiche.

1. Vai a **Dati** > **Origini dati**.

2. Seleziona i puntini di sospensione verticali (&vellip;) accanto all'origine dati che desideri modificare e seleziona **Modifica** dal menu a tendina.

   > [!div class="mx-imgBorder"]
   > ![Opzione Modifica.](media/edit-option-data-sources.png "Modifica opzione")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Applica le modifiche e le trasformazioni nella finestra di dialogo **Power Query - Modifica query** come descritto in [Creare una nuova origine dati](#create-a-new-data-source) sezione.

4. Seleziona **Salva** in Power Query dopo aver completato le modifiche, per salvare le modifiche.


[!INCLUDE [footer-include](includes/footer-banner.md)]
