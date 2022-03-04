---
title: Utilizzare i segmenti di Informazioni dettagliate sul gruppo di destinatari per filtrare i report di Informazioni dettagliate sull'interazione
description: Utilizza i segmenti di Informazioni dettagliate sul gruppo di destinatari nelle analisi interattive dei dati comportamentali acquisiti da Informazioni dettagliate sull'interazione nel sito Web di un cliente.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230491"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Utilizzare i segmenti di Informazioni dettagliate sul gruppo di destinatari per filtrare i report di Informazioni dettagliate sull'interazione

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Con Informazioni dettagliate sull'interazione, puoi utilizzare i segmenti di Informazioni dettagliate sul gruppo di destinatari nelle analisi interattive dei dati comportamentali acquisiti da Informazioni dettagliate sull'interazione nel sito Web di un cliente.

## <a name="prerequisite"></a>Prerequisito

- Un ambiente di Informazioni dettagliate sull'interazione in cui sono disponibili dati sui segmenti di Informazioni dettagliate sul gruppo di destinatari collegati all'ambiente di Informazioni dettagliate sul gruppo di destinatari in cui vengono creati i segmenti e i profili cliente. Ulteriori informazioni: [Creare un collegamento tra Informazioni dettagliate sul gruppo di destinatari e Informazioni dettagliate sull'interazione](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Creare segmenti di Informazioni dettagliate sul gruppo di destinatari 

> [!IMPORTANT]
> Affinché i segmenti di Informazioni dettagliate sul gruppo di destinatari siano visualizzati in informazioni dettagliate sull'interazione, devi prima [eseguire processi di merge e downstream](../audience-insights/merge-entities.md). I processi di downstream sono importanti perché generano una tabella univoca che prepara i segmenti di Informazioni dettagliate sul gruppo di destinatari da condividere con Informazioni dettagliate sull'interazione (se è pianificato un aggiornamento del sistema, includerà automaticamente i processi di downstream).

Puoi utilizzare i segmenti di Informazioni dettagliate sul gruppo di destinatari nei report predefiniti di Informazioni dettagliate sull'interazione o nei report personalizzati che hai creato. Per maggiori informazioni, vedi [Report predefiniti sui profili](profile-reports.md) e [Creare e modificare report personalizzati](custom-reports.md).

**Per utilizzare i segmenti di Informazioni dettagliate sul gruppo di destinatari nei report di Informazioni dettagliate sull'interazione**

1. Nella pagina **Area di lavoro**, seleziona **Dati**, quindi seleziona la scheda **Segmenti**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Selezionare la scheda Segmenti.":::

   >[!NOTE]
   > Selezionando un segmento di Informazioni dettagliate sul gruppo di destinatari accedi a Informazioni dettagliate sul gruppo di destinatari, dove puoi scoprire come è stato creato quel segmento in termini di regole e logica. Per ulteriori informazioni sui segmenti di Informazioni dettagliate sul gruppo di destinatari, vedi [Visualizzare e creare segmenti](../audience-insights/segments.md).

2. Seleziona un report predefinito o [crea un report personalizzato](custom-reports.md), quindi seleziona **Aggiungi condizione** (per questo esempio, abbiamo scelto il report **Visualizzazioni di pagina**).

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Aggiungere una condizione.":::

3. Seleziona **Filtra per segmento**, espandi l'elenco **Tipo di segmento** e quindi seleziona **Dati demografici**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Selezionare il tipo di segmento Dati demografici.":::

4. Espandi l'elenco **Nome segmento**, quindi scegli un segmento di Informazioni dettagliate sul gruppo di destinatari.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text=" Scegliere un segmento.":::

5. Puoi applicare uno o più segmenti, inclusi i segmenti comportamentali (Informazioni dettagliate sull'interazione) e demografici (Informazioni dettagliate sul gruppo di destinatari). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Report Visualizzazioni di pagina limitato ai clienti degli Stati Uniti e ai segmenti della home page.":::

Nell'immagine precedente, sono stati selezionati i segmenti **Clienti USA** e **Home page**, il che comporta la visualizzazione di soltanto quei due segmenti nel report **Visualizzazioni di pagina**. 


>[!NOTE]
> Puoi utilizzare i segmenti di Informazioni dettagliate sul gruppo di destinatari per filtrare i report predefiniti, i report personalizzati e i grafici a imbuto in Informazioni dettagliate sull'interazione. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]