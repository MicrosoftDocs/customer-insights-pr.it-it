---
title: Utilizzare i profili unificati in Dynamics 365 Marketing
description: Scopri come integrare i profili unificati e i segmenti con Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054437"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>Utilizzare i profili unificati del cliente in Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) migliora le esperienze dei clienti, consentendoti di orchestrare percorsi personalizzati su tutti i punti di contatto per rafforzare relazioni e guadagnare fedeltà. L'app Dynamics 365 Marketing funziona perfettamente con Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams e altri prodotti e consente di prendere decisioni migliori e più rapide sfruttando la potenza dei dati e dell'intelligenza artificiale.

Collegando i dati di Customer Insights con Marketing, puoi:

- Puntare a segmenti e profili cliente unificati. Ciò consente di interagire con ogni cliente, indipendentemente dalla posizione dei dati dei clienti.
- Basare il contenuto dinamico (come i token personalizzati) in messaggi e-mail, SMS e notifiche push su misure come lo stato di fedeltà, la data di rinnovo dell'abbonamento, l'account padre o qualsiasi altra misura acquisita nel profilo Customer Insights unificato.
- Caricare dati da Marketing in Customer Insights e combinarli con i dati dei clienti da altre origini.
- Applicare la pulizia, l'arricchimento, e gli strumenti di corrispondenza fuzzy dei dati di Customer Insights.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Utilizzare i profili avanzati dei clienti nel marketing in tempo reale

Il marketing in tempo reale consente di creare [trigger personalizzati](/dynamics365/marketing/real-time-marketing-custom-triggers) che avviano i percorsi del cliente in base a qualsiasi azione del cliente. Più i tuoi dati saranno personalizzati, più pertinenti e personalizzati saranno i tuoi percorsi. Questo è ciò che rende così avanzata la combinazione di Marketing e Customer Insights. Puoi [unificare i dati](data-unification.md) da qualsiasi origine, quindi utilizzarli per ottenere percorsi del cliente iper-personalizzati.

Altre informazioni: [Utilizzare i profili e i segmenti di Customer Insights nel marketing in tempo reale](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Utilizzare segmenti unificati con i percorsi del cliente in uscita

Customer Insights consente di affinare i dati da molte origini e combinarli in segmenti del cliente aggregati. Collegando [Customer Insights con il marketing in uscita](export-dynamics365-marketing.md), questi segmenti appariranno automaticamente *e* vengono automaticamente aggiornati nella finestra di progettazione del percorso del cliente.

Altre informazioni: [Utilizzare i segmenti da Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Estrarre dati da Azure Data Lake Storage

Non sei limitato allo spazio di archiviazione nel cloud se desideri utilizzare i dati di Customer Insights con Marketing. Se hai già la tua configurazione Azure Data Lake Storage, puoi connetterti con Customer Insights, quindi condividere i dati con l'app Marketing proprio come faresti con una configurazione basata su cloud.

Altre informazioni: [Abilitare la condivisione dei dati con Dataverse da Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)