---
title: Usare l'account Azure Data Lake Storage Gen2
author: mukeshpo
description: Scopri i requisiti per utilizzare il tuo account Azure Data Lake Storage per archiviare i dati di Customer Insights.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304386"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Usare l'account Azure Data Lake Storage Gen2

Dynamics 365 Customer Insights ti dà la possibilità di memorizzare tutti i tuoi dati in [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Salvando i dati in Data Lake Storage, accetti che i dati vengano trasferiti e archiviati nella posizione geografica appropriata per quell'account di archiviazione di Azure. Per ulteriori informazioni, vedi [Centro protezione Microsoft](https://www.microsoft.com/trust-center).

Gli amministratori in Customer Insights possono [creare ambienti](create-environment.md) e [specificare l'opzione di archiviazione dati](create-environment.md#step-2-configure-data-storage) nel processo.

## <a name="prerequisites"></a>Prerequisiti

- Gli account Azure Data Lake Storage devono trovarsi nella stessa area di Azure selezionata durante la creazione dell'ambiente Customer Insights. Per conoscere l'area dell'ambiente, vai a **Amministratore** > **Sistema** > **Informazioni** in Customer Insights.
- L'account di archiviazione Data Lake Storage Gen2. Gli account di archiviazione Azure Data Lake Gen1 non sono supportati.
- L'account di Data Lake Storage deve avere lo [spazio dei nomi gerarchico abilitato](/azure/storage/blobs/data-lake-storage-namespace).
- Un contenitore denominato `customerinsights` deve esistere nell'account di archiviazione. Crearlo prima di usare il tuo Data Lake Storage in Customer Insights.
- L'amministratore che configura l'ambiente Customer Insights richiede il ruolo Collaboratore dati BLOB di archiviazione o Proprietario dati BLOB di archiviazione nell'account di archiviazione o il contenitore `customerinsights`. Per ulteriori informazioni sull'assegnazione dell'autorizzazione in un account di archiviazione, vedi [Creare un account di archiviazione](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Collegare Customer Insights all'account di archiviazione

Quando crei un nuovo ambiente, assicurati che l'account Data Lake Storage esista e che tutti i prerequisiti siano soddisfatti.

1. Nel passaggio **Archivio dati** durante la creazione dell'ambiente, imposta **Salva i dati di output** su **Azure Data Lake Storage Gen2**.
1. Scegli come **collegare l'archiviazione**. È possibile scegliere tra un'opzione basata su risorse e un'opzione basata su sottoscrizione per l'autenticazione. Per ulteriori informazioni, vedi [Connessione a un account Azure Data Lake Storage tramite un'entità servizio di Azure](connect-service-principal.md).
   - Per **Sottoscrizione di Azure**, scegli **Sottoscrizione**, **Gruppo di risorse**, e **Account di archiviazione** che contiene il contenitore `customerinsights`.
   - Per **Chiave dell'account**, fornisci il **Nome utente** e la **Chiave dell'account** per l'account Data Lake Storage. L'utilizzo di questo metodo di autenticazione implica che sei informato se la tua organizzazione ruota le chiavi. Devi [aggiornare la configurazione dell'ambiente](manage-environments.md#edit-an-existing-environment) con la nuova chiave quando viene ruotata.
1. Scegli se vuoi usare il collegamento privato di Azure per connetterti all'account di archiviazione e [creare la connessione al collegamento privato](security-overview.md#set-up-an-azure-private-link).

Quando il sistema elabora l'inserimento dati come completato, il sistema crea le cartelle corrispondenti nell'account di archiviazione. I file di dati e i file model.json sono creati e aggiunti alle cartelle in base al nome del processo.

Se si creano più ambienti di Customer Insights e si sceglie di salvare le entità di output da questi ambienti nel proprio account di archiviazione, Customer Insights crea cartelle separate per ogni ambiente con `ci_environmentID` nel contenitore.
