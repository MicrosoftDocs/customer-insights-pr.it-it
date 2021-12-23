---
title: Gestire le regole di consenso predefinite sui segmenti
description: Con la funzionalità di gestione del consenso, puoi disabilitare o modificare le regole del consenso predefinite se le sostituzioni sono abilitate.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884175"
---
# <a name="disable-or-change-default-consent-rules"></a>Disabilita o modifica le regole di consenso predefinite

Se le tue organizzazioni usano la [funzionalità di gestione del consenso](../consent-management/overview.md) in combinazione con le informazioni dettagliate sul gruppo di destinatari, gli [amministratori possono applicare le regole di consenso](activate-consent.md) per segmenti. 

Con le regole di consenso applicate nell'area del segmento, ogni segmento fornisce informazioni sullo stato della verifica del consenso e delle regole. Se le sostituzioni sono consentite, le regole di consenso predefinite vengono disattivate per segmenti specifici. Ogni creatore di un segmento può aggiungere più regole oltre quelle predefinite per un segmento. 

## <a name="for-administrators"></a>Per gli amministratori

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Generatore di segmenti con opzioni per le regole di consenso.":::

**Per disattivare le regole di consenso predefinite:**

1. Nella notifica **Regole di consenso** seleziona **Vedi dettagli**. 

1. Imposta l'interruttore **Regole di consenso predefinite** su **Disattivato**.

**Per aggiungere altre regole di consenso:**

1. Nella notifica **Regole di consenso** seleziona **Vedi dettagli**. 

1. Seleziona **Aggiungi regole di consenso** e scegli una regola di consenso dall'elenco a discesa **Seleziona tipo di dati del consenso**.

1. Seleziona **Salva** per applicare la nuova regola al segmento.

## <a name="for-contributors"></a>Per i collaboratori

Per creare un segmento senza regole di consenso applicate, devi lavorare con il tuo amministratore per disabilitarle sul tuo segmento. Tuttavia, puoi aggiungere le tue regole di consenso ai segmenti che possiedi e gestisci.

È un processo in tre fasi: 
1. [Crea il segmento](segments.md) in destinatari approfondimenti e salvalo. 

1. Condividi il nome del segmento con il tuo amministratore e chiedi loro di [abilitare le sostituzioni per il tuo segmento](activate-consent.md). 

1. Apri di nuovo i tuoi segmenti. Nella notifica **Regole di consenso**, seleziona **Vedi dettagli** e aggiungi le regole di consenso che desideri applicare. Quindi, **Salva** ed **Esegui** il tuo segmento.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
