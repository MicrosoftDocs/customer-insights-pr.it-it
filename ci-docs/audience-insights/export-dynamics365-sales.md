---
title: Esportare dati di Customer Insights in Dynamics 365 Sales
description: Informazioni su come configurare la connessione a Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643823"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Connettore per Dynamics 365 Sales (anteprima)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilizza i tuoi dati cliente per creare elenchi marketing, effettuare il completamento dei flussi di lavoro e inviare promozioni con Dynamics 365 Sales.

## <a name="prerequisite"></a>Prerequisito

Record del contatto [di Dynamics 365 Sales inseriti utilizzando Common Data Service](connect-power-query.md).

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
