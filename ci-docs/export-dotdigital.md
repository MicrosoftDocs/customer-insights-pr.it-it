---
title: Esportare segmenti in DotDigital (anteprima)
description: Scopri come configurare la connessione ed esportare in DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724991"
---
# <a name="export-segments-to-dotdigital-preview"></a>Esportare segmenti in DotDigital (anteprima)

Esporta segmenti di profili cliente unificati nelle rubriche di DotDigital e usali per campagne, messaggi e-mail di marketing e per costruire segmenti di clientela con DotDigital.

## <a name="prerequisites"></a>Prerequisiti

- Un [account DotDigital](https://dotdigital.com/) e un [utente API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Un ID DotDigital ID una rubrica [nuova](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) o esistente in DotDigital. L'ID è presente nell'URL quando selezioni e apri una rubrica.
- [Segmenti configurati](segments.md) in Customer Insights.
- I profili cliente unificati nei segmenti esportati contengono un campo che rappresenta un indirizzo e-mail.

## <a name="known-limitations"></a>Limitazioni note

- Il collegamento privato in combinazione con Bring your own storage (BYOS) non è supportato.
- È possibile esportare fino a 1 milione di profili cliente per esportazione in DotDigital e il completamento di tale operazione può richiedere fino a tre ore a causa delle limitazioni sul lato provider. Il numero di profili cliente che puoi esportare in DotDigital dipende dal tuo contratto con DotDigital.
- Solo segmenti.

## <a name="set-up-connection-to-dotdigital"></a>Configurare la connessione a DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **DotDigital**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Inserisci il tuo **nome utente e la password dell'API DotDigital**.

1. Immetti l'**ID rubrica DotDigital**.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Connetti** per inizializzare la connessione.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione DotDigital. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Nella sezione **Corrispondenza dati** , nel campo **Email** , seleziona il campo che rappresenta l'indirizzo e-mail del cliente.

1. Eventualmente, esporta **Nome**, **Cognome** **Nome completo**, **Sesso** e **Codice postale**.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

In DotDigital, i tuoi segmenti si trovano nelle [rubriche DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
