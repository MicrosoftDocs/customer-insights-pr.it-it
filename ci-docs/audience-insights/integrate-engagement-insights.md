---
title: Integrare i dati Web di Informazioni dettagliate sull'interazione con Audience Insights
description: Porta le informazioni Web sui clienti da Informazioni dettagliate sull'interazione a Audience Insights.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mukeshpo
manager: shellyha
ms.openlocfilehash: ba1cf6c7e85b8fe90baf34018f1309095573adf1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267681"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrare i dati Web di Informazioni dettagliate sull'interazione con Audience Insights

I clienti spesso effettuano le transazioni quotidiane online utilizzando i siti Web. La funzionalità Informazioni dettagliate sull'interazione in Dynamics 365 Customer Insights è una comoda soluzione per integrare i dati Web come origine. Oltre ai dati transazionali, demografici o comportamentali, possiamo vedere gli impegni sul Web in profili cliente unificati. Possiamo utilizzare questo profilo per ottenere informazioni aggiuntive come segmenti, misure o previsioni per l'attivazione di destinatari.

Questo articolo descrive i passaggi per trasferire i dati sull'impegno Web dei tuoi clienti da Informazioni dettagliate sull'interazione nell'ambiente Audience Insights esistente.

In questo esempio, si presume un ambiente che contiene profili cliente unificati. I profili sono stati unificati con origini di sondaggi, vendite al dettaglio e un sistema di creazione di ticket. Mostra anche gli impegni correlati dei clienti. 

Ora vogliamo sapere se un cliente visita le nostre proprietà Web e capire i suoi impegni. Gli impegni includono, ad esempio, siti Web visitati o pagine di prodotto visualizzate da un collegamento ricevuto in un'e-mail.

## <a name="prerequisites"></a>Prerequisiti

Per integrare i dati da Informazioni dettagliate sull'interazione, è necessario soddisfare alcuni prerequisiti: 

- Integra l'SDK di Informazioni dettagliate sull'interazione con il tuo sito web. Per altre informazioni, vedere [Iniziare a usare l'SDK Web](../engagement-insights/instrument-website.md).
- L'esportazione di eventi Web da Informazioni dettagliate sull'interazione richiede l'accesso a un account di archiviazione ADLS Gen 2 che verrà utilizzato per inserire i dati degli eventi Web in Audience Insights. Per ulteriori informazioni, vedi [Esportare eventi](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Configurare eventi affinati in Informazioni dettagliate sull'interazione

Dopo che un amministratore ha instrumentato un sito Web con l'SDK di Informazioni dettagliate sull'interazione, *eventi di base* vengono raccolti quando un utente visualizza una pagina web o fa clic da qualche parte. Gli eventi di base tendono a contenere numerosi dettagli. A seconda del caso d'uso, è necessario solo un sottoinsieme di dati in un evento di base. Informazioni dettagliate sull'interazione ti consente di creare *eventi affinati* che contengono solo le proprietà di un evento di base selezionate.     

Per ulteriori informazioni, vedere [Creare e modificare eventi affinati](../engagement-insights/refined-events.md).

Considerazioni sulla creazione di eventi affinati: 

- Fornisci un nome significativo per l'evento affinato. Può essere utilizzato come nome dell'impegno in Audience Insights.
- Seleziona almeno le seguenti proprietà per creare un'impegno in Audience Insights: 
    - Signal.Action.Name - indicando i dettagli dell'impegno
    - Signal.User.Id - utilizzato per il mapping con l'ID cliente
    - Signal.View.Uri: utilizzato come indirizzo Web come base per segmenti o misure
    - Signal.Export.Id - da utilizzare come chiave primaria per gli eventi <!-- system generated, do we need to list?-->
    - Signal.Timestamp - per determinare la data e l'ora dell'impegno

Seleziona i filtri per concentrarti sugli eventi e sulle pagine importanti per il tuo caso d'uso. In questo esempio, utilizzeremo il nome di azione "Promozione tramite e-mail".

## <a name="export-the-refined-web-events"></a>Esportare gli eventi Web affinati 

Dopo aver definito l'evento affinato, è necessario configurare l'esportazione dei dati dell'evento in un Azure Data Lake Storage, che può essere impostato come origine dati per l'inserimento in Audience Insights. Le esportazioni avvengono costantemente man mano che gli eventi fluiscono dalla proprietà Web.

Per ulteriori informazioni, vedi [Esportare eventi](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Inserire i dati degli eventi in Audience Insights

Ora che hai definito l'evento affinato e configurato la sua esportazione, passiamo a inserire i dati in Audience Insights. È necessario creare una nuova origine dati basata su una cartella Common Data Model. Immettere i dettagli per l'account di archiviazione in cui esportare gli eventi. Nel file *default.cdm.json* seleziona l'evento affinato da inserire e crea l'entità in Audience Insights.

Per ulteriori informazioni, vedere [Connettersi a una cartella Common Data Model usando un account Azure Data Lake](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Correlare i dati degli eventi affinati come impegno di un profilo cliente

Dopo aver completato l'importazione dell'entità, è possibile configurare l'impegno per il profilo del cliente.

Per altre informazioni, vedi [Impegni cliente](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Pagina Impegni con riquadro Modifica impegno espanso e campi compilati.":::

Configura il nuovo impegno con la seguente mapping: 

- **Chiave primaria:** Signal.Export.Id, un ID univoco disponibile per ogni record di evento in Informazioni dettagliate sull'interazione. Questa proprietà viene generata automaticamente.

- **Timestamp:** Signal.Timestamp nella proprietà dell'evento.

- **Evento:** Signal.Name, il nome dell'evento di cui desideri tener traccia.

- **Indirizzo Web:** Signal.View.Uri che si riferisce all'URI della pagina che ha creato l'evento.

- **Dettagli:** Signal.Action.Name per rappresentare le informazioni da associare all'evento. La proprietà selezionata in questo caso indica che l'evento è per la promozione tramite e-mail.

- **Tipo di impegno:** In questo esempio, scegliamo il tipo di impegno esistente WebLog. Questa selezione è un'utile opzione di filtro per eseguire modelli di previsione o creare segmenti basati su questo tipo di impegno.

- **Imposta relazione:** Questa impostazione importante lega l'impegno ai profili cliente esistenti. **Signal.User.Id** è l'identificatore configurato nell'SDK da raccogliere e si riferisce all'ID utente in altre origini dati configurate in Audience Insights. In questo esempio, configuriamo la relazione tra Signal.User.Id e RetailCustomers:CustomerRetailId, che è la chiave primaria definita nella fase di mapping del processo di unificazione dei dati.


Dopo aver elaborato gli impegni, è possibile esaminare i record dei clienti e aprire una scheda cliente per visualizzare gli impegni di Informazioni dettagliate sull'interazione nella sequenza temporale. 

> [!TIP]
> Per trovare un ID cliente con un impegno di Informazioni dettagliate sull'interazione, vai a **Entità** e visualizza in anteprima i dati per l'entità UnifiedActivity. ActivityTypeDisplay = WebLog contiene l'impegno di Informazioni dettagliate sull'interazione configurato nell'esempio precedente. Copia l'ID cliente per uno di quei record e per quell'ID nel pagina **Clienti**.

## <a name="next-steps"></a>Passaggi successivi

Ora puoi creare [segmenti](segments.md), [misure](measures.md) e [previsioni](predictions.md) per stabilire una connessione significativa con i tuoi clienti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]