---
title: Arricchimento con l'arricchimento di terze parti Experian
description: Informazioni generali sull'arricchimento di terzi parti Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309825"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Arricchimento dei profili dei clienti con i dati demografici di Experian (anteprima)

Experian è leader globale nei servizi di marketing e rendicontazione creditizia dei consumatori e delle imprese. Con i servizi di arricchimento dei dati di Experian puoi approfondire la conoscenza dei tuoi clienti arricchendo i loro profili con dati demografici come dimensioni del nucleo familiare, reddito e altro ancora.

## <a name="prerequisites"></a>Prerequisiti

Per configurare Experian, devono essere rispettati i seguenti requisiti:

- Devi disporre di una sottoscrizione attiva di Experian. Per ottenere una sottoscrizione, [contatta Experian](https://www.experian.com/marketing-services/contact) direttamente. [Altre informazioni su Arricchimento dei dati di Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Una connessione Experian è già stata configurata da un amministratore *o* hai le autorizzazioni di [amministratore](permissions.md#administrator). È inoltre necessario l'ID utente, l'ID parte e il numero modello per l'account Secure Transport (ST) abilitato per SSH che Experian creato per te.

## <a name="supported-countriesregions"></a>Paesi/aree geografiche supportati

Attualmente supportiamo l'arricchimento dei profili dei clienti solo negli Stati Uniti.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** nel riquadro di Experian.

   > [!div class="mx-imgBorder"]
   > ![Experian riquadri](media/experian-tile.png "Experian tile")
   > 

1. Seleziona una [connessione](connections.md) dall'elenco a discesa. Contatta un amministratore se non è disponibile alcuna connessione. Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione** e scegliendo Experian dall'elenco a discesa. 

1. Seleziona **Connetti a Experian** per confermare la selezione della connessione.

1.  Seleziona **Avanti** e scegli il **Set di dati cliente** che vuoi arricchire con i dati demografici di Experian. Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. Seleziona **Avanti** e definisci il tipo di campi dei tuoi profili unificati da utilizzare per cercare i dati demografici corrispondenti in Experian. Almeno uno dei campi **Nome e indirizzo**, **Telefono**, o **E-mail** è obbligatorio. Per una maggiore precisione della corrispondenza, è possibile aggiungere fino a due altri campi. Questa selezione influenzerà i campi di mapping a cui hai accesso nel passaggio successivo.

    > [!TIP]
    > Altri attributi identificativi chiave inviati a Experian produrranno probabilmente un tasso di corrispondenza più elevato.

1. Seleziona **Avanti** per iniziare il mapping del campo.

1. Definisci quali campi dei tuoi profili unificati utilizzare per cercare i dati demografici corrispondenti in Experian. I campi obbligatori sono contrassegnati.

1. Fornisci un nome per l'arricchimento e un nome per l'entità di output.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

## <a name="configure-the-connection-for-experian"></a>Configurazione della connessione per Experian 

Devi essere un amministratore per configurare le connessioni. Seleziona **Aggiungi connessione** quando configuri un arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Experian.

1. Seleziona **Inizia subito**.

1. Immetti un nome per la connessione nella casella **nome visualizzato**.

1. Inserisci un ID utente, un ID parte e un numero di modello validi per il tuo account di trasporto sicuro Experian.

1. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione.

1. Dopo aver completato la verifica, seleziona **Salva**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Riquadro di configurazione della connessione di Experian.":::

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipenderà dalle dimensioni dei dati dei tuoi clienti e dai processi di arricchimento impostati per il tuo account da Experian.

Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**. Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Crea [segmenti](segments.md) e [misure](measures.md) e persino [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Experian, consenti il trasferimento di dati al di fuori del limite di conformità per Dynamics 365 Customer Insights, inclusi i dati potenzialmente sensibili come i Dati Personali. Microsoft trasferirà tali dati alle tue condizioni ma sei tu a dover garantire che Experian soddisfi tutti gli obblighi di privacy e sicurezza che sei tenuto a rispettare. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
