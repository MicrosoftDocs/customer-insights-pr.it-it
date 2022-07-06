---
title: Connettore Power BI (anteprima)
description: Scopri come utilizzare il connettore Dynamics 365 Customer Insights in Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 72daf6d4ef3b6afb8049c622b57e7ec44762fb21
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051274"
---
# <a name="power-bi-connector-preview"></a>Connettore Power BI (anteprima)

Crea visualizzazioni per i tuoi dati con Microsoft Power BI Desktop. Genera ulteriori informazioni dettagliate e crea report con i dati cliente unificati.

## <a name="prerequisites"></a>Prerequisiti

- Disponi di profili cliente unificati.
- L'ultima versione di [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) è installata sul tuo computer. [Scopri di più su Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurare il connettore per Power BI

1. In Power BI Desktop, seleziona **File** > **Estrai dati**.

1. Seleziona **Altro** e cerca **Dynamics 365 Customer Insights**

1. Seleziona **Connetti**.

1. **Accedi** con lo stesso account organizzativo utilizzato per Customer Insights e seleziona **Connetti**.
   > [!NOTE]
   > L'account indicato in questo passaggio viene utilizzato per recuperare i dati da Customer Insights e non è necessario che sia lo stesso con cui hai effettuato l'accesso a Power BI. Per reimpostare l'account utilizzato per il recupero dei dati, apri Power BI e seleziona **File** > **Opzioni** > **Impostazioni** > **Impostazioni origine dati**. Nell'elenco delle origini dati, seleziona **Accesso a Dynamics 365 Customer Insights**, quindi **Deseleziona autorizzazioni**.  

1. Nella finestra di dialogo **Navigator**. viene visualizzato l'elenco di tutti gli ambienti a cui hai accesso. Espandi un ambiente e apri una qualsiasi delle cartelle (entità, misure, segmenti, arricchimenti). Ad esempio, apri la cartella **Entità** per vedere tutte le entità che puoi importare.

   ![Esplorazione connettori Power BI.](media/power-bi-navigator.png "Esplorazione connettori Power BI")

1. Seleziona le caselle di controllo accanto alle entità da includere e **Carica**. Puoi selezionare più entità da più ambienti.

1. Durante il caricamento delle entità verrà visualizzata una finestra di dialogo di caricamento. Una volta caricate tutte le entità selezionate, puoi utilizzare le funzionalità di Power BI per visualizzare i dati.

## <a name="large-data-sets"></a>Set di dati di grandi dimensioni

Il connettore Customer Insights per Power BI è progettato per funzionare con set di dati che contengono fino a 1 milione di profili cliente. L'importazione di set di dati più grandi può funzionare, ma richiede molto tempo. Inoltre, potrebbe verificarsi un timeout nel processo a causa delle limitazioni di Power BI. Per ulteriori informazioni, vedere [Power BI: raccomandazioni per set di dati di grandi dimensioni](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Utilizzare un sottoinsieme di dati

Prendi in considerazione l'idea di utilizzare un sottoinsieme di dati. Ad esempio, puoi creare [segmenti](segments.md) anziché esportare tutti i record del cliente in Power BI.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>L'ambiente Customer Insights non viene visualizzato in Power BI

Gli ambienti che hanno più di una [relazione](relationships.md) definita tra due entità identiche in Customer Insights non saranno disponibili nel connettore Power BI.

Puoi identificare e rimuovere le Relazioni duplicate.

1. Vai a **Dati** > **Relazioni** sull'ambiente non presente in Power BI.
2. Identifica le relazioni duplicate:
   - Controlla se c'è più di una relazione definita tra le stesse due entità.
   - Controlla se esiste una relazione creata tra due entità che sono entrambe incluse nel processo di unificazione. Esiste una relazione implicita definita tra tutte le entità incluse nel processo di unificazione.
3. Rimuovi qualsiasi Relazione duplicata identificata.

Dopo la rimozione delle Relazioni duplicate, prova a configurare il connettore di Power BI di nuovo. L'ambiente dovrebbe essere disponibile ora.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Errori nei campi della data durante il caricamento delle entità in Power BI Desktop

Quando si caricano entità che contengono campi con un formato data come MM/GG/AAAA, è possibile riscontrare errori dovuti a formati locali non corrispondenti. Questa mancata corrispondenza si verifica quando il tuo file Power BI Desktop è impostato su un'altra lingua rispetto all'inglese (Stati Uniti), poiché i campi della data in Customer Insights vengono salvati in formato USA.

Il file Power BI Desktop ha un'unica impostazione locale, che viene applicata durante il recupero dei dati. Per ottenere l'interpretazione corretta di questi campi data, impostare le impostazioni internazionali del file .BPI su Inglese (Stati Uniti). [Scopri come modificare la lingua di un file di Power BI Desktop](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]
