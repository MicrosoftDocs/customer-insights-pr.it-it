---
title: Visualizzare profili cliente
description: Ottieni una visualizzazione combinata dei dati cliente unificati.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896332"
---
# <a name="customer-profiles"></a>Profili cliente

La pagina **Clienti** mostra una visualizzazione combinata dei tuoi clienti, basata sui dati del profilo di [tutte le origini dati](data-sources.md). I profili dei clienti sono disponibili una volta [creata l'entità cliente unificata](data-unification.md). Assicurati di completare il processo di unificazione dei dati per ottenere visualizzazioni più complete dei tuoi clienti. La pagina consente anche di cercare clienti.

I clienti possono essere persone fisiche o organizzazioni (anteprima). Ogni profilo cliente o organizzazione è rappresentato da un riquadro. Seleziona un riquadro per visualizzare ulteriori informazioni su quel cliente o organizzazione specifici. Utilizza i controlli di impaginazione nella parte inferiore della pagina per visualizzare altri record.

> [!div class="mx-imgBorder"] 
> ![Profili cliente B2C](media/profiles-customers.png "Profili cliente B2C")

Organizzazioni (anteprima)
> [!div class="mx-imgBorder"] 
> ![Profili cliente B2B](media/profile-customers-b2b.png "Profili cliente B2B")

> [!NOTE]
> Se non riesci a vedere i riquadri quando selezioni **Clienti** nello spostamento, l'amministratore deve [definire almeno un attributo ricercabile](search-filter-index.md) nell'**indice di ricerca e filtro**.

## <a name="search-for-customers"></a>Cercare clienti

Cerca i clienti inserendo un nome o un altro attributo nella casella di ricerca. La ricerca funziona solo all'interno dell'entità Profilo cliente creata durante il processo di unificazione dei dati.

Come amministratore, puoi configurare gli attributi ricercabili mediante la pagina **Indicizzazione ricerca e filtro**. Per ulteriori informazioni, vedi [Gestisci l'indice di ricerca e filtro](search-filter-index.md).

## <a name="filter-customers"></a>Filtrare i clienti

Puoi filtrare i clienti in base ai campi dell'entità Profilo cliente. Simile alla ricerca, l'amministratore dovrà prima definire i campi come filtrabili utilizzando la pagina **Indicizzazione ricerca e filtro**.

1. Seleziona **Filtra** nella pagina **Clienti**.

2. Seleziona le caselle di controllo accanto agli attributi in base a cui vuoi filtrare i clienti.

   > [!div class="mx-imgBorder"] 
   > ![Profili cliente](media/profiles-customers3.png "Profili cliente")

3. Rimuovi i filtri selezionando **Cancella filtri** nella pagina **Clienti**.

##  <a name="customer-details-page"></a>Pagina Dettagli cliente

Seleziona uno dei riquadri del cliente per aprire la **pagina Dettagli cliente**. Questa visualizzazione contiene informazioni unificate per il cliente selezionato.

I dettagli del cliente includono:

-   **Riquadro Profilo cliente:** questo riquadro mostra i diversi valori dell'entità del profilo cliente unificato. Questi dettagli possono includere indirizzo e-mail, nome, città e così via. 

-   **Interessi potenziali, Marchi potenziali:** mostra se hai configurato un arricchimento di prima parte. Rappresenta potenziali interessi e affinità per i marchi che un cliente con un profilo simile a questo cliente potrebbe avere. Per ulteriori informazioni, vedi [Arricchire profili cliente con affinità di marchi e interessi](enrichment-microsoft.md).

-   **Misure:** mostra se hai configurato una o più misure di un tipo specifico: misure attributo cliente. Includono KPI calcolati relativi ai clienti a livello di singolo cliente. Per ulteriori informazioni, vedi [Definire e gestire misure](measures.md).

-   **Sequenza temporale impegni:** mostra se hai configurato impegni. La visualizzazione della sequenza temporale contiene impegni ordinati cronologicamente di questo cliente, a partire dall'impegno più recente. Per altre informazioni, vedi [Impegni cliente](activities.md).

Seleziona **Torna a Clienti** per tornare alla pagina di ricerca del cliente.

## <a name="next-steps"></a>Passaggi successivi

[Aggiungere più origini dati](data-sources.md) o [creare segmenti di clienti](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]