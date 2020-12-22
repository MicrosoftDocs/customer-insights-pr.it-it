---
title: Cercare e filtrare profili cliente
description: Trova rapidamente informazioni sui profili cliente unificati e filtra per attributi specificati.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406139"
---
# <a name="customer-profiles-search--filter-index"></a>Profili cliente: indice di ricerca e filtro

Il risultato dell'unificazione dei dati cliente è un'entità Profilo cliente che fornisce una visualizzazione unificata della base clienti totale. Per [trovare rapidamente informazioni su un cliente o gruppo di clienti specifico](customer-profiles.md), puoi configurare le funzionalità **Cerca** o **Filtra** nella pagina **Cleinti**. Continua a leggere per scoprire come gli amministratori possono modificare gli attributi nella pagina **Indicizzazione ricerca e filtro**, che sono disponibili per gli utenti per la ricerca e l'applicazione di filtri.

> [!div class="mx-imgBorder"]
> ![Filtro ricerca](media/search-filter.png "Filtro ricerca")

## <a name="add-fields-and-specify-attributes"></a>Aggiungere campi e specificare attributi

Se è la prima volta che si definiscono gli attributi ricercabili come amministratore, devi definire prima i campi indicizzati. Ti consigliamo di scegliere tutti gli attributi in base ai quali gli utenti possono cercare e filtrare i clienti nella pagina **Clienti**. Puoi specificare solo gli attributi presenti nell'entità Profilo cliente creata durante il processo di unificazione dei dati.

1. Apri la pagina **Clienti** e seleziona **Indicizzazione ricerca e filtro**.

> [!NOTE]
> Creiamo una configurazione dell'indice di ricerca predefinita sugli attributi disponibili nell'entità Cliente dai seguenti tipi semantici, come definito nella pagina Mappa.
> - Nome, Cognome, Secondo nome, Nome completo
> - Nome organizzazione
> - Indirizzo e-mail
> - Numero di telefono
> - Informazioni sulla posizione

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
