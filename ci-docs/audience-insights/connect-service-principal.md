---
title: Connettersi a un account Azure Data Lake Storage Gen2 con un'entità servizio
description: Utilizza un'entità servizio di Azure per Audience Insights per connetterti al tuo data lake quando lo associ a Audience Insights.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596504"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Connettersi a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure per Audience Insights

Gli strumenti automatizzati che usano i servizi di Azure deve avere sempre autorizzazioni limitate. Anziché avere applicazioni che accedono come utente con privilegi completi, Azure fornisce entità servizio. Leggi questo articolo per scoprire come connettere Audience Insights con un account di Azure Data Lake Storage Gen2 utilizzando un'entità servizio di Azure anziché chiavi di account di archiviazione. 

Puoi utilizzare l'entità servizio per [aggiungere o modificare in modo sicuro una cartella di Common Data Model come origine dati](connect-common-data-model.md) o per [creare un ambiente o aggiornarne uno esistente](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - L'account di archiviazione di Azure Data Lake Gen2 che intende usare l'entità servizio deve avere lo [spazio dei nomi gerarchico abilitato](/azure/storage/blobs/data-lake-storage-namespace).
> - Per creare l'entità servizio, sono necessarie autorizzazioni di amministratore per la sottoscrizione di Azure.

## <a name="create-azure-service-principal-for-audience-insights"></a>Creare un'entità servizio di Azure per Audience Insights

Prima di creare una nuova entità servizio per Audience Insights, controlla se esiste già nella tua organizzazione.

### <a name="look-for-an-existing-service-principal"></a>Cercare un'entità servizio esistente

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com) e accedi alla tua organizzazione.

2. Seleziona **Azure Active Directory** nei servizi di Azure.

3. Sotto **Gestisci**, seleziona **Applicazioni aziendali**.

4. Cerca l'ID applicazione di prima parte `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` di Audience Insights o il nome `Dynamics 365 AI for Customer Insights`.

5. Se trovi un record corrispondente, significa che l'entità servizio per Audience Insights esiste. Non devi quindi crearla.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot che mostra l'entità servizio esistente.":::
   
6. Se non vengono restituiti risultati, crea una entità servizio.

### <a name="create-a-new-service-principal"></a>Creare un'entità servizio

1. Installa l'ultima versione di **Azure Active Directory PowerShell per Graph**. Per ulteriori informazioni, vedi [Installare Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2).
   - Nel PC, seleziona il tasto Windows sulla tastiera e cerca **Windows PowerShell**, quindi seleziona **Esegui come amministratore**.
   
   - Nella finestra di PowerShell che si apre, immetti `Install-Module AzureAD`.

2. Crea l'entità servizio per Audience Insights con il modulo Azure AD PowerShell.
   - Nella finestra di PowerShell, immetti `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Sostituisci "l'ID tenant" con l'ID effettivo del tenant in cui desideri creare l'entità servizio. Il parametro del nome dell'ambiente `AzureEnvironmentName` è facoltativo.
  
   - Immetti `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Questo comando crea l'entità servizio per Audience Insights nel tenant selezionato.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Concedere autorizzazioni all'entità servizio per accedere all'account di archiviazione

Vai al portale di Azure per concedere le autorizzazioni all'entità servizio per l'account di archiviazione che intendi usare in Audience Insights.

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com) e accedi alla tua organizzazione.

1. Apri l'account di archiviazione a cui l'entità servizio per Audience Insight deve avere accesso.

1. Seleziona **Controllo di accesso (IAM)** nel riquadro di spostamento e seleziona **Aggiungi** > **Aggiungi assegnazione ruolo**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot che mostra il portale di Azure durante l'aggiunta di un'assegnazione di ruolo.":::
   
1. Nel riquadro **Aggiungi assegnazione ruolo**, imposta le seguenti proprietà:
   - Ruolo: *Collaboratore dati BLOB di archiviazione*
   - Assegna accesso a: *Utente, gruppo o entità servizio*
   - Seleziona: *Dynamics 365 AI for Customer Insights* (l'[entità servizio creata](#create-a-new-service-principal))

1.  Seleziona **Salva**.

La propagazione delle modifiche può durare fino a 15 minuti.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Immetti l'ID risorsa di Azure o i dettagli della sottoscrizione di Azure nell'allegato dell'account di archiviazione di Audience Insights.

Associa un account di archiviazione di Azure Data Lake in Audience Insights per [memorizzare i dati di output](manage-environments.md) o [usalo come origine dati](connect-common-data-service-lake.md). La scelta dell'opzione Azure Data Lake ti consente di scegliere tra un approccio basato sulle risorse e un approccio basato sulla sottoscrizione.

Segui i passaggi seguenti per fornire le informazioni necessarie sull'approccio selezionato.

### <a name="resource-based-storage-account-connection"></a>Connessione dell'account di archiviazione basata sulle risorse

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com), accedi alla tua sottoscrizione e apri l'account di archiviazione.

1. Vai a **Impostazioni** > **Proprietà** nel riquadro di navigazione.

1. Copia il valore dell'ID risorsa dell'account di archiviazione.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiare il valore dell'ID risorsa dell'account di archiviazione.":::

1. In Audience Insights, inserisci l'ID risorsa nel campo della risorsa visualizzato nella schermata di connessione dell'account di archiviazione.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Immettere le informazioni dell'ID risorsa dell'account di archiviazione.":::   
   
1. Continua con i passaggi rimanenti in Audience Insights per associare l'account di archiviazione.

### <a name="subscription-based-storage-account-connection"></a>Connessione dell'account di archiviazione basata sulla sottoscrizione

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com), accedi alla tua sottoscrizione e apri l'account di archiviazione.

1. Vai a **Impostazioni** > **Proprietà** nel riquadro di navigazione.

1. Esamina la **Sottoscrizione**, il **Gruppo di risorse** e il **Nome** dell'account di archiviazione per assicurarti di selezionare i valori corretti in Audience Insights.

1. In Audience Insights, scegli i valori dei campi corrispondenti quando associ l'account di archiviazione.
   
1. Continua con i passaggi rimanenti in Audience Insights per associare l'account di archiviazione.


[!INCLUDE[footer-include](../includes/footer-banner.md)]