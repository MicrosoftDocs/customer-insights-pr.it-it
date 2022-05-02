---
title: Impostazioni di sicurezza in Dynamics 365 Customer Insights
description: Informazioni sulle impostazioni di sicurezza in Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653740"
---
# <a name="security-overview-page"></a>Pagina della panoramica della sicurezza

La pagina **Sicurezza** elenca le opzioni per configurare le autorizzazioni utente e le funzionalità che aiutano a rendere Dynamics 365 Customer Insights più sicuro. Solo gli amministratori possono accedere a questa pagina. 

Vai a **Amministratore** > **Sicurezza** per configurare le impostazioni.

La pagina **Sicurezza** include le seguenti schede:
- [Utenti](#users-tab)
- [API](#apis-tab)
- [Insieme di credenziali delle chiavi](#key-vault-tab)

## <a name="users-tab"></a>Scheda Utenti

L'accesso a Customer Insights è limitato agli utenti della tua organizzazione che sono stati aggiunti all'applicazione da un amministratore. La scheda **Utenti** ti consente di gestire l'accesso degli utenti e le loro autorizzazioni. Per ulteriori informazioni, vedi [autorizzazioni utente](permissions.md).

## <a name="apis-tab"></a>Scheda API

Visualizza e gestisci le chiavi per utilizzare le [API di Customer Insights](apis.md) con i dati del tuo ambiente.

È possibile creare nuove chiavi primarie e secondarie selezionando **Rigenera primaria** o **Rigenera secondaria**. 

Per bloccare l'accesso dell'API all'ambiente, seleziona **Disabilita**. Se le API sono disabilitate, puoi selezionare **Abilita** per concedere nuovamente l'accesso.

## <a name="key-vault-tab"></a>Scheda Key Vault

La scheda **Key Vault** consente di collegare e gestire la tua istanza di [Azure Key Vault](/azure/key-vault/general/basic-concepts) all'ambiente.
Il key vault dedicato può essere utilizzato per mettere in scena e utilizzare i segreti nel confine di conformità di un'organizzazione. Customer Insights può usare i segreti in Azure Key Vault per [stabilire le connessioni](connections.md) a sistemi di terze parti.

Per ulteriori informazioni, vedi [Utilizzo dalla propria istanza di Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
