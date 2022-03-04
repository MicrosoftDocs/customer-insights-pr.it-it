---
title: Utilizzare le dimensioni demografiche per suddividere i dati comportamentali (dimensioni curate)
description: Utilizza le dimensioni curate di profili unificati per abilitare le proprietà dei profili cliente di Informazioni dettagliate sul gruppo di destinatari.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233052"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Utilizzare le dimensioni demografiche per suddividere i dati comportamentali

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Utilizzando le dimensioni demografiche di profili unificati, gli utenti di Informazioni dettagliate sull'interazione possono accedere alle proprietà dei profili di Informazioni dettagliate sul gruppo di destinatari. Puoi quindi utilizzare queste proprietà nelle analisi interattive dei dati comportamentali, inclusi i dati acquisiti da Informazioni dettagliate sull'interazione nel sito Web nell'app per dispositivi mobili.

>[!NOTE]
> Le informazioni dettagliate includono dimensioni predefinite per le proprietà degli eventi. Altre informazioni: [Visualizzare e creare dimensioni](dimensions.md)

## <a name="prerequisite"></a>Prerequisito

- Un ambiente di Informazioni dettagliate sull'interazione in cui sono disponibili dati sui profili cliente collegati all'ambiente di Informazioni dettagliate sul gruppo di destinari in cui vengono creati i profili cliente. Ulteriori informazioni: [Creare un collegamento tra Informazioni dettagliate sul gruppo di destinatari e Informazioni dettagliate sull'interazione](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Dopo aver creato un collegamento tra gli ambienti di Informazioni dettagliate sul gruppo di destinatari e di Informazioni dettagliate sull'interazione, potresti volere solo dati specifici delle proprietà del profilo cliente, che possono essere utili come dimensioni in Informazioni dettagliate sull'interazione. Per ulteriori informazioni, vedi [Abilitare attributi e segmenti di profili unificati di Informazioni dettagliate sul gruppo di destinatari](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Creare un nuovo report personalizzato

1. Nel riquadro a sinistra, seleziona **Personalizza** > **Nuovo report**, quindi seleziona la metrica desiderata (per questo esempio, abbiamo scelto il report **Visualizzazioni di pagina per ora**).

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Selezionare una metrica.":::

2. Nell'editor visualizzazione, seleziona **Dimensioni**, quindi seleziona **Dati demografici** nel menu a discesa **Tipo di dimensione**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Selezionare dati demografici.":::

3. Seleziona una dimensione **Signal.Customer.*xxx** (questo esempio mostra Signal.Customer.Country).

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Selezionare una dimensione.":::
  
## <a name="limitations"></a>Limiti

Attualmente puoi soltanto usare le dimensioni demografiche per suddividere i dati comportamentali.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
