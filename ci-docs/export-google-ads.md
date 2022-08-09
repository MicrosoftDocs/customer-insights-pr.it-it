---
title: Esportare segmenti in Google Ads (anteprima)
description: Scopri come configurare la connessione ed esportare in Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196583"
---
# <a name="export-segments-to-google-ads-preview"></a>Esportare segmenti in Google Ads (anteprima)

Esporta segmenti di profili cliente unificati in un elenco di gruppi di destinatari di Google Ads e utilizzali per fare pubblicità su Ricerca Google, Gmail, YouTube e Rete Display di Google.

## <a name="prerequisites"></a>Prerequisiti

- Un [account Google Ads](https://ads.google.com/) e le credenziali di amministratore corrispondenti.
- Un [ID cliente Google Ads](https://support.google.com/google-ads/answer/1704344).
- I requisiti dei [criteri di Customer Match](https://support.google.com/adspolicy/answer/6299717) sono soddisfatti.
- I requisiti delle [dimensioni degli elenchi per il remarketing](https://support.google.com/google-ads/answer/7558048) sono soddisfatti.
- [Segmenti configurati](segments.md).
- I profili cliente unificati nei segmenti esportati contengono campi che rappresentano un indirizzo e-mail, telefono, ID inserzionista per dispositivi mobili, ID utente di terze parti o indirizzo.

## <a name="known-limitations"></a>Limitazioni note

- È possibile esportare fino a 1 milione di profili cliente per esportazione in Google Ads e il completamento di tale operazione può richiedere fino a 30 minuti a causa delle limitazioni sul lato provider.
- Solo segmenti.
- La corrispondenza in Google Ads può richiedere fino a 48 ore.

## <a name="set-up-connection-to-google-ads"></a>Configurare la connessione a Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vai ad **Amministratore** > **Connessioni**.

1. Seleziona **Aggiungi connessione** e scegli **Google Ads**.

1. Assegna alla tua connessione un nome riconoscibile nel campo **Nome visualizzato**. Il nome e il tipo di connessione descrivono la connessione. Consigliamo di scegliere un nome che spieghi lo scopo e l'obiettivo della connessione.

1. Scegli chi può utilizzare questa connessione. Per impostazione predefinita, sono solo amministratori. Per ulteriori informazioni, vedi [Consentire ai collaboratori di utilizzare una connessione per le esportazioni](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Immetti l'ID cliente Google Ads.

1. Leggi [Privacy e conformità dei dati](connections.md#data-privacy-and-compliance) e seleziona **Accetto**.

1. Seleziona **Esegui autenticazione con Google Ads** e fornisci le tue credenziali Google Ads.

1. Seleziona **Aggiungi te stesso come utente dell'esportazione** e fornisci le tue credenziali di Customer Insights.

1. Seleziona **Salva** per completare la connessione.

## <a name="configure-an-export"></a>Configurare un'esportazione

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vai a **Dati** > **Esportazioni**.

1. Seleziona **Aggiungi esportazione**.

1. Nel campo **Connessione per esportazione** seleziona una connessione dalla sezione Google Ads. Contatta un amministratore se non è disponibile alcuna connessione.

1. Immetti un nome per l'esportazione.

1. Scegli se usare un gruppo di destinatari esistente o creane uno:
   - Per aggiornare un gruppo di destinatari di Google Ads esistente, inserisci il tuo [ID gruppo di destinatari di Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Per creare un nuovo gruppo di destinatari, lascia vuoto il campo ID gruppo di destinatari di Google. Customer Insights creerà automaticamente un nuovo destinatario nel tuo account Google Ads e userà il nome del segmento esportato.

1. Nella sezione **Corrispondenza dati**, seleziona uno o più campi dati da esportare e seleziona il campo che rappresenta i campi dati corrispondenti in Customer Insights.

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
