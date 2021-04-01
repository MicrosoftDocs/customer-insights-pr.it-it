---
title: Installa e configura il componente aggiuntivo Scheda cliente
description: Installa e configura il componente aggiuntivo Scheda cliente per Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597332"
---
# <a name="customer-card-add-in-preview"></a>Componente aggiuntivo Scheda cliente (anteprima)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ottieni una panoramica completa dei tuoi clienti direttamente nelle app Dynamics 365. Visualizza dati demografici, informazioni dettagliate e sequenze temporali degli impegni con il componente aggiuntivo Scheda cliente.

## <a name="prerequisites"></a>Prerequisiti

- App Dynamics 365 (come Hub delle vendite o Hub del servizio clienti), versione 9.0 e successive con Unified Interface abilitato.
- Profili cliente [inseriti dall'app Dynamics 365 utilizzando Common Data Service](connect-power-query.md).
- Gli utenti del componente aggiuntivo Scheda cliente devono essere [aggiunti come utenti](permissions.md) in Audience Insights.
- [Funzionalità di ricerca e filtro configurate](search-filter-index.md).
- Controllo demografico: i campi demografici, come l'età o il sesso, sono disponibili nel profilo cliente unificato.
- Controllo Arricchimento: richiede [arricchimenti](enrichment-hub.md) attivi applicati ai profili cliente.
- Controllo dell'intelligenza: richiede dati generati tramite Azure Machine Learning ([previsioni](predictions.md) o [modelli personalizzati](custom-models.md))
- Controllo delle misure: richiede [misure configurate](measures.md).
- Controllo della sequenza temporale: richiede [impegni configurati](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installare il componente aggiuntivo Scheda cliente

Il componente aggiuntivo Scheda cliente è una soluzione per le app di interazione con i clienti in Dynamics 365. Per installare la soluzione, vai a AppSource e cerca **Scheda cliente Dynamics**. Seleziona il [componente aggiuntivo Scheda cliente su AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e seleziona **Prova adesso**.

Potrebbe essere necessario accedere con le credenziali di amministratore per l'app Dynamics 365 per installare la soluzione.

L'installazione della soluzione nell'ambiente potrebbe richiedere del tempo.

## <a name="configure-the-customer-card-add-in"></a>Configurare il componente aggiuntivo Scheda cliente

1. In qualità di amministratore, vai alla sezione **Impostazioni** in Dynamics 365 e seleziona **Soluzioni**.

1. Seleziona il collegamento **Nome visualizzato** per la soluzione **Componente aggiuntivo Scheda cliente di Dynamics 365 Customer Insights (anteprima)**.

   > [!div class="mx-imgBorder"]
   > ![Selezionare il nome visualizzato](media/select-display-name.png "Selezionare il nome visualizzato")

1. Seleziona **Accedi** e immetti le credenziali per l'account amministratore che utilizzi per configurare Customer Insights.

   > [!NOTE]
   > Verifica che il blocco popup del browser non blocchi la finestra di autenticazione quando selezioni il pulsante **Accedi**.

1. Seleziona l'ambiente da cui vuoi recuperare i dati.

1. Definisci quale campo mappare ai record nell'app Dynamics 365.
   - Per eseguire il mapping con un contatto, seleziona il campo nell'entità Cliente che corrisponde all'ID dell'entità di contatto.
   - Per eseguire il mapping con un account, seleziona il campo nell'entità Cliente che corrisponde all'ID dell'entità account.

   > [!div class="mx-imgBorder"]
   > ![Campo ID contatto](media/contact-id-field.png "Campo ID contatto")

1. Seleziona **Salva configurazione** per salvare le impostazioni.

1. Successivamente, devi assegnare ruoli di sicurezza in Dynamics 365 in modo che gli utenti possano personalizzare e visualizzare la scheda cliente. In Dynamics 365 vai a **Impostazioni** > **Sicurezza** > **Utenti**. Seleziona gli utenti per modificare i ruoli utente e seleziona **Gestisci ruoli**.

1. Assegna il ruolo **Addetto personalizzazione scheda Customer Insights** agli utenti che personalizzeranno il contenuto mostrato sulla scheda per l'intera organizzazione.

## <a name="add-customer-card-controls-to-forms"></a>Aggiungere i controlli Scheda cliente ai moduli
  
1. Per aggiungere i controlli della scheda cliente al modulo Contatto, vai a **Impostazioni** > **Personalizzazioni** in Dynamics 365.

1. Selezionare **Personalizza il sistema**.

1. Accedi all'entità **Contatto**, espandila e quindi seleziona **Moduli**.

1. Seleziona il modulo del contatto a cui vuoi aggiungere i controlli Scheda cliente.

    > [!div class="mx-imgBorder"]
    > ![Selezionare il modulo Contatto](media/contact-active-forms.png "Selezionare il modulo Contatto")

1. Per aggiungere un controllo, nell'editor di moduli trascina qualsiasi campo da **Esplora campi** nel punto in cui vuoi che il controllo venga visualizzato.

1. Seleziona il campo sul modulo che hai appena aggiunto e scegli **Cambia proprietà**.

1. Vai alla scheda **Controlli** e seleziona **Aggiungi controllo**. Scegli uno dei controlli personalizzati disponibili e seleziona **Aggiungi**.

1. Nella finestra di dialogo **Proprietà campo**, seleziona la casella di controllo **Visualizza etichetta nel modulo**.

1. Seleziona l'opzione **Web** per il controllo. Per il controllo Arricchimento, seleziona il tipo di arricchimento che vuoi visualizzare configurando il campo **enrichmentType**. Aggiungi un controllo arricchimento separato per ogni tipo di arricchimento.

1. Seleziona **Salva** e **Pubblica** per pubblicare il modulo contatto aggiornato.

1. Vai al modulo del contatto pubblicato. Vedrai il controllo appena aggiunto. Potrebbe essere necessario effettuare l'accesso la prima volta che lo si utilizza.

1. Per personalizzare quello che vuoi visualizzare nel controllo personalizzato, seleziona il pulsante di modifica nell'angolo superiore destro.

## <a name="upgrade-customer-card-add-in"></a>Aggiornare il componente aggiuntivo Scheda cliente
Il componente aggiuntivo Scheda cliente non si aggiorna automaticamente. Per eseguire l'aggiornamento alla versione più recente, segui questa procedura nell'app Dynamics 365 in cui è installato il componente aggiuntivo.

1. Nell'app Dynamics 365, vai a **Impostazioni** > **Personalizzazione** e seleziona **Soluzioni**.

1. Nella tabella dei componenti aggiuntivi cerca **CustomerInsightsCustomerCard** e seleziona la riga.

1. Seleziona **Applica aggiornamento soluzione** nella barra delle azioni.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Aggiorna la soluzione nell'area Personalizzazione delle app Dynamics 365":::

1. Dopo aver avviato il processo di aggiornamento, vedrai un indicatore di caricamento fino al completamento dell'aggiornamento. Se non è disponibile una versione più recente, l'aggiornamento mostrerà un messaggio di errore.


[!INCLUDE[footer-include](../includes/footer-banner.md)]