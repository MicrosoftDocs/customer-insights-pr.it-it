---
title: Arricchire profili cliente unificati
description: Usa specifiche funzionalità per arricchire i tuoi dati cliente.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269473"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Arricchimento per i profili cliente (anteprima)

Utilizza i dati provenienti da origini come Microsoft e altri partner per arricchire i dati dei tuoi clienti.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina dell'hub di arricchimento":::

In Audience Insights, vai a **Dati** > **Arricchimento** per utilizzare le opzioni di arricchimento.    
Devi disporre delle autorizzazioni come Collaboratore o Amministratore per creare o modificare gli arricchimenti. Per ulteriori informazioni, vedi [Autorizzazioni](permissions.md).

Nella scheda **Scopri**, troverai i seguenti arricchimenti:

- [Marchi](enrichment-microsoft-graph.md) forniti da Microsoft Graph
- [Interessi](enrichment-microsoft-graph.md) forniti da Microsoft Graph
- [Dati aziendali](enrichment-leadspace.md) forniti da Leadspace
- [Dati demografici](enrichment-experian.md) forniti da Experian
- [Dati di localizzazione](enrichment-here.md) forniti da HERE Technologies
- [Personalizzare i dati](enrichment-SFTP-custom-import.md) mediante Secure File Transfer Protocol (SFTP)

Nella scheda **I miei arricchimenti**, puoi vedere gli arricchimenti che hai configurato e modificarne le proprietà.

## <a name="manage-existing-enrichments"></a>Gestire gli arricchimenti esistenti

Vai a **Arricchimenti personali** per vedere tutti gli arricchimenti configurati. Ogni arricchimento è rappresentato come una riga che include informazioni aggiuntive sull'arricchimento.

Seleziona un arricchimento per vedere le opzioni disponibili. In alternativa, puoi selezionare i puntini di sospensione (...) su un elemento dell'elenco per visualizzare le opzioni.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opzioni per gestire gli arricchimenti nell'elenco degli arricchimenti":::

- **Visualizza** i dettagli dell'arricchimento con il numero di profili cliente arricchiti.
- **Modifica** la configurazione dell'arricchimento.
- **Eseguire** l'arricchimento per aggiornare i profili cliente con i dati più recenti.
- **Disattiva** un arricchimento esistente per impedirne l'aggiornamento automatico a ogni aggiornamento pianificato. I dati dell'ultimo aggiornamento riuscito continueranno a essere disponibili. **Attiva** un arricchimento inattivo per riavviare l'aggiornamento automatico con ogni aggiornamento pianificato.
- **Elimina** un arricchimento.

Puoi eseguire o disattivare più arricchimenti contemporaneamente selezionandoli nell'elenco. Le opzioni di visualizzazione e modifica non sono disponibili come azione in blocco e funzionano solo per un arricchimento alla volta.


[!INCLUDE[footer-include](../includes/footer-banner.md)]