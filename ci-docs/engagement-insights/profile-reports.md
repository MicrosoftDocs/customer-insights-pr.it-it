---
title: Abilitare report profilo predefiniti
description: Come creare report profilo predefiniti raggruppati per sesso, età e paese o area di origine.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486125"
---
# <a name="out-of-box-profile-reports"></a>Report profilo predefiniti

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un report è una raccolta di visualizzazioni di dati che consentono di comprendere il comportamento degli utenti. Se ti colleghi alle informazioni approfondite relative all'interattività di Customer Insights, tali informazioni possono mostrare un report con dati sui profili dei clienti unificati. Questo report include il numero di profili di cui disponi, raggruppati per sesso, età e posizione geografica.

## <a name="prerequisites"></a>Prerequisiti

L'ambiente delle informazioni dettagliate relative all'interattività deve archiviare i dati in un account Azure Data Lake Storage gestito dal cliente.

Se stai utilizzando una versione di prova della funzionalità relativa a Informazioni dettagliate sul gruppo di destinatari o un ambiente in un data lake gestito da Customer Insights, [contattaci](https://go.microsoft.com/fwlink/?linkid=2145734) per ricevere assistenza.  


## <a name="enable-the-customer-profile-report"></a>Abilitare il report sul profilo del cliente

Un amministratore di ambiente deve [collegare le informazioni dettagliate sull'interazione e le informazioni dettagliate sul gruppo di destinatari](integrate-audience-insights-engagement-insights.md).

Dopo aver specificato i dettagli della connessione, l'amministratore può concedere l'accesso ad altre persone dell'organizzazione per visualizzare il report. L'amministratore dell'ambiente che configura la connessione ha accesso automaticamente al report. 

Dopo aver completato la connessione, la funzionalità **Profili** sarà disponibile nel riquadro di spostamento a sinistra. 

- Vai a **Individua** > **Profili** per vedere il report.

Il report **Profili** contiene visualizzazioni su sesso, età e posizione geografica dei profili dei clienti collegati.

:::image type="content" source="media/customer-profiles.png" alt-text="Report profilo cliente.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]