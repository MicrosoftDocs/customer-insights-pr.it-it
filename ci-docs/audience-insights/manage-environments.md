---
title: Creare e gestire ambienti
description: Scopri come iscriverti al servizio e come gestire gli ambienti.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304885"
---
# <a name="manage-environments"></a>Gestisci ambienti

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

In questo viene descritto come creare una nuova organizzazione e come eseguire il provisioning di un ambiente.

## <a name="sign-up-and-create-an-organization"></a>Iscriversi e creare un'organizzazione

1. Vai al sito Web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Seleziona **Inizia subito**.

3. Scegli il tuo scenario di iscrizione preferito e seleziona il collegamento corrispondente.

4. Accetta le condizioni e seleziona **Continua** per iniziare a creare l'organizzazione.

5. Dopo aver creato l'ambiente, verrai reindirizzato a [Customer Insights](https://home.ci.ai.dynamics.com).

6. Utilizza l'ambiente demo per esplorare l'app o crea un nuovo ambiente seguendo i passaggi nella sezione successiva.

7. Dopo aver specificato le impostazioni dell'ambiente, seleziona **Crea**.

8. Dopo la corretta creazione dell'ambiente, sarai connesso.

## <a name="create-an-environment-in-an-existing-organization"></a>Creazione di un ambiente in un'organizzazione esistente

Ci sono due modi per creare un nuovo ambiente. Puo specifica una configurazione interamente nuova oppure copiare alcune impostazioni di configurazione da un ambiente esistente.

> [!NOTE]
> Le organizzazioni possono creare *due* ambienti per ogni licenza Customer Insights. Se la tua organizzazione acquista più di una licenza, [contatta il nostro team di supporto](https://go.microsoft.com/fwlink/?linkid=2079641) per aumentare il numero di ambienti disponibili. Per ulteriori informazioni sulla capacità e sulla capacità del componente aggiuntivo, scarica [Guida alle licenze di Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Per creare un ambiente:

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona **Nuovo**.

   > [!div class="mx-imgBorder"]
   > ![Impostazioni ambiente.](media/environment-settings-dialog.png)

1. Nella finestra di dialogo **Crea un ambiente** seleziona **Nuovo ambiente**.

   Per [copiare i dati dall'ambiente corrente](#considerations-for-copy-configuration-preview), seleziona **Copia dall'ambiente esistente**. Vedrai un elenco di tutti gli ambienti disponibili nella tua organizzazione da cui puoi copiare i dati.

1. Fornisci i seguenti dettagli:
   - **Nome**: il nome dell'ambiente. Questo campo è già compilato se hai copiato da un ambiente esistente, ma è possibile modificarlo.
   - **Tipo**: scegli se vuoi creare un ambiente di produzione o sandbox.
   - **Area geografica**: l'area geografica in cui il servizio viene distribuito e ospitato.
   
1. È possibile facoltativamente selezionare **Impostazioni avanzate**:

   - **Salva tutti i dati in**: specifica dove vuoi archiviare i dati di output generati da Customer Insights. Avrai due opzioni: **Archiviazione di Customer Insights** (un Azure Data Lake gestito dal team Customer Insights) e **Azure Data Lake Storage** (il tuo Azure Data Lake Storage). Per impostazione predefinita, l'opzione di archiviazione di Customer Insights è selezionata.

     > [!NOTE]
     > Salvando i dati in Azure Data Lake Storage, accetti che i dati vengano trasferiti e archiviati nella posizione geografica appropriata per tale account di archiviazione di Azure, che può essere diversa da quella in cui sono archiviati i dati in Dynamics 365 Customer Insights. [Altre informazioni nel Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > Attualmente, le entità inserite vengono sempre archiviate nel Data Lake gestito di Customer Insights. 
     > 
     > Supportiamo solo account Azure Data Lake Storage della stessa area di Azure selezionata durante la creazione dell'ambiente. 
     > 
     > Supportiamo solo account Azure Data Lake Storage con spazio dei nomi gerarchico abilitato.


   - Per l'opzione Azure Data Lake Storage puoi scegliere tra un'opzione basata sulle risorse e un'opzione basata su sottoscrizione per l'autenticazione. Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md). Il nome **Contenitore** non può essere cambiato e sarà `customerinsights`.
   
   - Se vuoi usare le [previsioni](predictions.md), configura la condivisione dei dati con Microsoft Dataverse o abilita l'inserimento dei dati dalle origini dati locali, fornisci l'URL dell'ambiente Microsoft Dataverse in **Configura la condivisione dei dati con Microsoft Dataverse e abilita funzionalità aggiuntive**. Seleziona **Abilita la condivisione dei dati** per condividere i dati di output di Customer Insights con un Data Lake gestito di Microsoft Dataverse.

     > [!NOTE]
     > - Condivisione dei dati con un Data Lake gestito di Microsoft Dataverse non è attualmente supportata quando salvi tutti i dati nel tuo Azure Data Lake Storage.
     > - [Previsione di valori mancanti in un'entità](predictions.md) non è attualmente supportata quando abiliti la condivisione dei dati con Data Lake gestito di Microsoft Dataverse.

     > [!div class="mx-imgBorder"]
     > ![Opzioni di configurazione per abilitare la condivisione dei dati con Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   Quando esegui processi, come l'inserimento dati o la creazione di segmenti, le cartelle corrispondenti verranno create nell'account di archiviazione specificato sopra. I file di dati e i file model.json verranno creati e aggiunti alle cartelle, a seconda del nome del processo.

   Se crei più ambienti di Customer Insights e scegli di salvare le entità di output da quegli ambienti nell'account di archiviazione, verranno create cartelle separate per ogni ambiente con ci_<environmentid> nel contenitore.

### <a name="considerations-for-copy-configuration-preview"></a>Considerazioni sulla configurazione della copia (anteprima)

Le impostazioni di configurazione seguenti vengono copiate:

- Configurazioni delle funzionalità
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

Le impostazioni di configurazione seguenti *non* vengono copiate:

- Profili cliente.
- Credenziali origine dati. Dovrai fornire le credenziali per ogni origine dati e aggiornare manualmente le origini dati.
- Origini dati della cartella Common Data Model e Data Lake gestito da Dataverse. Dovrai creare tali origini dati manualmente con lo stesso nome dell'ambiente di origine.

Quando copi un ambiente, vedrai un messaggio di conferma che il nuovo ambiente è stato creato. Seleziona **Vai a origini dati** per visualizzare l'elenco delle origini dati.

Tutte le origini dati mostreranno uno stato **Credenziali obbligatorie**. Modifica le origini dati e inserisci le credenziali per aggiornarle.

> [!div class="mx-imgBorder"]
> ![Origini dati copiate.](media/data-sources-copied.png)

Dopo aver aggiornato le origini dati, vai a **Dati** > **Unifica**. Qui troverai le impostazioni dall'ambiente di origine. Modificale in base alle necessità o seleziona **Esegui** per avviare il processo di unificazione dei dati e creare l'entità cliente unificata.

Quando l'unificazione dei dati è completa, vai a **Misure** e **Segmenti** per aggiornarli.

## <a name="edit-an-existing-environment"></a>Modificare un ambiente esistente

Puoi modificare alcuni dei dettagli degli ambienti esistenti.

1.  Seleziona il selettore **Ambiente** nell'intestazione dell'app.

2.  Seleziona l'icona **Modifica**.

3. Nella casella **Modifica ambiente** puoi aggiornare il **Nome visualizzato** dell'ambiente, ma non puoi modificare **Area** o **Tipo**.

4. Se un ambiente è configurato per memorizzare i dati in Azure Data Lake Storage, puoi aggiornare la **Chiave account**. Tuttavia, non puoi modificare il **Nome account** o il nome del **Contenitore**.

5. Facoltativamente, puoi eseguire l'aggiornamento da una connessione basata sulla chiave dell'account a una connessione basata su risorse o sottoscrizione. Dopo l'aggiornamento, non puoi ripristinare la chiave dell'account. Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md). Non puoi modificare le informazioni sul **Contenitore** durante l'aggiornamento della connessione.

6. Facoltativamente, puoi fornire un URL dell'ambiente Microsoft Dataverse in **Configura la condivisione dei dati con Microsoft Dataverse e abilita funzionalità aggiuntive**. Queste funzionalità includono la condivisione dei dati con applicazioni e soluzioni basate su Microsoft Dataverse, inserimento di dati da origini dati locali o l'utilizzo delle [previsioni](predictions.md). Seleziona **Abilita la condivisione dei dati** per condividere i dati di output di Customer Insights con un Data Lake gestito di Microsoft Dataverse.

   > [!NOTE]
   > - Condivisione dei dati con un Data Lake gestito di Microsoft Dataverse non è attualmente supportata quando salvi tutti i dati nel tuo Azure Data Lake Storage.
   > - [La previsione di valori mancanti in un'entità](predictions.md) non è attualmente supportata quando abiliti la condivisione dei dati con il data lake gestito di Microsoft Dataverse.

   Dopo aver abilitato la condivisione dei dati con Microsoft Dataverse, verrà attivato un aggiornamento completo delle origini dati e di altri processi. Se i processi sono attualmente in esecuzione, non vedrai l'opzione per abilitare la condivisione dei dati con Microsoft Dataverse. Attendere il completamento di tali processi o annullarli per abilitare la condivisione dei dati. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opzioni di configurazione per abilitare la condivisione dei dati con Microsoft Dataverse.":::
   
   Quando esegui processi, come l'inserimento dati o la creazione di segmenti, le cartelle corrispondenti verranno create nell'account di archiviazione specificato sopra. I file di dati e i file model.json verranno creati e aggiunti alle rispettive sottocartelle, a seconda del processo eseguito.

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
