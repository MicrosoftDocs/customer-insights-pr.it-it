---
title: Arricchire i profili aziendali con Leadspace (anteprima)
description: Informazioni generali sull'arricchimento di terze parti Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 3f23fe7177f931db3e3179970915d0cd3c736f87
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196215"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Arricchire i profili aziendali con Leadspace (anteprima)

Leadspace è una società di servizi di data science che fornisce una piattaforma per i dati dei clienti B2B. Permette agli ambienti con profili di clienti unificati basati su conti di arricchire i loro dati. Arricchisci *i profili dei clienti* con attributi come le dimensioni dell'azienda, la posizione o il settore. Arricchisci *i profili dei contatti* con attributi come il titolo, la persona o la verifica dell'e-mail.

## <a name="prerequisites"></a>Prerequisiti

- Una licenza Leadspace attiva.
- [Profili cliente unificati](customer-profiles.md) in base agli account.
- Una [connessione](connections.md) Leadspace [configurata](#configure-the-connection-for-leadspace) da un amministratore. Contatta [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) direttamente per i dettagli sul loro prodotto.

## <a name="configure-the-connection-for-leadspace"></a>Configurare la connessione per Leadspace

Devi essere un [amministratore](permissions.md#admin) in Customer Insights e disporre della "chiave perpetua" (denominata **Token Leadspace**).

1. Seleziona **Aggiungi connessione** quando configuri un arricchimento o vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Pagina di configurazione della connessione di Leadspace":::

1. Immetti un nome per la connessione e un token Leadspace valido.

1. Rivedi e fornisci il tuo consenso per [Conformità e privacy dei dati](#data-privacy-and-compliance) selezionando **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione e quindi seleziona **Salva**.

### <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Leadspace, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Leadspace rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** sul riquadro **Dati aziendali** di Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot del riquadro Leadspace.":::

1. Esamina la panoramica e quindi seleziona **Avanti**.

1. Seleziona la connessione. Contatta un amministratore se non è disponibile alcuna connessione.

1. Selezionare **Avanti**.

1. Seleziona **Set di dati cliente** e scegli il profilo o il segmento che vuoi arricchire con i dati della società di Leadspace. L'entità *Cliente* arricchisce tutti i tuoi profili cliente se un segmento arricchisce solo i profili cliente contenuti in quel segmento.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. Definisci quale tipo di campi dei tuoi profili unificati usare per la corrispondenza: l'indirizzo primario e/o secondario. Puoi specificare un mapping del campo per entrambi gli indirizzi e arricchire i profili per entrambi gli indirizzi separatamente. Ad esempio, per un indirizzo di casa e un indirizzo di lavoro. Selezionare **Avanti**.

1. Mappa i tuoi campi ai dati società di Leadspace. Il campo **Nome della società** è obbligatorio. Per una maggiore precisione della corrispondenza, fino a due altri campi, **Sito web della società** e **Sede della società**, possono essere aggiunti.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Riquadro di mapping dei campi di Leadspace.":::

1. Seleziona **Avanti** per completare il mapping del campo.

1. Seleziona la casella di controllo se hai dei *profili di contatto* che vuoi arricchire. Customer Insights mapperà automaticamente i campi richiesti.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Arricchimento dei record di contatto di Leadspace.":::

1. Selezionare **Avanti**.

1. Specifica un **Nome** per l'arricchimento e il **Nome entità di output**.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

1. Seleziona **Esegui** per avviare il processo di arricchimento o chiudere per tornare alla pagina **Arricchimenti**.

## <a name="view-enrichment-results"></a>Visualizzare i risultati dell'arricchimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Per ulteriori informazioni, vedi [API di Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]