---
title: Esportare dati di Customer Insights in AdRoll
description: Scopri come configurare la connessione ad AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697079"
---
# <a name="connector-for-adroll-preview"></a>Connettore per AdRoll (anteprima)

Esporta i segmenti dei profili cliente unificati in AdRoll e utilizzali per la pubblicità. 

## <a name="prerequisites"></a>Prerequisiti

-   Devi disporre di un [account AdRoll](https://www.adroll.com/) e delle credenziali di amministratore corrispondenti.
-   Disponi di [segmenti configurati](segments.md) in Audience Insights.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="connect-to-adroll"></a>Connetti ad AdRoll

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. Sotto **AdRoll**, seleziona **Configura**.

1. Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Riquadro di configurazione per la connessione ad AdRoll.":::

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connetti** per inizializzare la connessione ad AdRoll.

1. Seleziona **Esegui autenticazione con AdRoll** e fornisci le tue credenziali di amministratore per AdRoll. 

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Inserisci lil tuo **ID inserzionista AdRoll** [Inserzionista AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Seleziona **Avanti** per configurare l'esportazione.

## <a name="configure-the-connector"></a>Configurare il connettore

1. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. È necessario esportare i segmenti in AdRoll.

1. Seleziona i segmenti da esportare. Seleziona un segmento con almeno 100 membri. Non puoi esportare segmenti più piccoli. Inoltre, la dimensione massima di un segmento da esportare è di 250.000 membri per esportazione. 

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitazioni note

- Puoi esportare fino a 250.000 profili per esportazione in AdRoll.
- Non puoi esportare segmenti con meno di 100 profili in AdRoll. 
- L'esportazione in AdRoll è limitata ai segmenti.
- L'esportazione di un massimo di 250.000 profili in AdRoll può richiedere fino a 10 minuti per essere completata. 
- Il numero di profili che puoi esportare in AdRoll dipende ed è limitato dal tuo contratto con AdRoll.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati ad AdRoll, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che AdRoll rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
