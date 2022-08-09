---
title: Esportare segmenti in Dynamics 365 Marketing (anteprima)
description: Scopri come configurare la connessione ed esportare in Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196629"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Esportare segmenti in Dynamics 365 Marketing (anteprima)

Utilizza i [segmenti](segments.md) per generare campagne e contattare gruppi specifici di clienti con [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Se stai utilizzando le nuove funzionalità di Dynamics 365 Marketing per l'orchestrazione del percorso del cliente in tempo reale in un'organizzazione Dataverse, non devi creare un'esportazione standard in Dynamics 365 Marketing. I contatti e i segmenti di Customer Insights sono disponibili direttamente in Dynamics 365 Marketing dopo aver connesso Marketing e Customer Insights. Prima di eliminare le esportazioni esistenti, rivedi la documentazione su [come connettere Customer Insights e l'orchestrazione del percorso del cliente di Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Prerequisito

I record dei contatti devono essere presenti in Dynamics 365 Marketing prima di poter esportare un segmento da Customer Insights a Marketing. Ulteriori informazioni su come inserire i contatti in [Dynamics 365 Marketing utilizzando Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> L'esportazione di segmenti da Customer Insights a Marketing non creerà nuovi record di contatto nelle istanze di Marketing. I record dei contatti di Marketing devono essere inseriti in Customer Insights e utilizzati come origine dati. Devono inoltre essere inclusi nell'entità Cliente unificata per mappare gli ID cliente agli ID contatto prima che i segmenti possano essere esportati.

## <a name="set-up-connection-to-marketing"></a>Configurare la connessione a Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Dynamics 365 Marketing**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Inserisci l'URL di Marketing della tua organizzazione nel campo **Indirizzo server**.

1. Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Marketing.

1. Mappa il campo ID contatto dell'entità Cliente all'ID contatto di Dynamics 365.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Dynamics 365 Marketing. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Seleziona il campo ID contatto dell'entità Cliente che corrisponde all'ID contatto di Dynamics 365.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
