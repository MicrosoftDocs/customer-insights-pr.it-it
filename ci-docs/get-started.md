---
title: Operazioni preliminari di Dynamics 365 Customer Insights
description: Una panoramica di Customer Insights aiuta le risorse a iniziare rapidamente.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 68c26eb0ad0da787a9f594b4aebe679588b0d6bf
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833580"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Operazioni preliminari di Dynamics 365 Customer Insights

Customer Insights può aiutarti a ottenere una comprensione più profonda dei tuoi clienti. Connetti i dati da varie origini transazionali, comportamentali e osservativi per creare una visualizzazione cliente a 360 gradi. Utilizza queste informazioni dettagliate per promuovere esperienze e processi incentrati sul cliente. Unifica e comprendi i dati cliente e utilizzali per ottenere informazioni e azioni utili.

## <a name="step-1-create-an-environment"></a>Passaggio 1. Creare un ambiente

Innanzitutto, crea un ambiente in cui lavorare. Se la tua organizzazione ha già acquistato una licenza, vedi [Creare un ambiente](create-environment.md). Per avviare una versione di prova di Customer Insights, vedi [Configurare un ambiente di prova](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Passaggio 2: Scopri Customer Insights

La prima volta che accedi a Customer Insights, puoi configurare le impostazioni ed esplorare il prodotto.

1. [Accedi a Customer Insights](https://home.ci.ai.dynamics.com) usando il tuo account utente Microsoft Azure Active Directory (AAD).

1. Cambia l'ambiente per vedere i dati demo ed [esplorare Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Passaggio 3. Importare, unificare e configurare le relazioni per i tuoi dati

I profili unificati sono la base per ottenere informazioni dettagliate e agire sui dati. Acquisisci dati da varie fonti ed esegui il processo di unificazione dei dati per combinare i profili unificati. Specifica le relazioni tra le entità importate e utilizza le funzionalità di arricchimento per aggiungere informazioni ai profili.

1. Inserisci i dati creando origini dati da più opzioni. Scegli tra [connettori Power Query](connect-power-query.md), una [cartella Common Data Model](connect-common-data-model.md), o [Microsoft Dataverse](connect-dataverse-managed-lake.md).

1. Esegui il [processo di unificazione dei dati](data-unification.md) identificando i [campi di origine](map-entities.md), rimuovendo i [duplicati](remove-duplicates.md), [abbinando le condizioni](match-entities.md) e [unificando i campi](merge-entities.md).

1. Familiarizza con le [entità create da sistema](entities.md) e crea [relazioni tra le entità inserite](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Passaggio 4. Migliorare i profili unificati con previsioni, attività e misure

Con i profili unificati impostati, migliora i tuoi dati e aumenta ulteriormente le informazioni che forniscono.

1. Scegli da una libreria in espansione di provider di arricchimento per [arricchire i dati dei tuoi clienti](enrichment-hub.md).

1. Utilizza [modelli predefiniti](predictions-overview.md) per prevedere la probabilità di abbandono o i ricavi previsti.

1. [Configura le attività](activities.md) in base ai dati inseriti e visualizza le interazioni con i tuoi clienti in una sequenza temporale cronologica.

1. [Crea misure](measures.md) per valutare obiettivi aziendali e KPI.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Passaggio 5. Creare segmenti e attivare dati tramite varie opzioni di esportazione

Ora che i tuoi dati sono completi e contengono un'ampia gamma di informazioni sui tuoi clienti, cerca i modi per agire su quei dati.

1. [Crea segmenti](segments.md), sottoinsiemi della tua base clienti, per garantire che le tue azioni siano pertinenti per i clienti di riferimento.

1. Sfoglia il catalogo in espansione delle [opzioni di esportazione](export-destinations.md) dove è possibile utilizzare i dati dei clienti. Ad esempio, puoi utilizzare i dati per gestire promozioni e contattare i clienti con il marketing digitale.

1. Esamina le opzioni di integrazione, ad esempio con altre app Dynamics 365 con il [componente aggiuntivo scheda cliente](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
