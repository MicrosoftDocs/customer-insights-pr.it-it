---
title: Usare il consenso cliente
description: Rispetta le preferenze di consenso dei tuoi clienti in Customer Insights importando i dati sul consenso.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188052"
---
# <a name="use-customer-consent"></a>Usare il consenso cliente

Le normative sulla protezione dei dati e sulla privacy conferiscono alle persone il diritto di disciplinare il modo in cui un'organizzazione usa i propri dati personali. Esempi di tali normative sono il Regolamento generale sulla protezione dei dati nell'Unione Europea o il California Consumer Privacy Act negli Stati Uniti. Tali normative consentono alle persone di rifiutare esplicitamente la raccolta, il trattamento o la condivisione con terze parti dei propri dati personali.  

I clienti possono scegliere di revocare o negare il consenso per specifiche forme di contatto. Potrebbero inoltre richiederti di rifiutare esplicitamente la raccolta, l'archiviazione, l'uso o la vendita dei loro dati personali. È importante che la tua organizzazione rispetti le preferenze di consenso e privacy di tutti i clienti.  

Dynamics 365 Customer Insights ti aiuta a soddisfare le richieste dei tuoi clienti importando e archiviando le loro preferenze come parte dei profili cliente unificati.

Se i dati relativi al consenso sono archiviati separatamente dai profili dei tuoi clienti, [aggiungi i tuoi dati di consenso come nuova origine dati](#import-and-unify-consent-data). L'origine dati che contiene i dati di consenso viene aggiunta al processo di unificazione dei dati. La corretta esecuzione dell'unificazione dei dati di consenso e dei profili dei clienti porta quindi ai profili cliente unificati contenenti le informazioni sul consenso. Per i profili dei clienti che contengono già informazioni sul consenso, vai direttamente alla sezione [Utilizzare i dati di consenso](#use-consent-data).

## <a name="prerequisites"></a>Prerequisiti

Le seguenti informazioni devono essere disponibili nei dati di origine per unificare i dati di consenso con altri profili cliente:

- Chiave alternativa per mappare le informazioni sul consenso ai profili utente in Customer Insights. Ad esempio, un indirizzo e-mail o un numero di telefono.
- Valore del consenso per determinare lo stato del consenso del cliente.

Considera di aggiungere le seguenti informazioni *opzionali*:

- Chiave primaria per aggiornare lo stato del consenso se un cliente richiede una modifica.
- Tipo di consenso, se esiste più di un modo per elaborare le informazioni sui clienti.
- Data del consenso o qualsiasi altro tipo di dato rilevante per i tuoi scenari di consenso.

Tabella di esempio di un semplice database di consenso con più opzioni di consenso:

|ID consenso (chiave primaria)   |Indirizzo e-mail (chiave alternativa)  |Opzione di consenso  |Valore consenso  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Newsletter       |  False       |
|2    |  holly@contoso.com       |  Aggiornamenti del prodotto       |  Vero       |
|3    |  frank@contoso.com       |  Newsletter       | Vero        |
|4    |  frank@contoso.com       |  Aggiornamenti del prodotto       |  False       |

## <a name="import-and-unify-consent-data"></a>Importare e unificare i dati del consenso

Importa dati di consenso nello stesso modo in cui inserisci altre origini dati in Customer Insights. Per altre informazioni sulle origini dati supportate e su come importarle, vedi [Panoramica delle origini dati](data-sources.md).

Per altre informazioni sull'unificazione delle origini dati, vedi [Panoramica dell'unificazione dei dati](data-unification.md).

## <a name="use-consent-data"></a>Usare dati del consenso

Dopo che i dati di consenso fanno parte dei profili cliente unificati, puoi usarli in Customer Insights. Ad esempio, crea un segmento con una regola per assicurarti di rispettare le preferenze sulla privacy e sulla protezione dei dati dei tuoi clienti. Le regole che supportano le preferenze di consenso vengono usate per escludere gli utenti da un segmento in base agli attributi del profilo. Aggiungi una regola a un segmento che esclude i profili dei clienti che non hanno fornito il consenso al contatto.

Facendo riferimento alla tabella di esempio sopra, un segmento potrebbe contenere questa regola: `Consent option=Newsletter & Consent value=True`. Questa configurazione restituisce un segmento che rispetta le preferenze di contatto per inviare una newsletter.

Per altre informazioni sulla creazione di segmenti, vedi [Creare segmenti](segment-builder.md).

Dopo aver creato il segmento, puoi usare una delle tante [opzioni di esportazione](export-destinations.md) per usare il segmento in altre applicazioni.

## <a name="ensure-updated-consent-status"></a>Garantire l'aggiornamento dello stato del consenso

È importante mantenere aggiornato lo stato del consenso per i tuoi clienti. L'aggiornamento pianificato in Customer Insights importa sempre lo stato più recente delle origini dati. Queste informazioni vengono quindi elaborate attraverso l'unificazione dei dati e restituiscono profili clienti aggiornati, che vengono quindi usati per aggiornare i segmenti e assicurarti di usare le informazioni più aggiornate.

In altre parole, assicurati che i dati di origine che vengono importati in Customer Insights contengano sempre le informazioni più recenti.

Per altre informazioni, vedi [Aggiornare i segmenti manualmente](segments.md#refresh-segments) o [Configurare un aggiornamento pianificato](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]
