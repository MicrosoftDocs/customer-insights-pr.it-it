---
title: Arricchimento dei profili aziendali con Dun & Bradstreet
description: Informazioni generali sull'arricchimento di terze parti Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953896"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Arricchimento dei profili aziendali con Dun & Bradstreet (anteprima)

Dun & Bradstreet fornisce dati commerciali, analisi e informazioni dettagliate per le aziende. Consente ai clienti con profili cliente unificati per le aziende di arricchire i propri dati. Gli arricchimenti includono attributi quali il numero DUNS, le dimensioni, l'ubicazione e il settore di attività della società e altro ancora.

## <a name="prerequisites"></a>Prerequisiti

- Una licenza [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) attiva.
- [Profili cliente unificati](customer-profiles.md) per le aziende.
- Un [progetto](#set-up-your-dun--bradstreet-project) Dun & Bradstreet configurato.
- Una [connessione](connections.md) Dun & Bradstreet [configurata](#configure-a-connection-for-dun--bradstreet) da un amministratore.

## <a name="set-up-your-dun--bradstreet-project"></a>Configurare il progetto Dun & Bradstreet

In qualità di utente con licenza Dun & Bradstreet, puoi impostare un progetto in [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Accedi a [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Per recuperare le credenziali, [ripristina la tua password](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Scarica [il nostro file modello CSV](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) che verrà utilizzato per mappare i campi di Customer Insights ai corrispondenti campi Dun & Bradstreet.

1. Carica il file nel passaggio **Carica dati** dell'esperienza di creazione del progetto Dun & Bradstreet.

1. Seleziona i puntini orizzontali sotto la relativa **origine** nel progetto Dun & Bradstreet appena creato per vedere le opzioni disponibili.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Screenshot dei puntini in un progetto Dun & Bradstreet.":::

1. Scegli **Recupera i dettagli del S3**. Conserva queste informazioni in un luogo sicuro. Ne avrai bisogno per [configurare la connessione per l'arricchimento](#configure-a-connection-for-dun--bradstreet) in Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Screenshot della selezione di informazioni s3 in un progetto Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurare una connessione per Dun & Bradstreet

Devi essere un [amministratore](permissions.md#admin) in Customer Insights e disporre delle credenziali di Dun & Bradstreet Connect.

1. Seleziona **Aggiungi connessione** durante la configurazione dell'arricchimento o vai ad **Amministratore** > **Connessioni** e seleziona **Impostazione** nel riquadro Dun & Bradstreet.

1. Immettere un nome per la connessione.

1. Fornisci le credenziali Dun & Bradstreet valide e i dettagli del progetto Dun & Bradstreet *Regione, Percorso della cartella di destinazione e Nome della cartella di destinazione*. [Ottieni queste informazioni](#set-up-your-dun--bradstreet-project) dal progetto Dun & Bradstreet.

1. Rivedi e fornisci il tuo consenso per [Conformità e privacy dei dati](#data-privacy-and-compliance) selezionando **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione e quindi seleziona **Salva**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Pagina della configurazione della connessione per Dun & Bradstreet":::

### <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Dun & Bradstreet, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati su tua istruzione, ma sei tenuto a garantire che Dun & Bradstreet soddisfi qualsiasi obbligo di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.

## <a name="supported-countries-or-regions"></a>Paesi o aree geografiche supportati

Sono attualmente supportate le seguenti opzioni per paese/area geografica: Canada (inglese) o Stati Uniti (inglese).

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** sul riquadro **Dati azienda** per il riquadro Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Screenshot del riquadro Dun & Bradstreet.":::

1. Esamina la panoramica e quindi seleziona **Avanti**.

1. Seleziona la connessione e conferma. Contatta un amministratore se uno non è disponibile.

1. Selezionare **Avanti**.

1. Seleziona **Set di dati cliente** e scegli il profilo o il segmento che vuoi arricchire con i dati della società di Dun & Bradstreet. L'entità *Cliente* arricchisce tutti i tuoi profili cliente se un segmento arricchisce solo i profili cliente contenuti in quel segmento.

1. Definisci il tipo di campi per i tuoi profili unificati da usare per i dati della società corrispondenti di Dun & Bradstreet. Almeno uno dei campi **Nome e indirizzo**, **Telefono**, o **E-mail** è obbligatorio.

1. Selezionare **Avanti**.

1. Mappa i tuoi campi ai dati società di Dun & Bradstreet. I campi **Numero DUNS** o **Nome della società** e **Paese** sono obbligatori.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Riquadro di mapping dei campi di Dun & Bradstreet.":::

1. Seleziona **Avanti** per completare il mapping del campo.

1. Specifica un **Nome** per l'arricchimento e il **Nome entità di output**.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

1. Seleziona **Esegui** per avviare il processo di arricchimento o chiudere per tornare alla pagina **Arricchimenti**.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
