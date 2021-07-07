---
title: Arricchimento con l'arricchimento di terze parti di HERE Technologies
description: Informazioni generali sull'arricchimento di terze parti di HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305299"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Arricchimento dei profili cliente con HERE Technologies (anteprima)

HERE Technologies è una società di piattaforme di localizzazione che fornisce dati e servizi incentrati sulla posizione. Con i servizi di arricchimento dei dati di HERE Technologies, puoi creare una comprensione più precisa della posizione dei tuoi clienti con la normalizzazione degli indirizzi, l'estrazione di latitudine e longitudine e altro ancora.

## <a name="prerequisites"></a>Prerequisiti

Per configurare gli arricchimenti di HERE Technologies, è necessario soddisfare i seguenti prerequisiti:

- Devi disporre di una sottoscrizione di HERE Technologies. Per ottenere una sottoscrizione, puoi [iscriverti qui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [contatta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direttamente. [Ulteriori informazioni sull'arricchimento della posizione di HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Una [connessione](connections.md) HERE è disponibile *o* hai le autorizzazioni [amministratore](permissions.md#administrator) e la chiave API di HERE Technologies.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento**. 

1. Seleziona **Arricchisci i miei dati** nel riquadro HERE Technologies e seleziona **Attività iniziali**.

   > [!div class="mx-imgBorder"]
   > ![Riquadro HERE Technologies](media/HERE-tile.png "Riquadro HERE Technologies")

1. Seleziona una [connessione](connections.md) dall'elenco a discesa. Contatta un amministratore se non è disponibile alcuna connessione. Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione**. Scegli **HERE Technologies** dall'elenco a discesa. 

1. Seleziona **Connettiti a HERE Technologies** per confermare la selezione.

1.  Seleziona **Avanti** e scegli il **set di dati del cliente** che desideri arricchire con i dati della posizione di HERE Technologies. Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. Scegli se desideri mappare i campi all'indirizzo principale e/o secondario. Puoi specificare un mapping del campo per entrambi gli indirizzi e arricchire i profili per entrambi gli indirizzi separatamente. Ad esempio, se sono presenti una casa e un indirizzo aziendale. Seleziona **Avanti**.

1. Definisci quali campi dei profili unificati devono essere utilizzati per cercare dati di localizzazione corrispondenti di HERE Technologies. I campi **Via 1** e **Codice postale** sono obbligatori per l'indirizzo principale e/o secondario selezionato. Per una maggiore precisione della corrispondenza, è possibile aggiungere più campi.

   > [!div class="mx-imgBorder"]
   > ![Pagina di configurazione dell'arricchimento di HERE Technologies](media/enrichment-HERE-configuration.png "Pagina di configurazione dell'arricchimento di HERE Technologies")

1. Seleziona **Avanti** per completare il mapping del campo.

1. Immetti un nome per l'arricchimento. 

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

## <a name="configure-the-connection-for-here-technologies"></a>Configurazione della connessione per HERE Technologies 

Devi essere un amministratore per configurare le connessioni. Seleziona **Aggiungi connessione** quando si configura un arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro HERE technologies.

1. Immetti un nome per la connessione nella casella **nome visualizzato**.

1. Fornisci una chiave API HERE Technologies valida.

1. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione.

1. Dopo aver completato la verifica, seleziona **Salva**.

   > [!div class="mx-imgBorder"]
   > ![Pagina di configurazione della connessione di HERE technologies](media/enrichment-HERE-connection.png "Pagina di configurazione della connessione di HERE technologies")

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipenderà dalle dimensioni dei dati cliente e dai tempi di risposta API di HERE Technologies.

Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**. Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Crea [segmenti](segments.md) e [misure](measures.md) e persino [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a HERE Technologies, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che HERE Technologies rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
