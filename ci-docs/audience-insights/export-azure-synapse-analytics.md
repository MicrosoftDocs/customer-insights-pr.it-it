---
title: Esportare i dati di Customer Insights in Azure Synapse Analytics
description: Scopri come configurare la connessione ed esportare in Azure Synapse Analytics
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977382"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Esportare i dati in Azure Synapse Analytics (anteprima)

Azure Synapse è un servizio di analisi che accelera il tempo per ottenere informazioni dettagliate tra data warehouse e sistemi di big data. Puoi inserire e utilizzare i dati di Customer Insights in [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prerequisiti

I seguenti prerequisiti devono essere soddisfatti per configurare la connessione da Customer Insights a Azure Synapse.

> [!NOTE]
> Assicurati di impostare tutte le **assegnazioni di ruoli** come descritto.  

## <a name="prerequisites-in-customer-insights"></a>Prerequisiti in Customer Insights

* Disponi di un ruolo utente **Amministratore** nell'ambiente di informazioni dettagliate sul gruppo di destinatari. Scopri di più sull'[impostazione delle autorizzazioni utente nell'ambiente di informazioni dettagliate sul gruppo di destinatari](permissions.md#assign-roles-and-permissions)

In Azure: 

- Una sottoscrizione di Azure attiva.

- Se si utilizza un nuovo account Azure Data Lake Storage Gen2, *l'entità servizio per le informazioni dettagliate sul gruppo di destinatari* ha bisogno delle autorizzazioni DI **collaboratore ai dati BLOB del servizio di archiviazione**. Scopri di più sul [collegamento a un account Azure Data Lake Storage Gen2 con l'entità servizio di Azure per le informazioni dettagliate sul gruppo di destinatari](connect-service-principal.md). Il Data Lake Storage Gen2 **deve avere** lo [spazio dei nomi gerarchico](/azure/storage/blobs/data-lake-storage-namespace) abilitato.

- Nel gruppo di risorse in cui si trova l'area di lavoro Azure Synapse, *all'entità servizio* e *all'utente per le informazioni dettagliate sul gruppo di destinatari* devono essere assegnate almeno le autorizzazioni di **lettura**. Per ulteriori informazioni, vedi [Assegnare ruoli di Azure usando il portale di Azure](/azure/role-based-access-control/role-assignments-portal).

- L'*utente* deve avere le autorizzazioni del **collaboratore ai dati BLOB del servizio di archiviazione** per l'account Azure Data Lake Storage Gen2 in cui si trovano i dati e deve essere collegato all'area di lavoro Azure Synapse. Scopri di più sull'[utilizzo del portale di Azure per assegnare un ruolo di Azure per l'accesso ai dati di BLOB e coda](/azure/storage/common/storage-auth-aad-rbac-portal) e sulle [autorizzazioni del collaboratore ai dati BLOB del servizio di archiviazione](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L'*[identità gestita dall'area di lavoro Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* deve avere le autorizzazioni del **collaboratore ai dati BLOB del servizio di archiviazione** per l'account Azure Data Lake Storage Gen2 in cui si trovano i dati e deve essere collegato all'area di lavoro Azure Synapse. Scopri di più sull'[utilizzo del portale di Azure per assegnare un ruolo di Azure per l'accesso ai dati di BLOB e coda](/azure/storage/common/storage-auth-aad-rbac-portal) e sulle [autorizzazioni del collaboratore ai dati BLOB del servizio di archiviazione](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Nell'area di lavoro Azure Synapse, *l'entità servizio per le informazioni dettagliate sul gruppo di destinatari* deve avere il ruolo **amministratore Synapse** assegnato. Per ulteriori informazioni, vedi [Come impostare il controllo degli accessi per l'area di lavoro Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configurare la connessione ed esportare in Azure Synapse

### <a name="configure-a-connection"></a>Configurare una connessione

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Azure Synapse Analytics** o seleziona **Imposta** nel riquadro **Azure Synapse Analytics** per configurare la connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo Nome visualizzato. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Se non esegui alcuna azione, l'impostazione predefinita sarà Amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleziona o cerca l'abbonamento in cui desideri utilizzare i dati di Customer Insights. Non appena viene selezionato un abbonamento, puoi anche selezionare **Area di lavoro**, **Account di archiviazione**, e **Contenitore**.

1. Per salvare la connessione seleziona **Salva**.

### <a name="configure-an-export"></a>Configurare un'esportazione

Puoi configurare questa esportazione se hai accesso a una connessione di questo tipo. Per ulteriori informazioni, vedi [autorizzazioni necessarie per configurare un'esportazione](export-destinations.md#set-up-a-new-export).

1. Vai a **Dati** > **Esportazioni**.

1. Per creare una nuova esportazione seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione **Azure Synapse Analytics**. Se non vedi il nome di questa sezione, non sono disponibili [connessioni](connections.md) di questo tipo.

1. Fornisci un **nome visualizzato** riconoscibile per la tua esportazione e un **Nome del database**.

1. Seleziona le entità che desideri esportare in Azure Synapse Analytics.

1. Seleziona **Salva**.

Il salvataggio di un'esportazione non esegue l'esportazione immediatamente.

L'esportazione viene eseguita con ogni [aggiornamento pianificato](system.md#schedule-tab). Puoi anche [esportare i dati su richiesta](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Aggiornare un'esportazione

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Modifica** nell'esportazione che vuoi aggiornare.

   - **Aggiungi** o **Rimuovi** le entità dalla selezione. Se le entità vengono rimosse dalla selezione, non vengono eliminate dal database di Synapse Analytics. Tuttavia, gli aggiornamenti futuri dei dati non aggiorneranno le entità rimosse in quel database.

   - La **modifica del nome del database** crea un nuovo database Synapse Analytics. Il database con il nome configurato in precedenza non riceverà gli aggiornamenti futuri.
