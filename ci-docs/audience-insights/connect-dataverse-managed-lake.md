---
title: Connettersi alle tabelle in Microsoft Dataverse
description: Importa dati da un data lake Microsoft Dataverse gestito.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692579"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Connessione ai dati in un Data Lake gestito di Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Questo articolo fornisce informazioni su come gli utenti Dataverse possono connettersi rapidamente alle proprie entità analitiche in un lake gestito di Dataverse. Devi essere un amministratore dell'organizzazione Dataverse per procedere e vedere l'elenco delle entità disponibili nel lake gestito.

## <a name="important-considerations"></a>Considerazioni importanti

I dati archiviati nei servizi online come Azure Data Lake Storage possono essere archiviati in una posizione diversa rispetto a quella in cui i dati vengono elaborati o archiviati in Dynamics 365 Customer Insights.Importando o connettendoti a dati archiviati nei servizi online, accetti che i dati possano essere trasferiti e archiviati con Dynamics 365 Customer Insights. [Altre informazioni sono disponibili nel Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Connettersi a un data lake gestito Dataverse

1. In Audience Insights, vai a **Dati** > **Origini dati**.

2. Seleziona **Aggiungi origine dati**.

3. Seleziona **Connetti a lake Microsoft Dataverse gestito** e seleziona **Avanti**.

4. Immetti un **nome** per l'origine dati e quindi seleziona **Avanti**. Linee guida per i nomi: 
   - Deve iniziare con una lettera.
   - Usa solo lettere e numeri. Gli spazi e i caratteri speciali non sono consentiti.
   - Usa tra 3 e 64 caratteri.

5. Fornisci l'**Indirizzo del server** per l'organizzazione Dataverse e seleziona **Accedi**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Schermata nella fase di inserimento dei dati in cui un utente può inserire l'URL dell'ambiente Dataverse.":::

6. Seleziona le tabelle che desideri inserire come entità per informazioni dettagliate dall'elenco disponibile.    

   > [!NOTE]
   > Se alcune tabelle sono già selezionate, potrebbero essere utilizzate da altre applicazioni Dynamics 365 (come Dynamics 365 Sales Insights o Customer Service Insights). Non è possibile modificare la selezione. Queste tabelle saranno disponibili come entità una volta creata l'origine dati.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Finestra di dialogo che mostra un elenco di entità nell'ambiente Dataverse.":::

7. Salva la tua selezione per iniziare a sincronizzare le tabelle selezionate da Dataverse. Troverai la connessione appena aggiunta nella pagina **Origine dati**. Verrà messo in coda per l'aggiornamento e visualizzerà il conteggio delle entità su 0 fino a quando tutte le tabelle selezionate non saranno sincronizzate.

Solo un'origine dati di un ambiente può utilizzare contemporaneamente lo stesso data lake gestito di Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Modificare l'origine dati di un data lake gestito Dataverse

Modifichi la selezione dell'entità solo dopo aver creato l'origine dati. Ad esempio, se sono state aggiunte ulteriori entità a Dataverse e vuoi importare anche quelle.    
Per connettersi a un altro data lake Dataverse, [crea una nuova origine dati](#connect-to-a-dataverse-managed-lake).

1. In Audience Insights, vai a **Dati** > **Origini dati**.

2. Accanto all'origine dati che vuoi aggiornare, seleziona i puntini di sospensione.

3. Seleziona l'opzione **Modifica** nell'elenco.

4. Seleziona le entità aggiuntive dall'elenco disponibile di entità e seleziona **Salva**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]