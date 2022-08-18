---
title: Porta il tuo key vault Azure (anteprima)
description: Scopri come configurare Customer Insights per usare il tuo key vault Azure per gestire i segreti.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246160"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Porta il tuo key vault Azure (anteprima)

Il collegamento di un [key vault Azure](/azure/key-vault/general/basic-concepts) dedicato a un ambiente Customer Insights aiuta le organizzazioni a soddisfare i requisiti di conformità.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Collegare il Key Vault all'ambiente Customer Insights

Configura il key vault dedicato per preparare e utilizzare i segreti nei limiti di conformità di un'organizzazione.

### <a name="prerequisites"></a>Prerequisiti

- Una sottoscrizione di Azure attiva.

- Un ruolo di [amministratore](permissions.md#admin) [assegnato](permissions.md#add-users) in Customer Insights.

- Ruoli [Collaboratore](/azure/role-based-access-control/built-in-roles#contributor) e [Amministratore accessi utente](/azure/role-based-access-control/built-in-roles#user-access-administrator) per il key vault o il gruppo di risorse a cui il key vault appartiene. Per ulteriori informazioni, vai a [Aggiungere o rimuovere le assegnazioni dei ruoli Azure utilizzando il portale Azure](/azure/role-based-access-control/role-assignments-portal). Se non disponi del ruolo Amministratore accessi utente per il key vault, imposta separatamente le autorizzazioni di controllo degli accessi in base al ruolo per l'entità servizio di Azure per Dynamics 365 Customer Insights. Seguire i passaggi per [utilizzare un service principal di Azure](connect-service-principal.md) per il key vault che deve essere collegato.

- Il key vault deve avere il firewall Key Vault **disabilitato**.

- Il key vault si trova nella stessa [posizione Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) dell'ambiente di Customer Insights. In Customer Insights, vai ad **Amministratore** > **Sistema** e accedi alla scheda **Informazioni** per visualizzare l'area dell'ambiente.

### <a name="recommendations"></a>Elementi consigliati

- [Utilizza un key vault separato o dedicato](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) che contiene solo i segreti richiesti per Customer Insights.

- Seguite le [migliori pratiche per utilizzare Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) per controllare l'accesso, il backup, l'audit e le opzioni di recupero.

### <a name="link-a-key-vault-to-the-environment"></a>Collegare un key vault all'ambiente

1. Passa ad **Amministratore** > **Sicurezza**, e seleziona la scheda **Key Vault**.
1. Nel riquadro **Key Vault** , seleziona **Configurazione**.
1. Scegliere un **abbonamento**.
1. Scegli un key vault dall'elenco a discesa **Key Vault** . Se sono disponibili troppi key vault, seleziona un gruppo di risorse per limitare i risultati della ricerca.
1. Rivedi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.
1. Seleziona **Salva**.

Il riquadro **Key Vault** mostra il nome del key vault collegato, il gruppo di risorse e la sottoscrizione. È pronto per essere usato nella configurazione della connessione.
Per dettagli su quali autorizzazioni nel key vault sono concesse a Customer Insights, vai a [Autorizzazioni concesse nel key vault](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilizzare il key vault nella configurazione della connessione

Quando [imposti le connessioni](connections.md) per sistemi di [terze parti supportati](#supported-connection-types), usa i segreti del key vault collegato per configurare le connessioni.

1. Vai ad **Amministratore** > **Connessioni**.
1. Selezionare **Aggiungi connessione**.
1. Per i tipi di connessione supportati, un toggle **Usa Key Vault** è disponibile se hai collegato un key vault.
1. Anziché inserire il segreto manualmente, scegli il nome del segreto che punta al valore segreto nel key vault.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Riquadro di connessione con una connessione SFTP che usa un segreto di Key Vault.":::

1. Per creare la connessione seleziona **Salva**.

## <a name="supported-connection-types"></a>Tipi di connessione supportati

Sono supportate le seguenti connessioni di [esportazione](export-destinations.md) :

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Autorizzazioni concesse nel key vault

Le autorizzazioni seguenti vengono concesse a Customer Insights in un key vault collegato, se il [Criterio di accesso del Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o il [Controllo degli accessi in base al ruolo di Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) è abilitato.

### <a name="key-vault-access-policy"></a>Politica di accesso al Key Vault

| Digita        | Autorizzazioni          |
| ----------- | -------------------- |
| Tasto         | [Ottenere le chiavi](/rest/api/keyvault/keys/get-keys/get-keys), [ottenere la chiave](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Segreto      | [Prendi i segreti](/rest/api/keyvault/secrets/get-secrets/get-secrets), [prendi il segreto](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certificato | [Ottenere certificati](/rest/api/keyvault/certificates/get-certificates/get-certificates), [ottenere certificati](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

I valori precedenti sono il minimo da elencare e leggere durante l'esecuzione.

### <a name="azure-role-based-access-control"></a>Controllo dell'accesso basato sui ruoli di Azure

I [ruoli utente Lettore Key Vault e Segreti Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli) verranno aggiunti per Customer Insights.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Customer Insights può scrivere segreti o sovrascrivere segreti nel Key Vault?

Nr. Solo le autorizzazioni di lettura ed elenco descritte in [Autorizzazioni concesse](#permissions-granted-on-the-key-vault) sono concesse a Customer Insights. Il sistema non può aggiungere, cancellare o sovrascrivere segreti nel key vault. Questo è anche il motivo per cui non si possono inserire le credenziali quando una connessione usa Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Posso cambiare una connessione dall'uso dei segreti del Key Vault all'autenticazione predefinita?

Nr. Non si può tornare a una connessione predefinita dopo averla configurata usando un segreto da una cassaforte a chiave collegata. Crea una connessione separata e cancella quella vecchia se non ti serve più.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Come posso revocare l'accesso a un key vault per Customer Insights?

Se il [criterio di accesso a Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o il [controllo degli accessi in base al ruolo di Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) è abilitato, rimuovi i permessi per l'entità servizio `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` con il nome `Dynamics 365 AI for Customer Insights`. Tutte le connessioni che usano il key vault smetteranno di funzionare.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un segreto usato in una connessione è stato rimosso dal key vault. Cosa posso fare?

Viene visualizzata una notifica in Customer Insights quando un segreto configurato dal key vault non è più accessibile. Abilita la [cancellazione progressiva](/azure/key-vault/general/soft-delete-overview) sul key vault per ripristinare i segreti se vengono rimossi accidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Una connessione non funziona, ma il mio segreto è nel key vault. Quale potrebbe essere la causa?

Viene visualizzata una notifica in Customer Insights quando non è possibile accedere al key vault. La causa potrebbe essere:

- Le autorizzazioni per l'entità servizio Customer Insights sono state rimosse. Devono essere ripristinati manualmente.

- Il firewall sul key vault è abilitato. Il firewall deve essere disabilitato per rendere nuovamente accessibile il key vault per Customer Insights.
