---
title: Connettore Power Apps
description: Connettiti con Power Apps e Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031800"
---
# <a name="microsoft-power-apps-connector-preview"></a>Connettore Microsoft Power Apps (anteprima)

Importa i profili cliente unificati nelle tue app personalizzate con Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Eseguire la connessione a Power Apps e Dynamics 365 Customer Insights

Customer Insights è una delle tante [origini disponibili per i dati in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Fai riferimento alla documentazione di Power Apps per scoprire come [aggiungere una connessione dati a un'app](/powerapps/maker/canvas-apps/add-data-connection). Ti consigliamo di leggere anche [Utilizzo in Power Apps della delega per gestire set di dati di grandi dimensioni nelle app canvas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entità disponibili

Dopo aver aggiunto Customer Insights come connessione dati, puoi scegliere le seguenti entità in Power Apps:

- Cliente: per utilizzare i dati dal [profilo cliente unificato](customer-profiles.md).
- UnifiedActivity: per visualizzare la [sequenza temporale degli impegni](activities.md) sull'app.

## <a name="limitations"></a>Limiti

### <a name="retrievable-entities"></a>Entità recuperabili

Puoi recuperare solo le entità **Cliente**, **UnifiedActivity** e **Segmenti** attraverso il connettore Power Apps. Vengono visualizzate altre entità perché il connettore sottostante le supporta tramite trigger in Power Automate.  

### <a name="delegation"></a>Delega

La delega funziona per l'entità Cliente e l'entità UnifiedActivity. 

- Delega per l'entità **Cliente**: per utilizzare la delega per questa entità, i campi devono essere indicizzati in [Indicizzazione ricerca e filtro](search-filter-index.md).  

- Delega per **UnifiedActivity**: la delega per questa entità funziona solo per i campi **ActivityId** e **CustomerId**.  

- Per ulteriori informazioni sulla delega, vedi [Funzioni e operazioni delegabili di Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Esempio di controllo della raccolta

Ad esempio, aggiungi profili cliente a un [controllo della raccolta](/powerapps/maker/canvas-apps/add-gallery).

1. Aggiungi un controlo **Raccolta** a un'app che stai creando.

> [!div class="mx-imgBorder"]
> ![Aggiungere un elemento della raccolta.](media/connector-powerapps9.png "Aggiungere un elemento della raccolta")

1. Seleziona **Cliente** come origine dati per gli elementi.

    > [!div class="mx-imgBorder"]
    > ![Selezionare un'origine dati.](media/choose-datasource-powerapps.png "Selezionare un'origine dati")

1. Puoimodificare il pannello dati a destra per selezionare quale campo deve essere visualizzato nella raccolta per l'entità Cliente.

1. Se desideri mostrare nella raccolta qualsiasi campo del cliente selezionato, compila la proprietà Testo di un'etichetta: **{Name_of_the_gallery} .Selezionato. {property_name}**

    Esempio: Gallery1.Selected.address1_city

1. Per visualizzare la sequenza temporale unificata per un cliente, aggiungi un elemento Raccolta e aggiungi la proprietà Elementi: **Filtro ("UnifiedActivity", CustomerId = {Customer_Id})**

    Esempio: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]