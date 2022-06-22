---
title: Arricchimento con l'arricchimento di terze parti Experian
description: Informazioni generali sull'arricchimento di terzi parti Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 735da18e584b0d9db76b557f4d16dbdf1757f33c
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954092"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Arricchimento dei profili dei clienti con i dati demografici di Experian (anteprima)

Experian è leader globale nei servizi di marketing e rendicontazione creditizia dei consumatori e delle imprese. Con i servizi di arricchimento dei dati di Experian puoi approfondire la conoscenza dei tuoi clienti arricchendo i loro profili con dati demografici come dimensioni del nucleo familiare, reddito e altro ancora.

## <a name="supported-countriesregions"></a>Paesi/aree geografiche supportati

Attualmente supportiamo l'arricchimento dei profili dei clienti solo negli Stati Uniti.

## <a name="prerequisites"></a>Prerequisiti

- Una sottoscrizione Experian attiva. Per ottenere una sottoscrizione, [contatta Experian](https://www.experian.com/marketing-services/contact) direttamente. [Altre informazioni su Arricchimento dei dati di Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Una [connessione](connections.md) Experian [configurata](#configure-the-connection-for-experian) da un amministratore.

- ID utente, ID parte e numero modello Experian per l'account ST (Secure Transport) abilitato per SSH creato da Experian.

## <a name="configure-the-connection-for-experian"></a>Configurazione della connessione per Experian

Devi essere un [amministratore](permissions.md#admin) in Customer Insights e avere un ID utente, un ID parte e un numero modello Experian.

1. Seleziona **Aggiungi connessione** quando configuri un arricchimento o vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Riquadro di configurazione della connessione di Experian.":::

1. Immetti un nome per la connessione e un ID utente, un ID parte e Numero modello validi per il tuo account Secure Transport Experian.

1. Rivedi e fornisci il tuo consenso per [Conformità e privacy dei dati](#data-privacy-and-compliance) selezionando **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione e quindi seleziona **Salva**.

### <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Experian, consenti il trasferimento di dati al di fuori del limite di conformità per Dynamics 365 Customer Insights, inclusi i dati potenzialmente sensibili come i Dati Personali. Microsoft trasferirà tali dati alle tue condizioni ma sei tu a dover garantire che Experian soddisfi tutti gli obblighi di privacy e sicurezza che sei tenuto a rispettare. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** in **Dati demografici** nel riquadro Mappe di Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Riquadro Experian nella pagina della panoramica dell'arricchimento. ":::

1. Esamina la panoramica e quindi seleziona **Avanti**.

1. Seleziona la connessione. Contatta un amministratore se uno non è disponibile.

1. Selezionare **Avanti**.

1. Seleziona **Set di dati cliente** e scegli il profilo o il segmento che vuoi arricchire con i dati demografici di Experian. L'entità *Cliente* arricchisce tutti i tuoi profili cliente se un segmento arricchisce solo i profili cliente contenuti in quel segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. Definisci il tipo di campi per i tuoi profili unificati da usare per i dati demografici corrispondenti di Experian. Almeno uno dei campi **Nome e indirizzo**, **Telefono**, o **E-mail** è obbligatorio. Per una maggiore accuratezza di corrispondenza, aggiungi altri campi. Selezionare **Avanti**.

1. Mappa i tuoi campi ai dati demografici di Experian.

1. Seleziona **Avanti** per completare il mapping del campo.

1. Specifica un **Nome** per l'arricchimento e il **Nome entità di output**.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

1. Seleziona **Esegui** per avviare il processo di arricchimento o chiudere per tornare alla pagina **Arricchimenti**.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Il campo **Numero di clienti arricchiti per campo** fornisce un'analisi dettagliata della copertura di ciascun campo arricchito.

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
