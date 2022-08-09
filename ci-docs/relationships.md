---
title: Relazioni tra entità e percorsi di entità
description: Crea e gestisci relazioni tra entità in più origini dati.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183568"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Relazioni tra entità e percorsi di entità

Relazioni collega le entità e definisce un grafico dei tuoi dati quando le entità condividono un identificatore comune, una chiave esterna. È possibile fare riferimento a questa chiave esterna da un'entità a un'altra. Le entità connesse abilitano la definizione di segmenti e misure in base a più origini dati.

Esistono tre tipi di Relazioni: 
- Relazioni di sistema non modificabili, create dal sistema come parte del processo di unificazione dei dati
- Relazioni ereditate non modificabili, create automaticamente dall'importazione di origini dati
- Relazioni personalizzate modificabili, create e configurate dagli utenti

## <a name="non-editable-system-relationships"></a>Relazioni di sistema non modificabili

Durante l'unificazione dei dati, le relazioni del sistema vengono create automaticamente in base alla corrispondenza intelligente. Queste relazioni aiutano a mettere in relazione i record del profilo cliente con i record corrispondenti. Il diagramma seguente illustra la creazione di tre relazioni basate sul sistema. L'entità cliente è abbinata ad altre entità per produrre l'entità *Cliente* unificata.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagramma con percorsi relazione per l'entità cliente con tre relazioni 1-n.":::

- La **relazione *CustomerToContact*** è stata creata tra l'entità *Cliente* e l'entità *Contatto*. L'entità *Cliente* ottiene il campo chiave **Contact_contactID** per creare una relazione con il campo dell'entità chiave *Contatto* **contactID**.
- La **relazione *CustomerToAccount*** è stata creata tra l'entità *Cliente* e l'entità *Account*. L'entità *Cliente* ottiene il campo chiave **Account_accountID** per creare una relazione con il campo entità chiave *Account* **accountID**.
- La **relazione *CustomerToWebAccount*** è stata creata tra l'entità *Cliente* e l'entità *WebAccount*. L'entità *Cliente* ottiene il campo chiave **WebAccount_webaccountID** per creare una relazione con il campo entità chiave *WebAccount* **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Relazioni ereditate non modificabili

Durante il processo di acquisizione dei dati, il sistema controlla le origini dati per le relazioni esistenti. Se non esiste alcuna relazione, il sistema le crea automaticamente. Queste relazioni sono utilizzate anche nei processi a valle.

## <a name="create-a-custom-relationship"></a>Creare una relazione personalizzata

La relazione consiste in una *entità di origine* contenente la chiave esterna e una *entità di destinazione* a cui fa riferimento la chiave esterna dell'entità di origine. 

1. Vai a **Data** > **Relationships**.

2. Seleziona **Nuova relazione**.

3. Nel riquadro **Nuova relazione**, immetti le seguenti informazioni:

   :::image type="content" source="media/relationship-add.png" alt-text="Nuovo riquadro laterale delle relazioni con campi di input vuoti.":::

   - **Nome relazione**: nome che riflette lo scopo della relazione. Esempio: CustomerToSupportCase.
   - **Descrizione**: descrizione della relazione.
   - **Entità di origine**: Entità utilizzata come origine nella relazione. Esempio: SupportCase.
   - **Entità di destinazione**: Entità utilizzata come destinazione nella relazione. Esempio: cliente.
   - **Cardinalità di origine**: la cardinalità dell'entità di origine. La cardinalità descrive il numero di possibili elementi in un insieme. Si riferisce sempre alla cardinalità di destinazione. Puoi scegliere tra **Uno** e **Molti**. Sono supportate solo le relazioni molti-a-uno e uno-a-uno.  
     - Molti a uno: più record di origine possono essere correlati a un record di destinazione. Esempio: più casi di supporto da un singolo cliente.
     - Uno a uno: un singolo record di origine è correlato a un record di destinazione. Esempio: un ID fedeltà per un singolo cliente.

     > [!NOTE]
     > Relazioni Molti a molti possono essere create utilizzando due relazioni molti a uno e un'entità di collegamento, che collega l'entità di origine e l'entità di destinazione.

   - **Cardinalità destinazione**:la cardinalità dei record dell'entità di destinazione.
   - **Campo chiave di origine**: il campo della chiave esterna nell'entità di origine. Esempio: SupportCase usa **CaseID** come campo chiave esterna.
   - **Campo chiave di destinazione**: il campo chiave dell'entità di destinazione. Esempio Il cliente usa **CustomerID** come campo chiave.

4. Seleziona **Salva** per creare la relazione personalizzata.

## <a name="set-up-account-hierarchies"></a>Impostare le gerarchie degli account

Gli ambienti che sono configurati per utilizzare gli account aziendali come target primario possono configurare gerarchie di account per gli account aziendali correlati. Per esempio, un'azienda che ha unità di business separate.

Le organizzazioni creano gerarchie di account per gestire meglio gli account e le loro relazioni reciproche. Customer Insights supporta le gerarchie di account padre-figlio già esistenti nei dati dei clienti inseriti. Per esempio, conti da Dynamics 365 Sales. Queste gerarchie possono essere configurate nella pagina **Relazioni**.

1. Vai a **Data** > **Relationships**.
1. Seleziona la scheda **Gerarchia dell'account** .
1. Selezionare **Nuova gerarchia di conti**.
1. Nel riquadro della **gerarchia dell'account** , fornisci un nome per la gerarchia. Il sistema crea un nome per l'entità di output, ma puoi modificarlo.
1. Seleziona l'entità che contiene la tua gerarchia di conti. Di solito è nella stessa entità che contiene i conti.
1. Seleziona l'**UID account** e l'**UID padre** dell'entità selezionata.
1. Seleziona **Salva** per finalizzare la gerarchia degli account.

## <a name="manage-existing-relationships"></a>Gestisci relazioni esistenti

Vai alla pagina **Relazioni** per visualizzare tutte le relazioni create, la relativa entità di origine, l'entità di destinazione e la cardinalità.

:::image type="content" source="media/relationships-list.png" alt-text="Elenco di relazioni e opzioni nella barra delle azioni della pagina Relazioni.":::

Utilizza le opzioni **Filtra per** o **Cerca relazioni** per individuare una particolare relazione. Per visualizzare un diagramma di rete delle relazioni esistenti e la relativa cardinalità, seleziona [**Visualizzatore**](#explore-the-relationship-visualizer).

Seleziona una relazione per visualizzare le azioni disponibili:
- **Modifica**: aggiorna le proprietà delle relazioni personalizzate nel riquadro di modifica e salva le modifiche.
- **Elimina**: elimina le relazioni personalizzate.
- **Visualizza**: visualizza le relazioni create ed ereditate dal sistema.

### <a name="explore-the-relationship-visualizer"></a>Esplora il visualizzatore di relazioni

Il visualizzatore delle relazioni consente di visualizzare un diagramma di rete delle relazioni esistenti tra le entità connesse e la relativa cardinalità. Visualizza anche il percorso relazione.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Screenshot del diagramma di rete del visualizzatore delle relazioni con le connessioni tra entità correlate.":::

Per personalizzare la visualizzazione, puoi modificare la posizione delle caselle trascinandole sulla canvas. Altre opzioni includono: 
- **Esporta come immagine**: salva la vista corrente come file immagine.
- **Passa al layout orizzontale/verticale**: modifica l'allineamento delle entità e delle relazioni.
- **Modifica**: aggiorna le proprietà delle relazioni personalizzate nel riquadro di modifica e salva le modifiche.

## <a name="relationship-paths"></a>Percorsi delle relazioni

Un percorso di relazione descrive le entità connesse con relazioni tra un'entità di origine e un'entità di destinazione. È utilizzato quando si crea un segmento o una misura che include altre entità oltre all'entità del profilo unificato e sono disponibili più opzioni per raggiungere l'entità del profilo unificato. Percorsi relazione differenti possono produrre risultati differenti.

Ad esempio, l'entità *eCommerce_eCommercePurchases* ha le seguenti relazioni con l'entità *Cliente* del profilo unificato:

- eCommerce_eCommercePurchases > Customer
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Customer
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Customer

Un percorso di relazione determina quali entità è possibile utilizzare durante la creazione di regole per misure o segmenti. La scelta dell'opzione con il percorso relazione più lungo produrrà probabilmente meno risultati poiché i record corrispondenti devono essere parte di tutte le entità. In questo esempio, un cliente deve aver acquistato della merce tramite e-commerce (eCommerce_eCommercePurchases) in un punto vendita (POS_posPurchases) e partecipare al nostro programma di fedeltà (loyaltyScheme_loyCustomers). Quando si sceglie la prima opzione, è probabile che si ottengano più risultati perché i clienti devono esistere solo in un'entità aggiuntiva.

### <a name="direct-relationship"></a>Relazione diretta

Una relazione è classificata come **relazione diretta** quando un'entità di origine è correlata a un'entità di destinazione con una sola relazione.

Ad esempio, se un'entità di attività denominata *eCommerce_eCommercePurchases* si connette a un'entità di destinazione *eCommerce_eCommerceContacts* solo attraverso *ContactId*, si tratta di una relazione diretta.

:::image type="content" source="media/direct_Relationship.png" alt-text="L'entità di origine si connette direttamente all'entità di destinazione.":::

#### <a name="multi-path-relationship"></a>Relazione con percorsi multipli

Una **relazione con percorsi multipli** è un tipo speciale di relazione diretta che collega un'entità di origine a più entità di destinazione.

Ad esempio, se un'entità di attività denominata *eCommerce_eCommercePurchases* è correlata a due entità di destinazione, *eCommerce_eCommerceContacts* e *loyaltyScheme_loyCustomers*, si tratta di una relazione con percorsi multipli.

:::image type="content" source="media/multi-path_relationship.png" alt-text="L'entità di origine si connette direttamente a più entità di destinazione tramite una relazione multi-hop.":::

### <a name="indirect-relationship"></a>Relazione indiretta

Una relazione è classificata come **relazione indiretta** quando un'entità di origine è correlata a una o più entità aggiuntiva prima di correlarsi a un'entità di destinazione.

#### <a name="multi-hop-relationship"></a>Relazione multi-hop

Una **relazione multi-hop** è una *relazione indiretta* che consente di connettere un'entità di origine a un'entità di destinazione tramite una o più entità intermedie.

Ad esempio, se un'entità di attività denominata *eCommerce_eCommercePurchasesWest* si connette a un'entità intermedia denominata *eCommerce_eCommercePurchasesEast* e quindi si connette a un'entità di destinazione denominata *eCommerce_eCommerceContacts*, si tratta di una relazione multi-hop.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="L'entità di origine si connette direttamente a un'entità di destinazione con un'entità intermedia.":::

### <a name="multi-hop-multi-path-relationship"></a>Relazioni multi-hop con percorsi multipli

Le relazioni multi-hop e le relazioni con percorsi multipli possono essere usate insieme per creare **relazioni multi-hop con percorsi multipli**. Questo tipo speciale combina le funzioni delle relazioni **multi-hop** e **con percorsi multipli**. Ti consente di connetterti a più di un'entità di destinazione usando entità intermedie.

Ad esempio, se un'entità di attività denominata *eCommerce_eCommercePurchasesWest* si connette a un'entità intermedia denominata *eCommerce_eCommercePurchasesEast* e quindi si connette a due entità di destinazione *eCommerce_eCommerceContacts* e *loyaltyScheme_loyCustomers*, si tratta di una relazione multi-hop con percorsi multipli.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="L'entità di origine si connette direttamente a un'entità di destinazione e si connette a un'altra entità di destinazione tramite un'entità intermedia.":::

## <a name="next-step"></a>Passaggio successivo

Relazioni di sistema e personalizzate sono usate per [creare segmenti](segments.md) e [misure](measures.md) in base a più origini dati che non sono più in silos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
