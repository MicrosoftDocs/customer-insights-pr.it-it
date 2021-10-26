---
title: Ruoli e autorizzazioni
description: Panoramica dei ruoli e delle autorizzazioni disponibili per i membri dell'area di lavoro.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645542"
---
# <a name="roles-and-permissions"></a>Ruoli e autorizzazioni

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Uno spazio di lavoro è il luogo in cui si archiviano e si gestiscono eventi e rapporti. Per maggiori informazioni, vedi [Creare uno spazio di lavoro e aggiungere membri](create-workspace.md). 

Uno spazio di lavoro può includere i seguenti ruoli e permessi:

- I ruoli *membri* sono utenti che possono accedere a uno spazio di lavoro. Puoi assegnare membri alla tua area di lavoro e definirne i ruoli e le autorizzazioni. 
- I ruoli di *amministratore* gestiscono gli spazi di lavoro e gli ambienti e configurano gli approfondimenti sul coinvolgimento degli altri utenti. 
- I ruoli di *collaboratore* sono orientati verso gli analisti che non hanno bisogno di configurare gli approfondimenti sull'impegno, ma vogliono creare i propri report, funnel o segmenti.

## <a name="permissions"></a>Autorizzazioni
  
La seguente tabella identifica i permessi per ogni ruolo. 

| Autorizzazione | Amministratore dell'ambiente | Amministratore area di lavoro | Collaboratore ambiente | Collaboratore area di lavoro | 
|--|--|--|--|--|
| Crea ambienti (il creatore diventa automaticamente amministratore dell'ambiente) | X* | X* | X* | X* |  
| Configura ambiente (membri dell'ambiente, eliminare ambiente) | X |  |  |  |  
| Crea aree di lavoro | X |  |  |  |  
| Configurare l'area di lavoro (membri dell'area di lavoro, eliminare l'area di lavoro) | X | X |  |  |  
| Configura eventi ed eventi affinati | X | X | |  |  
| Visualizza eventi dell'area di lavoro ed eventi affinati | X | X | |  |  
| Visualizza risorse dell'area di lavoro (report, segmenti e metrica)| X | X | X | X |  
| Crea report e canalizzazioni personalizzati | X | X | X | X |  
| Crea metriche e dimensioni di base| X | X |  |  |  
| Creare segmenti| X | X | X | X |  

*Può creare solo ambienti di prova in anteprima. 

## <a name="add-members"></a>Aggiungi membri

Puoi aggiungere e rimuovere membri da aree di lavoro e ambienti. Per ulteriori informazioni, vedi [Ambienti e aree di lavoro](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
