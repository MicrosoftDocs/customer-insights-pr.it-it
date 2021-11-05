---
title: Arricchire profili cliente unificati
description: Usa specifiche funzionalità per arricchire i tuoi dati cliente.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: bc0128c222c032e8cfe35e6f3baa0ea722bce7cb
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673004"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Arricchimento per i profili cliente (anteprima)

Utilizza i dati provenienti da origini come Microsoft e altri partner per arricchire i dati dei tuoi clienti.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina dell'hub di arricchimento.":::

In Informazioni dettagliate sul gruppo di destinatari, vai a **Dati** > **Arricchimento** per utilizzare le opzioni di arricchimento.  

Devi disporre delle autorizzazioni come Collaboratore o Amministratore per creare o modificare gli arricchimenti. Per ulteriori informazioni, vedi [Autorizzazioni](permissions.md).

Nella scheda **Scopri** , troverai tutte le opzioni di arricchimento supportate.

# <a name="individual-consumers-b-to-c"></a>[Singoli utenti (da B a C)](#tab/b2c)

- [Marchi](enrichment-microsoft.md) forniti da Microsoft
- [Interessi](enrichment-microsoft.md) forniti da Microsoft
- [Indirizzi avanzati](enrichment-enhanced-addresses.md) forniti da Microsoft 
- [Dati demografici](enrichment-experian.md) forniti da Experian
- [Personalizzare i dati](enrichment-SFTP-custom-import.md) mediante Secure File Transfer Protocol (SFTP) 
- [Mappe di Azure](enrichment-azure-maps.md) fornito da Microsoft

# <a name="business-accounts-b-to-b"></a>[Account aziendali (da B a B)](#tab/b2b)

- [Dati aziendali](enrichment-leadspace.md) forniti da Leadspace
- [Indirizzi avanzati](enrichment-enhanced-addresses.md) forniti da Microsoft 
- [Dati di localizzazione](enrichment-here.md) forniti da HERE Technologies 
- [Personalizzare i dati](enrichment-SFTP-custom-import.md) mediante Secure File Transfer Protocol (SFTP) 
- [Mappe di Azure](enrichment-azure-maps.md) fornito da Microsoft

---

Nella scheda **I miei arricchimenti**, puoi vedere gli arricchimenti che hai configurato e modificarne le proprietà.

## <a name="manage-existing-enrichments"></a>Gestire gli arricchimenti esistenti

Vai alla scheda **I miei arricchimenti** per vedere tutti gli arricchimenti configurati. Ogni arricchimento è rappresentato come una riga che include informazioni aggiuntive sull'arricchimento.

Seleziona l'arricchimento per vedere le opzioni disponibili. È inoltre possibile selezionare i puntini di sospensione (...) di un elemento dell'elenco per visualizzare le opzioni. Se hai configurato diversi arricchimenti, puoi utilizzare la casella di ricerca per trovarli rapidamente.

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

L'entità da arricchire viene specificata durante la configurazione dell'arricchimento, che ti consente di arricchire solo un sottoinsieme dei tuoi profili. Ad esempio, arricchisci i dati solo per un segmento specifico. Puoi configurare diversi arricchimenti dello stesso tipo e riutilizzare la stessa connessione. Alcuni arricchimenti avranno dei limiti al numero di arricchimenti dello stesso tipo che possono essere creati. I limiti e l'uso corrente possono essere visualizzati nella pagina **Arricchimento**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Verificare lo stato del processo di arricchimento

Puoi trovare dettagli sull'elaborazione di un arricchimento, inclusi lo stato e i potenziali problemi durante l'aggiornamento o dopo il completamento di un aggiornamento. Potrai comprendere quali processi sono coinvolti nell'aggiornamento di un arricchimento e quanto tempo è necessario per eseguire i processi. Lo stato di arricchimento è supportato per Experian, Leadspace, HERE Technologies, SFTP Import e Mappe di Azure.

Per vedere lo stato di un arricchimento

1. Vai a **Dati** > **Arricchimento**. 
1. Nella scheda **I miei arricchimenti** seleziona lo stato di un arricchimento per aprire un riquadro laterale. 
1. Nel riquadro **Dettagli stato** espandi la sezione **Arricchimenti**. 
1. Per l'arricchimento di cui vuoi vedere i progressi, seleziona **Vedi dettagli**. 
1. Nel riquadro **Dettagli attività** seleziona **Mostra dettagli** per vedere i processi che sono coinvolti nell'aggiornamento dell'arricchimento e il relativo stato. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
