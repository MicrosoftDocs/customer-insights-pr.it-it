---
title: Lavorare con i conti aziendali
description: Ulteriori informazioni sugli account aziendali come gruppo di destinatari principale in Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 9bf91671b744198b2f37391edc7abf58eca3c820
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053118"
---
# <a name="work-with-business-accounts"></a>Lavorare con i conti aziendali

Dynamics 365 Customer Insights ti consente di configurare il tuo ambiente per diversi segmenti di gruppi di destinatari principali: singoli consumatori (B2C) e account aziendali (B2B). Negli scenari B2C, i dati sono incentrati sugli individui. Per gli scenari B2B, i destinatari principali sono account, ovvero organizzazioni o aziende, e contatti. Questo articolo vi aiuta a iniziare con un ambiente per i conti aziendali. Elenca le differenze per le aree delle funzionalità in Customer Insights, a seconda dell'ambiente attivo. Per maggiori informazioni sulle differenze, rivedete i documenti delle aree di funzione. 

## <a name="create-an-environment-for-business-accounts"></a>Creare un ambiente per i conti aziendali

Gli amministratori possono [creare un ambiente in un'organizzazione esistente](create-environment.md). Un passo nel processo di creazione di un nuovo ambiente chiede agli amministratori il target primario dell'ambiente. Nel caso si tratti della configurazione iniziale dopo l'acquisto di una licenza, un'esperienza guidata aiuta la creazione del primo ambiente.

Potete quindi [ingerire i dati](data-sources.md) per i conti commerciali e i relativi contatti come fonti di dati da tutte le fonti supportate.

Dopo aver unificato i dati, [specificate le gerarchie dei conti](relationships.md#set-up-account-hierarchies) come parte della configurazione delle relazioni. Puoi anche [configurare delle mappature semantiche](semantic-mappings.md) per collegare le entità di contatto e di conto. 

## <a name="switch-between-primary-target-audience"></a>Passare da un target primario all'altro

Se la tua organizzazione mantiene ambienti per clienti individuali e account aziendali, puoi usare il selettore nel pannello di sinistra per scegliere il pubblico di destinazione principale.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Switcher per cambiare il target primario tra clienti individuali e account aziendali.":::

## <a name="supported-feature-areas"></a>Aree di funzioni supportate

- [Attività](activities.md): Supporto per gli account e i contatti correlati per creare attività e mostrarle in una linea temporale.
- [Relazioni](relationships.md): Il wizard delle attività aiuta a creare relazioni tra le entità in modo che la vista dell'account possa mostrare tutte le attività dei contatti. I contatti possono essere approfonditi per vedere la vista dei contatti e le gerarchie possono essere utilizzate per le aggregazioni delle attività dell'account.
- [Misure](measures.md): Supporta le misure create dal costruttore di misure con un calcolo. Un'impostazione opzionale permette il roll-up per i sottoconti durante la creazione di misure.
- [Segmenti](segments.md): Supporta i segmenti creati da zero con il costruttore di segmenti. I nuovi operatori permettono di incorporare la gerarchia dei conti quando si costruiscono i segmenti.
- [Ingestione dei dati](data-sources.md): Tutte le caratteristiche di quest'area sono le stesse per gli account aziendali e per i clienti individuali.
- [Unificazione dei dati](data-unification.md): Tutte le caratteristiche di quest'area sono le stesse per gli account aziendali e per i clienti individuali.
- [Arricchimento](enrichment-hub.md): Alcuni tipi di arricchimento sono disponibili solo per scenari di clienti individuali, mentre altri sono disponibili esclusivamente per i conti aziendali.
- [Previsioni e modelli out-of-box](predictions-overview.md): La previsione di churn transazionale contiene passi aggiuntivi per i conti aziendali. Altre previsioni sono disponibili solo per i clienti individuali.
- [Attivazione ed esportazione](export-destinations.md): Le esportazioni sono disponibili per i conti aziendali e i clienti individuali. Alcune esportazioni richiedono una configurazione extra e informazioni di contatto proiettate nei segmenti sottostanti per essere valide per i conti aziendali.
- [Impostazioni di sistema](system.md) e [gestione degli utenti](permissions.md): Tutte le caratteristiche di quest'area sono le stesse per gli account aziendali e per i clienti individuali.

