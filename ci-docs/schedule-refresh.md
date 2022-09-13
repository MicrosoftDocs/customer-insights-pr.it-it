---
title: Pianificare gli aggiornamenti di sistema
description: Pianificare la data e l'ora in cui il sistema deve essere aggiornato
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395961"
---
# <a name="schedule-system-refresh"></a>Pianificare gli aggiornamenti di sistema

Pianifica gli aggiornamenti automatici di tutte le [origini dati inserite](data-sources.md). Gli aggiornamenti automatici aiutano a garantire che gli aggiornamenti delle tue origini dati si riflettano nei profili cliente unificati.

> [!NOTE]
> Le origini dati Power Query che gestisci vengono aggiornate in base alle relative pianificazioni. Per pianificare l'aggiornamento di queste origini dati Power Query, configura le impostazioni di aggiornamento per una specifica origine dati nella pagina **Origine dati**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Impostazioni dell'aggiornamento di un flusso di dati.":::

## <a name="set-system-refresh-schedule"></a>Impostare la pianificazione dell'aggiornamento di sistema

1. Vai in **Amministratore** > **Sistema** e seleziona la scheda **Pianifica**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Scheda Pianifica aggiornamento nella pagina Sistema.":::

1. Lo stato predefinito per l'aggiornamento pianificato è **Disattivato**. Per abilitare gli aggiornamenti pianificati, imposta l'interruttore nella parte superiore dello schermo su **Attivato**.

1. Scegli tra aggiornamenti **settimanali** (impostazione predefinita) e **giornalieri**. Se vuoi pianificare gli aggiornamenti settimanali, seleziona uno o più giorni in cui desideri eseguire l'aggiornamento.

1. Imposta il tuo **Fuso orario**, quindi utilizza il menu a discesa **Ora** per impostare i tempi di aggiornamento. Se desideri pianificare più aggiornamenti in un solo giorno, seleziona **Aggiungi un altro orario**. Puoi aggiungere fino a quattro aggiornamenti.

1. Seleziona **Salva** per applicare le modifiche.

[!INCLUDE [footer-include](includes/footer-banner.md)]
