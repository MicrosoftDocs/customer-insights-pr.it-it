---
title: Creare e gestire ambienti
description: Scopri come iscriverti al servizio e come gestire gli ambienti.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034182"
---
# <a name="manage-environments"></a>Gestisci ambienti

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Cambiare ambiente

Seleziona il controllo **Ambiente** nell'angolo superiore destro della pagina per modificare gli ambienti.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Screenshot del comando per cambiare ambiente.":::

Gli amministratori possono [creare](get-started-paid.md) e gestire ambienti.

## <a name="edit-an-existing-environment"></a>Modificare un ambiente esistente

Puoi modificare alcuni dei dettagli degli ambienti esistenti.

1.  Seleziona il selettore **Ambiente** nell'intestazione dell'app.

2.  Seleziona l'icona **Modifica**.

3. Nella casella **Modifica ambiente** puoi aggiornare il **Nome visualizzato** dell'ambiente, ma non puoi modificare **Area** o **Tipo**.

4. Se un ambiente è configurato per memorizzare i dati in Azure Data Lake Storage, puoi aggiornare la **Chiave account**. Tuttavia, non puoi modificare il **Nome account** o il nome del **Contenitore**.

5. Facoltativamente, puoi eseguire l'aggiornamento da una connessione basata sulla chiave dell'account a una connessione basata su risorse o sottoscrizione. Dopo l'aggiornamento, non puoi ripristinare la chiave dell'account. Per ulteriori informazioni, vedi [Connettere Informazioni dettagliate sul gruppo di destinatari a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md). Non puoi modificare le informazioni sul **Contenitore** durante l'aggiornamento della connessione.

6. Facoltativamente, puoi fornire un URL dell'ambiente Microsoft Dataverse in **Configura la condivisione dei dati con Microsoft Dataverse e abilita funzionalità aggiuntive**. Queste funzionalità includono la condivisione dei dati con applicazioni e soluzioni basate su Microsoft Dataverse, inserimento di dati da origini dati locali o l'utilizzo delle [previsioni](predictions.md). Seleziona **Abilita la condivisione dei dati** per condividere i dati di output di Customer Insights con un Data Lake gestito di Microsoft Dataverse.

   > [!NOTE]
   > - Condivisione dei dati con un Data Lake gestito di Microsoft Dataverse non è attualmente supportata quando salvi tutti i dati nel tuo Azure Data Lake Storage.
   > - La [previsione di valori mancanti in un'entità](predictions.md) e i report PowerBI Embedded nelle informazioni dettagliate (se abilitati nel tuo ambiente) non sono attualmente supportati quando abiliti la condivisione dei dati con il data lake gestito di Microsoft Dataverse.

   Dopo aver abilitato la condivisione dei dati con Microsoft Dataverse, verrà attivato un aggiornamento completo delle origini dati e di altri processi. Se i processi sono attualmente in esecuzione, non vedrai l'opzione per abilitare la condivisione dei dati con Microsoft Dataverse. Attendere il completamento di tali processi o annullarli per abilitare la condivisione dei dati. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opzioni di configurazione per abilitare la condivisione dei dati con Microsoft Dataverse.":::
   
   Quando esegui processi, come l'inserimento dati o la creazione di segmenti, le cartelle corrispondenti verranno create nell'account di archiviazione specificato sopra. I file di dati e i file model.json verranno creati e aggiunti alle rispettive sottocartelle, a seconda del processo eseguito.

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
