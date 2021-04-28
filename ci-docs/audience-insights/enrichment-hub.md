---
title: Arricchire profili cliente unificati
description: Usa specifiche funzionalità per arricchire i tuoi dati cliente.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896010"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Arricchimento per i profili cliente (anteprima)

Utilizza i dati provenienti da origini come Microsoft e altri partner per arricchire i dati dei tuoi clienti.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina dell'hub di arricchimento":::

In Audience Insights, vai a **Dati** > **Arricchimento** per utilizzare le opzioni di arricchimento.    
Devi disporre delle autorizzazioni come Collaboratore o Amministratore per creare o modificare gli arricchimenti. Per ulteriori informazioni, vedi [Autorizzazioni](permissions.md).

Nella scheda **Scopri**, troverai i seguenti arricchimenti:

- [Marchi](enrichment-microsoft.md) forniti da Microsoft
- [Interessi](enrichment-microsoft.md) forniti da Microsoft
- [Dati aziendali](enrichment-leadspace.md) forniti da Leadspace
- [Dati demografici](enrichment-experian.md) forniti da Experian
- [Dati di localizzazione](enrichment-here.md) forniti da HERE Technologies
- [Personalizzare i dati](enrichment-SFTP-custom-import.md) mediante Secure File Transfer Protocol (SFTP)

Nella scheda **I miei arricchimenti**, puoi vedere gli arricchimenti che hai configurato e modificarne le proprietà.

## <a name="manage-existing-enrichments"></a>Gestire gli arricchimenti esistenti

Vai a **Arricchimenti personali** per vedere tutti gli arricchimenti configurati. Ogni arricchimento è rappresentato come una riga che include informazioni aggiuntive sull'arricchimento.

Seleziona un arricchimento per vedere le opzioni disponibili. È inoltre possibile selezionare i puntini di sospensione (...) di un elemento dell'elenco per visualizzare le opzioni.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opzioni per gestire gli arricchimenti nell'elenco degli arricchimenti":::

- **Visualizza** i dettagli dell'arricchimento con il numero di profili cliente arricchiti.
- **Modifica** la configurazione dell'arricchimento.
- **Eseguire** l'arricchimento per aggiornare i profili cliente con i dati più recenti.
- **Disattiva** un arricchimento esistente per impedirne l'aggiornamento automatico a ogni aggiornamento pianificato. I dati dell'ultimo aggiornamento riuscito continueranno a essere disponibili. **Attiva** un arricchimento inattivo per riavviare l'aggiornamento automatico con ogni aggiornamento pianificato.
- **Elimina** un arricchimento.

Puoi eseguire o disattivare più arricchimenti contemporaneamente selezionandoli nell'elenco. Le opzioni di visualizzazione e modifica non sono disponibili come azione in blocco e funzionano solo per un arricchimento alla volta.

## <a name="enrichments-and-connections"></a>Arricchimenti e connessioni

Gli arricchimenti di terze parti vengono configurati utilizzando le [connessioni](connections.md), che un amministratore imposta con le credenziali e fornisce il consenso per il trasferimento dei dati. La connessione può essere utilizzata da amministratori e collaboratori per configurare gli arricchimenti.  

## <a name="multiple-enrichments-of-the-same-type"></a>Più arricchimenti dello stesso tipo

L'entità da arricchire viene specificata durante la configurazione dell'arricchimento, che ti consente di arricchire solo un sottoinsieme dei tuoi profili. Ad esempio, arricchisci i dati solo per un segmento specifico. Puoi configurare diversi arricchimenti dello stesso tipo e riutilizzare la stessa connessione. Alcuni arricchimenti avranno dei limiti al numero di arricchimenti dello stesso tipo che possono essere creati. I limiti e l'uso corrente possono essere visualizzati nella pagina **Arricchimento**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
