---
title: Arricchimento dei profili aziendali con l'arricchimento di terze parti Leadspace
description: Informazioni generali sull'arricchimento di terze parti Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 0db0c984f6bf9f7ded0704b6fa0caf39c7dace3a
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376789"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Arricchimento dei profili aziendali con Leadspace (anteprima)

Leadspace è una società di servizi di data science che fornisce una piattaforma per i dati dei clienti B2B. Permette agli ambienti con profili di clienti unificati basati su conti di arricchire i loro dati. Arricchisci *i profili dei clienti* con attributi come le dimensioni dell'azienda, la posizione o il settore. Arricchisci *i profili dei contatti* con attributi come il titolo, la persona o la verifica dell'e-mail.

## <a name="prerequisites"></a>Prerequisiti

Per configurare Leadspace, devono essere rispettati i seguenti requisiti:

- Hai una licenza Leadspace attiva.
- Avete [unificato i profili dei clienti](customer-profiles.md) in base agli account.
- Una connessione Leadspace è già stata configurata da un amministratore o hai le autorizzazioni di [amministratore](permissions.md#admin) e la "chiave perpetua" (denominata **token Leadspace**). Contatta [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) direttamente per i dettagli sul loro prodotto.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Dati** > **Arricchimento**.

1. Seleziona **Arricchisci i miei dati** nel riquadro Leadspace e seleziona **Attività iniziali**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot del riquadro Leadspace.":::

1. Seleziona una [connessione](connections.md) dall'elenco a discesa. Contatta un amministratore se non è disponibile alcuna connessione. Se sei un amministratore, puoi creare una connessione selezionando **Aggiungi connessione** e scegliendo **Leadspace**. 

1. Seleziona **Connettiti a Leadspace** per confermare la connessione.

1. Seleziona **Avanti** e scegli il **set di dati del cliente** che desideri arricchire con i dati aziendali di Leadspace. Puoi selezionare l'entità **Cliente** per arricchire tutti i tuoi profili cliente o selezionare un'entità segmento per arricchire solo i profili cliente contenuti in quel segmento.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Screenshot della scelta del set di dati cliente.":::

1. Seleziona **Avanti** e definisci quali campi dei profili unificati vengono utilizzati per cercare i dati aziendali corrispondenti di Leadspace. Il campo **Nome della società** è obbligatorio. Per una maggiore precisione della corrispondenza, fino a due altri campi, **Sito web della società** e **Sede della società**, possono essere aggiunti.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Riquadro di mappatura dei campi di Leadspace.":::

1. Seleziona **Avanti** per completare il mapping del campo.

1. Seleziona la casella di controllo se hai dei *profili di contatto* che vuoi arricchire. approfondimenti sul pubblico mapperà automaticamente i campi richiesti.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Arricchimento dei record di contatto di Leadspace.":::
 
1. Fornisci un nome per l'arricchimento e seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.


## <a name="configure-the-connection-for-leadspace"></a>Configurare la connessione per Leadspace 

Devi essere un amministratore per configurare le connessioni. Seleziona **Aggiungi connessione** quando si configura un arricchimento *o* vai ad **Amministratore** > **Connessioni** e seleziona **Imposta** nel riquadro Leadspace.

1. Seleziona **Inizia subito**. 

1. Immetti un nome per la connessione nella casella **nome visualizzato**.

1. Fornisci un token di Leadspace valido.

1. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando **Accetto**.

1. Seleziona **Verifica** per convalidare la configurazione.

1. Dopo aver completato la verifica, seleziona **Salva**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Pagina di configurazione della connessione di Leadspace":::

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Dopo aver aggiornato l'arricchimento, è possibile rivedere i dati aziendali appena arricchiti in [Arricchimenti personali](enrichment-hub.md). Puoi trovare l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

Per ulteriori informazioni, vedi [API di Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Passaggi successivi


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Leadspace, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Leadspace rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
