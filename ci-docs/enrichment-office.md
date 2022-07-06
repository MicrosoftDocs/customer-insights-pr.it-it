---
title: Arricchire i profili dei clienti con i dati di Microsoft Office 365 (anteprima)
description: Utilizza i dati proprietari di Microsoft Office per arricchire i profili dei tuoi clienti con dati di coinvolgimento.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055679"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Arricchire i profili dei clienti con i dati di Microsoft Office 365 (anteprima)

Usa i dati di Microsoft Office 365 per arricchire i profili del tuo account cliente con approfondimenti sul coinvolgimento attraverso app di Office 365. I dati di coinvolgimento sono costituiti da e-mail e attività di riunione, che vengono aggregati a livello di account. Ad esempio, il numero di e-mail da un account aziendale o il numero di riunioni con l'account. Non sono disponibili dati sui singoli utenti.

## <a name="supported-countries-or-regions"></a>Paesi o aree geografiche supportati

Attualmente supportiamo le seguenti aree geografiche: Regno Unito, Europa, Nord America.

## <a name="prerequisites"></a>Prerequisiti

- Una licenza cloud Office 365 attiva.
- [Profili cliente unificati](customer-profiles.md) in base agli [account aziendali](work-with-business-accounts.md).
- Un'[organizzazione Microsoft Dataverse collegata](create-environment.md#step-3-connect-to-microsoft-dataverse) nell'ambiente Customer Insights.
- Autorizzazioni dell'[amministratore](permissions.md#admin).
- Consenso dal tuo amministratore del tenant di Office 365 per usare i dati Office 365 per fornire **Approfondimenti per l'organizzazione** all'interno delle applicazioni Dynamics 365.

## <a name="configure-the-enrichment"></a>Configurare l'arricchimento

1. Vai a **Dati** > **Arricchimento** e selezionala scheda **Individua**.

1. Seleziona **Arricchisci i miei dati** sul riquadro **Interazione account**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Riquadro Interazione account.":::

1. Esamina la panoramica e quindi seleziona **Avanti**.

1. Immetti gli indirizzi e-mail dell'organizzazione per i quali verranno aggregati i dati di Office. Solo i dati degli indirizzi e-mail elencati vengono elaborati per la comunicazione pertinente. Una procedura consigliata consiste nell'usare gruppi e-mail, ad esempio *Team vendite USA* che puoi gestire in Office 365. Il numero di indirizzi e-mail nei gruppi viene risolto e mostrato. Il numero totale di indirizzi e-mail deve essere almeno 2 e non può superare i 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Indirizzi e-mail di coinvolgimento dell'account.":::

1. Rivedi e fornisci il tuo [consenso amministratore tenant di Office 365](#office-365-tenant-administrator-consent) selezionando **Accetto**.

1. Selezionare **Avanti**.

1. Seleziona **Set di dati contatto** e scegli il profilo che vuoi arricchire. Selezionare **Avanti**.

1. Mappa il campo dell'indirizzo e-mail di contatto e seleziona **Avanti**.

1. Fornisci un **nome** per l'arricchimento e l' **entità di output**.

1. Seleziona **Salva arricchimento** dopo aver esaminato le tue scelte.

1. Seleziona **Chiudi** per tornare alla pagina **Arricchimenti**.

### <a name="office-365-tenant-administrator-consent"></a>Consenso amministratore tenant di Office 365

Il consenso di un amministratore del tenant di Office 365 è necessario per attivare l'arricchimento. Viene inviata un'e-mail agli amministratori del tenant Office 365 quando l'arricchimento viene salvato, che chiede loro di rivedere e acconsentire al permesso alle applicazioni Dynamics 365 di utilizzare i dati aziendali di Office 365 per fornire **Approfondimenti per l'organizzazione**. L'amministratore del tenant di Office 365 può anche acconsentire direttamente nella console di amministrazione di Office 365, selezionando **Approfondimenti per l'organizzazione**.

## <a name="running-the-enrichment-for-the-first-time"></a>Esecuzione dell'arricchimento per la prima volta

Quando si avvia l'arricchimento per la prima volta, dopo che l'amministratore del tenant di Office 365 ha dato il consenso, il download dei dati da Office 365 inizia. Questo processo richiede del tempo. La prima esecuzione dell'arricchimento sarà programmata con un ritardo di sei ore. Puoi vedere il numero di giorni coperti dai dati nella pagina di panoramica del coinvolgimento dell'account al termine dell'arricchimento. Con un grande volume di dati, eseguire nuovamente l'arricchimento dopo alcuni giorni. Garantisce che i dati siano completi per l'intera finestra temporale, che è un anno.

A seconda delle dimensioni dei dati di Office, potrebbero essere necessarie diverse ore per il completamento dell'esecuzione dell'arricchimento.

Quando esegui un arricchimento, Microsoft elaborerà i dati all'interno del limite di conformità di Office 365 per creare approfondimenti aggregati, che vengono quindi aggiunti al tuo ambiente di Customer Insights. Nessun dato a livello individuale (ad esempio, il corpo di un'e-mail o un invito del calendario) diventa disponibile per gli utenti di Customer Insights.

Seleziona **Esegui** per avviare il processo di arricchimento.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Visualizzare i risultati dell'arricchimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Questa è l'entità *Office*. L'entità *Office_UserEntity* contiene gli ID di Active Directory per gli indirizzi e-mail scelti durante la configurazione dell'arricchimento.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Anteprima dei risultati dopo l'esecuzione del processo di arricchimento.":::

Tutti i dati vengono aggregati fino al livello dell'account. Il sistema calcola un punteggio di coinvolgimento, che va da 0 a 100, per ogni account. Il punteggio di coinvolgimento fornisce una misura composita del coinvolgimento dell'account tra e-mail e riunioni rispetto agli altri account. L'elenco seguente contiene i dati aggregati forniti dall'arricchimento del coinvolgimento dell'account:

| Dati                                                                              | Nome colonna                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Punteggio interazione                                                                  |  EngagementScore                         |
| Numero di e-mail sull'account                                                       |  NoOfEmails_ToAccount                    |
| Numero di e-mail dall'account                                                     |  NoOfEmails_FromAccount                  |
| Numero di riunioni avviate da account                                           |  NoOfMeetings_FromAccount                |
| Numero di riunioni avviate dalla tua organizzazione                                 |  NoOfMeetings_ToAccount                  |
| Numero di persone della tua organizzazione in riunioni con account                  |  NoOfContactsInvolved_Meetings           |
| Numero di persone della tua organizzazione in conversazioni e-mail con account       |  NoOfContactsInvolved_Emails             |
| Numero di persone in riunioni con account con la tua organizzazione                  |  NoOfAccountContactsInvolved_Meetings    |
| Numero di persone da account nelle conversazioni e-mail con la tua organizzazione       |  NoOfAccountContactsInvolved_Emails      |
| Data di inizio dell'impegno (prima e-mail o riunione nei dati)                        |  EngagementStartDate                     |
| Giorni dall'ultima e-mail                                                             |  DaysSinceLastEmail                      |
| Giorni dall'ultima riunione                                                           |  DaysSinceLastMeeting                    |
| Durata media delle riunioni                                                      |  AverageDuration_Of_Meetings             |
| Durata media delle risposte e-mail dall'account                                    |  AverageDuration_Of_AccountEmailReplies  |
| Data di inizio aggregazione                                                            |  AggregationStartDate                    |
| Livello di aggregazione (anno, mese o settimana)                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Visualizzare i dati di arricchimento nella scheda cliente

Il coinvolgimento dell'account può essere visualizzato anche sulle singole carte cliente. Vai a **Clienti** e seleziona un profilo cliente. Nella scheda cliente troverai il punteggio di coinvolgimento dell'account, il numero totale di e-mail e il numero totale di riunioni aggregate nell'ultimo anno. Trovi anche grafici che mostrano l'e-mail e la cronologia delle riunioni.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Scheda cliente con dati arricchiti.":::

## <a name="next-steps"></a>Passaggi successivi

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Ad esempio, un segmento che contiene tutti i clienti che hanno un valore superiore a 60 per *giorni dall'ultima e-mail* e *giorni dall'ultima riunione*. Quel segmento contiene account obsoleti che puoi provare a riattivare.

[!INCLUDE [footer-include](includes/footer-banner.md)]
