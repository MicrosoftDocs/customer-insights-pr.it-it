---
title: Arricchimento con l'arricchimento di terze parti Experian
description: Informazioni generali sull'arricchimento di terze parti Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896378"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Arricchisci i profili cliente con i dati demografici di Experian (anteprima)

Experian è un leader globale nei servizi di marketing e reporting del credito al consumo e alle imprese. Con Servizi di arricchimento dei dati di Experian, puoi acquisire una conoscenza più approfondita dei tuoi clienti arricchendo i tuoi profili cliente con dati demografici come le dimensioni del nucleo familiare, il reddito e altro ancora.

## <a name="prerequisites"></a>Prerequisiti

Per configurare Experian, devono essere rispettati i seguenti requisiti:

- Hai un abbonamento Experian attivo. Per ottenere un abbonamento, [contatta Experian](https://www.experian.com/marketing-services/contact) direttamente. [Altre informazioni sull'arricchimento dei dati Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Una connessione Experian è già stata configurata da un amministratore *o* hai le autorizzazioni di [amministratore](permissions.md#administrator). È inoltre necessario l'ID utente, l'ID parte e il numero di modello per l'account SSH-enabled Secure Transport (ST) che Experian ha creato per te.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** nel riquadro Experian.

   > [!div class="mx-imgBorder"]
   > ![Riquadro Experian](media/experian-tile.png "Riquadro Experian")
   > 

1. Seleziona una [connessione](connections.md) nell'elenco a discesa. Contatta un amministratore se non è disponibile alcuna connessione. Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione** e scegliendo Experian dal menu a discesa. 

1. Seleziona **Connettiti a Experian** per confermare la selezione della connessione.

1.  Seleziona **Avanti** e scegli il **set di dati del cliente** che desideri arricchire con i dati demografici di Experian. Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. Seleziona **Avanti** e definisci quale tipo di campi dei profili unificati devono essere utilizzati per cercare i dati demografici corrispondenti di Experian. Almeno uno dei campi **Nome e indirizzo**, **Telefono**, o **E-mail** è obbligatorio. Per una maggiore precisione della corrispondenza, è possibile aggiungere fino a due altri campi. Questa selezione influenzerà i campi di mapping a cui hai accesso nel passaggio successivo.

    > [!TIP]
    > Più attributi dell'identificatore chiave inviati a Experian probabilmente producono un tasso di corrispondenza più elevato.

1. Seleziona **Avanti** per iniziare il mapping del campo.

1. Definisci quali campi dei profili unificati devono essere utilizzati per cercare i dati demografici corrispondenti di Experian. I campi obbligatori sono contrassegnati.

1. Fornisci un nome per l'arricchimento e un nome per l'entità di output.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

## <a name="configure-the-connection-for-experian"></a>Configurare la connessione per Experian 

Devi essere un amministratore per configurare le connessioni. Seleziona **Aggiungi connessione** quando si configura un arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Experian.

1. Seleziona **Inizia subito**.

1. Immetti un nome per la connessione nella casella **nome visualizzato**.

1. Inserisci un ID utente, un ID parte e un numero di modello validi per il tuo account Experian Secure Transport.

1. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**

1. Seleziona **Verifica** per convalidare la configurazione.

1. Dopo aver completato la verifica, seleziona **Salva**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Riquadro di configurazione della connessione Experian.":::

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipenderà dalle dimensioni dei tuoi dati cliente e dai processi di arricchimento impostati per il tuo account da Experian.

Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**. Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Experian, consenti il trasferimento di dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma hai la responsabilità di assicurarti che Experian rispetti gli obblighi di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
