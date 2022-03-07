---
title: Attivare le regole di consenso per i segmenti
description: Segui questi passaggi per collegare i dati del consenso e attivare le verifiche del consenso nelle informazioni dettagliate sul gruppo di destinatari. Un amministratore può anche disabilitare le verifiche del consenso.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790781"
---
# <a name="activate-consent-rules"></a>Attiva regole di consenso

Il [Centro consenso (anteprima)](../consent-management/overview.md) ti aiuta ad armonizzare i dati del consenso da varie origini. Usa l'entità *Consenso* per applicare verifiche del consenso predefinite. Dopo aver importato i dati del consenso nel Centro consenso e configurato le regole per i dati, l'entità *Consenso* viene sincronizzata automaticamente con le informazioni dettagliate sul gruppo di destinatari.

## <a name="enable-consent-checks"></a>Abilita verifiche del consenso

Con i dati del consenso importati nel Centro consenso (anteprima) e le regole configurate, puoi abilitare le verifiche del consenso. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Scheda Consenso nelle impostazioni delle informazioni dettagliate sul gruppo di destinatari con i dati di consenso attivati.":::

1. In Audience Insights, vai a **Amministratore** > **Sistema**.

1. Seleziona la scheda **Consenso (anteprima)**.

1. Nella sezione **Abilita verifiche del consenso** imposta **Attivato** per tutte le aree che desideri abilitare.

1. Seleziona la casella di controllo **Consenti sostituzione delle regole predefinite di consenso** per rimuovere le verifiche del consenso predefinite applicate su un particolare segmento. 

1. Nel menu a discesa seleziona dove desideri consentire le sostituzioni.     

1. Nella sezione **Collega consenso ai profili cliente** scegli l'attributo che viene usato come identificatore per collegare i dati del consenso ai dati del cliente. È probabile che si tratti di un numero di telefono o un indirizzo e-mail. 

1. Seleziona **Salva** per applicare le impostazioni.

## <a name="disable-consent-checks"></a>Disabilita verifiche del consenso

Per arrestare l'utilizzo dei dati del consenso nelle informazioni dettagliate sul gruppo di destinatari, un amministratore deve aggiornare le impostazioni di sistema di conseguenza.

1. In Audience Insights, vai a **Amministratore** > **Sistema**.

1. Seleziona la scheda **Consenso (anteprima)**.

1. Nella sezione **Abilita verifiche del consenso** imposta l'interruttore su **Disattivato**.
