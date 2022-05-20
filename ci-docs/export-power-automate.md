---
title: Connettore Power Automate | Microsoft Docs
description: Crea i flussi in Microsoft Power Automate da Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741184"
---
# <a name="power-automate-connector-preview"></a>Connettore Power Automate (anteprima)

Attiva eventi specifici che si verificano automaticamente quando i dati vengono modificati e gestisci flussi più complessi direttamente in [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitazioni note

- Puoi fare un massimo di 100 chiamate ogni 60 secondi. Puoi chiamare l'endpoint dell'API più volte utilizzando il parametro $skip. [Ulteriori informazioni sul parametro $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Trigger di Power Automate

Utilizza i trigger per creare flussi cloud e automatizzare attività ripetitive, come notifiche o azioni più avanzate.

- Trigger in caso di errore di aggiornamento dell'origine dati.
- Trigger in caso di completamento dell'aggiornamento dell'origine dati.
- Trigger in caso di superamento di una soglia su un segmento. Il trigger è limitato al superamento della soglia.
- Trigger in caso di superamento di una soglia su una misura aziendale. Solo le misure aziendali senza una dimensione sono supportate. Il trigger è limitato al superamento della soglia.
- Trigger in caso di esecuzione di un aggiornamento completo (origini dati, segmenti, misure...).
- Completamento di un aggiornamento del processo di unificazione.

[Configurare i trigger in Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Azioni di Power Automate

Il connettore di Power Automate fornisce altre azioni oltre ai trigger disponibili. Per ulteriori informazioni, vedere la [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Creare un flusso Power Automate

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. Nel riquadro **Power Automate**, seleziona **Configura**.

1. Si apre il connettore di Customer Insights (anteprima) in Power Automate. **Accedi** a  Power Automate.

1. Scegli uno dei trigger disponibili e aggiungi più passaggi al tuo nuovo flusso. Per ulteriori informazioni, vedere [Creare un flusso cloud in Power Automate](/power-automate/get-started-logic-flow).

Esempi di utilizzo dei flussi: 
- Pubblica un messaggio in un canale Microsoft Teams se un aggiornamento di un'origine dati non riesce. 
- Invia un'e-mail ai proprietari dei dati quando viene superata una soglia in un segmento.



[!INCLUDE [footer-include](includes/footer-banner.md)]
