---
title: Panoramica delle connessioni (anteprima)
description: Connessioni ad altri servizi da Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245516"
---
# <a name="connections-preview-overview"></a>Panoramica delle connessioni (anteprima)

Le connessioni sono la chiave per abilitare la condivisione dei dati da e verso Customer Insights. Ogni connessione stabilisce la condivisione dei dati con un servizio specifico. Usa le connessioni per [configurare arricchimenti di terze parti](enrichment-hub.md) e [configurare le esportazioni](export-destinations.md). La stessa connessione può essere utilizzata più volte. Ad esempio, una connessione a Dynamics 365 Marketing funziona per più esportazioni e una connessione Leadspace può essere utilizzata per diversi arricchimenti.

## <a name="export-connections"></a>Esportare le connessioni

Solo gli amministratori possono configurare nuove connessioni, ma possono [concedere l'accesso ai collaboratori](#allow-contributors-to-use-a-connection-for-exports) per utilizzare le connessioni esistenti. Gli amministratori controllano dove possono andare i dati, i collaboratori definiscono il carico utile e la frequenza che si adatta alle loro esigenze.

## <a name="enrichment-connections"></a>Connessioni arricchimenti

Solo gli amministratori possono configurare nuove connessioni, ma le connessioni create sono sempre disponibili sia per gli amministratori che per i collaboratori. Gli amministratori gestiscono le credenziali e danno il consenso al trasferimento dei dati. Le connessioni possono essere utilizzate per gli arricchimenti da amministratori e collaboratori.

## <a name="add-a-new-connection"></a>Aggiungere una nuova connessione

### <a name="prerequisites"></a>Prerequisiti

- [Autorizzazioni dell'amministratore](permissions.md)
- Altri servizi Microsoft, se presenti, si trovano nella stessa organizzazione

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli il tipo di connessione che vuoi creare. Oppure, vai alla scheda **Individua** e seleziona **Configura** nel riquadro di connessione.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Immetti i dettagli richiesti. I campi esatti dipendono dal servizio a cui ti stai connettendo. Per i dettagli di un tipo di connessione specifico, fai riferimento all'articolo sul servizio di destinazione.

1. Se [usi il tuo Key Vault](use-azure-key-vault.md) per memorizzare i segreti, attiva **Usa Key Vault** e scegli il segreto dalla lista.

1. Leggi Privacy e conformità dei dati e seleziona **Accetto**.

1. Per creare la connessione seleziona **Salva**.

### <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a terze parti o altri prodotti Microsoft, acconsenti il trasferimento dei dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che le terze parti rispettino gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'amministratore di Dynamics 365 Customer Insights può rimuovere la connessione in qualsiasi momento per interrompere l'utilizzo della funzionalità.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Consentire ai collaboratori di utilizzare una connessione per le esportazioni

Quando imposti o modifichi una connessione di esportazione, scegli a quali utenti è consentito utilizzare questa connessione specifica per la definizione delle [esportazioni](export-destinations.md). Per impostazione predefinita, una connessione è disponibile per gli utenti con un ruolo amministratore. Modifica l'impostazione **Scegli chi può utilizzare questa connessione** per consentire agli utenti con il ruolo collaboratore di utilizzare questa connessione.

- I collaboratori non saranno in grado di visualizzare o modificare la connessione. Vedranno solo il nome visualizzato e il suo tipo durante la creazione di un'esportazione.
- Condividendo una connessione, consenti ai collaboratori di utilizzare una connessione. I collaboratori vedranno le connessioni condivise quando configurano le esportazioni. Possono gestire ogni esportazione che utilizza questa specifica connessione.
- Puoi modificare questa impostazione mantenendo le esportazioni che sono già state definite dai collaboratori.

## <a name="manage-existing-connections"></a>Gestire connessioni esistenti

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona la scheda **Arricchimento** o **Esportazioni** per visualizzare un elenco di connessioni di arricchimento o esportazione, il tipo di connessione, quando è stata creata e chi ha accesso. Puoi ordinare l'elenco delle connessioni in base a qualsiasi colonna.

1. Seleziona la connessione per visualizzare le azioni disponibili.

   - **Modifica** la connessione.
   - [**Rimuovi**](#remove-a-connection) una connessione.

### <a name="remove-a-connection"></a>Rimuovere una connessione

Se la connessione che stai rimuovendo viene utilizzata da arricchimenti o esportazioni, devi prima scollegarli o rimuoverli. La finestra di dialogo Rimuovi ti consente di individuare gli arricchimenti o le esportazioni pertinenti.

> [!TIP]
> Gli arricchimenti e le esportazioni disattivati e scollegati diventano inattivi. Li riattivi aggiungendo loro un'altra connessione nella pagina [Arricchimenti](enrichment-hub.md) o [Esportazioni](export-destinations.md).

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona la scheda **Arricchimento** o **Esportazioni**.

1. Seleziona la connessione che vuoi rimuovere.

1. Seleziona **Rimuovi** dal menu a discesa. Viene visualizzata una finestra di dialogo di conferma.

   1. Se sono presenti arricchimenti o esportazioni che utilizzano questa connessione, seleziona il pulsante per vedere cosa sta utilizzando la connessione.
      - **Esportazioni:** scegli di **rimuovere** l'esportazione o di **scollegare la connessione**. Lo scollegamento della connessione mantiene la configurazione di esportazione, ma questa non verrà eseguita fino a quando non verrà aggiunta un'altra connessione.
      - **Arricchimenti:** scegli di **eliminare** o **disattivare** gli arricchimenti.
   1. Una volta che la connessione non ha più dipendenze, torna a **Amministratore** > **Connessioni** e prova a rimuovere di nuovo la connessione.

1. Per confermare l'eliminazione seleziona **Rimuovi**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Impostare connessioni con segreti gestiti dal proprio Key Vault

Alcune connessioni hanno bisogno di segreti come chiavi API o password. Alcune connessioni supportano i segreti memorizzati nel proprio Key Vault. Ulteriori informazioni sulle connessioni supportate e su come eseguire la configurazione [del tuo Key Vault per Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
