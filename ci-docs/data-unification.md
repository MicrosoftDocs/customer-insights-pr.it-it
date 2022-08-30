---
title: Crea una visione unificata dei tuoi clienti
description: Passa attraverso il processo di unificazione dei dati con i tuoi dati per creare un unico dataset principale dell'account o dei profili dei clienti.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304432"
---
# <a name="data-unification-overview"></a>Panoramica sulla unificazione dei dati

Dopo [impostazione delle origini dati](data-sources.md), puoi unificare i dati. L'unificazione dei dati ti consente di unificare origini dati un tempo disparate in un unico set di dati principali che fornisce una vista unificata di tali dati.

Per i singoli consumatori (B2C) in cui i dati sono incentrati sulle persone, l'unificazione fornisce una visione unificata dei clienti. Per gli account aziendali (B2B) in cui i dati sono incentrati sugli account, l'unificazione fornisce una visione unificata degli account. [Unificazione dei contatti (anteprima)](data-unification-contacts.md) consente ai contatti di tali account di essere unificati separatamente e associati agli account.

I dati possono essere unificati in una singola entità o in più entità.

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (B2C)](#tab/b2c)

Il processo di unificazione mappa i dati dei clienti dalle tue origini dati, rimuove i duplicati, abbina i dati tra entità e crea un profilo unificato. L'unificazione viene eseguita nel seguente ordine:

1. [Campi di origine](map-entities.md) (precedentemente chiamati Mappa): nel passaggio dei campi di origine, seleziona le entità e i campi da includere nel processo di unificazione. Mappa i campi su un tipo semantico comune che descrive lo scopo del campo.

1. [Record duplicati](remove-duplicates.md) (precedentemente parte della corrispondenza): nel passaggio dei record duplicati, definisci facoltativamente le regole per rimuovere i record del cliente duplicati all'interno di ciascuna entità.

1. [Condizioni corrispondenti](match-entities.md) (precedentemente chiamate Corrispondenza): nel passaggio delle condizioni di corrispondenza, definisci le regole che mettono in corrispondenza i record dei clienti tra le entità. Quando un cliente viene trovato in due o più entità, viene creato un unico record consolidato con tutte le colonne e i dati di ciascuna entità.

1. [Campi cliente unificati](merge-entities.md) (precedentemente chiamati Unisci): nel passaggio dei campi cliente unificati determina quali campi di origine devono essere inclusi, esclusi o uniti in un profilo cliente unificato.  

1. [Esamina](review-unification.md) e crea il profilo unificato.

# <a name="business-accounts-b-to-b"></a>[Account aziendali (B2B)](#tab/b2b)

Il processo di unificazione mappa i dati dell'account dalle tue origini dati, rimuove i duplicati, abbina i dati tra entità e crea un profilo unificato. L'unificazione viene eseguita nel seguente ordine:

1. [Campi di origine](map-entities.md) (precedentemente chiamati Mappa): nel passaggio dei campi di origine, seleziona le entità e i campi da includere nel processo di unificazione dell'account. Mappa i campi su un tipo semantico comune che descrive lo scopo del campo.

1. [Record duplicati](remove-duplicates.md) (precedentemente parte della corrispondenza): nel passaggio dei record duplicati, definisci facoltativamente le regole per rimuovere i record dell'account duplicati all'interno di ciascuna entità.

1. [Condizioni corrispondenti](match-entities.md) (precedentemente chiamate Corrispondenza): nel passaggio delle condizioni di corrispondenza, definisci le regole che mettono in corrispondenza i record dell'account tra le entità. Quando un account viene trovato in due o più entità, viene creato un unico record consolidato con tutte le colonne e i dati di ciascuna entità.

1. [Campi cliente unificati](merge-entities.md) (precedentemente chiamati Unisci): nel passaggio dei campi cliente unificati determina quali campi di origine devono essere inclusi, esclusi o uniti in un profilo cliente unificato.  

1. [Esamina](review-unification.md) e crea il profilo unificato.

Dopo aver unificato gli account, puoi facoltativamente [unificare i contatti (anteprima)](data-unification-contacts.md) per questi account e collegare i contatti unificati sugli account unificati.

---

Dopo aver completato l'unificazione dei dati, puoi facoltativamente:

- [Configurare relazioni tra entità](relationships.md) per creare segmenti sofisticati.
- [Arricchire i tuoi dati](enrichment-hub.md) per ottenere una più ampia gamma di informazioni dettagliate sui tuoi clienti.
- [Definire gli impegni](activities.md) da alcuni degli attributi inseriti.
- [Costruire misure](measures.md) per comprendere meglio i comportamenti dei clienti e le prestazioni aziendali.

[!INCLUDE [footer-include](includes/footer-banner.md)]
