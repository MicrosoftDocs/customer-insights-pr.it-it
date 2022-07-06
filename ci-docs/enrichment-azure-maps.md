---
title: Arricchire i profili dei clienti con i dati di posizione di Mappe di Azure (anteprima)
description: Informazioni generali sull'arricchimento di prima parte di Mappe di Azure.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: dfadc08f67beac3fded1a97e557ee9e1880664e0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052612"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Arricchire i profili dei clienti con i dati di posizione di Mappe di Azure (anteprima)

Mappe di Azure fornisce dati e servizi incentrati sulla posizione per offrire esperienze basate su dati geospaziali con informazioni sulla posizione integrate. I servizi di arricchimento dei dati di Mappe di Azure migliorano la precisione delle informazioni sulla posizione dei clienti. Offre funzionalità come la normalizzazione degli indirizzi e l'estrazione di latitudine e longitudine in Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prerequisiti

- Una sottoscrizione di Mappe di Azure attiva. Per ottenere una sottoscrizione, [iscriviti o ottieni una versione di prova gratuita](https://azure.microsoft.com/services/azure-maps/).

- Una [connessione](connections.md) di Mappe di Azure è [configurata](#configure-the-connection-for-azure-maps) da un amministratore.

## <a name="configure-the-connection-for-azure-maps"></a>Configurare la connessione per Mappe di Azure

Devi essere un [amministratore](permissions.md#admin) in Customer Insights e avere una chiave API di Mappe di Azure attiva.

1. Seleziona **Aggiungi connessione** quando configuri un arricchimento o vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Mappe di Azure.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Pagina di configurazione della connessione di Mappe di Azure.":::

1. Immetti un nome per la connessione e una chiave API di Mappe di Azure valida.

1. Rivedi e fornisci il tuo consenso per [Conformità e privacy dei dati](#data-privacy-and-compliance) selezionando **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione e quindi seleziona **Salva**.

### <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Mappe di Azure, consenti il trasferimento di dati al di fuori del limite di conformità per Dynamics 365 Customer Insights, inclusi i dati potenzialmente sensibili come i Dati Personali. Microsoft trasferirà tali dati su tua istruzione, ma sei tenuto a garantire che Mappe di Azure soddisfi qualsiasi obbligo di privacy o sicurezza che potresti avere. Per maggiori informazioni, vai a [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** in **Posizione** nel riquadro Mappe di Microsoft Azure.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Riquadro Mappe di Azure.":::

1. Esamina la panoramica e quindi seleziona **Avanti**.

1. Seleziona la connessione. Contatta un amministratore se non è disponibile alcuna connessione.

1. Selezionare **Avanti**.

1. Seleziona **Set di dati cliente** e scegli il profilo o il segmento che vuoi arricchire con i dati di Microsoft. L'entità *Cliente* arricchisce tutti i tuoi profili cliente se un segmento arricchisce solo i profili cliente contenuti in quel segmento.

1. Definisci quale tipo di campi dei tuoi profili unificati usare per la corrispondenza: l'indirizzo primario e/o secondario. Puoi specificare un mapping del campo per entrambi gli indirizzi e arricchire i profili per entrambi gli indirizzi separatamente. Ad esempio, per un indirizzo di casa e un indirizzo di lavoro. Selezionare **Avanti**.

1. Mappa i tuoi campi su dati località da Mappe di Azure. I campi **Via 1** e **Codice postale** sono obbligatori per l'indirizzo principale e/o secondario selezionato. Per una maggiore accuratezza di corrispondenza, aggiungi più campi.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Mapping degli attributi di Mappe di Azure.":::

1. Seleziona **Avanti** per completare il mapping del campo.

1. Rivedi **Impostazioni avanzate** che offrono la massima flessibilità per gestire casi d'uso avanzati. Tuttavia, i seguenti valori predefiniti in genere non devono essere modificati.

   - **Tipo di indirizzi**: la migliore corrispondenza per gli indirizzi viene restituita anche se è incompleta. Per ottenere solo indirizzi completi, ad esempio indirizzi che includono il numero civico, deseleziona tutte le caselle di controllo tranne **Indirizzi punti**.
   - **Lingua** gli indirizzi vengono restituiti nella lingua in base all'area geografica dell'indirizzo. Per applicare una lingua di indirizzo standard, seleziona la lingua dal menu a discesa. Ad esempio, selezionando **Inglese** viene restituito **Copenhagen, Danimarca** anziché **København, Danmark**.
   - **Numero massimo di risultati**: numero di risultati per indirizzo.

1. Selezionare **Avanti**.

1. Specifica un **Nome** per l'arricchimento e il **Nome entità di output**.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

1. Seleziona **Esegui** per avviare il processo di arricchimento o chiudere per tornare alla pagina **Arricchimenti**.

## <a name="view-enrichment-results"></a>Visualizzare i risultati dell'arricchimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Il campo **Numero di clienti arricchiti per campo** fornisce un'analisi dettagliata della copertura di ciascun campo arricchito.

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
