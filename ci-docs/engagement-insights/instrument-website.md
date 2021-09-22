---
title: Aggiungere codice al sito Web
description: Come aggiungere un frammento di codice per acquisire eventi sul tuo sito Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035099"
---
# <a name="install-the-code-snippet-on-a-website"></a>Installare il frammento di codice su un sito Web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Questo articolo descrive in che modo un amministratore installa il frammento di codice su un sito Web. Inizierai a vedere gli eventi nella tua area di lavoro subito dopo aver aggiunto lo script al tuo sito Web. Per ulteriori informazioni, vedi [Gestire aree di lavoro e ambienti](manage-environments-workspaces.md). Per acquisire eventi nelle app mobili, vedi [Panoramica delle risorse per gli sviluppatori](developer-resources.md).


### <a name="prerequisites"></a>Prerequisiti

* Devi disporre delle autorizzazioni di amministratore per l'area di lavoro per archiviare i dati.
* Il tuo sito Web o progetto deve essere ospitato online per inviare i dati dell'impegno. I dati inviati da un file locale non saranno accettati dal server.


## <a name="add-code-to-your-website"></a>Aggiungere codice al sito Web
1.  Vai ad **Amministratore** > **Area di lavoro** e seleziona **Guida all'installazione**.
1. Seleziona **Copia codice** per copiare il frammento di codice. Per impostazione predefinita, la chiave di inserimento della tua area di lavoro è incorporata nel frammento di codice.
:::image type="content" source="media/copy-code.png" alt-text="Screenshot della pagina del frammento di codice.":::
3. Aggiungi il frammento di codice copiato al tuo sito Web, vicino al <head> tag e prima di qualsiasi altro script o tag CSS.
4.  Pubblica il tuo sito Web aggiornato e attendi qualche minuto per acquisire il traffico Web in entrata.
5.  Per visualizzare i dati, seleziona la tua area di lavoro dalla commutazione area di lavoro nel riquadro di spostamento. Quindi, seleziona uno dei report nella sezione **Individua**.

## <a name="configuration-options"></a>Opzioni di configurazione

Puoi modificare le seguenti opzioni di configurazione nel frammento di codice:

- **ingestionKey**: la chiave di inserimento utilizzata per inviare eventi alla tua area di lavoro. Puoi modificare la chiave di inserimento per inviare eventi a un'area di lavoro diversa. Una chiave di inserimento è univoca per ogni area di lavoro. 
- **autoCapture**: specifica se vengono acquisite le visualizzazioni di pagina e le interazioni con il sito Web. Ha due opzioni:
    - **Visualizza**: impostare su *true* per acquisire le visualizzazioni di pagina. Le visualizzazioni di pagina vengono acquisite come *Eventi di* [visualizzazione](glossary.md#event), un tipo di [evento di base](glossary.md#base-event).
    - **clic**: impostare su *true* per acquisire le interazioni dei visitatori sul sito Web. Le interazioni vengono acquisite come *Eventi di* [azione](glossary.md#event), un tipo di [evento di base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
