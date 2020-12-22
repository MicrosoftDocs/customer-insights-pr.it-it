---
title: Arricchimento dei profili aziendali con l'arricchimento di terze parti Leadspace
description: Informazioni generali sull'arricchimento di terze parti Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668728"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Arricchimento dei profili aziendali con Leadspace (anteprima)

Leadspace è una società di data science che fornisce una piattaforma dati per clienti B2B. Consente ai clienti con profili cliente unificati per le aziende di arricchire i propri dati. Gli arricchimenti includono attributi aggiuntivi come le dimensioni, l'ubicazione e il settore della società nonché altre informazioni.

## <a name="prerequisites"></a>Prerequisiti

Per configurare Leadspace, devono essere rispettati i seguenti requisiti:

- Disponi di una licenza Leadspace attiva e la "chiave perpetua" (denominata **Token Leadspace**). Contatta direttamente [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) per i dettagli sul prodotto.
- Devi avere autorizzazioni di [amministratore](permissions.md#administrator).
- Devi disporre di [profili cliente unificati](customer-profiles.md) per le aziende.

## <a name="configuration"></a>Configurazione

1. In Audience Insights, vai a **Dati** > **Arricchimento**.

1. Seleziona **Arricchisci i miei dati** sul riquadro Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot del riquadro Leadspace.":::

1. Seleziona **Inizia** e quindi immetti un **Token Leadspace** (chiave perpetua) attivo. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**. Conferma entrambi gli input selezionando **Connetti a Leadspace**.

1. Seleziona **Esegui mapping dei dati** e definisci quali campi dei profili unificati devono essere utilizzati per cercare dati aziendali corrispondenti in Leadspace. Il campo **Nome della società** è obbligatorio. Per una maggiore precisione della corrispondenza, fino a due altri campi, **Sito web della società** e **Sede della società**, possono essere aggiunti.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Riquadro di mapping del campo Leadspace.":::
   
1. Seleziona **Applica** per completare il mapping dei campi.

1. Seleziona **Esegui** per arricchire i profili aziendali. La durata di un arricchimento dipende dal numero di profili cliente unificati.

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Dopo aver aggiornato l'arricchimento, è possibile rivedere i dati aziendali appena arricchiti in [Arricchimenti personali](enrichment-hub.md). Puoi trovare l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

Per ulteriori informazioni, vedi [API di Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Leadspace, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Leadspace rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.