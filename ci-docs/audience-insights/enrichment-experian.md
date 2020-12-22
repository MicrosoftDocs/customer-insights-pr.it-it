---
title: Arricchimento con l'arricchimento di terze parti Experian
description: Informazioni generali sull'arricchimento di terze parti Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668817"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Arricchisci i profili cliente con i dati demografici di Experian (anteprima)

Experian è un leader globale nei servizi di marketing e reporting del credito al consumo e alle imprese. Con Servizi di arricchimento dei dati di Experian, puoi acquisire una conoscenza più approfondita dei tuoi clienti arricchendo i tuoi profili cliente con dati demografici come le dimensioni del nucleo familiare, il reddito e altro ancora.

## <a name="prerequisites"></a>Prerequisiti

Per configurare Experian, devono essere rispettati i seguenti requisiti:

- Hai un abbonamento Experian attivo. Per ottenere un abbonamento, [contatta Experian](https://www.experian.com/marketing-services/contact) direttamente. [Altre informazioni sull'arricchimento dei dati Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Disponi dell'ID utente, dell'ID parte e del numero di modello del tuo account Secure Transport (ST) abilitato per SSH che Experian ha creato per te.
- Disponi di autorizzazioni di [amministratore](permissions.md#administrator) in Audience Insights.

## <a name="configuration"></a>Configurazione

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** nel riquadro Experian.

   > [!div class="mx-imgBorder"]
   > ![Riquadro Experian](media/experian-tile.png "Riquadro Experian")

1. Seleziona **Inizia** e inserisci l'ID utente, l'ID parte e il numero di modello per il tuo account Experian Secure Transport. Rivedi e fornisci il tuo consenso per **Conformità e privacy dei dati** selezionando la casella di controllo **Accetto**. Conferma tutti gli input selezionando **Applica**.

## <a name="map-your-fields"></a>Esegui il mapping dei campi

1. Seleziona **Aggiungi dati** e scegli i tuoi identificatori chiave da **Nome e indirizzo**, **E-mail** o **Telefono** da inviare a Experian per la risoluzione dell'identità.

   > [!TIP]
   > Più attributi dell'identificatore chiave inviati a Experian probabilmente producono un tasso di corrispondenza più elevato.

1. Seleziona **Avanti** e mappa gli attributi corrispondenti dall'entità cliente unificata per i campi dell'identificatore chiave selezionati.

1. Seleziona **Aggiungi attributo** per mappare eventuali attributi aggiuntivi che desideri inviare a Experian.

1.  Seleziona **Salva** per completare la mappatura dei campi.

   > [!div class="mx-imgBorder"]
   > ![Mapping del campo Experian](media/experian-field-mapping.png "Mapping del campo Experian")

## <a name="enrichment-results"></a>Risultati dell'arricchimento

Per avviare il processo di arricchimento, seleziona **Esegui** dalla barra dei comandi. Puoi anche lasciare che il sistema esegua l'arricchimento automaticamente come parte di un [aggiornamento pianificato](system.md#schedule-tab). Il tempo di elaborazione dipenderà dalle dimensioni dei tuoi dati cliente e dai processi di arricchimento impostati per il tuo account da Experian.

Al termine del processo di arricchimento, puoi rivedere i dati dei profili cliente appena arricchiti in **I miei arricchimenti**. Inoltre, troverai l'ora dell'ultimo aggiornamento e il numero di profili arricchiti.

Puoi accedere a una visualizzazione dettagliata di ciascun profilo arricchito selezionando **Visualizza dati arricchiti**.

## <a name="next-steps"></a>Passaggi successivi

Crea sulla base dei tuoi dati cliente arricchiti. Crea [segmenti](segments.md), [misure](measures.md) ed [esporta i dati](export-destinations.md) per offrire esperienze personalizzate ai tuoi clienti.

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Experian, consenti il trasferimento di dati al di fuori dei limiti di conformità per Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma hai la responsabilità di assicurarti che Experian rispetti gli obblighi di privacy o sicurezza che potresti avere. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questo arricchimento in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
