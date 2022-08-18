---
title: Configurare le impostazioni di sicurezza
description: Informazioni sulle impostazioni di sicurezza in Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246067"
---
# <a name="configure-security-settings"></a>Configurare le impostazioni di sicurezza

Gestisci le chiavi API, accedi ai dati dei clienti e configura un collegamento privato di Azure.

## <a name="manage-api-keys"></a>Gestire le chiavi API

Visualizza e gestisci le chiavi per utilizzare le [API di Customer Insights](apis.md) con i dati nel tuo ambiente.

1. Vai a **Sistema** > **Sicurezza** e seleziona la scheda **API**.

1. Se l'accesso API all'ambiente non è stato configurato, seleziona **Abilita**. Oppure, per bloccare l'accesso API all'ambiente, seleziona **Disabilita** e conferma.

1. Gestisci le chiavi API primarie e secondarie:

   1. Per mostrare la chiave API primaria o secondaria, seleziona il simbolo **Mostra**.

   1. Per copiare la chiave API primaria o secondaria, seleziona il simbolo **Copia**.

   1. Per creare nuove chiavi API primarie o secondarie, seleziona **Rigenera primaria** o **Rigenera secondaria**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Accedere in modo sicuro ai dati dei clienti usando Customer Lockbox (anteprima)

Customer Insights usa la funzionalità Customer Lockbox di Power Platform. Customer Lockbox fornisce un'interfaccia per rivedere e approvare (o rifiutare) le richieste di accesso ai dati. Queste richieste si verificano quando è necessario l'accesso ai dati dei clienti per risolvere un caso di supporto. Per usare questa funzionalità, Customer Insights deve disporre di una connessione esistente all'ambiente Microsoft Dataverse nel tuo tenant.

Per altre informazioni su Customer Lockbox, vedi il [riepilogo](/power-platform/admin/about-lockbox#summary) di Customer Lockbox di Power Platform. L'articolo descrive anche il [flusso di lavoro](/power-platform/admin/about-lockbox#workflow) e la [configurazione](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) richiesta per abilitare Customer Lockbox.

> [!IMPORTANT]
> Gli amministratori globali per Power Platform o gli amministratori di Power Platform possono approvare le richieste Customer Lockbox emesse per Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Configurare un collegamento privato di Azure

[Collegamento privato di Azure](/azure/private-link/private-link-overview) consente a Customer Insights di connettersi al tuo account Azure Data Lake Storage su un endpoint privato nella tua rete virtuale. Per i dati in un account di archiviazione non esposto a Internet pubblico, Collegamento privato consente la connessione alla rete con restrizioni.

> [!IMPORTANT]
> Ruolo minimo richiesto per configurare una connessione con collegamento privato:
>
> - Customer Insights: Amministratore
> - Ruolo predefinito di Azure: [Collaboratore account di archiviazione](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Autorizzazioni per il ruolo di Azure personalizzato: [Microsoft.Storage/storageAccounts/read e Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. In Customer Insights, vai a **Amministratore** > **Sicurezza** e seleziona la scheda **Collegamenti privati**.

1. Seleziona **Aggiungi collegamento privato**.

   Il riquadro **Aggiungi collegamento privato** elenca gli account di archiviazione del tenant per cui disponi delle autorizzazioni per la visualizzazione.

1. Seleziona la sottoscrizione, il gruppo di risorse e l'account di archiviazione.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Salva**.

1. Vai al tuo account Data Lake Storage e apri il collegamento visualizzato sullo schermo.

1. Approva il collegamento privato.


[!INCLUDE [footer-include](includes/footer-banner.md)]
