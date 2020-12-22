---
title: Completare i dati parziali con le previsioni
description: Utilizza le previsioni per riempire dati cliente incompleti.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648716"
---
# <a name="complete-your-partial-data-with-predictions"></a>Completare i dati parziali con le previsioni

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Le previsioni consentono di creare facilmente valori stimati che possono migliorare la comprensione di un cliente. Nella pagina **Intelligenza** > **Predizioni**, puoi selezionare **Le mie previsioni** per visualizzare le previsioni che hai configurato in altre parti di Audience Insights e consentirti di personalizzarle ulteriormente.

> [!NOTE]
> Non è possibile usare questa funzionalità se l'ambiente usa l'archiviazione di Azure Data Lake Gen 2.
>
> La funzione di previsione utilizza strumenti automatici per valutare i dati e fare previsioni basate su tali dati, quindi può essere utilizzata come metodo di profiling, in base a come tale termine è definito dal Regolamento generale sulla protezione dei dati ("GDPR"). L'uso da parte del cliente di questa funzionalità per elaborare i dati può essere soggetto al GDPR o ad altre leggi o normative. Devi assicurarti che il tuo utilizzo di Dynamics 365 Customer Insights, comprese le previsioni, sia conforme a tutte le leggi e le norme applicabili, comprese le leggi relative alla privacy, ai dati personali, ai dati biometrici, alla protezione dei dati e alla riservatezza delle comunicazioni.

## <a name="prerequisites"></a>Prerequisiti

Prima che l'organizzazione possa utilizzare la funzionalità di previsioni, i prerequisiti seguenti devono essere soddisfatti:

1. La tua organizzazione ha un'istanza [configurata in Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) ed è nella stessa organizzazione di Customer Insights.

2. L'ambiente è associato alla tua istanza di Common Data Service.

Se [crei un nuovo ambiente](manage-environments.md), configuralo nella finestra di dialogo **Crea ambiente** e seleziona **Avanzate**. Se hai già creato un ambiente, vai alle relative impostazioni e seleziona **Avanzate**. In ogni caso, nella sezione **Usa previsioni**, inserisci l'URL dell'istanza Common Data Service a cui desideri associare il tuo ambiente.

## <a name="create-a-prediction-in-the-customer-entity"></a>Creare una previsione nell'entità Cliente

1. In Audience Insights, vai a **Dati** > **Entità**.

2. Seleziona l'entità **Cliente**.

3. Nell'entità **Cliente: CustomerInsights** seleziona la scheda **Campi**.

4. Individua il nome dell'attributo per il quale desideri prevedere i valori, quindi seleziona l'icona **Panoramica** nella colonna **Riepilogo**.
   > [!div class="mx-imgBorder"]
   > ![Icona Panoramica](media/intelligence-overviewicon.png "Icona Panoramica")

5. Se è presente un'alta percentuale di valori mancanti per l'attributo, seleziona **Prevedi valori mancanti** per continuare con la previsione.
   > [!div class="mx-imgBorder"]
   > ![Stato Panoramica con il pulsante Prevedi valori mancanti visualizzato](media/intelligence-overviewpredictmissingvalues.png "Stato Panoramica con il pulsante Prevedi valori mancanti visualizzato")

6. Inserisci un **nome visualizzato** e un **nome di entità output** per i risultati della previsione.

7. Un elenco precompilato di opzioni mostrerà dove è possibile mappare i valori a una categoria stimata. In questo caso, le uniche opzioni di categoria saranno 0 o 1 in quanto vengono mappate alla natura vera/falsa o binaria della previsione. Nella colonna Categoria, mappa i valori dei campi che desideri classificare come "0" nella previsione finale a "0" e gli elementi che desideri classificare come "1" nella previsione finale a "1".
   > [!div class="mx-imgBorder"]
   > ![Esempio che mostra i valori dei campi mappati alle categorie](media/intelligence-categorymapping.png "Esempio che mostra i valori dei campi mappati alle categorie")

8. Seleziona **Fatto** e la previsione verrà elaborata. L'elaborazione richiederà del tempo, a seconda delle dimensioni e della complessità dei dati. I risultati saranno disponibili in una nuova entità basata sul **nome dell'entità output** della previsione creata.

## <a name="create-a-prediction-while-creating-a-segment"></a>Creare una previsione durante la creazione di un segmento

La previsione dei valori mancanti per un attributo specifico è possibile anche durante la creazione di un segmento. In particolare, quando crei rapidamente un segmento basato sull'entità cliente unificata o sull'entità Customer_Measure.

Come parte di questo flusso scegli un attributo specifico su cui basare il segmento, ad esempio Soddisfazione del cliente o Importo acquisto. Alla creazione del segmento, il sistema suggerirà un metodo per prevedere eventuali valori mancanti per questo attributo.

1. In Audience Insights, vai a **Segmenti** e seleziona il riquadro **Profili**.

2. Scegli un **campo** su cui creare un segmento e seleziona un **operatore** , quindi seleziona **Revisione**.

3. Assegna un **nome** e un **nome visualizzato** al segmento.

4. Seleziona **Salva**.

5. Se il segmento creato contiene dati incompleti nel campo di origine, è possibile scegliere di prevedere i valori mancanti.
   > [!div class="mx-imgBorder"]
   > ![Pulsante Previsione](media/segments-predictoption.png "Pulsante Previsione")

6. Inserisci un **nome visualizzato** e un **nome di entità output** per i risultati della previsione.

7. Seleziona **Fine**. La previsione verrà generata a breve in una nuova entità con il nome fornito per il **nome dell'entità output**.

## <a name="view-a-prediction"></a>Visualizzare una previsione

1. In Audience Insights, vai a **Intelligenza** > **Previsioni** > **Le mie previsioni**.

2. Seleziona la previsione da rivedere.

3. Seleziona i puntini di sospensione nella colonna **Azioni** e scegli **Visualizza**.

4. Vedrai una serie di punti dati nella visualizzazione della previsione.
   > [!div class="mx-imgBorder"]
   > ![Pagina Previsioni](media/intelligence-predictionsviewpage.png "Pagina Previsioni")

   - I **valori previsti** mostrano il mapping creato durante la fase di mapping del valore Campo alla Categoria. Questi sono i valori nel set di dati che sono stati mappati a una categoria specifica.
   -**I principali influencer** sono i fattori all'interno del set di dati che hanno più probabilità di influenzare l'attendibilità della previsione del valore Campo mappato a una categoria specifica.
   - **Le prestazioni** indicano l'andamento delle previsioni. Per ulteriori informazioni, seleziona il collegamento.
   - **L'anteprima** mostra esempi del set di dati di output dalla previsione e la probabilità, o l'attendibilità, del valore previsto, dove 0 è incerto e 1 è certo.

## <a name="update-a-prediction"></a>Aggiornare una previsione

1. In Audience Insights, vai a **Intelligenza** > **Previsioni** > **Le mie previsioni**.

2. Seleziona la previsione da aggiornare e seleziona l'icona **Aggiorna**.

3. La previsione verrà pianificata per l'elaborazione. È possibile visualizzare l'ora dell'ultimo aggiornamento nella colonna **Aggiornato** della pagina **Previsioni**.

## <a name="edit-a-prediction"></a>Modificare una previsione

Dopo aver creato una previsione, è possibile personalizzare il modello in AI Builder per aumentare l'efficacia del modello.  

1. In Audience Insights, vai a **Intelligenza** > **Previsioni** > **Le mie previsioni**.

2. Seleziona la previsione che desideri modificare.

3. Seleziona i puntini di sospensione nella colonna **Azioni** e scegli **Visualizza**.

4. Seleziona **Personalizza in AI Builder**.

5. Aggiorna il modello in AI Builder. [Ulteriori informazioni sulla gestione dei modelli in AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).

La successiva esecuzione della previsione utilizzerà il modello aggiornato creato.

> [!NOTE]
> I nuovi modelli creati in AI Builder non verranno visualizzati in Audience Insights a meno che il modello non sia stato creato sulla base delle esperienze elencate sopra.

## <a name="remove-a-prediction"></a>Rimuovere una previsione

1. In Audience Insights, vai a **Intelligenza** > **Previsioni** > **Le mie previsioni**.

2. Seleziona la previsione che desideri eliminare.

3. Seleziona i puntini di sospensione nella colonna **Azioni** e scegli **Elimina**.

4. Conferma l'eliminazione.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Se non riesci a completare il processo di Common Data Service associato a causa di un errore, puoi provare a completare il processo manualmente. Esistono due problemi noti che possono verificarsi nel processo di collegamento:

- Il componente aggiuntivo Scheda cliente non è installato.
    1. Completa le istruzioni per [installare e configurare la soluzione](customer-card-add-in.md).

- Le autorizzazioni dell'app non sono concesse.
    1. Passare a [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Seleziona **Ambienti**.
    1. Seleziona i puntini di sospensione accanto all'ambiente a cui desideri aggiungere l'autorizzazione e seleziona **Impostazioni**.
    1. Espandi **Utenti + autorizzazioni** e seleziona **Utenti**.
    1. Seleziona **+ Nuovo** e seleziona **Utente**.
    1. Seleziona **Utente dell'applicazione** se non è già selezionato e immetti le seguenti informazioni:
        - **Nome utente:** cihelp@microsoft.com
        - **ID applicazione:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Nome:** cliente
        - **Cognome:** informazioni dettagliate
        - **Indirizzo di posta elettronica primario:** cihelp@microsoft.com
    1. Seleziona **Salva e chiudi**.
    1. Seleziona l'utente appena creata.
    1. Seleziona **Gestisci ruoli** nella barra di menu superiore.
    1. Seleziona **Amministratore di sistema**, quindi seleziona **OK**.
