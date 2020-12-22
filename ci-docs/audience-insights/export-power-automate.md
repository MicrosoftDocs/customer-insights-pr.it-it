---
title: Connettore Power Automate | Microsoft Docs
description: Crea flussi in Microsoft Power Automate da Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406092"
---
# <a name="power-automate-connector-preview"></a>Connettore Power Automate (anteprima)

Attiva eventi specifici che si verificano automaticamente quando i dati vengono modificati e gestisci flussi più complessi direttamente in [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Trigger di Power Automate

Puoi utilizzare una varietà di trigger che consentono di creare flussi per automatizzare attività ripetitive, come notifiche o azioni più avanzate. 

- Trigger in caso di errore di aggiornamento dell'origine dati. 
- Trigger in caso di completamento dell'aggiornamento dell'origine dati.
- Trigger in caso di superamento di una soglia su un segmento. Il trigger è limitato al superamento della soglia.
- Trigger in caso di superamento di una soglia su una misura aziendale. Il trigger è limitato al superamento della soglia.
- Trigger in caso di completamento di un aggiornamento completo (origini dati, segmenti, misure...).
- Trigger in caso di completamento di un aggiornamento del processo di unificazione (mappa, corrispondenza, unione).

[Configurare i trigger in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Azioni di Power Automate
Il connettore di Power Automate fornisce altre azioni oltre ai trigger disponibili. Per ulteriori informazioni, vedere la [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Creare un flusso Power Automate in Audience Insights

1. In Audience Insights, vai a **Amministratore** > **Sistema**.

1. Nella pagina **Sistema** seleziona la scheda **Stato**.

1. Nella sezione **Origini dati**, seleziona **Flussi** e seleziona **Crea un flusso** dall'elenco a discesa.
   > [!div class="mx-imgBorder"]
   > ![Connettore Power Automate che mostra l'azione Crea un flusso](media/power-automate-connector-create-flow.png "Connettore Power Automate che mostra l'azione Crea un flusso")

1. In Power Automate, seleziona uno dei trigger disponibili per creare il flusso preferito. Se stai creando il tuo primo flusso, devi prima autenticarti con il connettore Power Automate.
