---
title: Arricchimento con l'arricchimento di terze parti di HERE Technologies
description: Informazioni generali sull'arricchimento di terze parti di HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597746"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Arricchimento dei profili cliente con HERE Technologies (anteprima)

HERE Technologies è una società di piattaforme di localizzazione che fornisce dati e servizi incentrati sulla posizione. Con i servizi di arricchimento dei dati di HERE Technologies, puoi creare una comprensione più precisa della posizione dei tuoi clienti con la normalizzazione degli indirizzi, l'estrazione di latitudine e longitudine e altro ancora.

## <a name="prerequisites"></a>Prerequisiti

Per configurare gli arricchimenti di HERE Technologies, è necessario soddisfare i seguenti prerequisiti:

- Devi disporre di una sottoscrizione di HERE Technologies. Per ottenere una sottoscrizione, puoi [iscriverti qui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [contatta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direttamente. [Ulteriori informazioni sull'arricchimento della posizione di HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Devi disporre della chiave API di HERE Technologies.

- Devi avere autorizzazioni di [amministratore](permissions.md#administrator).

## <a name="configuration"></a>Configurazione

1. Vai a **Dati** > **Arricchimento**.

1. Seleziona **Arricchisci i miei dati** nel riquadro HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Riquadro HERE Technologies](media/HERE-tile.png "Riquadro HERE Technologies")

1. Immetti una **chiave API di HERE Technologies**. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**. 

1. Conferma entrambi gli input selezionando **Connettiti a HERE**.

1.  Seleziona **Aggiungi dati** e scegli il **Set di dati cliente** che vuoi arricchire con i dati sulla posizione di HERE Technologies. Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. Scegli se desideri mappare i campi all'indirizzo principale e/o secondario. Puoi specificare un mapping dei campi per entrambi gli indirizzi (ad esempio, un indirizzo abitazione e un indirizzo ufficio) e arricchire i profili per entrambi gli indirizzi separatamente. Seleziona **Avanti**.

1. Definisci quali campi dei profili unificati devono essere utilizzati per cercare dati di localizzazione corrispondenti di HERE Technologies. I campi **Via 1** e **Codice postale** sono obbligatori per l'indirizzo principale e/o secondario selezionato. Per una maggiore precisione della corrispondenza, è possibile aggiungere più campi.

   > [!div class="mx-imgBorder"]
   > ![Pagina di configurazione dell'arricchimento di HERE Technologies](media/enrichment-HERE-configuration.png "Pagina di configurazione dell'arricchimento di HERE Technologies")

1. Seleziona **Applica** per completare il mapping dei campi.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipenderà dalle dimensioni dei dati cliente e dai tempi di risposta API di HERE Technologies.

Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**. Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a HERE Technologies, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che HERE Technologies rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]