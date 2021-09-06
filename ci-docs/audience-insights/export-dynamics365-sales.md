---
title: Esportare dati di Customer Insights in Dynamics 365 Sales
description: Scopri come configurare la connessione ed esportare in Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8a0654ac062e41ef7eb52a34b1ae169e28b389f86875eead774422fef60f2232
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031535"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Utilizzare i segmenti in Dynamics 365 Sales (anteprima)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilizza i tuoi dati del cliente per creare elenchi marketing, effettuare il completamento dei flussi di lavoro e inviare promozioni con Dynamics 365 Sales.

## <a name="prerequisite-for-connection"></a>Prerequisiti per la connessione

1. I record dei contatti devono essere presenti in Dynamics 365 Sales prima di poter esportare un segmento da Customer Insights a Sales. Ulteriori informazioni su come inserire i contatti in [Dynamics 365 Sales utilizzando Microsoft Dataverse](connect-power-query.md).

   > [!NOTE]
   > L'esportazione di segmenti da Informazioni dettagliate sul gruppo di destinatari a Sales non creerà nuovi record dei contatti nelle istanze di Sales. I record dei contatti di Sales devono essere inseriti in Informazioni dettagliate sul gruppo di destinatari e utilizzati come origine dati. Devono inoltre essere inclusi nell'entità Cliente unificata per mappare gli ID cliente agli ID contatto prima che i segmenti possano essere esportati.

## <a name="set-up-the-connection-to-sales"></a>Configurare la connessione a Sales

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Dynamics 365 Sales** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Inserisci l'URL di Sales della tua organizzazione nel campo **Indirizzo server**.

1. Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Sales.

1. Esegui il mapping di un campo ID cliente all'ID contatto di Dynamics 365.

1. Seleziona **Salva** per completare la connessione. 

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Dynamics 365 Sales. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Scegli uno o più segmenti.

1. Seleziona **Salva**

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
