---
title: Connettersi alle entità nel data lake gestito di Common Data Service
description: Importa dati da un data lake Common Data Service gestito.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267819"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Connessione ai dati in un Data Lake gestito di Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Questo articolo fornisce informazioni su come i clienti Dynamics 365 esistenti possono connettersi rapidamente alle loro entità analitiche nel lake Common Data Service gestito. Devi essere un amministratore dell'organizzazione Common Data Service per procedere e vedere l'elenco delle entità disponibili nel lake gestito.

## <a name="important-considerations"></a>Considerazioni importanti

I dati archiviati nei servizi online come Azure Data Lake Storage possono essere archiviati in una posizione diversa rispetto a quella in cui i dati vengono elaborati o archiviati in Dynamics 365 Customer Insights.Importando o connettendoti a dati archiviati nei servizi online, accetti che i dati possano essere trasferiti e archiviati con Dynamics 365 Customer Insights. [Altre informazioni sono disponibili nel Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Connettersi a un data lake gestito Common Data Service

1. In Audience Insights, vai a **Dati** > **Origini dati**.

2. Seleziona **Aggiungi origine dati**.

3. Seleziona **Connetti a Common Data Service** e seleziona **Avanti**.

4. Immetti un **nome** per l'origine dati e quindi seleziona **Avanti**. Linee guida per i nomi: 
   - Deve iniziare con una lettera.
   - Usa solo lettere e numeri. Gli spazi e i caratteri speciali non sono consentiti.
   - Usa tra 3 e 64 caratteri.

5. Fornisci l'**Indirizzo server** per l'organizzazione Common Data Service e seleziona **Accedi**.

   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo per inserire l'indirizzo del server Common Data Service](media/enter-CDS-org-details.png)

6. Seleziona le entità che desideri inserire dall'elenco disponibile.    

   > [!NOTE]
   > Se alcune entità sono già selezionate, potrebbero essere utilizzate da altre applicazioni di Dynamics 365 (come Dynamics 365 Sales Insights o Customer Service Insights). Non è possibile modificare la selezione. Queste entità saranno disponibili una volta creata l'origine dati.

   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo che mostra un elenco di entità nell'organizzazione Common Data Service](media/select-analytical-entities.png)

7. Salva la selezione per iniziare a sincronizzare le entità selezionate nel data lake gestito Common Data Service. Troverai la connessione appena aggiunta nella pagina **Origine dati**. Sarà messa in coda per l'aggiornamento e mostrerà un numero di entità pari a 0 fino a quando tutte le entità sono sincronizzate.

Solo un'origine dati di un ambiente può utilizzare contemporaneamente lo stesso data lake gestito di Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Modificare l'origine dati di un data lake gestito Common Data Service

Modifichi la selezione dell'entità solo dopo aver creato l'origine dati. Ad esempio, se sono state aggiunte ulteriori entità a Common Data Service e vuoi importare anche quelle.    
Per connettersi a un Common Data Service diverso, [creare una nuova origine dati](#connect-to-a-common-data-service-managed-lake).

1. In Audience Insights, vai a **Dati** > **Origini dati**.

2. Accanto all'origine dati che vuoi aggiornare, seleziona i puntini di sospensione.

3. Seleziona l'opzione **Modifica** nell'elenco.

4. Seleziona le entità aggiuntive dall'elenco disponibile di entità e seleziona **Salva**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]