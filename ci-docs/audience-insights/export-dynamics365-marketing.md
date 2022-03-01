---
title: Esportare dati di Customer Insights in Dynamics 365 Marketing
description: Scopri come configurare la connessione ed esportare in Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2c673c432f308efa289625a159de608d07f8d2b3
ms.sourcegitcommit: f988114ac7a288ccadf2db35b02dbef5cacea4d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2022
ms.locfileid: "7975129"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Utilizzare i segmenti in Dynamics 365 Marketing (anteprima)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilizza i [segmenti](segments.md) per generare campagne e contattare gruppi specifici di clienti con Dynamics 365 Marketing. Per ulteriori informazioni, vedi [Utilizzare segmenti di Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Se stai utilizzando le nuove funzionalità di Dynamics 365 Marketing per l'orchestrazione del percorso del cliente in tempo reale in un'organizzazione Dataverse, non devi creare un'esportazione standard in Dynamics 365 Marketing. I contatti e i segmenti di Informazioni dettagliate sul gruppo di destinatari sono disponibili direttamente in Dynamics 365 Marketing dopo aver collegato Marketing e Customer Insights. Prima di eliminare le esportazioni esistenti, esamina la documentazione su [come connettere Informazioni dettagliate sul gruppo di destinatari e l'orchestrazione del percorso del cliente di Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Prerequisiti per la connessione

- I record dei contatti devono essere presenti in Dynamics 365 Marketing prima di poter esportare un segmento da Customer Insights a Marketing. Ulteriori informazioni su come inserire i contatti in [Dynamics 365 Marketing utilizzando Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > L'esportazione di segmenti da Informazioni dettagliate sul gruppo di destinatari a Marketing non creerà nuovi record dei contatti nelle istanze di Marketing. I record dei contatti di Marketing devono essere inseriti in Informazioni dettagliate sul gruppo di destinatari e utilizzati come origine dati. Devono inoltre essere inclusi nell'entità Cliente unificata per mappare gli ID cliente agli ID contatto prima che i segmenti possano essere esportati.

## <a name="set-up-connection-to-marketing"></a>Configurare la connessione a Marketing

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Dynamics 365 Marketing** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Inserisci l'URL di Marketing della tua organizzazione nel campo **Indirizzo server**.

1. Nella sezione **Account amministratore del server**, seleziona **Accedi** e scegli un account di Dynamics 365 Marketing.

1. Mappa il campo ID contatto dell'entità Cliente all'ID contatto di Dynamics 365.

1. Seleziona **Salva** per completare la connessione. 

## <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [Autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi destinazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Dynamics 365 Marketing. Se non vedi il nome di questa sezione, non sono disponibili connessioni di questo tipo.

1. Scegli uno o più segmenti.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
