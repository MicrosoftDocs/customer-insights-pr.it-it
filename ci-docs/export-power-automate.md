---
title: Connettore Power Automate (anteprima) | Microsoft Docs
description: Crea i flussi in Microsoft Power Automate da Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196123"
---
# <a name="power-automate-connector-preview"></a>Connettore Power Automate (anteprima)

Attiva eventi specifici che si verificano automaticamente quando i dati vengono modificati e gestisci flussi più complessi direttamente in [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitazioni note

- Un massimo di 100 chiamate ogni 60 secondi. Usa il [parametro $skip](/connectors/customerinsights/#get-items-from-an-entity) per chiamare l'endpoint API più volte.

## <a name="power-automate-triggers"></a>Trigger di Power Automate

Utilizza i trigger per creare flussi cloud e automatizzare attività ripetitive, come notifiche o azioni più avanzate. Usa i trigger quando:

- L'aggiornamento di un'origine dati non riesce.
- L'aggiornamento di un'origine dati riesce.
- In caso di superamento di una soglia per un segmento. Il trigger è limitato al superamento della soglia.
- In caso di superamento di una soglia per una misura aziendale. Solo le misure aziendali senza una dimensione sono supportate. Il trigger è limitato al superamento della soglia.
- Quando viene completato un aggiornamento pianificato completo. Questo trigger non funziona per gli aggiornamenti avviati manualmente.
- In caso di completamento dell'aggiornamento di un processo di unificazione.

[Configurare i trigger in Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Azioni di Power Automate

Il connettore di Power Automate fornisce altre azioni oltre ai trigger disponibili. Per ulteriori informazioni, vedere la [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Creare un flusso Power Automate

1. Vai ad **Amministratore** > **Connessioni**.

1. Nel riquadro **Power Automate**, seleziona **Configura**.

1. Si apre il connettore di Customer Insights (anteprima) in Power Automate. **Accedi** a  Power Automate.

1. Scegli uno dei trigger disponibili e aggiungi più passaggi al tuo nuovo flusso. Per ulteriori informazioni, vedere [Creare un flusso cloud in Power Automate](/power-automate/get-started-logic-flow).

Esempi di utilizzo dei flussi: 
- Pubblica un messaggio in un canale Microsoft Teams se un aggiornamento di un'origine dati non riesce. 
- Invia un'e-mail ai proprietari dei dati quando viene superata una soglia in un segmento.

[!INCLUDE [footer-include](includes/footer-banner.md)]
