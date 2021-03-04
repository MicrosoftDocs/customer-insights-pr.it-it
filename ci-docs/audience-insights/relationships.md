---
title: Relazioni tra entità e percorsi di entità
description: Crea e gestisci relazioni tra entità in più origini dati.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269884"
---
# <a name="relationships-between-entities"></a>Relazioni tra entità

Le relaizoni consentono di connettere entità e a generare un grafico dei tuoi dati quando le entità condividono un identificatore comune (chiave esterna) a cui è possibile fare riferimento da un'entità all'altra. Le entità connesse consentono di definire segmenti e misure in base a più origini dati.

Esistono due tipi di relazioni. Relazioni di sistema non modificabili che vengono create automaticamente e relazioni personalizzate create e configurate dagli utenti.

Durante i processi di corrispondenza e unione, le relazioni di sistema vengono create in background in base alla corrispondenza intelligente. Queste relazioni aiutano a mettere in relazione i record del profilo cliente con i record di altre entità corrispondenti. Il diagramma seguente illustra la creazione di tre relazioni di sistema quando viene eseguita la corrispondenza tra l'entità cliente ed altre entità per produrre l'entità Profilo cliente finale.

> [!div class="mx-imgBorder"]
> ![Creazione della relazione](media/relationships-entities-merge.png "Creazione della relazione")

- La **relazione *CustomerToContact*** è stata creata tra l'entità cliente e l'entità contatto. L'entità cliente ottiene il campo chiave **Contact_contactId** per creare una relazione con il campo Chiave entità contatto **contactID**.
- La **relazione *CustomerToAccount*** è stata creata tra l'entità cliente e l'entità account. L'entità cliente ottiene il campo chiave **Account_accountId** per creare una relazione con il campo Chiave entità account **accountID**.
- La **relazione *CustomerToWebAccount*** è stata creata tra l'entità cliente e l'entità WebAccount. L'entità cliente ottiene il campo chiave **WebAccount_webaccountId** per creare una relazione con il campo Chiave entità WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Creare una relazione

Definire relazioni personalizzate nella pagina **Relazioni**. Ogni relazione è costituita da un'entità di origine (l'entità che detiene la chiave esterna) e un'entità di destinazione (l'entità a cui punta la chiave esterna dell'entità di origine).

1. In Audience Insights, vai a **Dati** > **Relazioni**.

2. Seleziona **Nuova relazione**.

3. Nel riquadro **Aggiungi relazione**, immetti le seguenti informazioni:

   > [!div class="mx-imgBorder"]
   > ![Inserire i dettagli della relazione](media/relationships-add.png "Inserire i dettagli della relazione")

   - **Nome relazione**: nome che riflette lo scopo della relazione (ad esempio, **AccountWebLogs**).
   - **Descrizione**: descrizione della relazione.
   - **Entità origine**: seleziona l'entità utilizzata come origine nella relazione (ad esempio, WebLog).
   - **Cardinalità**: seleziona la cardinalità dei record dell'entità di origine. Ad esempio, "molti" significa che più record Weblog sono correlati a un WebAccount.
   - **Campo chiave origine**: rappresenta il campo chiave esterna nell'entità di origine. Ad esempio, WebLog ha il campo chiave esterna **accountId**.
   - **Entità di destinazione**: seleziona l'entità utilizzata come destinazione nella relazione (ad esempio, WebAccount).
   - **Cardinalità destinazione**: seleziona la cardinalità dei record dell'entità di destinazione. Ad esempio, "uno" significa che più record Weblog sono correlati a un WebAccount.
   - **Campo chiave destinazione**: questo campo rappresenta il campo chiave dell'entità di destinazione. Ad esempio, WebAccount ha il campo chiave **accountId**.

> [!NOTE]
> Sono supportate solo le relazioni molti-a-uno e uno-a-uno. Le relazioni molti-a-molti possono essere create usando due relazioni molti-a-uno e un'entità di collegamento (un'entità utilizzata per connettere l'entità di origine e l'entità di destinazione).

## <a name="delete-a-relationship"></a>Eliminare una relazione

1. In Audience Insights, vai a **Dati** > **Relazioni**.

2. Seleziona le caselle di controllo per le relazioni che vuoi eliminare.

3. Seleziona **Elimina** nella parte superiore della tabella **Relazioni**.

4. Conferma l'eliminazione.

## <a name="next-step"></a>Passaggio successivo

Le relazioni di sistema e personalizzate vengono utilizzate per creare segmenti in base a più origini dati che non sono più in silo. Per ulteriori informazioni, vedi [Segmenti](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]