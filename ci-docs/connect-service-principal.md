---
title: Connettersi a un account Azure Data Lake Storage utilizzando un'entità servizio di Azure
description: Utilizza un'entità servizio di Azure per connetterti al data lake.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304202"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Connettersi a un account Azure Data Lake Storage utilizzando un'entità servizio di Azure

Dynamics 365 Customer Insights fornisce un'opzione per connettersi a un account Azure Data Lake Storage utilizzando un'entità servizio di Azure anziché le chiavi dell'account di archiviazione.

Gli strumenti automatizzati che usano i servizi di Azure devono avere autorizzazioni limitate. Anziché avere applicazioni che accedono come utente con privilegi completi, Azure fornisce entità servizio. Utilizzare entità di servizio per [aggiungere o modificare una cartella Common Data Model come origine dati](connect-common-data-model.md) in modo sicuro o [creare o aggiornare un ambiente](create-environment.md).

## <a name="prerequisites"></a>Prerequisiti

- L'account Data Lake Storage che utilizzerà l'entità servizio deve essere Gen2. Gli account di archiviazione Azure Data Lake Gen1 non sono supportati.
- L'account Data Lake Storage ha [spazio dei nomi gerarchico abilitato](/azure/storage/blobs/data-lake-storage-namespace).
- Le autorizzazioni di amministratore per il tenant di Azure, se devi creare una nuova entità servizio.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Creare un'entità servizio di Azure per Customer Insights

Prima di creare una nuova entità servizio per Customer Insights, verifica se esiste già nell'organizzazione. Nella maggior parte dei casi, esiste già.

### <a name="look-for-an-existing-service-principal"></a>Cercare un'entità servizio esistente

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com) e accedi alla tua organizzazione.

2. In **Servizi di Azure**, seleziona **Azure Active Directory**.

3. Sotto **Gestisci**, seleziona **Applicazione Microsoft**.

4. Aggiungi un filtro per **L'ID applicazione inizia con** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` oppure cerca il nome `Dynamics 365 AI for Customer Insights`.

5. Se trovi un record corrispondente, significa che l'entità servizio esiste già. [Concedere autorizzazioni](#grant-permissions-to-the-service-principal-to-access-the-storage-account) per l'entità servizio per accedere all'account di archiviazione.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot che mostra un'entità servizio esistente.":::

6. Se non vengono restituiti risultati, [crea una nuova entità servizio](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Creare un'entità servizio

1. Installa l'ultima versione di Azure Active Directory PowerShell for Graph. Per maggiori informazioni, vedi [Installare Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Sul PC, premi il tasto Windows sulla tastiera e cerca **Windows PowerShell** e seleziona **Esegui come amministratore**.

   1. Nella finestra di PowerShell che si apre, immetti `Install-Module AzureAD`.

2. Creare l'entità servizio per Customer Insights con il modulo Azure AD PowerShell.

   1. Nella finestra di PowerShell, immetti `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Sostituisci *[il tuo ID directory]* con l'ID directory effettivo della sottoscrizione di Azure in cui vuoi creare l'entità servizio. Il parametro del nome dell'ambiente `AzureEnvironmentName` è facoltativo.
  
   1. Immetti `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Questo comando crea l'entità servizio per Customer Insights nella sottoscrizione di Azure selezionata.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Concedere autorizzazioni all'entità servizio per accedere all'account di archiviazione

Per concedere le autorizzazioni all'entità servizio per l'account di archiviazione che si desidera utilizzare in Customer Insights, è necessario assegnare uno dei seguenti ruoli all'account di archiviazione o al contenitore:

|Credenziali|Requisiti|
|----------|------------|
|Utente attualmente connesso|**Ruolo**: Lettore dati del BLOB di archiviazione, Collaboratore BLOB di archiviazione o Proprietario BLOB di archiviazione.<br>**Livello**: le autorizzazioni concesse per l'account di archiviazione o il contenitore.</br>|
|Entità servizio Customer Insights -<br>Utilizzo di Azure Data Lake Storage come origine dati</br>|Opzione 1<ul><li>**Ruolo**: Lettore dati del BLOB di archiviazione, Collaboratore dati BLOB di archiviazione o Proprietario dati BLOB di archiviazione.</li><li>**Livello**: le autorizzazioni concesse per l'account di archiviazione.</li></ul>Opzione 2 *(senza condividere l'accesso dell'entità servizio all'account di archiviazione)*<ul><li>**Ruolo1**: Lettore dati del BLOB di archiviazione, Collaboratore dati BLOB di archiviazione o Proprietario dati BLOB di archiviazione.</li><li>**Livello**: le autorizzazioni concesse per il contenitore.</li><li>**Ruolo 2**: Delegante dati BLOB di archiviazione.</li><li>**Livello**: le autorizzazioni concesse per l'account di archiviazione.</li></ul>|
|Entità servizio Customer Insights - <br>Utilizzo di Azure Data Lake Storage come output o destinazione</br>|Opzione 1<ul><li>**Ruolo**: Collaboratore dati BLOB di archiviazione o Proprietario BLOB di archiviazione.</li><li>**Livello**: le autorizzazioni concesse per l'account di archiviazione.</li></ul>Opzione 2 *(senza condividere l'accesso dell'entità servizio all'account di archiviazione)*<ul><li>**Ruolo**: Collaboratore dati BLOB di archiviazione o Proprietario BLOB di archiviazione.</li><li>**Livello**: le autorizzazioni concesse per il contenitore.</li><li>**Ruolo 2**: Delegante BLOB di archiviazione.</li><li>**Livello**: le autorizzazioni concesse per l'account di archiviazione.</li></ul>|

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com) e accedi alla tua organizzazione.

1. Apri l'account di archiviazione a cui vuoi che l'entità servizio per Customer Insights abbia accesso.

1. Nel riquadro di sinistra, seleziona **Controllo di accesso (IAM)**, quindi seleziona **Aggiungi** > **Aggiungi un'assegnazione di ruolo**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot che mostra il portale di Azure durante l'aggiunta di un'assegnazione di ruolo.":::

1. Nel riquadro **Aggiungi un'assegnazione di ruolo**, imposta le seguenti proprietà:
   - **Ruolo**: Lettore dati del BLOB di archiviazione, Collaboratore BLOB di archiviazione o Proprietario BLOB di archiviazione in base alle credenziali elencate sopra.
   - **Assegna accesso a**: **Utente, gruppo o entità servizio**
   - **Seleziona** i membri: **Dynamics 365 AI per Customer Insights** (l'[entità servizio](#create-a-new-service-principal) che hai cercato in precedenza in questa procedura)

1. Seleziona **Rivedi + assegna**.

La propagazione delle modifiche può durare fino a 15 minuti.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Immetti l'ID risorsa di Azure o i dettagli della sottoscrizione di Azure nel collegamento dell'account di archiviazione a Customer Insights

Associare un account Data Lake Storage in Customer Insights sul gruppo di destinatari per [memorizzare i dati di output](manage-environments.md) o [usarlo come origine dati](connect-dataverse-managed-lake.md). Scegliere tra un approccio [basato sulle risorse](#resource-based-storage-account-connection) o [basato sulla sottoscrizione](#subscription-based-storage-account-connection) e seguire questi passaggi.

### <a name="resource-based-storage-account-connection"></a>Connessione dell'account di archiviazione basata sulle risorse

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com), accedi alla tua sottoscrizione e apri l'account di archiviazione.

1. Nel riquadro sinistro, vai a **Impostazioni** > **Endpoint**.

1. Copia il valore dell'ID risorsa dell'account di archiviazione.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiare il valore dell'ID risorsa dell'account di archiviazione.":::

1. In Customer Insights, inserisci l'ID risorsa nel campo della risorsa visualizzato nella schermata di connessione dell'account di archiviazione.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Immettere le informazioni dell'ID risorsa dell'account di archiviazione.":::

1. Continua con i passaggi rimanenti in Customer Insights per collegare l'account di archiviazione.

### <a name="subscription-based-storage-account-connection"></a>Connessione dell'account di archiviazione basata sulla sottoscrizione

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com), accedi alla tua sottoscrizione e apri l'account di archiviazione.

1. Nel riquadro a sinistra, seleziona **Impostazioni** > **Proprietà**.

1. Rivedi i campi **Sottoscrizione**, **Gruppo di risorse**, e **Nome** dell'account di archiviazione per assicurarti di selezionare i valori corretti in Customer Insights.

1. In Customer Insights, scegli i valori per i campi corrispondenti quando colleghi l'account di archiviazione.

1. Continua con i passaggi rimanenti in Customer Insights per collegare l'account di archiviazione.

[!INCLUDE [footer-include](includes/footer-banner.md)]
