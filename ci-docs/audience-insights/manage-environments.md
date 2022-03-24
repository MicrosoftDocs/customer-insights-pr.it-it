---
title: Creare e gestire ambienti
description: Scopri come iscriverti al servizio e come gestire gli ambienti.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376881"
---
# <a name="manage-environments"></a>Gestisci ambienti

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

## <a name="connect-to-microsoft-dataverse"></a>Connessione a Microsoft Dataverse
   
Il passo **Microsoft Dataverse** permette di collegare Customer Insights con il vostro ambiente Dataverse.

Per utilizzare i [modelli di predizione out-of-box](predictions-overview.md#out-of-box-models), configurare la condivisione dei dati con Dataverse. Oppure puoi abilitare l'ingestione dei dati da fonti di dati on-premises, fornendo l'URL dell'ambiente Microsoft Dataverse che la tua organizzazione amministra.

> [!IMPORTANT]
> Customer Insights e Dataverse devono trovarsi nella stessa regione per consentire la condivisione dei dati.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Opzioni di configurazione per abilitare la condivisione dei dati con Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights non supporta i seguenti scenari di condivisione dei dati:
> - Se salvi tutti i dati sull'istanza di Azure Data Lake Storage in uso, non sarai in grado di abilitare la condivisione dei dati con un data lake gestito di Dataverse.
> - Se abiliti la condivisione dei dati con Dataverse, non sarai in grado di [creare valori previsti o mancanti in un'entità](predictions.md).

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

- Origini dati dalla cartella Common Data Model e dal data lake gestito di Dataverse. Dovrai creare tali origini dati manualmente con lo stesso nome dell'ambiente di origine.

Quando copi un ambiente, vedrai un messaggio di conferma che il nuovo ambiente è stato creato. Seleziona **Vai a origini dati** per visualizzare l'elenco delle origini dati.

Tutte le origini dati mostreranno uno stato **Credenziali obbligatorie**. Modifica le origini dati e inserisci le credenziali per aggiornarle.

:::image type="content" source="media/data-sources-copied.png" alt-text="Elenco delle origini dati che sono state copiate e richiedono l'autenticazione.":::

Dopo aver aggiornato le origini dati, vai a **Dati** > **Unifica**. Qui troverai le impostazioni dall'ambiente di origine. Modificale in base alle necessità o seleziona **Esegui** per avviare il processo di unificazione dei dati e creare l'entità cliente unificata.

Quando l'unificazione dei dati è completa, vai a **Misure** e **Segmenti** per aggiornarli.

## <a name="change-the-owner-of-an-environment"></a>Cambiare il proprietario di un ambiente

Sebbene diversi utenti possano disporre delle autorizzazioni di amministratore in Customer Insights, solo un utente è il proprietario di un ambiente. Per impostazione predefinita, è l'amministratore che crea inizialmente un ambiente. In qualità di amministratore di un ambiente, puoi assegnare la proprietà a un altro utente con autorizzazioni di amministratore.

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona l'icona **Modifica**.

1. Nella casella **Modifica ambiente** vai al passaggio **Informazioni di base**.

1. Nel campo **Cambia proprietario dell'ambiente** scegli il nuovo proprietario dell'ambiente.  

1. Seleziona **Verifica e termina** e poi **Aggiorna** per applicare le modifiche. 

## <a name="claim-ownership-of-an-environment"></a>Rivendicare la proprietà di un ambiente

Se il proprietario di un ambiente lascia l'organizzazione o il suo account utente viene eliminato, l'ambiente non avrà alcun proprietario. Un utente con autorizzazioni di amministratore può rivendicare la proprietà e diventare il nuovo proprietario. Può continuare a essere il proprietario dell'ambiente o [passare la proprietà a un altro amministratore](#change-the-owner-of-an-environment). 

Per rivendicare la proprietà, seleziona il pulsante **Diventa proprietario** visualizzato nella parte superiore di ogni pagina di Customer Insights quando il proprietario originale lascia l'organizzazione.

## <a name="reset-an-existing-environment"></a>Reimpostare un ambiente esistente

In qualità di proprietario di un ambiente, puoi reimpostare un ambiente su uno stato vuoto se desideri eliminare tutte le configurazioni e rimuovere i dati inseriti.

1.  Seleziona il selettore **Ambiente** nell'intestazione dell'app. 

2.  Seleziona l'ambiente che desideri reimpostare, quindi i puntini di sospensione (**...**). 

3. Scegli l'opzione **Reimposta**. 

4.  Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Reimposta**.

## <a name="delete-an-existing-environment"></a>Eliminare un ambiente esistente

In qualità di proprietario di un ambiente, puoi eliminare un ambiente che amministri.

1.  Seleziona il selettore **Ambiente** nell'intestazione dell'app.

2.  Seleziona l'ambiente che desideri reimpostare, quindi i puntini di sospensione (**...**). 

3. Scegli l'opzione **Elimina**. 

4.  Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Elimina**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
