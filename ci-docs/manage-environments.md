---
title: Come gestire gli ambienti
description: Scopri come gestire gli ambienti Customer Insights esistenti come amministratore.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fc3b3f404cf0ac84c782778414494289c803babe
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081676"
---
# <a name="how-to-manage-environments"></a>Come gestire gli ambienti

Gli amministratori [creano](create-environment.md) e gestitscono gli ambienti. Possono modificare alcune impostazioni negli ambienti esistenti. Azienda, tipo, regione, opzione di archiviazione e le impostazioni Dataverse vengono corrette dopo la creazione dell'ambiente. Se vuoi modificare queste impostazioni, ripristina l'ambiente o crea un nuovo ambiente.

## <a name="edit-an-existing-environment"></a>Modificare un ambiente esistente

Puoi modificare alcuni dei dettagli degli ambienti esistenti.

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona l'icona **Modifica**.

   :::image type="content" source="media/edit-environment.png" alt-text="Icona per modificare le impostazioni dell'ambiente.":::

1. Nella casella **Modifica ambiente** , puoi aggiornare le impostazioni dell'ambiente.

Per iniziare con un nuovo ambiente, vedi [Creare un nuovo ambiente](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Cambiare il proprietario di un ambiente

Diversi utenti possano disporre delle autorizzazioni di amministratore, ma solo un utente è il proprietario di un ambiente. Per impostazione predefinita, è l'amministratore che crea inizialmente un ambiente. In qualità di amministratore di un ambiente, puoi assegnare la proprietà a un altro utente con autorizzazioni di amministratore.

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona l'icona **Modifica**.

1. Nella casella **Modifica ambiente** vai al passaggio **Informazioni di base**.

1. Nel campo **Cambia proprietario dell'ambiente** scegli il nuovo proprietario dell'ambiente.  

1. Seleziona **Verifica e termina** e poi **Aggiorna** per applicare le modifiche.

## <a name="claim-ownership-of-an-environment"></a>Rivendicare la proprietà di un ambiente

Se l'account utente del proprietario viene eliminato o sospeso, l'ambiente non avrà un proprietario. Ogni utente con autorizzazioni di amministratore può rivendicare la proprietà e diventare il nuovo proprietario. Può continuare a essere il proprietario dell'ambiente o [passare la proprietà a un altro amministratore](#change-the-owner-of-an-environment).

Per rivendicare la proprietà, seleziona il pulsante **Diventa proprietario** visualizzato nella parte superiore di ogni pagina di Customer Insights quando il proprietario originale lascia l'organizzazione.

## <a name="reset-an-existing-environment-preview"></a>Reimpostare l'ambiente esistente (anteprima)

In qualità di proprietario di un ambiente, puoi reimpostare un ambiente su uno stato vuoto se desideri eliminare tutte le configurazioni e rimuovere i dati inseriti.

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona l'ambiente che desideri ripristinare e seleziona i puntini di sospensione verticali (&vellip;).

1. Scegli l'opzione **Reimposta**.

   :::image type="content" source="media/reset-environment.png" alt-text="Controllo per reimpostare un ambiente.":::

1. Scegli se desideri reimpostare l'intero ambiente, tutto tranne le origini dati o tutto ciò che è configurato nel profilo cliente unificato.

1. Per confermare, immetti il nome dell'ambiente e seleziona **Reimposta**.

## <a name="delete-an-existing-environment"></a>Eliminare un ambiente esistente

In qualità di proprietario di un ambiente, puoi eliminare un ambiente che amministri.

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona l'ambiente che desideri ripristinare e seleziona i puntini di sospensione verticali (&vellip;). 

1. Scegli l'opzione **Elimina**.

   :::image type="content" source="media/delete-environment.png" alt-text="Controllo per eliminare l'ambiente.":::

1. Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Elimina**.

> [!IMPORTANT]
> L'eliminazione di un ambiente non rimuove la connessione all'ambiente Dataverse. Se prevedi di connettere lo stesso ambiente Dataverse a un nuovo ambiente Customer Insights in futuro, è necessario rimuovere tale connessione. Scopri come [rimuovere una connessione esistente all'ambiente Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]