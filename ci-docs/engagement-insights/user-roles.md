---
title: Ruoli e autorizzazioni
description: Panoramica dei ruoli e delle autorizzazioni disponibili per i membri dell'area di lavoro.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036698"
---
# <a name="roles-and-permissions"></a>Ruoli e autorizzazioni

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un'area di lavoro è uno spazio in cui archiviare e gestire eventi e report. Un membro è un utente che può accedere a un'area di lavoro. Puoi assegnare membri alla tua area di lavoro e definirne i ruoli e le autorizzazioni. I ruoli amministratore gestiscono le aree di lavoro e gli ambienti e configurano le informazioni dettagliate per altri utenti. I ruoli Collaboratore sono orientati agli analisti che non hanno bisogno di configurare le informazioni dettagliate ma vogliono creare i propri report, le proprie canalizzazioni o i propri segmenti.

## <a name="permissions"></a>Autorizzazioni
  
Il grafico seguente identifica le autorizzazioni per ogni ruolo. 

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
