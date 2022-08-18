---
title: Esportare i dati in Azure Synapse Analytics (anteprima)
description: Informazioni su come configurare la connessione ad Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259849"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Esportare i dati in Azure Synapse Analytics (anteprima)

Azure Synapse è un servizio di analisi che accelera il tempo per ottenere informazioni dettagliate tra data warehouse e sistemi di big data. Puoi inserire e utilizzare i dati di Customer Insights in [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prerequisiti

> [!NOTE]
> Assicurati di impostare tutte le **assegnazioni di ruoli** come descritto.

- In Customer Insights, il tuo account utente Azure Active Directory (AD) deve avere il [ruolo Amministratore](permissions.md#add-users).

In Azure:

- Una sottoscrizione di Azure attiva.

- Se usi un nuovo account Azure Data Lake Storage Gen2, l'[entità servizio per Customer Insights](connect-service-principal.md) dispone delle autorizzazioni **Collaboratore dati BLOB di archiviazione**. Il Data Lake Storage Gen2 **deve avere** lo [spazio dei nomi gerarchico](/azure/storage/blobs/data-lake-storage-namespace) abilitato.

- Nel gruppo di risorse in cui si trova Azure Synapse workspace, all'*entità servizio* e all'*utente Azure AD* con autorizzazioni di amministratore in Customer Insights devono essere assegnate almeno le [autorizzazioni](/azure/role-based-access-control/role-assignments-portal) di **lettore**.

- L'utente *Azure AD con autorizzazioni di amministratore in Customer Insights* dispone delle autorizzazioni **Collaboratore dati BLOB di archiviazione** nell'account Azure Data Lake Storage Gen2 in cui i dati sono contenuti e collegati ad Azure Synapse workspace. Scopri di più sull'[utilizzo del portale di Azure per assegnare un ruolo di Azure per l'accesso ai dati di BLOB e coda](/azure/storage/common/storage-auth-aad-rbac-portal) e sulle [autorizzazioni del collaboratore ai dati BLOB del servizio di archiviazione](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L'*[identità gestita da Azure Synapse workspace](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* dispone delle autorizzazioni **Collaboratore dati BLOB di archiviazione** per l'account Azure Data Lake Storage Gen2 in cui i dati sono contenuti e collegati ad Azure Synapse workspace. Scopri di più sull'[utilizzo del portale di Azure per assegnare un ruolo di Azure per l'accesso ai dati di BLOB e coda](/azure/storage/common/storage-auth-aad-rbac-portal) e sulle [autorizzazioni del collaboratore ai dati BLOB del servizio di archiviazione](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- In Azure Synapse workspace, all'*entità servizio per Customer Insights* è [assegnato il ruolo](/azure/synapse-analytics/security/how-to-set-up-access-control) **Amministratore di Synapse**.

- Se il tuo ambiente Customer Insights archivia i dati nel tuo [Azure Data Lake Storage](own-data-lake-storage.md), l'utente che imposta la connessione a Azure Synapse Analytics ha bisogno di almeno il ruolo **Lettore** predefinito nell'account Data Lake Storage. Per ulteriori informazioni, vedi [Assegnare ruoli di Azure usando il portale di Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Configurare la connessione ad Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Azure Synapse Analytics**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleziona o cerca l'abbonamento in cui desideri utilizzare i dati di Customer Insights. Non appena viene selezionato un abbonamento, puoi anche selezionare **Area di lavoro**, **Account di archiviazione**, e **Contenitore**.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)] Per configurare l'esportazione con una connessione condivisa, devi disporre di almeno le autorizzazioni **Collaboratore** in Customer Insights.

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione**, scegli una connessione dalla sezione Azure Synapse Analytics. Contatta un amministratore se non è disponibile alcuna connessione.

1. Fornisci un **nome visualizzato** riconoscibile per la tua esportazione e un **Nome del database**. L'esportazione creerà un nuovo [lake database Azure Synapse](/azure/synapse-analytics/database-designer/concepts-lake-database) nell'area di lavoro definita nella connessione.

1. Seleziona le entità che desideri esportare in Azure Synapse Analytics.
   > [!NOTE]
   > Le origini dati basate su una [cartella Common Data Model](connect-common-data-model.md) non sono supportate.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Per eseguire query sui dati esportati in Synapse Analytics, è necessario l'accesso **Lettore dati del BLOB di archiviazione** all'archiviazione di destinazione nell'area di lavoro delle esportazioni.

## <a name="update-an-export"></a>Aggiornare un'esportazione

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Modifica** nell'esportazione che vuoi aggiornare.

   - **Aggiungi** o **Rimuovi** le entità dalla selezione. Se le entità vengono rimosse dalla selezione, non vengono eliminate dal database di Synapse Analytics. Tuttavia, gli aggiornamenti futuri dei dati non aggiorneranno le entità rimosse in quel database.

   - La **modifica del nome del database** crea un nuovo database Synapse Analytics. Il database con il nome configurato in precedenza non riceverà gli aggiornamenti futuri.

[!INCLUDE [footer-include](includes/footer-banner.md)]
