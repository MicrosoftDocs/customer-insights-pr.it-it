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
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033957"
---
# <a name="out-of-box-profile-reports"></a>Report profilo predefiniti

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un report è una raccolta di visualizzazioni di dati che consentono di comprendere il comportamento degli utenti. Se ti colleghi alle informazioni approfondite relative all'interattività di Customer Insights, tali informazioni possono mostrare un report con dati sui profili dei clienti unificati. Questo report include il numero di profili di cui disponi, raggruppati per sesso, età e posizione geografica.

## <a name="prerequisites"></a>Prerequisiti

L'ambiente delle informazioni dettagliate relative all'interattività deve archiviare i dati in un account Azure Data Lake Storage gestito dal cliente.

Se stai utilizzando una versione di prova della funzionalità relativa a Informazioni dettagliate sul gruppo di destinatari o un ambiente in un data lake gestito da Customer Insights, [contattaci](https://go.microsoft.com/fwlink/?linkid=2145734) per ricevere assistenza.  


## <a name="enable-the-customer-profile-report"></a>Abilitare il report sul profilo del cliente

Un amministratore dell'ambiente deve [creare una connessione a Informazioni dettagliate sul gruppo di destinatari](configure-connections.md).

Dopo aver specificato i dettagli della connessione, l'amministratore può concedere l'accesso ad altre persone dell'organizzazione per visualizzare il report. L'amministratore dell'ambiente che configura la connessione ha accesso automaticamente al report. 

Dopo aver completato la connessione, la funzionalità **Profili** sarà disponibile nel riquadro di spostamento a sinistra. 

- Vai a **Individua** > **Profili** per vedere il report.

Il report **Profili** contiene visualizzazioni su sesso, età e posizione geografica dei profili dei clienti collegati.

:::image type="content" source="media/customer-profiles.png" alt-text="Report profilo cliente.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]