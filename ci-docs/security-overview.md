---
title: Impostazioni di sicurezza in Customer Insights
description: Informazioni sulle impostazioni di sicurezza in Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947420"
---
# <a name="security-settings-in-customer-insights"></a>Impostazioni di sicurezza in Customer Insights

La pagina **Sicurezza** elenca le opzioni per configurare le autorizzazioni utente e le funzionalità che aiutano a rendere Dynamics 365 Customer Insights più sicuro. Solo gli amministratori possono accedere a questa pagina.

Vai a **Amministratore** > **Sicurezza** per configurare le impostazioni.

La pagina **Sicurezza** include le seguenti schede:

- [Utenti](#users-tab)
- [API](#apis-tab)
- [Collegamenti privati](#private-links-tab)
- [Insieme di credenziali delle chiavi](#key-vault-tab)
- [Accedere in modo sicuro ai dati dei clienti usando Customer Lockbox (anteprima)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Scheda Utenti

L'accesso a Customer Insights è limitato agli utenti della tua organizzazione che sono stati aggiunti all'applicazione da un amministratore. La scheda **Utenti** ti consente di gestire l'accesso degli utenti e le loro autorizzazioni. Per ulteriori informazioni, vedi [autorizzazioni utente](permissions.md).

## <a name="apis-tab"></a>Scheda API

Visualizza e gestisci le chiavi per utilizzare le [API di Customer Insights](apis.md) con i dati del tuo ambiente.

È possibile creare nuove chiavi primarie e secondarie selezionando **Rigenera primaria** o **Rigenera secondaria**. 

Per bloccare l'accesso dell'API all'ambiente, seleziona **Disabilita**. Se le API sono disabilitate, puoi selezionare **Abilita** per concedere nuovamente l'accesso.

## <a name="private-links-tab"></a>Scheda Collegamenti privati

[Collegamento privato di Azure](/azure/private-link/private-link-overview) consente a Customer Insights di connettersi al tuo account Azure Data Lake Storage su un endpoint privato nella tua rete virtuale. Per i dati in un account di archiviazione non esposto a Internet pubblico, Collegamento privato consente la connessione alla rete con restrizioni.

> [!IMPORTANT]
> Ruolo minimo richiesto per configurare una connessione con collegamento privato:
>
> - Customer Insights: Amministratore
> - Ruolo predefinito di Azure: [Collaboratore account di archiviazione](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Autorizzazioni per il ruolo di Azure personalizzato: [Microsoft.Storage/storageAccounts/read e Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

La configurazione del collegamento privato in Customer Insights è un processo in due passaggi. Innanzitutto, devi avviare la creazione di un collegamento privato da **Amministratore** > **Sicurezza** > **Collegamenti privati** in Customer Insights. Il riquadro **Aggiungi collegamento privato** elenca gli account di archiviazione del tenant per cui disponi delle autorizzazioni per la visualizzazione. Seleziona l'account di archiviazione e fornisci il consenso per creare il collegamento privato.

Dovrai quindi approvare il collegamento privato sul lato account di Data Lake Storage. Apri il collegamento visualizzato sullo schermo per approvare il nuovo collegamento privato.

## <a name="key-vault-tab"></a>Scheda Key Vault

La scheda **Key Vault** consente di collegare e gestire la tua istanza di [Azure Key Vault](/azure/key-vault/general/basic-concepts) all'ambiente.
Il key vault dedicato può essere utilizzato per mettere in scena e utilizzare i segreti nel confine di conformità di un'organizzazione. Customer Insights può usare i segreti in Azure Key Vault per [stabilire le connessioni](connections.md) a sistemi di terze parti.

Per ulteriori informazioni, vedi [Utilizzo dalla propria istanza di Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Accedere in modo sicuro ai dati dei clienti usando Customer Lockbox (anteprima)

Customer Insights usa la funzionalità Customer Lockbox di Power Platform. Customer Lockbox fornisce un'interfaccia per rivedere e approvare (o rifiutare) le richieste di accesso ai dati. Queste richieste si verificano quando è necessario l'accesso ai dati dei clienti per risolvere un caso di supporto. Per usare questa funzionalità, Customer Insights deve disporre di una connessione esistente all'ambiente Microsoft Dataverse nel tuo tenant.

Per altre informazioni su Customer Lockbox, vedi il [riepilogo](/power-platform/admin/about-lockbox#summary) di Customer Lockbox di Power Platform. L'articolo descrive anche il [flusso di lavoro](/power-platform/admin/about-lockbox#workflow) e la [configurazione](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) richiesta per abilitare Customer Lockbox.

> [!IMPORTANT]
> Gli amministratori globali per Power Platform o gli amministratori di Power Platform possono approvare le richieste Customer Lockbox emesse per Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
