---
title: Connettere a una cartella Common Data Model usando un account Azure Data Lake
description: Utilizza i dati di Common Data Model con Azure Data Lake Storage.
ms.date: 09/29/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: c12603b9ed8a814356a0f8d0137e97afc749b87c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609947"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Connettersi ai dati in Azure Data Lake Storage

Inserisci dati in Dynamics 365 Customer Insights usando il tuo account Azure Data Lake Storage Gen2. L'inserimento dati può essere completo o incrementale.

## <a name="prerequisites"></a>Prerequisiti

- L'inserimento dati supporta solo account Azure Data Lake Storage *Gen2*. Non puoi usare account Data Lake Storage Gen1 per inserire i dati.

- L'account Azure Data Lake Storage deve avere lo [spazio dei nomi gerarchico abilitato](/azure/storage/blobs/data-lake-storage-namespace). I dati devono essere archiviati in un formato di cartella gerarchica che definisce la cartella radice e dispone di sottocartelle per ciascuna entità. Le sottocartelle possono contenere cartelle di dati completi o di dati incrementali.

- Per eseguire l'autenticazione con un'entità servizio di Azure, assicurati che sia configurata nel tenant. Per ulteriori informazioni, vedi [Connessione a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md).

- L'istanza di Azure Data Lake Storage a cui desideri connetterti e usare per l'inserimento di dati deve trovarsi nella stessa area di Azure dell'ambiente Dynamics 365 Customer Insights. Le connessioni a una cartella di Common Data Model da un data lake in un'area diversa di Azure non sono supportate. Per conoscere l'area di Azure dell'ambiente, vai a **Amministratore** > **Sistema** > **Informazioni** in Customer Insights.

- I dati memorizzati nei servizi online possono essere archiviati in una posizione diversa da quella in cui i dati vengono elaborati o archiviati in Dynamics 365 Customer Insights.Importando o connettendoti a dati archiviati nei servizi online, accetti che i dati possano essere trasferiti e archiviati con Dynamics 365 Customer Insights. [Altre informazioni sono disponibili nel Microsoft Trust Center.](https://www.microsoft.com/trust-center).

- L'entità servizio Customer Insights deve avere uno dei ruoli seguenti per accedere all'account di archiviazione. Per altre informazioni, vedi [Concedere le autorizzazioni all'entità servizio per accedere all'account di archiviazione](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Lettore dati BLOB di archiviazione
  - Proprietario dati BLOB di archiviazione
  - Collaboratore dati BLOB di archiviazione

- L'utente che configura la connessione origine dati necessita di autorizzazioni minime per i dati del BLOB di archiviazione contributore nell'account di archiviazione.

- I dati in Data Lake Storage devono seguire lo standard Common Data Model per l'archiviazione dei dati e avere il manifesto Common Data Model per rappresentare lo schema dei file di dati (*.csv o *.parquet). Il manifesto deve fornire i dettagli delle entità come colonne di entità e tipi di dati, nonché la posizione del file di dati e il tipo di file. Per altre informazioni, vedi [Manifesto Common Data Model](/common-data-model/sdk/manifest). Se il manifesto non è presente, gli utenti amministratori con accesso Proprietario dati BLOB di archiviazione o Collaboratore dati BLOB di archiviazione possono definire lo schema durante l'inserimento dei dati.

## <a name="recommendations"></a>Elementi consigliati

Per prestazioni ottimali, Customer Insights consiglia che la dimensione di una partizione sia pari o inferiore a 1 GB e il numero di file di partizione in una cartella non sia superiore a 1.000.

## <a name="connect-to-azure-data-lake-storage"></a>Connettersi a Azure Data Lake Storage

1. Vai a **Dati** > **Origini dati**.

1. Seleziona **Aggiungi origine dati**.

1. Seleziona **Azure Data Lake Storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Finestra di dialogo per immettere i dettagli di connessione per Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Immetti un **Nome** per l'origine dati e una **Descrizione** opzionale. Il nome identifica in modo univoco l'origine dati. Viene inoltre fatto riferimento a esso nei processi downstream e non può essere modificato.

1. Scegli una delle seguenti opzioni per **Connetti lo spazio di archiviazione tramite**. Per altre informazioni, vedi [Connessione a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md).

   - **Risorsa di Azure**: immetti un valore in **ID risorsa**. Facoltativamente, se desideri inserire i dati da un account di archiviazione tramite un collegamento privato di Azure, seleziona **Abilita collegamento privato**. Per altre informazioni, vedi [Collegamenti privati](security-overview.md#set-up-an-azure-private-link).
   - **Sottoscrizione di Azure**: seleziona **Sottoscrizione** e quindi **Gruppo di risorse** e **Account di archiviazione**. Facoltativamente, se desideri inserire i dati da un account di archiviazione tramite un collegamento privato di Azure, seleziona **Abilita collegamento privato**. Per altre informazioni, vedi [Collegamenti privati](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > È necessario uno dei seguenti ruoli per il contenitore o l'account di archiviazione per creare l'origine dati:
   >
   >  - Lettore dati del BLOB di archiviazione è sufficiente per leggere da un account di archiviazione e importare i dati in Customer Insights.
   >  - Collaboratore dati BLOB di archiviazione o Proprietario è necessario per modificare i file manifesto direttamente in Customer Insights.  
  
1. Scegli il nome del **Contenitore** che contiene i dati e lo schema (file model.json o manifest.json) da cui importare i dati e seleziona **Avanti**.
   > [!NOTE]
   > Qualsiasi file model.json o manifest.json associato a un'altra origine dati nell'ambiente non verrà visualizzato nell'elenco. Tuttavia, lo stesso file model.json o manifest.json può essere utilizzato per origini dati in più ambienti.

1. Per creare un nuovo schema, vai a [Creare un nuovo file di schema](#create-a-new-schema-file).

1. Per usare uno schema esistente, vai alla cartella contenente il file model.json o manifest.cdm.json. Puoi eseguire la ricerca in una directory per trovare il file.

1. Seleziona il file json, quindi **Avanti**. Viene visualizzato un elenco delle entità disponibili.

   :::image type="content" source="media/review-entities.png" alt-text="Finestra di dialogo di un elenco di entità da selezionare":::

1. Seleziona le entità che desideri includere.

   :::image type="content" source="media/ADLS_required.png" alt-text="Finestra di dialogo che mostra Richiesto per la chiave primaria":::

   > [!TIP]
   > Per modificare un'entità in un'interfaccia di modifica JSON, seleziona l'entità e quindi **Modifica file schema**. Apporta le modifiche e seleziona **Salva**.

1. Per le entità selezionate che richiedono l'inserimento incrementale, **Obbligatoria** viene visualizzato in **Aggiornamento incrementale**. Per ciascuna di queste entità, vedi [Configurare un aggiornamento incrementale per le origini dati di Azure Data Lake](incremental-refresh-data-sources.md).

1. Per le entità selezionate in cui non è stata definita una chiave primaria, **Obbligatoria** viene visualizzato in **Chiave primaria**. Per ciascuna di queste entità:
   1. Seleziona **Obbligatoria**. Viene visualizzato il pannello **Modifica entità**.
   1. Scegli la **chiave primaria**. La chiave primaria è un attributo univoco per l'entità. Affinché un attributo sia una chiave primaria valida, non deve includere valori duplicati, valori mancanti o valori null. Gli attributi del tipo di dati String, Integer e GUID sono supportati come chiavi primarie.
   1. Facoltativamente, modifica il modello di partizione.
   1. Seleziona **Chiudi** per salvare e chiudere il pannello.

1. Seleziona il numero di **Attributi** per ciascuna entità inclusa. Visualizzata la pagina **Gestisci gli attributi**.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Finestra di dialogo per selezionare il profiling dei dati.":::

   1. Crea nuovi attributi, modifica o elimina gli attributi esistenti. È possibile modificare il nome, il formato dei dati o aggiungere un tipo semantico.
   1. Per abilitare l'analisi e altre funzionalità, seleziona **Profiling dei dati** per l'intera entità o per attributi specifici. Per impostazione predefinita, nessuna entità è abilitata per il profiling dei dati.
   1. Seleziona **Fatto**.

1. Seleziona **Salva**. Verrà aperta la pagina **Origine dati** che mostra la nuova origine dati con stato **Aggiornamento in corso**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Il caricamento dei dati può richiedere tempo. Al termine dell'aggiornamento, i dati inseriti possono essere esaminati nella pagina [**Entità**](entities.md).

### <a name="create-a-new-schema-file"></a>Creare un nuovo file di schema

1. Seleziona **Nuovo file di schema**.

1. Immetti un nome per il file e seleziona **Salva**.

1. Seleziona **Nuova entità**. Viene visualizzato il pannello **Nuova entità**.

1. Immetti il nome dell'entità e scegli il **Percorso file di dati**.
   - **Più file csv o parquet**: accedi alla cartella radice, seleziona il tipo di modello e immetti l'espressione.
   - **File csv o parquet singolo**: passa al file csv o parquet e selezionalo.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Finestra di dialogo per creare una nuova entità con il percorso file di dati evidenziato.":::

1. Seleziona **Salva**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Finestra di dialogo per definire o generare automaticamente attributi.":::

1. Seleziona **definisci gli attributi** per aggiungere manualmente gli attributi o seleziona **generali automaticamente**. Per definire gli attributi, immetti un nome, seleziona il formato dei dati e il tipo semantico opzionale. Per gli attributi generati automaticamente:

   1. Dopo che gli attributi sono stati generati automaticamente, seleziona **Rivedi gli attributi**. Visualizzata la pagina **Gestisci gli attributi**.

   1. Assicurati che il formato dei dati sia corretto per ogni attributo.

   1. Per abilitare l'analisi e altre funzionalità, seleziona **Profiling dei dati** per l'intera entità o per attributi specifici. Per impostazione predefinita, nessuna entità è abilitata per il profiling dei dati.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Finestra di dialogo per selezionare il profiling dei dati.":::

   1. Seleziona **Fatto**. Viene visualizzata la pagina **Seleziona entità**.

1. Continua ad aggiungere entità e attributi, se applicabile.

1. Dopo aver aggiunto tutte le entità, seleziona **Includi** per includere le entità nell'inserimento dell'origine dati.

   :::image type="content" source="media/ADLS_required.png" alt-text="Finestra di dialogo che mostra Richiesto per la chiave primaria":::

1. Per le entità selezionate che richiedono l'inserimento incrementale, **Obbligatoria** viene visualizzato in **Aggiornamento incrementale**. Per ciascuna di queste entità, vedi [Configurare un aggiornamento incrementale per le origini dati di Azure Data Lake](incremental-refresh-data-sources.md).

1. Per le entità selezionate in cui non è stata definita una chiave primaria, **Obbligatoria** viene visualizzato in **Chiave primaria**. Per ciascuna di queste entità:
   1. Seleziona **Obbligatoria**. Viene visualizzato il pannello **Modifica entità**.
   1. Scegli la **chiave primaria**. La chiave primaria è un attributo univoco per l'entità. Affinché un attributo sia una chiave primaria valida, non deve includere valori duplicati, valori mancanti o valori null. Gli attributi del tipo di dati String, Integer e GUID sono supportati come chiavi primarie.
   1. Facoltativamente, modifica il modello di partizione.
   1. Seleziona **Chiudi** per salvare e chiudere il pannello.

1. Seleziona **Salva**. Verrà aperta la pagina **Origine dati** che mostra la nuova origine dati con stato **Aggiornamento in corso**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Il caricamento dei dati può richiedere tempo. Al termine dell'aggiornamento, i dati inseriti possono essere esaminati nella pagina [**Entità**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Modificare un'origine dati Azure Data Lake Storage

Puoi aggiornare l'opzione *Connettiti a un account di archiviazione usando*. Per altre informazioni, vedi [Connessione a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md). Per connetterti a un contenitore diverso dal tuo account di archiviazione o modificare il nome dell'account, [crea una nuova connessione all'origine dati](#connect-to-azure-data-lake-storage).

1. Vai a **Dati** > **Origini dati**.

1. Accanto all'origine dati che desideri aggiornare, seleziona **Modifica**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Finestra di dialogo per modificare l'origine dati Azure Data Lake.":::

1. Modifica una delle seguenti informazioni:

   - **Description**
   - **Connetti lo spazio di archiviazione tramite** e informazioni sulla connessione. Non puoi modificare le informazioni sul **Contenitore** durante l'aggiornamento della connessione.
      > [!NOTE]
      > Uno dei seguenti ruoli deve essere assegnato all'account di archiviazione o al contenitore:
        > - Lettore dati BLOB di archiviazione
        > - Proprietario dati BLOB di archiviazione
        > - Collaboratore dati BLOB di archiviazione

   - **Abilita collegamento privato** se desideri inserire i dati da un account di archiviazione tramite un collegamento privato di Azure. Per altre informazioni, vedi [Collegamenti privati](security-overview.md#set-up-an-azure-private-link).

1. Selezionare **Avanti**.
1. Esegui una delle modifiche seguenti:
   - Passa a un altro file model.json o manifest.json con un set di entità diverso dal contenitore.
   - Per aggiungere altre entità da inserire, seleziona **Nuova entità**.
   - Per rimuovere eventuali entità già selezionate se non ci sono dipendenze, seleziona l'entità, quindi **Elimina**.
      > [!IMPORTANT]
      > Se sono presenti dipendenze dal file model.json o manifest.json esistente e dal set di entità, verrà visualizzato un messaggio di errore e non sarà possibile selezionare un file model.json o manifest.json diverso. Rimuovi queste dipendenze prima di cambiare il file model.json o manifest.json o crea un nuovo origine dati con il file model.json o manifest.json che vuoi utilizzare per evitare di rimuovere le dipendenze.
   - Per modificare il percorso dei file di dati o la chiave primaria, seleziona **Modifica**.
   - Per modificare i dati di inserimento incrementale, vedi [Configurare un aggiornamento incrementale per le origini dati di Azure Data Lake](incremental-refresh-data-sources.md).
   - Modifica solo il nome dell'entità in modo che corrisponda al nome dell'entità nel file .json.

     > [!NOTE]
     > Mantieni sempre il nome dell'entità in Customer Insights uguale al nome dell'entità nel file model.json o manifest.json dopo l'inserimento. Customer Insights convalida tutti i nomi di entità con model.json o manifest.json durante ogni aggiornamento del sistema. Se il nome di un'entità viene modificato all'interno o all'esterno di Customer Insights, si verifica un errore perché Customer Insights non riesce a trovare il nuovo nome di entità nel file .json. Se il nome di un'entità inserito è stato modificato accidentalmente, modifica il nome dell'entità in Customer Insights di modo che corrisponda al nome nel file .json.

1. Seleziona **Attributi** per aggiungere o modificare attributi o per abilitare la profiling dei dati. Quindi seleziona **Fatto**.

1. Fai clic su **Salva** per applicare le modifiche e tornare alla pagina **Origine dati**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Motivi comuni per errori di inserimento o dati danneggiati

Durante l'inserimento dati, alcuni dei motivi più comuni per cui un record potrebbe essere considerato danneggiato includono:

- I tipi di dati e i valori dei campi tra il file di origine e lo schema non corrispondono
- Il numero di colonne nel file di origine non corrisponde allo schema
- I campi contengono caratteri che fanno sì che le colonne risultino sfalsate rispetto allo schema previsto. Ad esempio: virgolette formattate in modo errato, virgolette senza caratteri di escape, caratteri di nuova riga o caratteri di tabulazione.
- Mancano i file di partizione
- Se sono presenti colonne datetime/date/datetimeoffset, il loro formato deve essere specificato nello schema se non segue il formato standard.

### <a name="schema-or-data-type-mismatch"></a>Mancata corrispondenza dello schema o del tipo di dati

Se i dati non sono conformi allo schema, il processo di inserimento viene completato con errori. Correggere i dati di origine o lo schema e reinserire i dati.

### <a name="partition-files-are-missing"></a>Mancano i file di partizione

- Se l'inserimento ha avuto esito positivo senza record danneggiati, ma non è possibile visualizzare alcun dato, modifica il file model.json o manifest.json per assicurarti che le partizioni siano specificate. Quindi, [aggiorna l'origine dati](data-sources.md#refresh-data-sources).

- Se l'inserimento dati avviene contemporaneamente all'aggiornamento delle origini dati durante un aggiornamento pianificato automatico, i file di partizione potrebbero essere vuoti o non disponibili per l'elaborazione da parte di Customer Insights. Ai fini dell'allineamento con la pianificazione dell'aggiornamento a monte, modifica la [pianificazione di aggiornamento del sistema](schedule-refresh.md) o la pianificazione di aggiornamento per l'origine dati. Allinea le tempistiche in modo che gli aggiornamenti non avvengano tutti in una volta e vengano forniti i dati più recenti da elaborare in Customer Insights.

### <a name="datetime-fields-in-the-wrong-format"></a>Formato errato dei campi datetime

I campi datetime nell'entità non sono nei formati ISO 8601 o en-US. Il formato datetime predefinito in Customer Insights è il formato en-US. Tutti i campi datetime in un'entità devono essere nello stesso formato. Customer Insights supporta altri formati, a condizione che le annotazioni o i tratti vengano creati a livello di origine o di entità nel modello o nel file manifest.json. Ad esempio: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  In un manifest.json, il formato datetime può essere specificato a livello di entità o di attributo. A livello di entità, usa "exhibitsTraits" nell'entità in *.manifest.cdm.json per definire il formato datetime. A livello di attributo, usa "appliedTraits" nell'attributo in entityname.cdm.json.

**Manifest.json a livello di entità**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json a livello di entità**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
