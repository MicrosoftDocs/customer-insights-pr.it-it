---
title: Gestire profili sconosciuti con Customer Insights
description: Utilizza profili cliente sconosciuti creati e gestiti in Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776826"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Gestire profili sconosciuti con Customer Insights

Gli utenti di Internet sono spesso non identificati o anonimi online. Anche i clienti più fedeli possono sembrare "sconosciuti" se non hanno effettuato l'accesso su dispositivi diversi. Per molti marchi, gli utenti noti o autenticati sono una minoranza nonostante le crescenti aspettative dei clienti relative alla personalizzazione. Con i cookie di terze parti futuri in questione, la gestione delle preferenze degli utenti in base a dati proprietari è fondamentale per ottenere esperienze personalizzate.

Una personalizzazione ottimale dipende da quanto bene conosci il tuo cliente e Customer Insights ti aiuta a farlo monitorando tutti i tuoi clienti.  Non devi limitare o interrompere l'utilizzo dei dati raccolti all'inizio del percorso del cliente. Customer Insights ti consente di utilizzare i tuoi dati per creare un profilo cliente per utenti sconosciuti. Puoi quindi utilizzare quel profilo per ulteriori azioni, nonostante informazioni di contatto mancanti. Importa dati proprietari da origini come sistemi Web, per dispositivi mobili o CRM in Customer Insights per arricchire continuamente i profili cliente. Man mano che unisci più interazioni, [trasforma il cliente *sconosciuto* in un cliente *noto*](unknown-to-known.md).

## <a name="sample-scenario"></a>Scenario di esempio

Supponiamo che un utente utilizzi il proprio dispositivo mobile per navigare nel tuo sito di e-commerce. Il sito Web assegna l'identificatore univoco "mobile_guest123" al visitatore e inizia a raccogliere attività comportamentali in base alla sua attività online. Ad esempio, quali pagine ha visitato, quanto tempo ha trascorso su quelle pagine o su quali collegamenti ha fatto clic. Non conosci il suo nome o indirizzo e-mail, ma questi dati possono fornire informazioni dettagliate su questo specifico utente ai marchi. A tua volta, puoi utilizzare tali informazioni dettagliate la prossima volta che l'utente visita il sito. Utilizza Customer Insights per cercare "mobile_guest123" e recuperare l'elenco dei segmenti dell'utente, ad esempio "bio", "clienti con prenotazione via dispositivo mobile", "clienti di alto valore" ecc., oppure per recuperare il profilo e creare esperienze web personalizzate. Puoi anche esportare i dati in qualsiasi sistema di attivazione per fare la stessa cosa.

## <a name="prerequisites"></a>Prerequisiti

- Inserimento di dati proprietari in Customer Insights
- Ogni entità dispone di un ID univoco impostato come chiave primaria
- Ogni entità con una chiave primaria per la personalizzazione è unificata
- Il sistema di gestione dei contenuti del tuo sito Web può utilizzare le API (per la personalizzazione del Web basata sulla comunicazione diretta con Customer Insights)

La tabella seguente mostra un esempio semplificato di come possono essere acquisiti eventi Web di alto valore.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|1|15-09-2022 9:00:00|abc123|CookieID1|Vista prodotto|
|2|18-09-2022 10:05:00|abc123|CookieID1|Vista prodotto|
|3|18-09-2022 10:10:00|abc123|CookieID1|Aggiungi al carrello|
|4|21-09-2022 09:05:00|abc123|CookieID1|Vista prodotto|

## <a name="data-ingestion"></a>Inserimento dati

Per ulteriori informazioni sulle opzioni disponibili per l'inserimento di dati, vedi [Panoramica delle origini dati](data-sources.md).

## <a name="data-unification"></a>Unificazione dei dati

Per altre informazioni sull'unificazione di profili cliente, vedi [Panoramica dell'unificazione dei dati](data-unification.md).

## <a name="get-insights"></a>Informazioni approfondite

[Arricchisci](enrichment-hub.md) i tuoi dati, genera [misure](measures.md) e crea [segmenti](segments.md) per un'ulteriore attivazione.

Ad esempio, puoi creare segmenti di utenti sconosciuti che hanno visitato le stesse pagine di prodotto ma non hanno mai completato la transazione.

## <a name="activation"></a>Attivazione

Con i tuoi dati in Customer Insights e le tue informazioni dettagliate pronte per iniziare a lavorare, puoi utilizzare Customer Insights per la personalizzazione:

1. Utilizza l'[API OData](apis.md) per recuperare un profilo cliente o di appartenenza di un segmento. Per altri esempi, vedi [Esempi di query OData per le API di Customer Insights](odata-examples.md).

1. [Esporta](export-destinations.md) i tuoi dati nei tuoi sistemi di attivazione.

Esempio: un utente sconosciuto visita più volte un sito Web e visita le pagine dei prodotti per vari modelli di scarpe in pelle. Con quei dati disponibili in Customer Insights, puoi includere l'utente sconosciuto nel segmento di persone interessate alle scarpe in pelle. Utilizza tale segmento per informare la personalizzazione della build del tuo sito Web per i visitatori che ritornano. Alla visita successiva, il sito riconosce l'utente sconosciuto e potrebbe offrirgli un coupon del 10% sulle scarpe in pelle.

[!INCLUDE [footer-include](includes/footer-banner.md)]
