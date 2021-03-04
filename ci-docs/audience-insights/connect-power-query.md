---
title: Inserire dati tramite un connettore Power Query
description: Connettori per origini dati basati su Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267774"
---
# <a name="connect-to-a-power-query-data-source"></a>Connettersi a un'origine dati Power Query

Power Query offre un'ampia gamma di connettori per inserire i dati. La maggior parte di questi connettori è supportata da Dynamics 365 Customer Insights. L'aggiunta di origini dati basate sui connettori Power Query generalmente segue i passaggi descritti nella sezione successiva. Tuttavia, a seconda del connettore utilizzato, sono necessarie informazioni diverse. Per ulteriori informazioni, vedere la documentazione sui singoli connettori in [Riferimento al connettore Power Query](https://docs.microsoft.com/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Crea una nuova origine dati

1. In Audience Insights, vai a **Dati** > **Origini dati**.

1. Seleziona **Aggiungi origine dati**.

1. Scegli il metodo **Importa dati** e seleziona **Avanti**.

1. Fornisci un **Nome** per l'origine dati e seleziona **Avanti** per creare l'origine dati. Linee guida per i nomi: 
   - Deve iniziare con una lettera.
   - Usa solo lettere e numeri. Gli spazi e i caratteri speciali non sono consentiti.
   - Usa tra 3 e 64 caratteri.

1. Scegli uno dei [connettori disponibili](#available-power-query-data-sources). Per questo esempio, selezioniamo il connettore **Testo/CSV**.

1. Immetti i dettagli richiesti in **Impostazioni di connessione** per il connettore selezionato e seleziona **Avanti** per visualizzare un'anteprima dei dati.

1. Seleziona **Trasforma dati**. In questo passaggio, aggiungerai entità alla tua origine dati. Le entità sono set di dati. Se disponi di un database che include più set di dati, ogni set di dati è la propria entità.

1. La finestra di dialogo **Power Query - Modifica query** consente di rivedere e perfezionare i dati. Le entità identificate dai sistemi nell'origine dati selezionata vengono visualizzate nel riquadro di sinistra.

   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo Modifica query](media/data-manager-configure-edit-queries.png "Finestra di dialogo Modifica query")

1. Puoi anche trasformare i dati. Seleziona un'entità da modificare o trasformare. Utilizza le opzioni nella finestra Power Query per applicare le trasformazioni. Ogni trasformazione viene elencata in **Passaggi applicati**. Power Query fornisce numerose opzioni di trasformazione predefinite. Per altre informazioni, vedi [Trasformazioni di Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).

1. Puoi aggiungere altre entità alla tua origine dati selezionando **Estrai dati** nella finestra di dialogo **Modifica query**.

   Queste trasformazioni sono altamente raccomandate:

   - Se stai inserendo dati da un file CSV, la prima riga spesso contiene intestazioni. Vai a **Trasforma tabella** e seleziona **Usa intestazioni come prima riga**.
   - Assicurati che il tipo di dati sia impostato in modo appropriato.

1. Seleziona **Salva** nella parte inferiore della finestra di Power Query per salvare le trasformazioni. Dopo aver salvato, troverai la tua origine dati su **Dati** > **Origini dati**.

1. Nella pagina **Origini dati** noterai che la nuova origine dati è nello stato **Aggiornamento in corso**.

## <a name="available-power-query-data-sources"></a>Origini dati Power Query disponibili

Vedi [Riferimento al connettore Power Query](https://docs.microsoft.com/power-query/connectors/) per un elenco aggiornato dei connettori che è possibile selezionare per importare i dati in Customer Insights. 

Connettori con un segno di spunta nella colonna **Customer Insights (Flussi di dati)** sono disponibili per creare nuove origini dati basate su Power Query. Esamina la documentazione di un connettore specifico per ulteriori informazioni su prerequisiti, limitazioni e altri dettagli.

## <a name="edit-power-query-data-sources"></a>Modifica origini dati Power Query disponibili

> [!NOTE]
> Potrebbe non essere possibile apportare modifiche alle origini dati attualmente utilizzate in uno dei processi dell'app (*segmentazione*, *corrispondenza* o *unione*, ad esempio). 
>
> Usando la pagina **Impostazioni**, puoi tener traccia dell'avanzamento di ciascuno dei processi attivi. Al termine di un processo, puoi tornare alla pagina **Origine dei dati** e apportare le tue modifiche.

1. In Audience Insights, vai a **Dati** > **Origini dati**.

2. Seleziona i puntini di sospensione verticali accanto all'origine dati che desideri modificare e seleziona **Modifica** dal menu a discesa.

   > [!div class="mx-imgBorder"]
   > ![Modifica opzione](media/edit-option-data-sources.png "Modifica opzione")

3. Applica le modifiche e le trasformazioni nella finestra di dialogo **Power Query - Modifica query** come descritto nella sezione [Crea una nuova origine dati](#create-a-new-data-source).

4. Seleziona **Salva** in Power Query dopo aver completato le modifiche per salvare le modifiche.


[!INCLUDE[footer-include](../includes/footer-banner.md)]