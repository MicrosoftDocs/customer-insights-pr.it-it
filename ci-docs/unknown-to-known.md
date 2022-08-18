---
title: Personalizzare le esperienze con dati su utenti noti e sconosciuti
description: Incorpora le informazioni sugli utenti precedentemente sconosciuti quando conosci la loro identità.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224300"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalizzare le esperienze con dati su utenti noti e sconosciuti

La gestione dei dati dei clienti non è una nuova sfida, ma sta diventando sempre più complessa a mano a mano che gli utenti navigano tra i vari canali digitali che offrono i marchi. Un utente noto (autenticato) in un canale diventa sconosciuto (non autenticato) in un altro canale se non ha effettuato l'accesso. Il problema in genere è che gli utenti non autenticati (sconosciuti) non hanno un ID comune. Potrebbe essere utilizzato per associare attributi di profili significativi e generare profili cliente unificati. Customer Insights consente di risolvere questo problema inserendo i dati dei metodi di tracciamento nei tuoi sistemi di origine. Il consolidamento di profili sconosciuti e noti fornisce alle organizzazioni una visione completa dei profili aggiornati e dei relativi comportamenti, transazioni storiche e dati demografici. Forniscono inoltre una risoluzione dell'identità che ti consente di unificare l'attività dei clienti in più canali, inclusi il tuo sito Web, l'acquisto nel punto vendita, i programmi fedeltà e così via.

## <a name="sample-scenario"></a>Scenario di esempio

Prendiamo in considerazione una catena di caffetterie, con un'ampia base di clienti che acquista caffè e cibo nei punti vendita e ordina prodotti online. Spesso i visitatori online non vengono autenticati durante la navigazione dei prodotti, il che li rende "utenti sconosciuti". Non è facile per la catena di caffetterie fornire offerte ed esperienze personalizzate se gli utenti sono sconosciuti. D'altra parte, i clienti possono accedere al proprio account e diventare "utenti noti" per l'azienda aderendo a un sistema fedeltà, che a sua volta consente esperienze più personalizzate. Customer Insights può consentire alla catena di caffetterie di ottenere informazioni dettagliate su utenti noti e precedentemente sconosciuti.

Con Customer Insights, l'azienda può combinare i profili dei clienti con i dati sulle attività di sessioni non autenticate (sconosciute) dopo che un utente ha effettuato l'accesso ed è diventato noto. La catena di caffetterie può importare dati da altre origini dati in Customer Insights utilizzando connettori integrati per unire le identità dei clienti di vari canali.

## <a name="prerequisites"></a>Prerequisiti

- I dati Web vengono raccolti e contengono "ID visitatore" per tutti i visitatori.
- I dati Web contengono "ID utente autenticati" per i visitatori che hanno effettuato l'accesso. Questi ID sono collegati al sistema fedeltà.
- I dati sugli eventi di alto valore come "Vista prodotto" e "Checkout" sono definiti e inclusi nei dati di origine insieme al timestamp dell'evento e a un ID evento.

La tabella seguente mostra un esempio semplificato di come possono essere acquisiti eventi Web di alto valore.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Vista prodotto|
|2|07-23-2022 10:05:00|abc123|707|Accesso fedeltà|
|3|07-23-2022 10:10:00|abc123|707|Checkout|
|4|07-23-2022 10:20:00|xyz789|--|Vista prodotto|

## <a name="data-ingestion"></a>Inserimento dati

I dati sui clienti possono provenire dal tuo sito Web come dati di eventi e possono essere archiviati nei tuoi servizi di analisi di dati interni o di terze parti. I dati Web contengono utenti noti e sconosciuti se il sito Web dispone di un flusso di autenticazione che si integra con un servizio di autenticazione. Ad esempio, un sistema di eCommerce che richiede agli utenti di fornire i propri dettagli completi per completare una transazione di acquisto. Oppure un sistema fedeltà che richiede l'autenticazione per confermare un destinatario valido degli sconti premio.

I dati dell'evento nell'esempio sopra contengono gli ID profilo distinti degli utenti noti e sconosciuti. Negli eventi 1 e 4, gli utenti sono sconosciuti mentre negli eventi 2 e 3 l'utente con l'ID abc123 si iscrive a un programma fedeltà.

:::image type="content" source="media/website-data-source.png" alt-text="Origini dati che includono il sito Web di Contoso.":::

Per ulteriori informazioni sulle opzioni disponibili per l'inserimento di dati, vedi [Panoramica delle origini dati](data-sources.md).

## <a name="data-unification"></a>Unificazione dei dati

La convergenza di identità sconosciute con identità note consente la personalizzazione in base ai comportamenti degli utenti, indipendentemente dallo stato del loro profilo (noto o sconosciuto). I contenuti personalizzati per tutti gli utenti consentono ai clienti di arrivare rapidamente ai prodotti o servizi più pertinenti a cui sono interessati in quel momento.

Poiché alcuni degli utenti nei nostri dati sono noti, possiamo utilizzare Customer Insights per combinare tali dati con il profilo dell'utente. Per altre informazioni sull'unificazione di profili cliente, vedi [Panoramica dell'unificazione dei dati](data-unification.md).

1. Seleziona i campi di origine dell'entità dei dati Web. Utilizza i dati del profilo memorizzati nei tuoi dati Web e seleziona i campi che rappresentano gli ID con dati demografici.

   :::image type="content" source="media/website-source-fields.png" alt-text="Campi di origine per l'origine dati Web":::

1. Aggiungi regole per unire record duplicati. Per i dati Web, scegli i dati più immessi.

1. Configura le regole di corrispondenza e le condizioni I dati degli eventi dei profili Web in questo esempio verranno confrontati agli ID con i profili di altre origini dati che contengono informazioni sui clienti. Configura regole di corrispondenza esatta negli ID come regole separate con ognuna delle altre entità del profilo che hanno una chiave primaria o una corrispondenza ID corrispondente. Nell'esempio, i dati del profilo dell'evento Web vengono utilizzati come ultima entità corrispondente di modo che altri dati del profilo siano combinati per primi.
   1. La non selezione di **Includi tutti i record** crea profili unificati per utenti noti e include i relativi ID utente sconosciuto corrispondenti. È utile negli scenari in cui intendi visualizzare le attività comportamentali passate di utenti noti quando erano ancora sconosciuti.
   1. La selezione di **Includi tutti i record** crea record di profilo distinti per utenti sconosciuti. Gli utenti sconosciuti hanno un ID cliente univoco. In futuro, quando un profilo noto verrà associato ai dati del profilo degli eventi Web, il percorso del nuovo utente noto potrà essere visualizzato e utilizzato per la personalizzazione anche in base a dati comportamentali sconosciuti passati.

:::image type="content" source="media/website-match-rule.png" alt-text="Regola di corrispondenza per l'entità origine dati del sito Web.":::

## <a name="get-insights"></a>Informazioni approfondite

Se vengono creati profili cliente per utenti sconosciuti e noti, i dati degli eventi Web di alto valore possono essere utilizzati come [attività](activities.md). Queste attività possono essere utilizzate per creare ulteriori informazioni dettagliate. Ad esempio, i clienti che hanno visitato un sito Web sei mesi prima (quando erano ancora sconosciuti) o i clienti che non dispongono di un ID fedeltà e che non hanno mai completato un checkout.

:::image type="content" source="media/website-known-unknown.png" alt-text="Screenshot della pagina con clienti noti e sconosciuti.":::

[Arricchisci](enrichment-hub.md) i tuoi dati, genera [misure](measures.md) e crea [segmenti](segments.md) per un'ulteriore attivazione.

Ad esempio, puoi creare segmenti di utenti noti che hanno esaminato alcuni prodotti ma non hanno mai completato il checkout.

Per maggiori informazioni, vedi [Panoramica dei segmenti](segments.md).

## <a name="activate-insights"></a>Attivare informazioni dettagliate

Esistono diversi modi per esportare i dati e intraprendere azioni in base alle informazioni dettagliate sottostanti.

Per ulteriori informazioni, vedi [Panoramica delle esportazioni](export-destinations.md).
