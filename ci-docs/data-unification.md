---
title: Crea una visione unificata dei tuoi clienti
description: Esegui il processo di unificazione con i tuoi dati per creare un unico set di dati di profili cliente unificati.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755739"
---
# <a name="data-unification-overview"></a>Panoramica sulla unificazione dei dati

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Dopo [impostazione delle origini dati](data-sources.md), puoi unificare i dati. L'unificazione dei dati ti consente di unificare origini dati un tempo disparate in un unico set di dati principali che fornisce una vista unificata di tali dati. Per i singoli consumatori (B2C) in cui i dati sono incentrati sulle persone, l'unificazione fornisce una visione unificata dei clienti. Per gli account aziendali (B2B) in cui i dati sono incentrati sugli account, l'unificazione fornisce una visione unificata degli account.

I dati possono essere unificati in una singola entità o in più entità. L'unificazione viene eseguita nel seguente ordine:

1. [Campi di origine](map-entities.md) (precedentemente chiamati Mappa): nel passaggio dei campi di origine, seleziona le entità e i campi da includere nel processo di unificazione. Mappa i campi su un tipo semantico comune che descrive lo scopo del campo.

1. [Record duplicati](remove-duplicates.md) (precedentemente parte della corrispondenza): nel passaggio dei record duplicati, definisci facoltativamente le regole per rimuovere i record del cliente duplicati all'interno di ciascuna entità.

1. [Condizioni corrispondenti](match-entities.md) (precedentemente chiamate Corrispondenza): nel passaggio delle condizioni di corrispondenza, definisci le regole che mettono in corrispondenza i record dei clienti tra le entità. Quando un cliente viene trovato in due o più entità, viene creato un unico record consolidato con tutte le colonne e i dati di ciascuna entità.

1. [Campi cliente unificati](merge-entities.md) (precedentemente chiamati Unisci): nel passaggio dei campi cliente unificati determina quali campi di origine devono essere inclusi, esclusi o uniti in un profilo cliente unificato.  

1. [Esamina](review-unification.md) e crea il profilo unificato.

Dopo aver completato l'unificazione dei dati, puoi facoltativamente:

- [Configurare relazioni tra entità](relationships.md) per creare segmenti sofisticati.
- [Arricchire i tuoi dati](enrichment-hub.md) per ottenere una più ampia gamma di informazioni dettagliate sui tuoi clienti.
- [Definire gli impegni](activities.md) da alcuni degli attributi inseriti.
- [Costruire misure](measures.md) per comprendere meglio i comportamenti dei clienti e le prestazioni aziendali.

[!INCLUDE [footer-include](includes/footer-banner.md)]
