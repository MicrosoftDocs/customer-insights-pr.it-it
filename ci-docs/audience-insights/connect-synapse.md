---
title: Inserire dati da Azure Synapse Analytics
description: Usa un database in Azure Synapse come origine dati in Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356024"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Collegare un'origine dati Azure Synapse (anteprima)

Azure Synapse Analytics è un servizio di analisi aziendale che accelera il tempo per ottenere informazioni dettagliate tra i data warehouse e i sistemi di big data. Azure Synapse Analytics riunisce il meglio delle tecnologie SQL utilizzate nel data warehousing aziendale, le tecnologie Spark utilizzate per i big data, Esplora dati per l'analisi di log e serie temporali, Pipeline per l'integrazione dei dati e ETL/ELT e una profonda integrazione con altri servizi di Azure come Power BI, Cosmos DB e AzureML.

Per ulteriori informazioni, vedi [Panoramica di Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prerequisiti

I seguenti prerequisiti devono essere soddisfatti per configurare la connessione da Customer Insights a Azure Synapse.

> [!IMPORTANT]
> Assicurati di impostare tutte le **assegnazioni di ruoli** come descritto.  

## <a name="prerequisites-in-customer-insights"></a>Prerequisiti in Customer Insights

* Hai un ruolo di **amministratore** in Customer Insights. Scopri di più sui [permessi degli utenti in approfondimenti sul pubblico](permissions.md#assign-roles-and-permissions).

In Azure: 

- Una sottoscrizione di Azure attiva.

- Se si utilizza un nuovo account Azure Data Lake Storage Gen2, *l'entità servizio per Informazioni dettagliate sul gruppo di destinatari* ha bisogno delle autorizzazioni DI **collaboratore ai dati BLOB del servizio di archiviazione**. Scopri di più sul [collegamento ad un Azure Data Lake Storage con un'entità servizio per informazioni dettagliate sul gruppo di destinatari](connect-service-principal.md). Il Data Lake Storage Gen2 **deve avere** lo [spazio dei nomi gerarchico](/azure/storage/blobs/data-lake-storage-namespace) abilitato.

- Nel gruppo di risorse in cui si trova l'area di lavoro Azure Synapse, *all'entità servizio* e *all'utente per Informazioni dettagliate sul gruppo di destinatari* devono essere assegnate almeno le autorizzazioni di **lettura**. Per ulteriori informazioni, vedi [Assegnare ruoli di Azure usando il portale di Azure](/azure/role-based-access-control/role-assignments-portal).

- L'*utente* deve avere le autorizzazioni del **collaboratore ai dati BLOB del servizio di archiviazione** per l'account Azure Data Lake Storage Gen2 in cui si trovano i dati e deve essere collegato all'area di lavoro Azure Synapse. Scopri di più sull'[utilizzo del portale di Azure per assegnare un ruolo di Azure per l'accesso ai dati di BLOB e coda](/azure/storage/common/storage-auth-aad-rbac-portal) e sulle [autorizzazioni del collaboratore ai dati BLOB del servizio di archiviazione](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L'*[identità gestita dall'area di lavoro Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* deve avere le autorizzazioni del **collaboratore ai dati BLOB del servizio di archiviazione** per l'account Azure Data Lake Storage Gen2 in cui si trovano i dati e deve essere collegato all'area di lavoro Azure Synapse. Scopri di più sull'[utilizzo del portale di Azure per assegnare un ruolo di Azure per l'accesso ai dati di BLOB e coda](/azure/storage/common/storage-auth-aad-rbac-portal) e sulle [autorizzazioni del collaboratore ai dati BLOB del servizio di archiviazione](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Nell'area di lavoro Azure Synapse, *l'entità servizio per Informazioni dettagliate sul gruppo di destinatari* deve avere il ruolo **amministratore Synapse** assegnato. Per ulteriori informazioni, vedi [Come impostare il controllo degli accessi per l'area di lavoro Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Connettersi ai database data lake in Azure Synapse Analytics

1. Vai a **Dati** > **Origini dati**.

1. Seleziona **Aggiungi origine dati**.

1. Scegli il metodo **Azure Synapse Analytics (Anteprima)**.

1. Fornisci un **Nome** per l'origine dati e seleziona **Avanti** per creare l'origine dati. 

1. Scegli una [connessione disponibile](connections.md) ad Azure Synapse Analytics o creane una nuova.

1. Scegli un **Lake Database** dall'area di lavoro connessa nella connessione Azure Synapse Analytics selezionata e selezionaa **Avanti**.

1. Seleziona le entità da inserire dal database connesso. 

1. Facoltativamente, scegli le entità di dati su cui consentire la profilazione dei dati. 

1. Seleziona **Salva** per applicare la selezione e avviare l'inserimento dei dati dalla tua origine dati appena creata e collegata alle tabelle del Lake database in Azure Synapse Analytics.
