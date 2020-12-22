---
title: Unificazione dei dati
description: Scopri come unificare i dati inseriti.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406100"
---
# <a name="data-unification"></a>Unificazione dei dati

Dopo [impostazione delle origini dati](data-sources.md), puoi unificare i dati. L'unificazione dei dati comprende tre passaggi: **Mapping**, **Corrispondenza** e **Unione**.

Il processo di unificazione dei dati ti consente di unificare le origini dei dati una volta disparate in un unico master set di dati che fornisce una visione unificata dei tuoi clienti. Le fasi di unificazione sono obbligatorie ed eseguite nel seguente ordine:

1. [Mapping](map-entities.md)
2. [Corrispondenza](match-entities.md)
3. [Unione](merge-entities.md)

Dopo aver completato l'unificazione dei dati, puoi facoltativamente

- [configurare relazioni tra entità](relationships.md) per creare segmenti sofisticati
- [arricchire i tuoi dati](enrichment-hub.md) per ottenere una più ampia gamma di informazioni dettagliate sui tuoi clienti
- [definire gli impegni](activities.md) da alcuni degli attributi inseriti
