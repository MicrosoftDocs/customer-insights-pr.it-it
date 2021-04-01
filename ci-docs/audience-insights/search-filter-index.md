---
title: Cercare e filtrare profili cliente
description: Trova rapidamente informazioni sui profili cliente unificati e filtra per attributi specificati.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597148"
---
# <a name="customer-profiles-search--filter-index"></a>Profili cliente: indice di ricerca e filtro

Il risultato dell'unificazione dei dati cliente è un'entità Profilo cliente che fornisce una visualizzazione unificata della base clienti totale. Per [trovare rapidamente informazioni su un cliente o gruppo di clienti specifico](customer-profiles.md), puoi configurare le funzionalità **Cerca** o **Filtra** nella pagina **Cleinti**. Continua a leggere per scoprire come gli amministratori possono modificare gli attributi nella pagina **Indicizzazione ricerca e filtro**, che sono disponibili per gli utenti per la ricerca e l'applicazione di filtri.

> [!div class="mx-imgBorder"]
> ![Filtro ricerca](media/search-filter.png "Filtro ricerca")

## <a name="add-fields-and-specify-attributes"></a>Aggiungere campi e specificare attributi

Se è la prima volta che si definiscono gli attributi ricercabili come amministratore, devi definire prima i campi indicizzati. Ti consigliamo di scegliere tutti gli attributi in base ai quali gli utenti possono cercare e filtrare i clienti nella pagina **Clienti**. Puoi specificare solo gli attributi presenti nell'entità Profilo cliente creata durante il processo di unificazione dei dati.

1. Apri la pagina **Clienti** e seleziona **Indicizzazione ricerca e filtro**.

2. Seleziona **+ Aggiungi** per specificare i campi indicizzati.

3. Seleziona gli attributi nell'elenco che vuoi aggiungere come campi indicizzati. Puoi sempre aggiungere altri attributi selezionando **Aggiungi**. Puoi anche rimuovere tutti gli attributi selezionati selezionando il simbolo **Rimuovi**.

## <a name="explore-the-indexed-customer-fields-table"></a>Esplorare la tabella Campi cliente indicizzati

Nella tabella vengono presentate le seguenti informazioni.

- **Nome**: rappresenta il nome dell'attributo così come viene visualizzato nell'entità Profilo cliente.
- **Tipo di dati**: specifica se il tipo di dati è una stringa, un numero o una data.
- **Incluso nella ricerca**: specifica se questo attributo può essere utilizzato per la ricerca dei clienti nella pagina **Clienti** utilizzando il campo **Cerca**.
- **Aggiungi filgtro**: controllo per definire la modalità di utilizzo di questo attributo per il filtro nella pagina **Clienti**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Modifica delle opzioni di filtro per un determinato attributo

Il menu **Filtra** nella pagina **Clienti** può includere un numero variabile di livelli di attributo (ad esempio, diverse fasce di età in base alle quali filtrare i clienti).

1. Seleziona **Aggiungi filtro** per un determinato attributon ella pagina **Indicizzazione ricerca e filtro**. Puoi definire il numero di risultati e l'ordine in cui verranno organizzati. A seconda del tipo di dati dell'attributo, viene visualizzato uno dei riquadri seguenti.

- Attributi di tipo stringa: specifica il numero di risultati desiderati nel pannello **Opzioni di filtro stringa** e i criteri di ordine in base ai quali verranno organizzati.

- Attributi di tipo numerico: specifica gli intervalli inclusi nel pannello **Opzioni di filtro numeri** e i criteri di ordine in base ai quali verranno organizzati.

- Attributi di tipo data: specifica gli intervalli inclusi nel pannello **Opzioni filtro data** e i criteri di ordine in base ai quali verranno organizzati.

2. Seleziona **Salva** per applicare le modifiche.

3. Seleziona **Esegui** quando sei pronto per applicare le impostazioni.

## <a name="next-steps"></a>Passaggi successivi

Vai alla pagina **Clienti** per cercare i profili dei clienti o utilizza i campi indicizzati per visualizzare un sottoinsieme di tutti i profili dei clienti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]