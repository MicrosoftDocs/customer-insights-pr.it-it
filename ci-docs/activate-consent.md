---
title: Attivare le regole di consenso per i segmenti
description: Segui questi passaggi per collegare i dati del consenso e attivare le verifiche del consenso in Dynamics 365 Customer Insights. Un amministratore può anche disabilitare le verifiche del consenso.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755175"
---
# <a name="activate-consent-rules"></a>Attiva regole di consenso

Il [Centro consenso (anteprima)](consent-management/overview.md) ti aiuta ad armonizzare i dati del consenso da varie origini. Usa l'entità *Consenso* per applicare verifiche del consenso predefinite. Dopo aver importato i dati del consenso le regole di mapping, l'entità *Consenso* viene sincronizzata automaticamente con Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Abilita verifiche del consenso

Con i dati del consenso importati nel Centro consenso (anteprima) e le regole configurate, puoi abilitare le verifiche del consenso. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Scheda Consenso in Customer Insights con i dati di consenso attivati.":::

1. In Customer Insights, vai a **Amministratore** > **Sistema**.

1. Seleziona la scheda **Consenso (anteprima)**.

1. Nella sezione **Abilita verifiche del consenso** imposta **Attivato** per tutte le aree che desideri abilitare.

1. Seleziona la casella di controllo **Consenti sostituzione delle regole predefinite di consenso** per rimuovere le verifiche del consenso predefinite applicate su un particolare segmento. 

1. Nel menu a discesa seleziona dove desideri consentire le sostituzioni.     

1. Nella sezione **Collega consenso ai profili cliente** scegli l'attributo che viene usato come identificatore per collegare i dati del consenso ai dati del cliente. È probabile che si tratti di un numero di telefono o un indirizzo e-mail. 

1. Seleziona **Salva** per applicare le impostazioni.

## <a name="disable-consent-checks"></a>Disabilita verifiche del consenso

Per arrestare l'utilizzo dei dati del consenso in Customer Insights, un amministratore deve aggiornare le impostazioni di sistema di conseguenza.

1. In Customer Insights, vai a **Amministratore** > **Sistema**.

1. Seleziona la scheda **Consenso (anteprima)**.

1. Nella sezione **Abilita verifiche del consenso** imposta l'interruttore su **Disattivato**.

> [!TIP]
> Per interrompere l'utilizzo della funzionalità di gestione del consenso, vedi [Impostazioni di sistema in Centro consenso (anteprima)](consent-management/system-settings.md).
