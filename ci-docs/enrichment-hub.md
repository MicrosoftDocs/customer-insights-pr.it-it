---
title: Arricchire profili cliente unificati
description: Usa specifiche funzionalità per arricchire i tuoi dati cliente.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954046"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Arricchimento per i profili cliente (anteprima)

Utilizza i dati provenienti da origini come Microsoft e altri partner per arricchire i dati dei tuoi clienti.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina dell'hub di arricchimento.":::

Vai a **Dati** > **Arricchimento** per lavorare con le opzioni di arricchimento.  

Devi disporre delle autorizzazioni come Collaboratore o Amministratore per creare o modificare gli arricchimenti. Per ulteriori informazioni, vedi [Autorizzazioni](permissions.md).

Nella scheda **Scopri** , troverai tutte le opzioni di arricchimento supportate.

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

- [Identità AbiliTec](enrichment-liveramp.md) fornita da LiveRamp AbiliTec
- [Marchi](enrichment-microsoft.md) forniti da Microsoft
- [Dati demografici](enrichment-experian.md) forniti da Experian
- [Indirizzi avanzati](enrichment-enhanced-addresses.md) forniti da Microsoft
- [Interessi](enrichment-microsoft.md) forniti da Microsoft
- [Dati località](enrichment-azure-maps.md) forniti da Mappe di Microsoft Azure
- [Dati di localizzazione](enrichment-here.md) forniti da HERE Technologies
- [Dati personalizzati SFTP](enrichment-SFTP-custom-import.md) mediante Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

- [Dati sul coinvolgimento dell'account](enrichment-office.md) fornito da Microsoft
- [Dati aziendali](enrichment-dnb.md) forniti da Dun & Bradstreet
- [Dati aziendali](enrichment-leadspace.md) forniti da Leadspace
- [Indirizzi avanzati](enrichment-enhanced-addresses.md) forniti da Microsoft
- [Dati aziendali ottimizzati](enrichment-enhanced-company-data.md) forniti da Microsoft
- [Dati località](enrichment-azure-maps.md) forniti da Mappe di Microsoft Azure
- [Dati di localizzazione](enrichment-here.md) forniti da HERE Technologies
- [Dati personalizzati SFTP](enrichment-SFTP-custom-import.md) mediante Secure File Transfer Protocol (SFTP)

---

Nella scheda **I miei arricchimenti**, puoi vedere gli arricchimenti che hai configurato e modificarne le proprietà. Puoi anche creare [segmenti](segments.md) o [misure](measures.md) dagli arricchimenti.

## <a name="manage-existing-enrichments"></a>Gestire gli arricchimenti esistenti

Vai alla scheda **I miei arricchimenti** per vedere tutti gli arricchimenti configurati. Ogni arricchimento è rappresentato come una riga che include informazioni aggiuntive sull'arricchimento.

Seleziona l'arricchimento per vedere le opzioni disponibili. Puoi anche selezionare i puntini di sospensione verticali (&vellip;) su un elemento dell'elenco per visualizzare le opzioni. Se hai configurato diversi arricchimenti, puoi utilizzare la casella di ricerca per trovarli rapidamente.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opzioni per gestire gli arricchimenti nell'elenco degli arricchimenti.":::

- **Visualizza** i dettagli dell'arricchimento con il numero di profili cliente arricchiti.
- **Modifica** la configurazione dell'arricchimento.
- **Eseguire** l'arricchimento per aggiornare i profili cliente con i dati più recenti.
- **Disattiva** un arricchimento esistente per impedirne l'aggiornamento automatico a ogni aggiornamento pianificato. I dati dell'ultimo aggiornamento riuscito continueranno a essere disponibili. **Attiva** un arricchimento inattivo per riavviare l'aggiornamento automatico con ogni aggiornamento pianificato.
- **Elimina** l'arricchimento.

Esegui o disattiva più arricchimenti contemporaneamente selezionandoli nell'elenco. Le opzioni di visualizzazione e modifica non sono disponibili come azioni collettive. Funzionano solo per un arricchimento alla volta.

## <a name="enrichments-and-connections"></a>Arricchimenti e connessioni

Gli arricchimenti di terze parti vengono configurati utilizzando le [connessioni](connections.md), che un amministratore imposta con le credenziali e fornisce il consenso per il trasferimento dei dati. Le connessioni possono essere utilizzate dagli amministratori e dai collaboratori per configurare gli arricchimenti.  

## <a name="multiple-enrichments-of-the-same-type"></a>Più arricchimenti dello stesso tipo

L'entità da arricchire viene specificata durante la configurazione dell'arricchimento, che ti consente di arricchire solo un sottoinsieme dei tuoi profili. Ad esempio, arricchisci i dati solo per un segmento specifico. Puoi configurare diversi arricchimenti dello stesso tipo e riutilizzare la stessa connessione. Alcuni arricchimenti avranno dei limiti al numero di arricchimenti dello stesso tipo che possono essere creati. I limiti e l'uso corrente possono essere visualizzati su ciascun riquadro nella scheda **Individua** della pagina **Arricchimento**.

## <a name="enrich-data-sources-before-unification"></a>Arricchire le origini dati prima dell'unificazione

Puoi arricchire i dati dei tuoi clienti prima dell'unificazione dei dati per aumentare la qualità di una corrispondenza di dati. Per altre informazioni, vedi [arricchimento per le origini dati](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Esegui o aggiorna gli arricchimenti

1. Per avviare il processo di arricchimento, seleziona **Esegui**. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipende dalle dimensioni dei dati del cliente.

1. Se lo desideri, [vedi lo stato del processo di arricchimento](#see-the-progress-of-the-enrichment-process).

1. Al termine del processo di arricchimento, vai a **I miei arricchimenti** per rivedere i dati dei profili dei clienti appena arricchiti, l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

1. Seleziona l'arricchimento per visualizzare i [risultati dell'arricchimento](#enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Verificare lo stato del processo di arricchimento

Puoi trovare dettagli sull'elaborazione di un arricchimento, inclusi lo stato e i potenziali problemi durante l'aggiornamento o dopo il completamento di un aggiornamento. Potrai comprendere quali processi sono coinvolti nell'aggiornamento di un arricchimento e quanto tempo è necessario per eseguire i processi. Lo stato di arricchimento è supportato per Experian, Leadspace, HERE Technologies, SFTP Import e Mappe di Azure.

1. Vai a **Dati** > **Arricchimento**.
1. Nella scheda **I miei arricchimenti** seleziona lo stato dell'arricchimento per aprire un riquadro laterale.
1. Nel riquadro **Dettagli stato** espandi la sezione **Arricchimenti**.
1. Per l'arricchimento di cui vuoi vedere i progressi, seleziona **Vedi dettagli**.
1. Nel riquadro **Dettagli attività** seleziona **Mostra dettagli** per vedere i processi che sono coinvolti nell'aggiornamento dell'arricchimento e il relativo stato.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Dopo un ciclo di arricchimento completato, esamina i risultati dell'arricchimento.

1. Vai a **Dati** > **Arricchimento**.
1. Nella scheda **I miei arricchimenti** seleziona l'arricchimento su cui desideri informazioni.

Tutti gli arricchimenti mostrano informazioni di base come il numero di profili arricchiti e il numero di profili arricchiti nel tempo. Il riquadro **Anteprima clienti arricchita** mostra un esempio dell'entità di arricchimento generata. Per una vista dettagliata, seleziona **Visualizza altro** e seleziona la scheda **Dati**.

:::image type="content" source="media/enrichments-results.png" alt-text="Pagina dei risultati degli arricchimenti.":::

Se disponibile, il campo **Numero di clienti arricchiti per campo** fornisce un'analisi dettagliata della copertura di ciascun campo arricchito.

Alcuni arricchimenti mostrano anche informazioni specifiche per il tipo di arricchimento. Per altre informazioni, vedi la documentazione correlata.

[!INCLUDE [footer-include](includes/footer-banner.md)]
