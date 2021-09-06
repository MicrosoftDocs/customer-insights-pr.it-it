---
title: Esportare i dati di Customer Insights in RollWorks
description: Scopri come configurare la connessione ed esportare in RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d8ce4d867835dcb7cf56c6fffff4e25d1f5c109af0e401fc0eb8b3a7427c1de4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034595"
---
# <a name="export-segments-to-rollworks-preview"></a>Esportare segmenti in RollWorks (anteprima)

Esporta segmenti di profili cliente unificati in RollWorks e utilizzali per la pubblicità. 

## <a name="prerequisites-for-a-connection"></a>Prerequisiti per una connessione

-   Hai un [account RollWorks](https://www.rollworks.com/) e le corrispondenti credenziali di amministratore.
-   Disponi di [segmenti configurati](segments.md) in Informazioni dettagliate sul gruppo di destinatari.
-   I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 250.000 profili per esportazione in RollWorks.
- Non è possibile esportare segmenti con meno di 100 profili in RollWorks. 
- L'esportazione in RollWorks è limitata ai segmenti.
- L'esportazione di un massimo di 250.000 profili in RollWorks può richiedere fino a 10 minuti per essere completata. 
- Il numero di profili che puoi esportare in RollWorks dipende ed è limitato dal tuo contratto con RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Configurare la connessione a RollWorks

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **RollWorks** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Connettiti** per inizializzare la connessione a RollWorks.

1. Seleziona **Autentica con RollWorks** e fornisci le tue credenziali di amministratore per RollWorks.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione RollWorks. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Inserisci il tuo **ID inserzionista RollWorks** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Nella sezione **Corrispondenza dati** nel campo **E-mail**, seleziona il campo nel tuo profilo cliente unificato che rappresenta l'indirizzo e-mail di un cliente. È necessario per esportare i segmenti in RollWorks.

1. Seleziona i segmenti da esportare. Seleziona un segmento con almeno 100 membri. Non puoi esportare segmenti più piccoli. Inoltre, la dimensione massima di un segmento da esportare è di 250.000 membri per esportazione. 

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a RollWorks, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma sei responsabile di garantire che RollWorks soddisfi eventuali obblighi di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
