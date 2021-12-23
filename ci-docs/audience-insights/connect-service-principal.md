---
title: Connettersi a un account Azure Data Lake Storage utilizzando un'entità servizio
description: Utilizza un'entità servizio di Azure per connetterti al data lake.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: faef3583337fd495e7baf40b0a208f1d9f10281a
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900263"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Connettersi a un account Azure Data Lake Storage utilizzando un'entità servizio di Azure

Questo articolo spiega come connettersi a Dynamics 365 Customer Insights con un account Azure Data Lake Storage usando un'entità servizio di Azure anziché le chiavi dell'account di archiviazione. 

Gli strumenti automatizzati che usano i servizi di Azure deve avere sempre autorizzazioni limitate. Anziché avere applicazioni che accedono come utente con privilegi completi, Azure fornisce entità servizio. È possibile utilizzare entità servizio per [aggiungere o modificare una cartella Common Data Model come origine dati](connect-common-data-model.md) in modo sicuro o [creare o aggiornare un ambiente](create-environment.md).

> [!IMPORTANT]
> - L'account Data Lake Storage che utilizzerà l'entità servizio deve avere lo [spazio dei nomi gerarchico abilitato](/azure/storage/blobs/data-lake-storage-namespace).
> - Sono necessarie le autorizzazioni di amministratore per la sottoscrizione di Azure per creare un'entità servizio.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Creare un'entità servizio di Azure per Customer Insights

Prima di creare una nuova entità servizio per Customer Insights, verifica se esiste già nell'organizzazione.

### <a name="look-for-an-existing-service-principal"></a>Cercare un'entità servizio esistente

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com) e accedi alla tua organizzazione.

2. In **Servizi di Azure**, seleziona **Azure Active Directory**.

3. Sotto **Gestisci**, seleziona **Applicazioni aziendali**.

4. Cerca l'ID dell'applicazione Microsoft:
   - Informazioni dettagliate sul gruppo di destinatari: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` con il nome `Dynamics 365 AI for Customer Insights`
   - Informazioni dettagliate sull'interazione: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` con il nome `Dynamics 365 AI for Customer Insights engagement insights`

5. Se trovi un record corrispondente, significa che l'entità servizio esiste già. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot che mostra un'entità servizio esistente.":::
   
6. Se non vengono restituiti risultati, crea una entità servizio.

>[!NOTE]
>Per sfruttare tutta la potenza di Dynamics 365 Customer Insights, ti consigliamo di aggiungere entrambe le app all'entità servizio.

### <a name="create-a-new-service-principal"></a>Creare un'entità servizio

1. Installa l'ultima versione di Azure Active Directory PowerShell for Graph. Per maggiori informazioni, vedi [Installare Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Nel PC, seleziona il tasto WINDOWS della tastiera e cerca **Windows PowerShell** e seleziona **Esegui come amministratore**.
   
   1. Nella finestra di PowerShell che si apre, immetti `Install-Module AzureAD`.

2. Creare l'entità servizio per Customer Insights con il modulo Azure AD PowerShell.

   1. Nella finestra di PowerShell, immetti `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Sostituisci l'*[ID tenant]* con l'ID effettivo del tenant in cui desideri creare l'entità servizio. Il parametro del nome dell'ambiente `AzureEnvironmentName` è facoltativo.
  
   1. Immetti `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Questo comando crea l'entità servizio per Informazioni dettagliate sul gruppo di destinatari nel tenant selezionato. 

   1. Immetti `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Questo comando crea l'entità servizio per Informazioni dettagliate sull'interazione sul tenant selezionato.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Concedere autorizzazioni all'entità servizio per accedere all'account di archiviazione

Vai al portale di Azure per concedere le autorizzazioni all'entità servizio per l'account di archiviazione che intendi usare in Informazioni dettagliate sul gruppo di destinatari.

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com) e accedi alla tua organizzazione.

1. Apri l'account di archiviazione a cui l'entità servizio per Informazioni dettagliate sul gruppo di destinatari deve avere accesso.

1. Nel riquadro di sinistra, seleziona **Controllo di accesso (IAM)**, quindi seleziona **Aggiungi** > **Aggiungi un'assegnazione di ruolo**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot che mostra il portale di Azure durante l'aggiunta di un'assegnazione di ruolo.":::

1. Nel riquadro **Aggiungi un'assegnazione di ruolo**, imposta le seguenti proprietà:
   - Ruolo: **Collaboratore dati BLOB di archiviazione**
   - Assegna accesso a: **Utente, gruppo o entità servizio**
   - Seleziona: **Dynamics 365 AI for Customer Insights** e **Informazioni dettagliate sull'interazione di Dynamics 365 AI for Customer Insights** (le due [entità servizio](#create-a-new-service-principal) create in precedenza in questa procedura)

1.  Seleziona **Salva**.

La propagazione delle modifiche può durare fino a 15 minuti.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Immetti l'ID risorsa di Azure o i dettagli della sottoscrizione di Azure nell'allegato dell'account di archiviazione di Informazioni dettagliate sul gruppo di destinatari

Puoi associare un account Data Lake Storage nelle informazioni dettagliate sul gruppo di destinatari per [archiviare i dati di output](manage-environments.md) o [usarlo come origine dati](connect-common-data-service-lake.md). Questa opzione ti consente di scegliere tra un approccio basato sulle risorse o un approccio basato sulla sottoscrizione. A seconda dell'approccio scelto, segui la procedura in una delle sezioni seguenti.

### <a name="resource-based-storage-account-connection"></a>Connessione dell'account di archiviazione basata sulle risorse

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com), accedi alla tua sottoscrizione e apri l'account di archiviazione.

1. Nel riquadro a sinistra, seleziona **Impostazioni** > **Proprietà**.

1. Copia il valore dell'ID risorsa dell'account di archiviazione.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiare il valore dell'ID risorsa dell'account di archiviazione.":::

1. In Informazioni dettagliate sul gruppo di destinatari, inserisci l'ID risorsa nel campo della risorsa visualizzato nella schermata di connessione dell'account di archiviazione.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Immettere le informazioni dell'ID risorsa dell'account di archiviazione.":::   

1. Continua con i passaggi rimanenti in Informazioni dettagliate sul gruppo di destinatari per associare l'account di archiviazione.

### <a name="subscription-based-storage-account-connection"></a>Connessione dell'account di archiviazione basata sulla sottoscrizione

1. Vai al [portale di amministrazione di Azure](https://portal.azure.com), accedi alla tua sottoscrizione e apri l'account di archiviazione.

1. Nel riquadro a sinistra, seleziona **Impostazioni** > **Proprietà**.

1. Esamina la **Sottoscrizione**, il **Gruppo di risorse** e il **Nome** dell'account di archiviazione per assicurarti di selezionare i valori corretti in Informazioni dettagliate sul gruppo di destinatari.

1. In Informazioni dettagliate sul gruppo di destinatari scegli i valori per i campi corrispondenti quando associ l'account di archiviazione.

1. Continua con i passaggi rimanenti in Informazioni dettagliate sul gruppo di destinatari per associare l'account di archiviazione.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
