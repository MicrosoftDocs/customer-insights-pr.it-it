---
title: Esportare dati di Customer Insights in Dynamics 365 Sales
description: Informazioni su come configurare la connessione a Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269013"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Connettore per Dynamics 365 Sales (anteprima)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilizza i tuoi dati del cliente per creare elenchi marketing, effettuare il completamento dei flussi di lavoro e inviare promozioni con Dynamics 365 Sales.

## <a name="prerequisite"></a>Prerequisito

1. I record dei contatti devono essere presenti in Dynamics 365 Sales prima di poter esportare un segmento da Customer Insights a Sales. Ulteriori informazioni su come inserire i contatti in [Dynamics 365 Sales utilizzando Common Data Services](connect-power-query.md).

   > [!NOTE]
   > L'esportazione di segmenti da Audience Insights a Sales non creerà nuovi record dei contatti nelle istanze di Sales. I record dei contatti di Sales devono essere inseriti in Audience Insights e utilizzati come origine dati. Devono inoltre essere inclusi nell'entità Cliente unificata per mappare gli ID cliente agli ID contatto prima che i segmenti possano essere esportati.

## <a name="configure-the-connector-for-sales"></a>Configurare il connettore per Sales

1. In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.

1. In **Dynamics 365 Sales**, seleziona **Configura**.

1. Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Inserisci l'URL di Sales della tua organizzazione nel campo **Indirizzo server**.

1. Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Sales.

1. Esegui il mapping di un campo ID cliente all'ID contatto di Dynamics 365.

1. Seleziona **Avanti**.

1. Scegli uno o più segmenti.

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]