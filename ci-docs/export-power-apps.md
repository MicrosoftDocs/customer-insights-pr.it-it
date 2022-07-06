---
title: Connettore Power Apps (anteprima)
description: Connettiti con Power Apps e Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 0b71f723d1e491d422d24b1be6616d2f33c95d40
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055265"
---
# <a name="power-apps-connector-preview"></a>Connettore Power Apps (anteprima)

Importa i profili cliente unificati nelle tue app personalizzate con Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Eseguire la connessione a Power Apps e Dynamics 365 Customer Insights

Customer Insights è una delle tante [origini disponibili per i dati in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Fai riferimento alla documentazione di Power Apps per scoprire come [aggiungere una connessione dati a un'app](/powerapps/maker/canvas-apps/add-data-connection). Ti consigliamo di leggere anche [Utilizzo in Power Apps della delega per gestire set di dati di grandi dimensioni nelle app canvas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entità disponibili

Dopo aver aggiunto Customer Insights come connessione dati, puoi scegliere le seguenti entità in Power Apps:

- **Cliente**: per utilizzare i dati del [profilo cliente unificato](customer-profiles.md).
- **UnifiedActivity**: per visualizzare la [timeline delle attività](activities.md) nell'app.
- **ContactProfile**: per visualizzare i contatti di un cliente. Questa entità è disponibile solo negli ambienti di Customer Insights per gli account aziendali.

## <a name="limitations"></a>Limiti

### <a name="retrievable-entities"></a>Entità recuperabili

Si possono recuperare solo le entità **Cliente**, **UnifiedActivity**, **Segmenti** e **ContactProfile** attraverso il connettore Power Apps . L'entità ContactProfile è disponibile solo nell'istanza di Customer Insights per gli account aziendali. Vengono visualizzate altre entità perché il connettore sottostante le supporta tramite trigger in Power Automate.

Puoi fare un massimo di 100 chiamate ogni 60 secondi. Puoi chiamare l'endpoint dell'API più volte utilizzando il parametro $skip. [Ulteriori informazioni sul parametro $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delega

La delega funziona per l'entità **Customer** e l'entità **UnifiedActivity** . 

- Delega per l'entità **Cliente**: per utilizzare la delega per questa entità, i campi devono essere indicizzati in [Indicizzazione ricerca e filtro](search-filter-index.md).  
- Delega per **UnifiedActivity**: la delega per questa entità funziona solo per i campi **ActivityId** e **CustomerId**.  
- Delega per **ContactProfile**: La delega per questa entità funziona solo per i campi **ContactId** e **CustomerId**. L'entità ContactProfile è disponibile solo negli ambienti di Customer Insights per gli account aziendali.

Per maggiori informazioni sulla delega, andate su [Power Apps funzioni e operazioni delegabili](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Esempio di controllo della raccolta

Puoi aggiungere i profili dei clienti a un [controllo della galleria](/powerapps/maker/canvas-apps/add-gallery).

1. Aggiungi un controllo della **galleria** a un'app che stai costruendo.

    > [!div class="mx-imgBorder"]
    > ![Aggiungere un elemento della raccolta.](media/connector-powerapps9.png "Aggiungi un elemento di galleria.")

2. Seleziona **Cliente** come origine dati per gli elementi.

    > [!div class="mx-imgBorder"]
    > ![Selezionare un'origine dati.](media/choose-datasource-powerapps.png "Seleziona un'origine dati.")

3. Puoimodificare il pannello dati a destra per selezionare quale campo deve essere visualizzato nella raccolta per l'entità Cliente.

4. Se volete mostrare qualsiasi campo del cliente selezionato nella galleria, riempite la proprietà **Testo** di un'etichetta usando **{Name_of_the_gallery}.Selezionato.{property_name}**  
    - Per esempio: _Galleria1.selezionato.indirizzo1_città_

5. Per visualizzare la linea temporale unificata per un cliente, aggiungere un elemento di galleria e aggiungere la proprietà **Elementi** usando **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Per esempio: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
