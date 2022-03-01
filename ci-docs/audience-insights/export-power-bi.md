---
title: Connettore Power BI
description: Scopri come utilizzare il connettore Dynamics 365 Customer Insights in Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406097"
---
# <a name="connector-for-power-bi-preview"></a>Connettore per Power BI(anteprima)

Crea visualizzazioni per i dati con Power BI Desktop. Genera ulteriori informazioni dettagliate e crea report con i dati cliente unificati.

## <a name="prerequisites"></a>Prerequisiti

- Disponi di profili cliente unificati.
- L'ultima versione di [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) è installata sul tuo computer. [Scopri di più su Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurare il connettore per Power BI

1. In Power BI Desktop, seleziona **File** > **Estrai dati**.

1. Seleziona **Altro** e cerca **Dynamics 365 Customer Insights**

1. Seleziona il risultato e seleziona **Connetti**.

1. **Accedi** con lo stesso account organizzativo utilizzato per Customer Insights e seleziona **Connetti**.
   > [!NOTE]
   > L'account indicato in questo passaggio viene utilizzato per recuperare i dati da Customer Insights e non è necessario che sia lo stesso con cui hai effettuato l'accesso a Power BI. Per reimpostare l'account utilizzato per il recupero dei dati, apri Power BI e seleziona **File** > **Opzioni** > **Impostazioni** > **Impostazioni origine dati**. Nell'elenco delle origini dati, seleziona **Accesso a Dynamics 365 Customer Insights**, quindi **Deseleziona autorizzazioni**.  

1. Nella finestra di dialogo **Navigator**. viene visualizzato l'elenco di tutti gli ambienti a cui hai accesso. Espandi un ambiente e apri una qualsiasi delle cartelle (entità, misure, segmenti, arricchimenti). Ad esempio, apri la cartella **Entità** per vedere tutte le entità che puoi importare.

   ![Esplorazione connettori Power BI](media/power-bi-navigator.png "Esplorazione connettori Power BI")

1. Seleziona le caselle di controllo accanto alle entità da includere e **Carica**. Puoi selezionare più entità da più ambienti.

1. Durante il caricamento delle entità verrà visualizzata una finestra di dialogo di caricamento. Una volta caricate tutte le entità selezionate, puoi utilizzare le funzionalità di Power BI per visualizzare i dati.

## <a name="large-data-sets"></a>Set di dati di grandi dimensioni

Il connettore Customer Insights per Power BI è progettato per funzionare con set di dati che contengono fino a 1 milione di profili cliente. L'importazione di set di dati più grandi può funzionare, ma richiede molto tempo. Inoltre, potrebbe verificarsi un timeout nel processo a causa delle limitazioni di Power BI. Per ulteriori informazioni, vedere [Power BI: raccomandazioni per set di dati di grandi dimensioni](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Utilizzare un sottoinsieme di dati

Prendi in considerazione l'idea di utilizzare un sottoinsieme di dati. Ad esempio, puoi creare [segmenti](segments.md) anziché esportare tutti i record del cliente in Power BI.
