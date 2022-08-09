---
title: Connessione ai dati in un Data Lake gestito di Microsoft Dataverse
description: Importa dati da un data lake Microsoft Dataverse gestito.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206958"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Connessione ai dati in un Data Lake gestito di Microsoft Dataverse

Gli utenti di Microsoft Dataverse possono connettersi rapidamente alle entità analitiche in un data lake gestito da Microsoft Dataverse. Solo un'origine dati di un ambiente può utilizzare contemporaneamente lo stesso data lake gestito di Dataverse.

> [!NOTE]
> Devi essere un amministratore nell'organizzazione Dataverse per procedere e visualizzare l'elenco delle entità disponibili nel lake gestito.

## <a name="prerequisites"></a>Prerequisiti

- I dati archiviati nei servizi online come Azure Data Lake Storage possono essere archiviati in una posizione diversa rispetto a quella in cui i dati vengono elaborati o archiviati in Dynamics 365 Customer Insights.Importando o connettendoti a dati archiviati nei servizi online, accetti che i dati possano essere trasferiti e archiviati con Dynamics 365 Customer Insights. [Altre informazioni sono disponibili nel Microsoft Trust Center.](https://www.microsoft.com/trust-center).

- Sono visibili solo entità Dataverse con il [rilevamento modifiche](/power-platform/admin/enable-change-tracking-control-data-synchronization) abilitato. Queste entità possono essere esportate in un data lake gestito da Dataverse e utilizzato in Customer Insights. Le tabelle predefinite di Dataverse hanno il rilevamento modifiche abilitato per impostazione predefinita. Devi attivare il rilevamento modifiche per le tabelle personalizzate. Per verificare se una tabella di Dataverse è abilitata per il rilevamento modifiche, vai a [Power Apps](https://make.powerapps.com) > **Dati** > **Tabelle**. Trova la tabella desiderata e selezionala. Vai a **Impostazioni** > **Opzioni avanzate** ed esamina l'impostazione **Rilevamento modifiche**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Connettersi a un data lake gestito Dataverse

1. Vai a **Dati** > **Origini dati**.

1. Seleziona **Aggiungi origine dati**.

1. Seleziona **Microsoft Dataverse**.

1. Immetti un **Nome** per l'origine dati e una **Descrizione** opzionale.

1. Fornisci l'**Indirizzo del server** per l'organizzazione Dataverse e seleziona **Accedi**.

1. Seleziona le tabelle che desideri inserire come entità in Customer Insights dall'elenco disponibile.

   > [!NOTE]
   > Se alcune tabelle sono già selezionate, potrebbero essere utilizzate da altre applicazioni Dynamics 365 (come Dynamics 365 Sales Insights o Customer Service Insights). Non è possibile modificare la selezione. Queste tabelle saranno disponibili come entità una volta creata l'origine dati.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Finestra di dialogo che mostra un elenco di entità nell'ambiente Dataverse.":::

1. Salva la tua selezione per iniziare a sincronizzare le tabelle selezionate da Dataverse. Troverai la connessione appena aggiunta nella pagina **Origine dati**. Verrà messo in coda per l'aggiornamento e visualizzerà il conteggio delle entità su 0 fino a quando tutte le tabelle selezionate non saranno sincronizzate.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Il caricamento dei dati può richiedere tempo. Al termine dell'aggiornamento, i dati inseriti possono essere esaminati nella pagina [**Entità**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Modificare l'origine dati di un data lake gestito Dataverse

Modifichi la selezione dell'entità solo dopo aver creato l'origine dati. Ad esempio, se sono state aggiunte ulteriori entità a Dataverse e vuoi importare anche quelle.
Per connettersi a un altro data lake Dataverse, [crea una nuova origine dati](#connect-to-a-dataverse-managed-lake).

1. Vai a **Dati** > **Origini dati**.

1. Accanto all'origine dati che desideri aggiornare, seleziona **Modifica**.

1. Seleziona le entità aggiuntive dall'elenco disponibile di entità.

1. Fai clic su **Salva** per applicare le modifiche e tornare alla pagina **Origine dati**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]