---
title: Arricchimento dei profili aziendali con Dun & Bradstreet
description: Informazioni generali sull'arricchimento di terze parti Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653723"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Arricchimento dei profili aziendali con Dun & Bradstreet (anteprima)

Dun & Bradstreet fornisce dati commerciali, analisi e informazioni dettagliate per le aziende. Consente ai clienti con profili cliente unificati per le aziende di arricchire i propri dati. Gli arricchimenti includono attributi quali il numero DUNS, le dimensioni, l'ubicazione e il settore di attività della società e altro ancora.

## <a name="prerequisites"></a>Prerequisiti

Per configurare l'arricchimento Dun & Bradstreet, devono essere rispettati i seguenti requisiti:

- Avere una licenza [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) attiva.
- Devi disporre di [profili cliente unificati](customer-profiles.md) per le aziende.
- Avere una [connessione](connections.md) Dun & Bradstreet configurata da un amministratore. Puoi crearla se hai le autorizzazioni di [amministratore](permissions.md#admin) e le credenziali di Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Configurazione del progetto Dun & Bradstreet

In qualità di utente con licenza Dun & Bradstreet, puoi impostare un progetto in [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Accedi a [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Per recuperare le credenziali, [ripristina la tua password](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Scarica [il nostro file modello CSV](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) che verrà utilizzato per mappare i campi delle informazioni dettagliate gruppo di destinatari ai corrispondenti campi Dun & Bradstreet. 

1. Carica il file nel passaggio **Carica dati** dell'esperienza di creazione del progetto Dun & Bradstreet. 

1. Seleziona i puntini orizzontali sotto la relativa **origine** nel progetto Dun & Bradstreet appena creato per vedere le opzioni disponibili.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Screenshot dei puntini in un progetto Dun & Bradstreet.":::

1. Scegli **Recupera i dettagli del S3**. Conserva queste informazioni in un luogo sicuro. Ne avrai bisogno per [configurare la connessione per l'arricchimento](#configure-a-connection-for-dun--bradstreet) nelle informazioni dettagliate gruppo di destinatari. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Screenshot della selezione di informazioni s3 in un progetto Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Dati** > **Arricchimento**.

1. Seleziona **Arricchisci i miei dati** nel riquadro Dun & Bradstreet e seleziona **Inizia**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Screenshot del riquadro Dun & Bradstreet.":::

1. Seleziona una [connessione](connections.md) dall'elenco a discesa. Contatta un amministratore se non è disponibile alcuna connessione. Se sei un amministratore, puoi creare una connessione. Seleziona **Aggiungi connessione** e scegli **Dun & Bradstreet**. 

1. Seleziona **Connetti a Dun & Bradstreet** per confermare la connessione.

1. Seleziona **Avanti** e scegli il **Set di dati cliente** che vuoi arricchire con i dati della società di Dun & Bradstreet. Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente unificati contenuti in quel segmento.

1. Seleziona **Avanti** e definisci quali campi dei tuoi profili unificati sono utilizzati per cercare i dati della società corrispondenti di Dun & Bradstreet. I campi **Numero DUNS** o **Nome della società** e **Paese** sono obbligatori. Il campo paese supporta i [codici paese di due o tre lettere](https://www.iso.org/iso-3166-country-codes.html), nome del paese in inglese, nome del paese nella lingua madre e prefisso del telefono. Alcune varianti di paesi comuni includono:

   * US: Stati Uniti d'America, Stati Uniti, USA, America.
   * CA: Canada.
   * GB: Regno Unito, UK, Gran Bretagna, GB, Regno Unito di Gran Bretagna e Irlanda del Nord, Regno Unito di Gran Bretagna.
   * AU: Australia, Commonwealth of Australia.
   * FR: Francia, Repubblica francese.
   * DE: Germania, Tedesco, Repubblica Federale Tedesca, Repubblica Tedesca.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Riquadro di mapping dei campi di Dun & Bradstreet.":::

1. Seleziona **Avanti** per completare il mapping del campo.

1. Fornisci un nome per l'arricchimento e seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurare una connessione per Dun & Bradstreet 

Devi essere un amministratore per configurare le connessioni. Seleziona **Aggiungi connessione** durante la configurazione dell'arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Impostazione** nel riquadro Dun & Bradstreet.

1. Seleziona **Inizia subito**. 

1. Immetti un nome per la connessione nella casella **nome visualizzato**.

1. Fornisci le credenziali Dun & Bradstreet valide e i dettagli del progetto Dun & Bradstreet *Regione, Percorso della cartella di destinazione e Nome della cartella di destinazione*. [Ottieni queste informazioni](#setting-up-your-dun--bradstreet-project) dal progetto Dun & Bradstreet.

1. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione.

1. Dopo aver completato la verifica, seleziona **Salva**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Pagina della configurazione della connessione per Dun & Bradstreet":::

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Dopo aver aggiornato l'arricchimento, è possibile rivedere i dati aziendali appena arricchiti in [Arricchimenti personali](enrichment-hub.md). Puoi trovare l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Dun & Bradstreet, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati su tua istruzione, ma sei tenuto a garantire che Dun & Bradstreet soddisfi qualsiasi obbligo di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](includes/footer-banner.md)]
