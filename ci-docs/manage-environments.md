---
title: Gestisci ambienti
description: Scopri come gestire gli ambienti Customer Insights esistenti come amministratore.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304286"
---
# <a name="manage-environments"></a>Gestisci ambienti

Gli amministratori [creano](create-environment.md) e gestitscono gli ambienti. Possono modificare alcune impostazioni negli ambienti esistenti. Azienda, tipo, regione, opzione di archiviazione e le impostazioni Dataverse vengono corrette dopo la creazione dell'ambiente. Se vuoi modificare queste impostazioni, [ripristina l'ambiente](#reset-an-existing-environment-preview) o [crea un nuovo ambiente](create-environment.md).

## <a name="edit-an-existing-environment"></a>Modificare un ambiente esistente

Modifica i dettagli di un ambiente esistente come il nome o l'impostazione dell'ambiente predefinito.

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona l'icona **Modifica**.

   :::image type="content" source="media/edit-environment.png" alt-text="Icona per modificare le impostazioni dell'ambiente.":::

1. Nel riquadro **Modifica ambiente** , aggiorna le impostazioni dell'ambiente.

1. Seleziona **Verifica e termina** e poi **Aggiorna** per applicare le modifiche.

## <a name="change-the-owner-of-an-environment"></a>Cambiare il proprietario di un ambiente

Diversi utenti possano disporre delle autorizzazioni di amministratore, ma solo un utente è il proprietario di un ambiente. Per impostazione predefinita, è l'amministratore che crea inizialmente un ambiente. In qualità di amministratore di un ambiente, puoi assegnare la proprietà a un altro utente con autorizzazioni di amministratore.

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona l'icona **Modifica**.

1. Nel riquadro **Modifica ambiente** vai al passaggio **Informazioni di base**.

1. Nel campo **Cambia proprietario dell'ambiente** scegli il nuovo proprietario dell'ambiente.  

1. Seleziona **Verifica e termina** e poi **Aggiorna** per applicare le modifiche.

## <a name="claim-ownership-of-an-environment"></a>Rivendicare la proprietà di un ambiente

Se l'account utente del proprietario viene eliminato o sospeso, l'ambiente non avrà un proprietario. Qualsiasi utente con autorizzazioni di amministratore può rivendicare la proprietà e diventare il nuovo proprietario. L'amministratore proprietario può continuare a essere il proprietario dell'ambiente o [passare la proprietà a un altro amministratore](#change-the-owner-of-an-environment).

Per rivendicare la proprietà, seleziona il pulsante **Diventa proprietario** visualizzato nella parte superiore di ogni pagina di Customer Insights quando il proprietario originale lascia l'organizzazione.

## <a name="reset-an-existing-environment-preview"></a>Reimpostare l'ambiente esistente (anteprima)

In qualità di proprietario di un ambiente, reimposta un ambiente su uno stato vuoto se desideri eliminare tutte le configurazioni e rimuovere i dati inseriti.

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona l'ambiente che desideri ripristinare e seleziona i puntini di sospensione verticali (&vellip;).

1. Scegliere **Ripristina (anteprima)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Controllo per reimpostare un ambiente.":::

1. Scegli se desideri reimpostare l'intero ambiente, tutto tranne le origini dati o tutto ciò che è configurato nel profilo cliente unificato.

1. Per confermare, immetti il nome dell'ambiente e seleziona **Reimposta**.

## <a name="delete-an-existing-environment"></a>Eliminare un ambiente esistente

In qualità di proprietario di un ambiente, puoi eliminarlo.

> [!IMPORTANT]
> L'eliminazione di un ambiente non rimuove la connessione all'ambiente Dataverse. Se prevedi di connettere lo stesso ambiente Dataverse a un nuovo ambiente Customer Insights in futuro, devi [rimuovere tale connessione all'ambiente Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Seleziona il selettore **Ambiente** nell'intestazione dell'app.

1. Seleziona l'ambiente che desideri eliminare e seleziona i puntini di sospensione verticali (&vellip;). 

1. Scegli **Elimina**.

   :::image type="content" source="media/delete-environment.png" alt-text="Controllo per eliminare l'ambiente.":::

1. Per confermare l'eliminazione, immetti il nome dell'ambiente e seleziona **Elimina**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
