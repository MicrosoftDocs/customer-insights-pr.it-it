---
title: Componente aggiuntivo scheda cliente per Dynamics 365 (anteprima) (video)
description: Mostra i dati del profilo del cliente da Customer Insights nelle app Dynamics 365 con questo componente aggiuntivo.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: ead18963959f94fd07912384cf61802f83523e2f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081256"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Componente aggiuntivo scheda cliente per Dynamics 365 (anteprima)

Ottieni una panoramica completa dei tuoi clienti direttamente nelle app Dynamics 365. Con il Customer Card Add-in installato in un'applicazione Dynamics 365 supportata, è possibile scegliere di visualizzare i campi del profilo del cliente, gli approfondimenti e la timeline delle attività. Il componente aggiuntivo recupera i dati da Customer Insights senza influire sui dati nell'app Dynamics 365 connessa.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Prerequisiti

- Il componente aggiuntivo funziona solo con le app Dynamics 365 basate su modello, come Sales o Customer Service, versione 9.0 e successive.
- Affinché i dati di Dynamics 365 vengano mappati ai profili del cliente Customer Insights, consigliamo di [importarli dall'app Dynamics 365 utilizzando il connettore Microsoft Dataverse](connect-power-query.md). Se utilizzi un metodo diverso per importare i contatti (o gli account) di Dynamics 365, devi assicurarti che il campo `contactid` (o `accountid`) sia impostato come [chiave primaria per l'origine dati nel passaggio della mappa del processo di unificazione dei dati](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Tutti gli utenti Dynamics 365 del componente aggiuntivo scheda cliente devono essere [aggiunti come utenti](permissions.md) in Customer Insights per vedere i dati.
- [Funzionalità di ricerca e filtro configurate](search-filter-index.md) in Customer Insights sono necessarie affinché la ricerca dei dati funzioni.
- Ogni controllo del componente aggiuntivo si basa su dati specifici in Customer Insights. Alcuni dati e controlli sono disponibili solo in ambienti di tipo specifico. La configurazione del componente aggiuntivo ti informerà se un controllo non è disponibile a causa del tipo di ambiente selezionato. Per saperne di più sui [casi d'uso dell'ambiente](work-with-business-accounts.md).
  - **Controllo delle misure**: Richiede [misure configurate](measures.md) di attributi del cliente tipo.
  - **Controllo intelligente**: richiede dati generati utilizzando [previsioni o modelli personalizzati](predictions-overview.md).
  - **Controllo dei dettagli del cliente**: Tutti i campi del profilo sono disponibili nel profilo cliente unificato.
  - **Controllo dell'arricchimento**: Richiede [arricchimenti](enrichment-hub.md) attivi applicati ai profili dei clienti. Il componente aggiuntivo della scheda supporta questi arricchimenti: [Marchi](enrichment-microsoft.md) fornito da Microsoft, [Interessi](enrichment-microsoft.md) fornito da Microsoft e [Dati sull'engagement di Office](enrichment-office.md) fornito da Microsoft.
  - **Controllo dei contatti**: Richiede la definizione di un'entità semantica di tipo contacts.
  - **Controllo della timeline**: Richiede [attività configurate](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installare il componente aggiuntivo Scheda cliente

Il componente aggiuntivo Scheda cliente è una soluzione per le app di interazione con i clienti in Dynamics 365. Per installare la soluzione, vai a AppSource e cerca **Scheda cliente Dynamics**. Seleziona il [componente aggiuntivo Scheda cliente su AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e seleziona **Prova adesso**.

Potrebbe essere necessario accedere con le credenziali di amministratore per l'app Dynamics 365 per installare la soluzione. L'installazione della soluzione nell'ambiente potrebbe richiedere del tempo.

## <a name="configure-the-customer-card-add-in"></a>Configurare il componente aggiuntivo Scheda cliente

1. In qualità di amministratore, vai alla sezione **Impostazioni** in Dynamics 365 e seleziona **Soluzioni**.

1. Seleziona il collegamento **Nome visualizzato** per la soluzione **Componente aggiuntivo Scheda cliente di Dynamics 365 Customer Insights (anteprima)**.

   > [!div class="mx-imgBorder"]
   > ![Selezionare il nome visualizzato.](media/select-display-name.png "Seleziona il nome del display.")

1. Seleziona **Accedi** e immetti le credenziali per l'account amministratore che utilizzi per configurare Customer Insights.

   > [!NOTE]
   > Verifica che il blocco popup del browser non blocchi la finestra di autenticazione quando selezioni il pulsante **Accedi**.

1. Seleziona l'ambiente di Customer Insights da cui vuoi recuperare i dati.

1. Definisci la mappatura dei campi ai record nell'app Dynamics 365. A seconda dei vostri dati in Customer Insights, potete scegliere di mappare le seguenti opzioni:
   - Per eseguire il mapping con un contatto, seleziona il campo nell'entità Cliente che corrisponde all'ID dell'entità di contatto.
   - Per eseguire il mapping con un account, seleziona il campo nell'entità Cliente che corrisponde all'ID dell'entità account.

   > [!div class="mx-imgBorder"]
   > ![Campo ID contatto.](media/contact-id-field.png "Campo ID del contatto.")

1. Seleziona **Salva configurazione** per salvare le impostazioni.

1. Successivamente, devi assegnare ruoli di sicurezza in Dynamics 365 in modo che gli utenti possano personalizzare e visualizzare la scheda cliente. In Dynamics 365 vai a **Impostazioni** > **Sicurezza** > **Utenti**. Seleziona gli utenti per modificare i ruoli utente e seleziona **Gestisci ruoli**.

1. Assegna il ruolo **Addetto personalizzazione scheda Customer Insights** agli utenti che personalizzeranno il contenuto mostrato sulla scheda per l'intera organizzazione.

## <a name="add-customer-card-controls-to-forms"></a>Aggiungere i controlli Scheda cliente ai moduli

A seconda del tuo scenario, puoi scegliere di aggiungere controlli al modulo **Contatto** o al modulo **Account** . Se il tuo ambiente Customer Insights è per account aziendali, ti consigliamo di aggiungere i controlli al modulo Account. In questo caso, sostituite "contatto" nei passi seguenti con "account"

1. Per aggiungere i controlli della scheda cliente al modulo Contatto, vai a **Impostazioni** > **Personalizzazioni** in Dynamics 365.

1. Selezionare **Personalizza il sistema**.

1. Naviga fino all'entità **Contatto** , espandila e seleziona **Moduli**.

1. Seleziona il modulo di contatto a cui vuoi aggiungere i controlli della scheda cliente.

    > [!div class="mx-imgBorder"]
    > ![Selezionare il modulo Contatto.](media/contact-active-forms.png "Selezionare Modulo di contatto.")

1. Per aggiungere un controllo, nell'editor di moduli trascina qualsiasi campo da **Esplora campi** nel punto in cui vuoi che il controllo venga visualizzato.

1. Seleziona il campo del modulo che hai appena aggiunto e seleziona **Modifica proprietà**.

1. Vai alla scheda **Controlli** e seleziona **Aggiungi controllo**. Scegli uno dei controlli personalizzati disponibili e seleziona **Aggiungi**.

1. Nella finestra di dialogo **Proprietà campo**, seleziona la casella di controllo **Visualizza etichetta nel modulo**.

1. Seleziona l'opzione **Web** per il controllo. Per il controllo Arricchimento, seleziona il tipo di arricchimento che vuoi visualizzare configurando il campo **enrichmentType**. Aggiungi un controllo arricchimento separato per ogni tipo di arricchimento.

1. Seleziona **Salva** e **Pubblica** per pubblicare il modulo contatto aggiornato.

1. Vai al modulo del contatto pubblicato. Vedrai il controllo appena aggiunto. Potrebbe essere necessario effettuare l'accesso la prima volta che lo si utilizza.

1. Per personalizzare quello che vuoi visualizzare nel controllo personalizzato, seleziona il pulsante di modifica nell'angolo superiore destro.

## <a name="upgrade-customer-card-add-in"></a>Aggiornare il componente aggiuntivo Scheda cliente

Il componente aggiuntivo Scheda cliente non si aggiorna automaticamente. Per aggiornare all'ultima versione, segui questi passi nell'applicazione Dynamics 365 che ha il componente aggiuntivo installato.

1. Nell'app Dynamics 365, vai a **Impostazioni** > **Personalizzazione** e seleziona **Soluzioni**.

1. Nella tabella dei componenti aggiuntivi, cercate **CustomerInsightsCustomerCard** e selezionate la riga.

1. Seleziona **Applica aggiornamento soluzione** nella barra delle azioni.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Aggiorna la soluzione nell'area Personalizzazione delle app Dynamics 365.":::

1. Dopo aver avviato il processo di aggiornamento, vedrai un indicatore di caricamento fino al completamento dell'aggiornamento. Se non è disponibile una versione più recente, l'aggiornamento mostrerà un messaggio di errore.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>I controlli dal componente aggiuntivo della scheda cliente non trovano dati

**Problema:**

Anche con i campi ID correttamente configurati, i controlli non riescono a trovare dati per nessun cliente.  

**Risoluzione:**

1. Assicurati di aver configurato il componente aggiuntivo Scheda secondo le istruzioni: [Configurare il componente aggiuntivo della scheda cliente](#configure-the-customer-card-add-in)

1. Esamina la configurazione dell'importazione dei dati. Modifica l'origine dati per il sistema Dynamics 365 che contiene il GUID dell'ID contatto. Se il GUID dell'ID contatto viene visualizzato con caratteri maiuscoli nell'editor Power Query, prova le operazioni seguenti:
    1. Modifica l'origine dati per aprirla nell'editor Power Query.
    1. Selezionare la colonna ID contatto.
    1. Seleziona **Trasforma** nella barra dell'intestazione per vedere le azioni disponibili.
    1. Seleziona **minuscolo**. Convalida se i GUID nella tabella ora sono in minuscolo.
    1. Salva l'origine dati.
    1. Esegui i processi di inserimento, unificazione e downstream dei dati per propagare le modifiche al GUID.

Dopo che il sistema ha terminato l'aggiornamento completo, i controlli del componente aggiuntivo della scheda cliente dovrebbero mostrare i dati previsti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
