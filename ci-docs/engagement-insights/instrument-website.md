---
title: Aggiungere codice al sito Web
description: Come aggiungere un frammento di codice per acquisire eventi di Dynamics 365 Customer Insights sul tuo sito Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231027"
---
# <a name="install-the-web-sdk-on-a-website"></a>Installazione dell'SDK Web su un sito Web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Questo articolo descrive in che modo un amministratore installa il kit di strumenti di sviluppo software (SDK) su un sito Web. Inizierai a vedere gli eventi nella tua area di lavoro poco dopo aver configurato il tuo sito Web. Per ulteriori informazioni, vedi [Gestire aree di lavoro e ambienti](manage-environments-workspaces.md). Per acquisire eventi nelle app mobili, vedi [Panoramica delle risorse per gli sviluppatori](developer-resources.md).


### <a name="prerequisites"></a>Prerequisiti

* Devi disporre delle autorizzazioni di amministratore per l'area di lavoro per archiviare i dati.
* Il tuo sito Web o progetto deve essere ospitato online per inviare i dati dell'impegno. I dati inviati da un file locale non saranno accettati dal server.


## <a name="add-web-sdk-to-your-website"></a>Aggiunta di SDK Web al tuo sito Web

Vai ad **Amministratore** > **Area di lavoro** e seleziona **Guida all'installazione**. Sono disponibili due opzioni per l'installazione dell'SDK Web. La prima prevede l'uso di un collegamento per il download e la seconda nell'installazione di un pacchetto Gestione pacchetti del nodo (NPM).

### <a name="option-1-using-the-download-link"></a>Opzione 1: uso del collegamento per il download

1. Seleziona **Copia codice** per copiare il frammento di codice. Per impostazione predefinita, la chiave di inserimento della tua area di lavoro è incorporata nel frammento di codice.
  :::image type="content" source="media/copy-code.png" alt-text="Screenshot della pagina del frammento di codice.":::

1. Aggiungi il codice copiato al tuo sito Web, vicino al <head> tag e prima di qualsiasi altro script o tag CSS.
1. Pubblica il tuo sito Web aggiornato e attendi qualche minuto per acquisire il traffico Web in entrata.
1. Per visualizzare i dati, seleziona la tua area di lavoro dalla commutazione area di lavoro nel riquadro di spostamento. Quindi, seleziona uno dei report nella sezione **Individua**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Opzione 2: uso del pacchetto NPM (consigliato per app Web basate su JavaScript)

1. Vai alla [pagina Web di NPM](https://www.npmjs.com/package/engagementinsights-web) e segui le istruzioni per installare e configurare il pacchetto Web NPM SDK.
1. Pubblica il tuo sito Web aggiornato e attendi qualche minuto per acquisire il traffico Web in entrata.
1. Per visualizzare i dati, seleziona la tua area di lavoro dalla commutazione area di lavoro nel riquadro di spostamento. Quindi, seleziona uno dei report nella sezione **Individua**.

## <a name="configuration-options"></a>Opzioni di configurazione

Puoi modificare le seguenti opzioni di configurazione nel frammento di codice:

- **ingestionKey**: la chiave di inserimento utilizzata per inviare eventi alla tua area di lavoro. Puoi modificare la chiave di inserimento per inviare eventi a un'area di lavoro diversa. Una chiave di inserimento è univoca per ogni area di lavoro.
- **autoCapture**: specifica se vengono acquisite le visualizzazioni di pagina e le interazioni con il sito Web. Ha due opzioni:
    - **Visualizza**: impostare su *true* per acquisire le visualizzazioni di pagina. Le visualizzazioni di pagina vengono acquisite come *Eventi di* [visualizzazione](glossary.md#event), un tipo di [evento di base](glossary.md#base-event).
    - **clic**: impostare su *true* per acquisire le interazioni dei visitatori sul sito Web. Le interazioni vengono acquisite come *Eventi di* [azione](glossary.md#event), un tipo di [evento di base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
