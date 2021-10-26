---
title: Porta il tuo key vault Azure per gestire i segreti
description: Scopri come configurare Customer Insights per utilizzare il tuo key vault Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606090"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Porta il tuo key vault Azure (anteprima)

Collegare un [Azure key vault](/azure/key-vault/general/basic-concepts) dedicato a un ambiente di approfondimenti sul pubblico aiuta le organizzazioni a soddisfare i requisiti di conformità.
Il key vault dedicato può essere utilizzato per mettere in scena e utilizzare i segreti nel confine di conformità di un'organizzazione. Le intuizioni del pubblico possono utilizzare i segreti in Azure Key Vault per impostare le [connessioni](connections.md) a sistemi di terze parti.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Collegare la volta chiave all'ambiente di intuizione del pubblico

### <a name="prerequisites"></a>Prerequisiti

Per configurare il key vault in approfondimenti sul pubblico, devono essere soddisfatti i seguenti prerequisiti:

- Hai un abbonamento attivo ad Azure.

- Disponi di un ruolo utente [Amministratore](permissions.md#administrator) nell'ambiente di Informazioni dettagliate sul gruppo di destinatari. Scopri di più sui [permessi degli utenti in approfondimenti sul pubblico](permissions.md#assign-roles-and-permissions).

- Hai i ruoli [Contribuente](/azure/role-based-access-control/built-in-roles#contributor) e [Amministratore accesso utente](/azure/role-based-access-control/built-in-roles#user-access-administrator) sul key vault o sul gruppo di risorse a cui il key vault appartiene. Per ulteriori informazioni, vai a [Aggiungere o rimuovere le assegnazioni dei ruoli Azure utilizzando il portale Azure](/azure/role-based-access-control/role-assignments-portal). Se non si dispone del ruolo User Access Administrator sul key vault, è necessario impostare separatamente le autorizzazioni di controllo dell'accesso basate sui ruoli per il principal del servizio Azure per Dynamics 365 Customer Insights . Seguire i passaggi per [utilizzare un service principal di Azure](connect-service-principal.md) per il key vault che deve essere collegato.

- Il key vault deve avere il Key Vault firewall **disabilitato**.

- Il key vault si trova nella stessa [posizione Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) dell'ambiente di approfondimenti sul pubblico. La regione dell'ambiente in approfondimenti sul pubblico è elencata in **Amministratore** > **Sistema** > **Informazioni** > **Regione**.

### <a name="link-a-key-vault-to-the-environment"></a>Collegare un key vault all'ambiente

1. Vai su **Amministratore** > **Sistema**, e poi seleziona la scheda **Sicurezza** .
1. Nel riquadro **Key Vault** , seleziona **Configurazione**.
1. Scegliere un **abbonamento**.
1. Scegli un key vault dall'elenco a discesa **Key Vault** . Se vengono visualizzati troppi key vault, seleziona un gruppo di risorse per limitare i risultati della ricerca.
1. Accettare la dichiarazione sulla **privacy e la conformità dei dati** .
1. Seleziona **Salva**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Passi per impostare un key vault collegato in approfondimenti sul pubblico.":::

Il riquadro del **Key Vault** ora mostra il nome del key vault collegato, il gruppo di risorse e la sottoscrizione. È pronto per essere usato nella configurazione della connessione.
Per i dettagli su quali permessi sul key vault sono concessi agli approfondimenti del pubblico, vai a [Permessi concessi sul key vault agli approfondimenti del pubblico](#permissions-granted-on-the-key-vault-to-audience-insights), più avanti in questo articolo.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilizzare il key vault nella configurazione della connessione

Quando si [impostano](connections.md) le connessioni a sistemi di terze parti, i segreti del Key Vault collegato possono essere usati per configurare le connessioni.

1. Vai ad **Amministratore** > **Connessioni**.
1. Selezionare **Aggiungi connessione**.
1. Per i tipi di connessione supportati, un toggle **Usa Key Vault** è disponibile se hai collegato un key vault.
1. Invece di inserire il segreto manualmente, puoi scegliere il nome del segreto che punta al valore segreto nel key vault.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Riquadro di connessione con una connessione SFTP che usa un segreto di Key Vault.":::

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Permessi concessi sulla volta chiave per gli approfondimenti sul pubblico

Le seguenti autorizzazioni sono concesse agli approfondimenti del pubblico su un key vault collegato se è abilitato il [criterio di accesso al key vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o il [controllo di accesso basato sui ruoli di Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) .

### <a name="key-vault-access-policy"></a>Politica di accesso al Key Vault

| Digita        | Autorizzazioni          |
| ----------- | -------------------- |
| Tasto         | [Ottenere le chiavi](/rest/api/keyvault/get-keys), [ottenere la chiave](/rest/api/keyvault/get-key)                                 |
| Segreto      | [Prendi i segreti](/rest/api/keyvault/get-secrets), [prendi il segreto](/rest/api/keyvault/get-secret)                     |
| Certificato | [Ottenere certificati](/rest/api/keyvault/get-certificates), [ottenere certificati](/rest/api/keyvault/get-certificate) |

I valori precedenti sono il minimo da elencare e leggere durante l'esecuzione.

### <a name="azure-role-based-access-control"></a>Controllo dell'accesso basato sui ruoli di Azure

I ruoli Key Vault Reader e Key Vault Secrets User saranno aggiunti per gli approfondimenti del pubblico. Per i dettagli su questi ruoli, vai a [Azure built-in roles for Key Vault data plane operations](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Elementi consigliati

- Utilizzate un key vault separato o dedicato che contiene solo i segreti necessari per gli approfondimenti del pubblico. Leggi di più sul perché [si raccomandano key vault separati per le chiavi](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Seguite le [migliori pratiche per utilizzare Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) per controllare l'accesso, il backup, l'audit e le opzioni di recupero.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Le intuizioni del pubblico possono scrivere segreti o sovrascrivere segreti nel key vault?

Nr. Solo i permessi di lettura e di elenco delineati nella sezione dei [permessi concessi](#permissions-granted-on-the-key-vault-to-audience-insights) in precedenza in questo articolo sono concessi agli approfondimenti del pubblico. Il sistema non può aggiungere, cancellare o sovrascrivere segreti nel key vault. Questo è anche il motivo per cui non si possono inserire le credenziali quando una connessione usa Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Posso cambiare una connessione dall'uso dei segreti del Key Vault all'autenticazione predefinita?

Nr. Non si può tornare a una connessione predefinita dopo averla configurata usando un segreto da una cassaforte a chiave collegata. Crea una connessione separata e cancella quella vecchia se non ti serve più.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Come posso revocare l'accesso a un key vault per gli approfondimenti sul pubblico?

A seconda che sia abilitato il [criterio di accesso a Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o il [controllo di accesso basato sui ruoli di Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) , è necessario rimuovere i permessi per il principal del servizio `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` con il nome `Dynamics 365 AI for Customer Insights`. Tutte le connessioni che usano il key vault smetteranno di funzionare.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un segreto usato in una connessione è stato rimosso dal key vault. Cosa posso fare?

Una notifica appare in approfondimenti sul pubblico quando un segreto configurato dal key vault non è più accessibile. Abilita la [cancellazione progressiva](/azure/key-vault/general/soft-delete-overview) sul key vault per ripristinare i segreti se vengono rimossi accidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Una connessione non funziona, ma il mio segreto è nel key vault. Quale potrebbe essere la causa?

Una notifica appare in approfondimenti sul pubblico quando non può accedere al key vault. La causa potrebbe essere:

- I permessi per il principale del servizio approfondimenti sul pubblico sono stati rimossi. Devono essere ripristinati manualmente.

- Il firewall sul key vault è abilitato. Il firewall deve essere disattivato per rendere il key vault di nuovo accessibile per gli approfondimenti del pubblico.
