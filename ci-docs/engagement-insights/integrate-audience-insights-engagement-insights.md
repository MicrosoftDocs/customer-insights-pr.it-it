---
title: Creare un collegamento tra Informazioni dettagliate sul gruppo di destinatari e Informazioni dettagliate sull'interazione
description: Crea un collegamento attivo tra Informazioni dettagliate sul gruppo di destinatari e Informazioni dettagliate sull'interazione per consentire la condivisione bidirezionale dei dati.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d93a49a29c29103e189a6d4a42294c18dc28abd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2021
ms.locfileid: "7559023"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Creare un collegamento tra Informazioni dettagliate sul gruppo di destinatari e Informazioni dettagliate sull'interazione

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

L'integrazione tra Informazioni dettagliate sul gruppo di destinatari e Informazioni dettagliate sull'interazione collega gli ambienti di entrambe le funzionalità e consente la condivisione bidirezionale dei dati tra le stesse.

Utilizza profili e segmenti unificati di Informazioni dettagliate sul gruppo di destinatari per ulteriori opzioni di analisi in Informazioni dettagliate sull'interazione. Esporta gli eventi che hanno un alto valore aziendale da Informazioni dettagliate sull'interazione. Utilizza questi eventi per aggiungere dati a profili unificati in Informazioni dettagliate sul gruppo di destinatari.

## <a name="prerequisites"></a>Prerequisiti

- I profili di Informazioni dettagliate sul gruppo di destinatari devono essere archiviati in un account Azure Data Lake Storage di cui sei proprietario o in un data lake gestito di [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;. 
- Inoltre, l'ambiente delle informazioni dettagliate sul gruppo di destinatari deve avere un ambiente Dataverse associato. Se inoltre tale ambiente usa anche Dataverse per l'archiviazione dei dati, assicurati di selezionare l'opzione **Abilita condivisione dati** nelle informazioni dettagliate sul gruppo di destinatari. Per ulteriori informazioni, vedi [Creare e configurare un collegamento a pagamento nelle informazioni dettagliate sul gruppo di destinatari](../audience-insights/get-started-paid.md).
- Sono necessarie autorizzazioni di amministratore per gli ambienti di Informazioni dettagliate sull'interazione e Informazioni dettagliate del gruppo di destinatari.
- Gli ambienti collegati devono trovarsi nella stessa area geografica.

> [!NOTE]
> - Se la sottoscrizione alle informazioni dettagliate sul gruppo di destinatari è una versione di valutazione che utilizza un data lake gestito internamente dalle informazioni dettagliate sul gruppo di destinatari, contatta [pirequest@microsoft.com](mailto:pirequest@microsoft.com) per assistenza. 
> - Se il tuo ambiente di Informazioni dettagliate sul gruppo di destinatari utilizza Azure Data Lake Storage per archiviare i dati, devi aggiungere un'entità servizio Azure di Informazioni dettagliate sull'interazione all'account di archiviazione. Per informazioni dettagliate, vedi [Connettersi a un account Azure Data Lake Storage con un'entità servizio di Azure per Informazioni dettagliate sul gruppo di destinatari](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Creare un collegamento all'ambiente

Puoi creare un collegamento all'ambiente aggiornando le impostazioni **Amministratore** > **Ambiente** in Informazioni dettagliate sull'interazione.

**Per stabilire un collegamento attivo tra Informazioni dettagliate sul gruppo di destinatari e Informazioni dettagliate sull'interazione**

1. Nella pagina **Amministratore dell'ambiente**, seleziona la scheda **Collega ambienti**.

    :::image type="content" source="media/integrate1.png" alt-text="Configurare un ambiente.":::

1. Seleziona **Configura ambienti** nell'angolo in alto a sinistra o nella parte inferiore della schermata.

     :::image type="content" source="media/integrate2.png" alt-text="Selezionare l'ambiente di Informazioni dettagliate sul gruppo di destinatari.":::

1. Seleziona un ambiente di Informazioni dettagliate sul gruppo di destinatari , quindi seleziona ***Avanti** per finire. Ora puoi selezionare funzionalità facoltative per gli ambienti collegati.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Abilitare attributi e segmenti di profili unificati di Informazioni dettagliate sul gruppo di destinatari

Dopo aver collegato gli ambienti, puoi selezionare funzionalità facoltative per tali ambienti. Queste funzionalità abilitano attributi e segmenti di profili unificati di Informazioni dettagliate sul gruppo di destinatari per l'analisi interattiva dei dati dei clienti.

> [!IMPORTANT]
> Affinché i segmenti di Informazioni dettagliate sul gruppo di destinatari siano visualizzati in informazioni dettagliate sull'interazione, devi prima [eseguire processi di merge e downstream](../audience-insights/merge-entities.md). I processi di downstream sono importanti perché generano una tabella univoca che prepara i segmenti di Informazioni dettagliate sul gruppo di destinatari da condividere con Informazioni dettagliate sull'interazione (se è pianificato un aggiornamento del sistema, includerà automaticamente i processi di downstream).

**Per analizzare i dati web in Informazioni dettagliate sull'interazione**

1. Nella pagina **Amministratore dell'ambiente**, attiva **Condividi dati di Informazioni dettagliate sul gruppo di destinatari con Informazioni dettagliate sull'interazione**, quindi seleziona **Avanti**.

    :::image type="content" source="media/integrate4.png" alt-text="Selezionare funzionalità.":::

1. Seleziona gli attributi dei profili unificati che diventeranno dimensioni in Informazioni dettagliate sull'interazione (non tutti gli attributi sono dimensioni utili; ad esempio, è improbabile che tu abbia bisogno di **Nome** o **Cognome** come attributo per l'analisi degli eventi del sito Web).

    :::image type="content" source="media/integrate5.png" alt-text="Curare dimensioni.":::

   >[!NOTE]
   > Tutti gli attributi di profilo di Informazioni dettagliate sul gruppo di destinatari che rappresentano identificatori (come **ID** e **ID alternativo**) vengono filtrati dagli attributi disponibili e diventano dimensioni in Informazioni dettagliate sull'interazione.

1. Al termine della selezione degli attributi, seleziona **Avanti**.
1. Aggiungi gli utenti che possono visualizzare dimensioni e segmenti di profilo di Informazioni dettagliate sul gruppo di destinatari in Informazioni dettagliate sull'interazione.

    :::image type="content" source="media/integrate6.png" alt-text="Gestire l'accesso ai dati del cliente.":::

   > [!IMPORTANT]
   > Se non aggiungi esplicitamente gli utenti in questo passaggio, i dati non saranno visibili agli utenti in informazioni dettagliate sull'interazione.
   > Affinché i segmenti di Informazioni dettagliate sul gruppo di destinatari siano visualizzati in informazioni dettagliate sull'interazione, devi prima [eseguire processi di merge e downstream](../audience-insights/merge-entities.md). I processi di downstream sono importanti perché generano una tabella univoca che prepara i segmenti di Informazioni dettagliate sul gruppo di destinatari da condividere con Informazioni dettagliate sull'interazione (se è pianificato un aggiornamento del sistema, includerà automaticamente i processi di downstream).

1. Esamina la selezione, quindi seleziona **Fine**.

    :::image type="content" source="media/integrate7.png" alt-text="Esaminare le impostazioni dei dati dei clienti.":::

## <a name="export-refined-events-to-audience-insights"></a>Esportare gli eventi affinati in Informazioni dettagliate sul gruppo di destinatari

Dopo aver creato un collegamento tra gli ambienti, puoi esportare gli eventi affinati da Informazioni dettagliate sull'interazione in Informazioni dettagliate sul gruppo di destinatari e utilizzarli come nuova origine dati. 

Per maggiori informazioni, vedi [Integrare dati Web di Informazioni dettagliate sull'interazione con Informazioni dettagliate sul gruppo di destinatari](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
