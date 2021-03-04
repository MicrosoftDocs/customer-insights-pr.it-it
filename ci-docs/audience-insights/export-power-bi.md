---
title: Connettore Power BI
description: Scopri come utilizzare il connettore Dynamics 365 Customer Insights in Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477093"
---
# <a name="connector-for-power-bi-preview"></a>Connettore per Power BI(anteprima)

Crea visualizzazioni per i dati con Power BI Desktop. Genera ulteriori informazioni dettagliate e crea report con i dati cliente unificati.

## <a name="prerequisites"></a>Prerequisiti

- Disponi di profili cliente unificati.
- L'ultima versione di [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) è installata sul tuo computer. [Scopri di più su Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurare il connettore per Power BI

1. In Power BI Desktop, seleziona **File** > **Estrai dati**.

1. Seleziona **Altro** e cerca **Dynamics 365 Customer Insights**

1. Seleziona **Connetti**.

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

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>L'ambiente Customer Insights non viene visualizzato in Power BI

Ambienti che hanno più di una [relazione](relationships.md) definita tra due entità identiche in Audience Insights non saranno disponibili nel connettore di Power BI.

Puoi identificare e rimuovere le Relazioni duplicate.

1. In Audience Insights, vai a **Dati** > **Relazioni** nell'ambiente che ti manca in Power BI.
2. Identifica le relazioni duplicate:
   - Controlla se c'è più di una relazione definita tra le stesse due entità.
   - Controlla se esiste una relazione creata tra due entità che sono entrambe incluse nel processo di unificazione. Esiste una relazione implicita definita tra tutte le entità incluse nel processo di unificazione.
3. Rimuovi qualsiasi Relazione duplicata identificata.

Dopo la rimozione delle Relazioni duplicate, prova a configurare il connettore di Power BI di nuovo. L'ambiente dovrebbe essere disponibile ora.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

