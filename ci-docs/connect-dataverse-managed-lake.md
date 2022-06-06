---
title: Connettersi alle tabelle in Microsoft Dataverse
description: Importa dati da un data lake Microsoft Dataverse gestito.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 7140e9254108bc6f0d518b3ccf4b10fc33cde115
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800178"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Connessione ai dati in un Data Lake gestito di Microsoft Dataverse

Questo articolo fornisce informazioni su come gli utenti Dataverse possono connettersi rapidamente alle entità analitiche in un lake Microsoft Dataverse gestito. 

> [!NOTE]
> Devi essere un amministratore nell'organizzazione Dataverse per procedere e visualizzare l'elenco delle entità disponibili nel lake gestito.

## <a name="important-considerations"></a>Considerazioni importanti

1. I dati archiviati nei servizi online come Azure Data Lake Storage possono essere archiviati in una posizione diversa rispetto a quella in cui i dati vengono elaborati o archiviati in Dynamics 365 Customer Insights.Importando o connettendoti a dati archiviati nei servizi online, accetti che i dati possano essere trasferiti e archiviati con Dynamics 365 Customer Insights. [Altre informazioni sono disponibili nel Microsoft Trust Center.](https://www.microsoft.com/trust-center).
2. Sono visibili solo entità Dataverse con il [rilevamento modifiche](/power-platform/admin/enable-change-tracking-control-data-synchronization) abilitato. Queste entità possono essere esportate in un data lake gestito da Dataverse e utilizzato in Customer Insights. Le tabelle predefinite di Dataverse hanno il rilevamento modifiche abilitato per impostazione predefinita. Devi attivare il rilevamento modifiche per le tabelle personalizzate. Per verificare se una tabella di Dataverse è abilitata per il rilevamento modifiche, vai a [Power Apps](https://make.powerapps.com) > **Dati** > **Tabelle**. Trova la tabella desiderata e selezionala. Vai a **Impostazioni** > **Opzioni avanzate** ed esamina l'impostazione **Rilevamento modifiche**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Connettersi a un data lake gestito Dataverse

1. In Customer Insights, vai a **Dati** > **Origine dati**.

2. Seleziona **Aggiungi origine dati**.

3. Seleziona **Microsoft Dataverse**, quindi **Avanti**.

4. Immetti un **nome** per l'origine dati e quindi seleziona **Avanti**. 

5. Fornisci l'**Indirizzo del server** per l'organizzazione Dataverse e seleziona **Accedi**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Schermata nella fase di inserimento dei dati in cui un utente può inserire l'URL dell'ambiente Dataverse.":::

6. Seleziona le tabelle che desideri importare come entità in Customer Insights dall'elenco disponibile.    

   > [!NOTE]
   > Se alcune tabelle sono già selezionate, potrebbero essere utilizzate da altre applicazioni Dynamics 365 (come Dynamics 365 Sales Insights o Customer Service Insights). Non è possibile modificare la selezione. Queste tabelle saranno disponibili come entità una volta creata l'origine dati.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Finestra di dialogo che mostra un elenco di entità nell'ambiente Dataverse.":::

7. Salva la tua selezione per iniziare a sincronizzare le tabelle selezionate da Dataverse. Troverai la connessione appena aggiunta nella pagina **Origine dati**. Verrà messo in coda per l'aggiornamento e visualizzerà il conteggio delle entità su 0 fino a quando tutte le tabelle selezionate non saranno sincronizzate.

Solo un'origine dati di un ambiente può utilizzare contemporaneamente lo stesso data lake gestito di Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Modificare l'origine dati di un data lake gestito Dataverse

Modifichi la selezione dell'entità solo dopo aver creato l'origine dati. Ad esempio, se sono state aggiunte ulteriori entità a Dataverse e vuoi importare anche quelle.    
Per connettersi a un altro data lake Dataverse, [crea una nuova origine dati](#connect-to-a-dataverse-managed-lake).

1. Vai a **Dati** > **Origini dati**.

2. Accanto all'origine dati che desideri aggiornare, seleziona i puntini di sospensione verticali (&vellip;).

3. Seleziona l'opzione **Modifica** nell'elenco.

4. Seleziona le entità aggiuntive dall'elenco disponibile di entità e seleziona **Salva**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
