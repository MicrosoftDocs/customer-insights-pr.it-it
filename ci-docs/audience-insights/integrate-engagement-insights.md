---
title: Integrare i dati Web di Informazioni dettagliate sull'interazione con Informazioni dettagliate sul gruppo di destinatari
description: Porta le informazioni Web sui clienti da Informazioni dettagliate sull'interazione a Informazioni dettagliate sul gruppo di destinatari.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2789a7d1379e0cf56511b272a763c904d8a3d347058ea9e029aaff0f723a028
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033774"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrare i dati Web di Informazioni dettagliate sull'interazione con Informazioni dettagliate sul gruppo di destinatari

I clienti spesso effettuano le transazioni quotidiane online utilizzando i siti Web. La funzionalità di informazioni dettagliate sull'interazione (anteprima) in Dynamics 365 Customer Insights è una soluzione pratica per integrare i dati Web come origine. Oltre ai dati transazionali, demografici o comportamentali, possiamo vedere gli impegni sul Web in profili cliente unificati. Possiamo utilizzare questi profili per ottenere ulteriori informazioni dettagliate, come segmenti, misure o previsioni per l'attivazione di gruppi di destinatari.

Questo articolo descrive i passaggi per trasferire i dati sull'impegno Web dei tuoi clienti da Informazioni dettagliate sull'interazione nell'ambiente Informazioni dettagliate sul gruppo di destinatari esistente.

In questo esempio, si presume un ambiente che contiene profili cliente unificati. I profili sono stati unificati con origini di sondaggi, vendite al dettaglio e un sistema di creazione di ticket. Mostra anche gli impegni correlati dei clienti. 

Ora vogliamo sapere se un cliente visita le nostre proprietà Web e capire i suoi impegni. Gli impegni includono, ad esempio, siti Web visitati o pagine di prodotto visualizzate da un collegamento ricevuto in un'e-mail.

## <a name="prerequisites"></a>Prerequisiti

Per integrare i dati da Informazioni dettagliate sull'interazione, è necessario soddisfare alcuni prerequisiti: 

- Integra l'SDK di Informazioni dettagliate sull'interazione con il tuo sito web. Per ulteriori informazioni, vedi [Panoramica delle risorse per gli sviluppatori](../engagement-insights/developer-resources.md).
- L'esportazione di eventi Web dalle informazioni dettagliate sull'interazione richiede l'accesso a un account Azure Data Lake Storage che verrà utilizzato per inserire i dati degli eventi Web nelle informazioni dettagliate sui gruppi di destinatari. Per ulteriori informazioni, vedi [Esportare eventi](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Configurare eventi affinati in Informazioni dettagliate sull'interazione

Dopo che un amministratore esegue la strumentazione di un sito Web con l'SDK di informazioni dettagliate sull'interazione, vengono raccolti *eventi di base* quando un utente visualizza una pagina Web o fa clic in un punto qualsiasi. Gli eventi di base tendono a contenere numerosi dettagli. A seconda del caso d'uso, è necessario solo un sottoinsieme di dati in un evento di base. Informazioni dettagliate sull'interazione ti consente di creare *eventi affinati* che contengono solo le proprietà di un evento di base selezionate.     

Per ulteriori informazioni, vedere [Creare e modificare eventi affinati](../engagement-insights/refined-events.md).

Considerazioni sulla creazione di eventi affinati: 

- Fornisci un nome significativo per l'evento affinato. Verrà utilizzato come nome dell'attività nelle informazioni dettagliate dei gruppi di destinatari.
- Seleziona almeno le seguenti proprietà per creare un'impegno in Informazioni dettagliate sul gruppo di destinatari: 
    - Signal.Action.Name - indica i dettagli dell'attività.
    - Signal.User.Id - viene utilizzato per il mapping con l'ID cliente.
    - Signal.View.Uri - viene utilizzato come indirizzo Web come base per segmenti o misure.
    - Signal.Export.Id - viene usato come chiave primaria per gli eventi.
    - Signal.Timestamp - determina la data e l'ora per l'attività.

Seleziona i filtri per concentrarti sugli eventi e sulle pagine importanti per il tuo caso d'uso. In questo esempio, utilizzeremo il nome di azione "Promozione tramite e-mail".

## <a name="export-the-refined-web-events"></a>Esportazione degli eventi Web affinati 

Dopo aver definito l'evento affinato, devi configurare l'esportazione dei dati dell'evento in Azure Data Lake Storage, che può essere impostato come origine dati per l'inserimento nelle informazioni dettagliate sui gruppi di destinatari. Le esportazioni avvengono costantemente man mano che gli eventi fluiscono dalla proprietà Web.

Per ulteriori informazioni, vedi [Esportare eventi](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Inserire i dati degli eventi in Informazioni dettagliate sul gruppo di destinatari

Ora che hai definito l'evento affinato e configurato la sua esportazione, passiamo a inserire i dati in Informazioni dettagliate sul gruppo di destinatari. È necessario creare una nuova origine dati basata su una cartella Common Data Model. Immettere i dettagli per l'account di archiviazione in cui esportare gli eventi. Nel file *default.cdm.json* seleziona l'evento affinato da inserire e crea l'entità in Informazioni dettagliate sul gruppo di destinatari.

Per ulteriori informazioni, vedi [Connettersi a una cartella Common Data Model usando un account Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Correlare i dati degli eventi affinati come impegno di un profilo cliente

Dopo aver completato l'importazione dell'entità, è possibile configurare l'impegno per il profilo del cliente.

Per altre informazioni, vedi [Impegni cliente](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Pagina Impegni con riquadro Modifica impegno espanso e campi compilati.":::

Configura il nuovo impegno con la seguente mapping: 

- **Chiave primaria**: Signal.Export.Id, un ID univoco disponibile per ogni record di evento nelle informazioni dettagliate sull'interazione. Questa proprietà viene generata automaticamente.

- **Timestamp**: Signal.Timestamp nella proprietà dell'evento.

- **Evento**: Signal.Name, il nome dell'evento di cui desideri tener traccia.

- **indirizzo Web**: Signal.View.Uri che fa riferimento all'URI della pagina che ha creato l'evento.

- **Dettagli**: Signal.Action.Name per rappresentare le informazioni da associare all'evento. La proprietà selezionata in questo caso indica che l'evento è per la promozione tramite e-mail.

- **Tipo di attività**: in questo esempio scegliamo il tipo di attività esistente WebLog. Questa selezione è un'utile opzione di filtro per eseguire modelli di previsione o creare segmenti basati su questo tipo di impegno.

- **Imposta relazione**: questa impostazione importante lega l'impegno ai profili cliente esistenti. **Signal.User.Id** è l'identificatore configurato nell'SDK da raccogliere e si riferisce all'ID utente in altre origini dati configurate in Informazioni dettagliate sul gruppo di destinatari. In questo esempio configuriamo la relazione tra Signal.User.Id e RetailCustomers:CustomerRetailId, che è la chiave primaria identificata nel passaggio della mappa del processo di unificazione dei dati.

Dopo aver elaborato gli impegni, è possibile esaminare i record dei clienti e aprire una scheda cliente per visualizzare gli impegni di Informazioni dettagliate sull'interazione nella sequenza temporale. 

> [!TIP]
> Per trovare un ID cliente con un impegno di informazioni dettagliate sull'interazione, vai a **Entità** e visualizza in anteprima i dati per l'entità UnifiedActivity. ActivityTypeDisplay = WebLog contiene l'impegno di informazioni dettagliate sull'interazione configurato nell'esempio precedente. Copia l'ID cliente per uno di quei record e per quell'ID nel pagina **Clienti**.

## <a name="next-steps"></a>Passaggi successivi

Ora puoi creare [segmenti](segments.md), [misure](measures.md) e [previsioni](predictions.md) per stabilire una connessione significativa con i tuoi clienti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
