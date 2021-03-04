---
title: Connettere i dati di Common Data Model a un account Azure Data Lake
description: Utilizza i dati di Common Data Model con Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267865"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Connettere a una cartella Common Data Model usando un account Azure Data Lake

Questo articolo fornisce informazioni su come inserire dati di una cartella Common Data Model utilizzando l'account Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Considerazioni importanti

- I dati in Azure Data Lake devono seguire lo standard Common Data Model. Altri formati non sono supportati al momento.

- L'inserimento dati supporta esclusivamente gli account di archiviazione di Azure Data Lake *Gen2*. Non puoi usare account di archiviazione di Azure Data Lake Gen1 per inserire i dati.

- Per eseguire l'autenticazione con un'entità servizio di Azure, assicurati che sia configurata nel tenant. Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md).

- L'Azure Data Lake da cui intendi eseguire la connessione e inserire i dati deve trovarsi nella stessa area di Azure dell'ambiente Dynamics 365 Customer Insights. Le connessioni a una cartella di Common Data Model da un data lake in un'area diversa di Azure non sono supportate. Per conoscere l'area di Azure dell'ambiente, seleziona **Amministratore** > **Sistema** > **Informazioni** in Audience Insights.

- I dati memorizzati nei servizi online possono essere archiviati in una posizione diversa da quella in cui i dati vengono elaborati o archiviati in Dynamics 365 Customer Insights.Importando o connettendoti a dati archiviati nei servizi online, accetti che i dati possano essere trasferiti e archiviati con Dynamics 365 Customer Insights. [Altre informazioni sono disponibili nel Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Connetti a cartella di Common Data Model

1. In Audience Insights, vai a **Dati** > **Origini dati**.

1. Seleziona **Aggiungi origine dati**.

1. Seleziona **Connetti a cartella di Common Data Model**, immetti un **Nome** per l'origine dati e seleziona **Avanti**. Linee guida per i nomi: 
   - Deve iniziare con una lettera.
   - Usa solo lettere e numeri. Gli spazi e i caratteri speciali non sono consentiti.
   - Usa tra 3 e 64 caratteri.

1. Puoi scegliere tra l'utilizzo di un'opzione basata su risorse e un'opzione basata su sottoscrizione per l'autenticazione. Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md). Immetti le informazioni relative al **Contenitore** e seleziona **Avanti**.
   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo di immissione dei dettagli della nuova connessione per Azure Data Lake](media/enter-new-storage-details.png)
   > [!NOTE]
   > È necessario uno dei seguenti ruoli per il contenitore o l'account di archiviazione di cui sopra per essere in grado di connettersi e creare un'origine dati:
   >  - Lettore dati BLOB di archiviazione
   >  - Proprietario dati BLOB di archiviazione
   >  - Collaboratore dati BLOB di archiviazione

1. Nella finestra di dialogo **Seleziona una cartella di Common Data Model** , seleziona il file model.json o manifest.json da cui importare i dati e seleziona **Avanti**.
   > [!NOTE]
   > Qualsiasi file model.json o manifest.json associato a un'altra origine dati nell'ambiente non verrà visualizzato nell'elenco.

1. Otterrai un elenco di entità disponibili nel file model.json o manifest.json selezionato. Puoi rivedere e selezionare dall'elenco di entità disponibili e selezionare **Salva**. Tutte le entità selezionate verranno inserite dalla nuova origine dati.
   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo che mostra un elenco di entità da un file model.json](media/review-entities.png)

8. Specifica le entità di dati per cui vuoi abilitare il profiling dei dati e seleziona **Salva**. Il profiling dei dati consente l'analisi e altre funzionalità. Puoi selezionare l'intera entità, che seleziona tutti gli attributi dall'entità, o selezionare alcuni attributi di tua scelta. Per impostazione predefinita, nessuna entità è abilitata per il profiling dei dati.
   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo che mostra un profiling dei dati](media/dataprofiling-entities.png)

9. Dopo aver salvato le selezioni, viene visualizzata la pagina **Origini dati**. Ora la connessione alla cartella Common Data Model viene visualizzata come origine dati.

> [!NOTE]
> Un file model.json o manifest.json può essere associato solo a un'origine dati nello stesso ambiente. Tuttavia, lo stesso file model.json o manifest.json può essere utilizzato per origini dati in più ambienti.

## <a name="edit-a-common-data-model-folder-data-source"></a>Modificare un'origine dati della cartella Common Data Model

Puoi aggiornare la chiave di accesso per l'account di archiviazione contenente la cartella di Common Data Model. Puoi anche modificare il file model.json o manifest.json. Per connetterti a un contenitore diverso dal tuo account di archiviazione o modificare il nome dell'account, [crea una nuova connessione all'origine dati](#connect-to-a-common-data-model-folder).

1. In Audience Insights, vai a **Dati** > **Origini dati**.

2. Accanto all'origine dati che vuoi aggiornare, seleziona i puntini di sospensione.

3. Seleziona l'opzione **Modifica** nell'elenco.

4. Facoltativamente, aggiorna il valore di **Chiave di accesso** e seleziona **Avanti**.

   ![Finestra di dialogo per modificare e aggiornare una chiave di accesso per un'origine dati esistente](media/edit-access-key.png)

5. Facoltativamente, puoi eseguire l'aggiornamento da una connessione con chiave dell'account a una connessione basata su risorse o sottoscrizione. Per ulteriori informazioni, vedi [Connettere Audience Insights a un account Azure Data Lake Storage Gen2 con un'entità servizio di Azure](connect-service-principal.md). Non puoi modificare le informazioni sul **Contenitore** durante l'aggiornamento della connessione.
   > [!div class="mx-imgBorder"]

   > ![Finestra di dialogo per immettere i dettagli di connessione per Azure Data Lake a un account di archiviazione esistente](media/enter-existing-storage-details.png)

   > [!NOTE]
   > È necessario uno dei seguenti ruoli per il contenitore o l'account di archiviazione di cui sopra per essere in grado di connettersi e creare un'origine dati:
   >  - Lettore dati BLOB di archiviazione
   >  - Proprietario dati BLOB di archiviazione
   >  - Collaboratore dati BLOB di archiviazione


6. Facoltativamente, scegli un file model.json o manifest.json diverso con un set di entità diverso dal contenitore.

7. Facoltativamente, puoi selezionare entità aggiuntive da inserire. Puoi anche rimuovere qualsiasi entità già selezionata se non ci sono dipendenze.

   > [!IMPORTANT]
   > Se sono presenti dipendenze dal file model.json o manifest.json esistente e dal set di entità, verrà visualizzato un messaggio di errore e non sarà possibile selezionare un file model.json o manifest.json diverso. Rimuovi queste dipendenze prima di cambiare il file model.json o manifest.json o crea un nuovo origine dati con il file model.json o manifest.json che vuoi utilizzare per evitare di rimuovere le dipendenze.

8. Facoltativamente, puoi selezionare attributi o entità aggiuntivi per abilitare il profilng dei dati o disabilitare quelli già selezionati.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]