---
title: Arricchire i profili dei clienti con HERE Technologies (anteprima)
description: Informazioni generali sull'arricchimento di terze parti di HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 26de9fce863c9832b70adf3ce39cb2ae0ce43d0e
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196261"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Arricchire i profili dei clienti con HERE Technologies (anteprima)

HERE Technologies è una società di piattaforme di localizzazione che fornisce dati e servizi incentrati sulla posizione. I servizi di arricchimento dei dati di HERE Technologies migliorano la precisione delle informazioni relative alla posizione dei tuoi clienti. Vengono forniti la normalizzazione degli indirizzi, l'estrazione di latitudine e longitudine e altro ancora.

## <a name="prerequisites"></a>Prerequisiti

- Una sottoscrizione di HERE Technologies attiva. Per ottenere una sottoscrizione, [iscriviti qui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [contatta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direttamente. [Ulteriori informazioni sull'arricchimento della posizione di HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Una [connessione](connections.md) HERE [configurata](#configure-the-connection-for-here-technologies) da un amministratore.

## <a name="configure-the-connection-for-here-technologies"></a>Configurazione della connessione per HERE Technologies

Devi essere un [amministratore](permissions.md#admin) in Customer Insights e avere una chiave API di HERE Technologies attiva.

1. Seleziona **Aggiungi connessione** quando configuri un arricchimento o vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro HERE technologies.

1. Immetti un nome per la connessione e una chiave API di HERE Technologies valida.

1. Rivedi e fornisci il tuo consenso per [Conformità e privacy dei dati](#data-privacy-and-compliance) selezionando **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione e quindi seleziona **Salva**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Pagina di configurazione della connessione di HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a HERE Technologies, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che HERE Technologies rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** in **Posizione** nel riquadro HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Riquadro HERE Technologies.":::

1. Esamina la panoramica e quindi seleziona **Avanti**.

1. Seleziona la connessione. Contatta un amministratore se non è disponibile alcuna connessione.

1. Selezionare **Avanti**.

1. Seleziona **Set di dati cliente** e scegli il profilo o il segmento che vuoi arricchire con i dati di HERE Technologies. L'entità *Cliente* arricchisce tutti i tuoi profili cliente se un segmento arricchisce solo i profili cliente contenuti in quel segmento.

1. Definisci quale tipo di campi dei tuoi profili unificati usare per la corrispondenza: l'indirizzo primario e/o secondario. Puoi specificare un mapping del campo per entrambi gli indirizzi e arricchire i profili per entrambi gli indirizzi separatamente. Ad esempio, per un indirizzo di casa e un indirizzo di lavoro. Selezionare **Avanti**.

1. Mappa i tuoi campi ai dati di HERE Technologies. I campi **Via 1** e **Codice postale** sono obbligatori per l'indirizzo principale e/o secondario selezionato. Per una maggiore accuratezza di corrispondenza, aggiungi più campi.

1. Seleziona **Avanti** per completare il mapping del campo.

1. Specifica un **Nome** per l'arricchimento e il **Nome entità di output**.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

1. Seleziona **Esegui** per avviare il processo di arricchimento o chiudere per tornare alla pagina **Arricchimenti**.

## <a name="view-enrichment-results"></a>Visualizzare i risultati dell'arricchimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Il campo **Numero di clienti arricchiti per campo** fornisce un'analisi dettagliata della copertura di ciascun campo arricchito.

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
