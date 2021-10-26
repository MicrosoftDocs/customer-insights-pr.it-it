---
title: Creare e gestire ambienti
description: Scopri come iscriverti al servizio e come gestire gli ambienti.
ms.date: 10/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: ce2fdd435a81bb04148057554c5958e3ab59f125
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645131"
---
# <a name="manage-environments"></a>Gestisci ambienti

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Cambiare ambiente

Seleziona il controllo **Ambiente** nell'angolo superiore destro della pagina per modificare gli ambienti.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Screenshot del comando per cambiare ambiente.":::

Gli amministratori possono [creare](create-environment.md) e gestire ambienti.

## <a name="edit-an-existing-environment"></a>Modificare un ambiente esistente

Puoi modificare alcuni dei dettagli degli ambienti esistenti.

1.  Seleziona il selettore **Ambiente** nell'intestazione dell'app.

2.  Seleziona l'icona **Modifica**.

3. Nella casella **Modifica ambiente** , puoi aggiornare le impostazioni dell'ambiente.

Per maggiori informazioni sulle impostazioni dell'ambiente, vedi [Creare un nuovo ambiente](create-environment.md).

## <a name="copy-the-environment-configuration"></a>Copia la configurazione dell'ambiente

Quando crei un nuovo ambiente, puoi scegliere di copiare la configurazione da un ambiente esistente. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Screenshot delle opzioni di impostazione nelle impostazioni dell'ambiente.":::

Vedrai un elenco di tutti gli ambienti disponibili nella tua organizzazione da cui puoi copiare i dati.

Le impostazioni di configurazione seguenti vengono copiate:

- Origini dati inserite/importate
- Configurazione di unificazione dei dati (mapping, corrispondenza, unione)
- Segmenti
- Misure
- Relazioni
- Impegni
- Indice di ricerca e filtro
- Destinazioni di esportazione
- Aggiornamento pianificato
- Arricchimenti
- Gestione modelli
- Assegnazioni di ruolo

I seguenti dati *non* vengono copiati:

- Profili cliente.
- Credenziali origine dati. Dovrai fornire le credenziali per ogni origine dati e aggiornare manualmente le origini dati.
- Origini dati della cartella Common Data Model e Data Lake gestito da Dataverse. Dovrai creare tali origini dati manualmente con lo stesso nome dell'ambiente di origine.

Quando copi un ambiente, vedrai un messaggio di conferma che il nuovo ambiente è stato creato. Seleziona **Vai a origini dati** per visualizzare l'elenco delle origini dati.

Tutte le origini dati mostreranno uno stato **Credenziali obbligatorie**. Modifica le origini dati e inserisci le credenziali per aggiornarle.

:::image type="content" source="media/data-sources-copied.png" alt-text="Elenco delle origini dati che sono state copiate e richiedono l'autenticazione.":::

Dopo aver aggiornato le origini dati, vai a **Dati** > **Unifica**. Qui troverai le impostazioni dall'ambiente di origine. Modificale in base alle necessità o seleziona **Esegui** per avviare il processo di unificazione dei dati e creare l'entità cliente unificata.

Quando l'unificazione dei dati è completa, vai a **Misure** e **Segmenti** per aggiornarli.

## <a name="reset-an-existing-environment"></a>Reimpostare un ambiente esistente

Come amministratore, puoi reimpostare un ambiente su uno stato vuoto se desideri eliminare tutte le configurazioni e rimuovere i dati inseriti.

1.  Seleziona il selettore **Ambiente** nell'intestazione dell'app. 

2.  Seleziona l'ambiente che desideri reimpostare, quindi i puntini di sospensione (**...**). 

3. Scegli l'opzione **Reimposta**. 

4.  Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Reimposta**.

## <a name="delete-an-existing-environment"></a>Eliminare un ambiente esistente

In qualità di amministratore, puoi eliminare un ambiente che amministri.

1.  Seleziona il selettore **Ambiente** nell'intestazione dell'app.

2.  Seleziona l'ambiente che desideri reimpostare, quindi i puntini di sospensione (**...**). 

3. Scegli l'opzione **Elimina**. 

4.  Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Elimina**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
