---
title: Connessioni ad altri servizi da Customer Insights.
description: Condividi i dati con altri servizi.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: d85de28a12565e1a2e36278d0e8b74f6de286b20
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755314"
---
# <a name="connections-preview-overview"></a>Panoramica delle connessioni (anteprima)

Le connessioni sono la chiave per abilitare la condivisione dei dati da e verso Customer Insights. Ogni connessione stabilisce la condivisione dei dati con un servizio specifico. Le connessioni sono la base per [configurare arricchimenti di terze parti](enrichment-hub.md) e [configurare le esportazioni](export-destinations.md). La stessa connessione può essere utilizzata più volte. Ad esempio, una connessione a Dynamics 365 Marketing funziona per più esportazioni e una connessione Leadspace può essere utilizzata per diversi arricchimenti.

Vai a **Amministratore** > **Connessioni** per creare e visualizzare le connessioni.

La scheda **Connessioni** mostra tutte le connessioni attive. L'elenco mostra una riga per ogni connessione.

Ottieni una rapida panoramica, una descrizione e scopri cosa puoi fare con ciascuna opzione di estensibilità nella scheda **Individua**.

## <a name="exports"></a>Esportazioni

Solo gli amministratori possono configurare nuove connessioni, ma possono concedere l'accesso ai collaboratori per utilizzare le connessioni esistenti. Gli amministratori controllano dove possono andare i dati, i collaboratori definiscono il carico utile e la frequenza che si adatta alle loro esigenze. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Arricchimenti

Solo gli amministratori possono configurare nuove connessioni, ma le connessioni create sono sempre disponibili sia per gli amministratori che per i collaboratori. Gli amministratori gestiscono le credenziali e danno il consenso al trasferimento dei dati. Le connessioni possono essere utilizzate per gli arricchimenti da amministratori e collaboratori.

## <a name="add-a-new-connection"></a>Aggiungere una nuova connessione

Per aggiungere connessioni, devi avere le [autorizzazioni di amministratore](permissions.md). Se ti connetti ad altri servizi Microsoft, presumiamo che entrambi i servizi appartengano alla stessa organizzazione.

1. Vai ad **Amministratore** > **Connessioni (anteprima)**.

1. Passa alla scheda **Connessioni**.

1. Seleziona **Aggiungi connessione** per creare una nuova connessione. Scegli dal menu a tendina che tipo di connessione vuoi creare.

1. Nel riquadro **Configura connessione** fornisci i dettagli richiesti.
   1. Il **nome visualizzato** e il tipo di connessione descrivono una connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo di questa connessione.
   1. I campi esatti dipendono dal servizio a cui ti stai connettendo. Puoi conoscere i dettagli di un tipo di connessione specifico nell'articolo sul servizio di destinazione.
   1. Se [usi il tuo Key Vault](use-azure-key-vault.md) per memorizzare i segreti, attiva **Usa Key Vault** e scegli il segreto dalla lista.

1. Per creare la connessione seleziona **Salva**.

Puoi anche selezionare **Configura** su un riquadro della scheda **Scopri**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Consentire ai collaboratori di utilizzare una connessione per le esportazioni

Quando si imposta o si modifica una connessione di esportazione, si sceglie a quali utenti è consentito utilizzare questa connessione specifica per la definizione delle [esportazioni](export-destinations.md). Per impostazione predefinita, una connessione è disponibile per gli utenti con un ruolo amministratore. Puoi modificare questa impostazione in **Scegli chi può utilizzare questa connessione** e consentire agli utenti con il ruolo collaboratore di utilizzare questa connessione.

- I collaboratori non saranno in grado di visualizzare o modificare la connessione. Vedranno solo il nome visualizzato e il suo tipo durante la creazione di un'esportazione.
- Condividendo una connessione, consenti ai collaboratori di utilizzare una connessione. I collaboratori vedranno le connessioni condivise quando configurano le esportazioni. Possono gestire ogni esportazione che utilizza questa specifica connessione.
- Puoi modificare questa impostazione mantenendo le esportazioni che sono già state definite dai collaboratori.

## <a name="edit-a-connection"></a>Modificare una connessione

1. Vai ad **Amministratore** > **Connessioni (anteprima)**.

1. Passa alla scheda **Connessioni**.

1. Seleziona i puntini di sospensione verticali per la connessione che vuoi modificare.

1. Seleziona **Modifica**

1. Modifica i valori che vuoi aggiornare e seleziona **Salva**.

## <a name="remove-a-connection"></a>Rimuovere una connessione

Se la connessione che stai rimuovendo viene utilizzata da arricchimenti o esportazioni, devi prima scollegarli o rimuoverli. La finestra di dialogo Rimuovi ti guiderà agli arricchimenti o alle esportazioni pertinenti.

Gli arricchimenti e le esportazioni distaccati diventano inattivi. Li riattivi aggiungendo loro un'altra connessione nella pagina [Arricchimenti](enrichment-hub.md) o [Esportazioni](export-destinations.md).

1. Vai ad **Amministratore** > **Connessioni (anteprima)**.

1. Passa alla scheda **Connessioni**.

1. Seleziona i puntini di sospensione verticali per la connessione che vuoi rimuovere.

1. Seleziona **Rimuovi** dal menu a discesa. Viene visualizzata una finestra di dialogo di conferma.

   1. Se sono presenti arricchimenti o esportazioni che utilizzano questa connessione, seleziona il pulsante per vedere cosa sta utilizzando la connessione.
      - **Esportazioni:** Puoi scegliere di rimuovere o disconnettere le esportazioni per poter rimuovere la connessione. Per disconnettere un'esportazione, gli amministratori possono utilizzare l'azione **Disconnetti**. Questa azione è disponibile per esportazioni singole e multiple selezionate. Scollegandoti mantieni la configurazione di esportazione, ma non verrà eseguita fino a quando non verrà aggiunta un'altra connessione.
      - **Arricchimenti:** Puoi scegliere di rimuovere o disattivare gli arricchimenti per poter rimuovere la connessione.
   1. Una volta che la connessione non ha più dipendenze, torna a **Amministratore** > **Connessioni** e prova a rimuovere di nuovo la connessione.

1. Per confermare l'eliminazione seleziona **Rimuovi**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Impostare connessioni con segreti gestiti dal proprio Key Vault

Alcune connessioni hanno bisogno di segreti come chiavi API o password. Alcune connessioni supportano i segreti memorizzati nel proprio Key Vault. Ulteriori informazioni sulle connessioni supportate e su come eseguire la configurazione [del tuo Key Vault per Customer Insights](use-azure-key-vault.md).
