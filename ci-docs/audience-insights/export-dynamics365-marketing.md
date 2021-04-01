---
title: Esportare dati di Customer Insights in Dynamics 365 Marketing
description: Informazioni su come configurare la connessione a Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597608"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Connettore per Dynamics 365 Marketing (anteprima)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilizza i [segmenti](segments.md) per generare campagne e contattare gruppi specifici di clienti con Dynamics 365 Marketing. Per ulteriori informazioni, vedere [Utilizzare segmenti da Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Prerequisito

- I record dei contatti devono essere presenti in Dynamics 365 Marketing prima di poter esportare un segmento da Customer Insights a Marketing. Ulteriori informazioni su come inserire i contatti in [Dynamics 365 Marketing utilizzando Common Data Services](connect-power-query.md).

  > [!NOTE]
  > L'esportazione di segmenti da Audience Insights a Marketing non creerà nuovi record dei contatti nelle istanze di Marketing. I record dei contatti di Marketing devono essere inseriti in Audience Insights e utilizzati come origine dati. Devono inoltre essere inclusi nell'entità Cliente unificata per mappare gli ID cliente agli ID contatto prima che i segmenti possano essere esportati.

## <a name="configure-the-connector-for-marketing"></a>Configurare il connettore per Marketing

1. In Audience Insights, vai a **Amministratore** > **Destinazioni di esportazione**.

1. In **Dynamics 365 Marketing**, seleziona **Configura**.

1. Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Inserisci l'URL di Marketing della tua organizzazione nel campo **Indirizzo server**.

1. Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Marketing.

1. Esegui il mapping di un campo ID cliente all'ID contatto di Dynamics 365.

1. Seleziona **Avanti**.

1. Scegli uno o più segmenti.

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]