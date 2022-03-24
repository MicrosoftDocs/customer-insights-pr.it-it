---
title: Arricchisci i profili dei clienti con dati località di Mappe di Azure
description: Informazioni generali sull'arricchimento di prima parte di Mappe di Azure.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 2cc44f7b453d2aca328c397b14787c8a02c5e490
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376651"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Arricchimento dei profili dei clienti con Mappe di Azure (anteprima)

Mappe di Azure fornisce dati e servizi incentrati sulla località per offrire esperienze basate su dati geospaziali con informazioni sulla posizione integrate. I servizi di arricchimento dei dati di Mappe di Azure migliorano la precisione delle informazioni sulla posizione dei clienti. Offre funzionalità come la normalizzazione degli indirizzi e l'estrazione di latitudine e longitudine in Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prerequisiti

Per configurare l'arricchimento dei dati di Mappe di Azure, devono essere soddisfatti i seguenti prerequisiti:

- Devi disporre di una sottoscrizione attiva di Mappe di Azure. Per ottenere una sottoscrizione, puoi [iscriverti o ottenere una versione di prova gratuita](https://azure.microsoft.com/services/azure-maps/).

- È disponibile una [connessione](connections.md) a Mappe di Azure *oppure* disponi di autorizzazioni di [amministratore](permissions.md#admin) e una chiave API di Mappe di Azure attiva.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento**. 

1. Nel riquadro **Posizione** seleziona **Arricchisci i miei dati**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Riquadro Mappe di Azure.":::

1. Seleziona una [connessione](connections.md) dall'elenco a discesa. Contatta un amministratore se non è disponibile alcuna connessione a Mappe di Azure. Se sei un amministratore, puoi [configurare la connessione per Mappe di Azure](#configure-the-connection-for-azure-maps). 

1. Seleziona **Avanti** per confermare la selezione.

1. Scegli il **set di dati del cliente** da arricchire con dati località di Mappe di Azure. Puoi selezionare l'entità **Cliente** per arricchire tutti i profili cliente unificati. In alternativa è possibile selezionare un'entità segmento per migliorare l'indirizzo solo nei profili cliente contenuti nel segmento.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. Scegli se desideri mappare i campi all'indirizzo primario e/o secondario. È possibile specificare un mapping di campi per entrambi gli indirizzi e arricchire i profili per entrambi gli indirizzi separatamente, ad esempio un indirizzo dell'abitazione e uno dell'ufficio. Selezionare **Avanti**.

1. Definisci quali campi dei tuoi profili unificati utilizzare per cercare i dati località corrispondenti in Mappe di Azure. I campi **Via 1** e **CAP** sono obbligatori per gli indirizzi primario e secondario selezionati. Per un'accuratezza della corrispondenza migliore, puoi aggiungere altri campi.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Pagina di configurazione dell'arricchimento di Mappe di Azure.":::

1. Seleziona **Avanti** per completare il mapping del campo.

1. Valuta se vuoi modificare **Impostazioni avanzate**. Si tratta di impostazioni fornite per garantire la massima flessibilità di gestione dei casi d'uso avanzati, ma i valori predefiniti saranno adeguati nella maggior parte dei casi:
   - **Tipo di indirizzi**: in base al comportamento predefinito, l'arricchimento restituirà la migliore corrispondenza di indirizzo anche se incompleto. Per ottenere solo indirizzi completi, ad esempio indirizzi che includono il numero civico, deseleziona tutte le caselle di controllo tranne **Indirizzi punti**. 
   - **Lingua**: per impostazione predefinita, gli indirizzi vengono restituiti nella lingua dell'area geografica a cui l'indirizzo risulta associato. Per applicare una lingua di indirizzo standard, seleziona la lingua dal menu a discesa. Ad esempio, selezionando **Inglese** verrà restituito **Copenhagen, Denmark** anziché **København, Danmark**.

1. Immetti un nome per l'arricchimento.

1. Esamina le scelte effettuate e quindi seleziona **Salva arricchimento**.

## <a name="configure-the-connection-for-azure-maps"></a>Configurare la connessione per Mappe di Azure

Devi essere un amministratore nelle informazioni dettagliate sul gruppo di destinatari per configurare le connessioni. Seleziona **Aggiungi connessione** quando configuri un arricchimento o vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Mappe di Azure.

1. Nella casella **Nome visualizzato** immetti un nome per la connessione.

1. Fornisci una chiave API di Mappe di Azure valida.

1. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**

1. Seleziona **Verifica** per convalidare la configurazione.

1. Dopo aver completato la verifica, seleziona **Salva**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Pagina di configurazione della connessione di Mappe di Azure.":::

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipenderà dalla dimensione dei dati del cliente e dai tempi di risposta dell'API.

Al termine del processo di arricchimento, potrai esaminare i dati dei profili dei clienti appena arricchiti in **I miei arricchimenti**. Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere i dati a Mappe di Azure, consenti il trasferimento di dati al di fuori del limite di conformità per Dynamics 365 Customer Insights, inclusi i dati potenzialmente sensibili come i Dati Personali. Microsoft trasferirà tali dati alle tue istruzioni, ma sei tu a dover garantire che Mappe di Azure soddisfi tutti gli obblighi di privacy e sicurezza che sei tenuto a rispettare. Per maggiori informazioni, vai a [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
