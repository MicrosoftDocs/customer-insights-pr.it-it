---
title: Unificare i campi dei clienti per l'unificazione dei dati
description: Unisci entità per creare profili cliente unificati.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: a6f29c4985ee274207d122fb1bd76d97b98613b6
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213587"
---
# <a name="unify-customer-fields-for-data-unification"></a>Unificare i campi dei clienti per l'unificazione dei dati

In questo passaggio del processo di unificazione, scegli ed escludi gli attributi da unire all'interno dell'entità del tuo profilo unificato. Ad esempio, se tre entità avevano dati e-mail, puoi mantenere tutti i tre i campi e-mail separati o puoi unirli in un unico campo e-mail per il profilo unificato. Alcuni attributi vengono combinati automaticamente dal sistema. Puoi creare ID cliente stabili e univoci e raggruppare profili correlati in un cluster.

:::image type="content" source="media/m3_unify.png" alt-text="Pagina di unione nel processo di unificazione dei dati che mostra la tabella con i campi uniti che definiscono il profilo del cliente unificato.":::

## <a name="review-and-update-the-customer-fields"></a>Rivedi e aggiorna i campi cliente

1. Esamina l'elenco dei campi che verranno unificati nella scheda **Campi cliente** della tabella. Apporta eventuali modifiche, se applicabile.

   1. Per tutti i campi combinati, puoi:
      - [Modifica](#edit-a-merged-field)
      - [Rinomina](#rename-fields)
      - [Separa](#separate-merged-fields)
      - [Escludi](#exclude-fields)
      - [Sposta su o sposta giù](#change-the-order-of-fields)

   1. Per tutti i campi singoli, puoi:
      - [Combina campi](#combine-fields-manually)
      - [Combinare un gruppo di campi](#combine-a-group-of-fields)
      - [Rinomina](#rename-fields)
      - [Escludi](#exclude-fields)
      - [Sposta su o sposta giù](#change-the-order-of-fields)

1. Facoltativamente, [genera la configurazione dell'ID cliente](#configure-customer-id-generation).

1. Facoltativamente, [raggruppa profili in famiglie o cluster](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Passaggio successivo: rivedi l'unificazione](review-unification.md)

### <a name="edit-a-merged-field"></a>Modificare un campo unito

1. Seleziona un campo unito e scegli **Modifica**. Viene visualizzato il riquadro Combina campi.

1. Specifica come combinare o unire i campi tramite una delle tre opzioni:
    - **Importanza**: identifica il valore prevalente in base al grado di importanza specificato per i campi partecipanti. È l'opzione di unione predefinita. Seleziona **Sposta su/giù** per impostare la classifica per importanza.

      > [!NOTE]
      > Customer Insights utilizza il primo valore non nullo. Ad esempio, date le entità A, B e C classificate in quest'ordine, se A.Name e B.Name sono nulli, viene utilizzato il valore di C.Name.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Opzione di importanza nella finestra di dialogo dei campi di unione.":::

    - **Più recente**: identifica il valore prevalente in base alla maggiore recency. Richiede un campo data o numerico per ogni entità partecipante nell'ambito dei campi di unione per definire la recency.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Opzione di recency nella finestra di dialogo dei campi di unione.":::

    - **Meno recente**: identifica il valore prevalente in base alla minore recency. Richiede un campo data o numerico per ogni entità partecipante nell'ambito dei campi di unione per definire la recency.

1. È possibile aggiungere altri campi per partecipare al processo di fusione.

1. Puoi rinominare il campo unito.

1. Seleziona **Fatto** per applicare le modifiche.

### <a name="rename-fields"></a>Rinominare i campi

Modifica il nome visualizzato dei campi uniti o separati. Non è possibile modificare il nome dell'entità di output.

1. Seleziona il campo e scegli **Rinomina**.

1. Immetti il nuovo nome visualizzato.

1. Seleziona **Fatto**.

### <a name="separate-merged-fields"></a>Separare i campi uniti

Per separare i campi uniti, trova l'attributo nella tabella. I campi separati vengono visualizzati come punti dati individuali nel profilo del cliente unificato.

1. Seleziona il campo unito e scegli **Campi separati**.

1. Conferma la separazione.

### <a name="exclude-fields"></a>Escludi i campi

Escludi un campo unito o separato dal profilo cliente unificato. Se il campo viene utilizzato in altri processi, ad esempio in un segmento, rimuovilo da questi processi prima di escluderlo dal profilo del cliente.

1. Seleziona un campo e scegli **Escludi**.

1. Conferma l'esclusione.

Per visualizzare l'elenco di tutti i campi esclusi, seleziona **Campi esclusi**. Se necessario, puoi riaggiungere il campo escluso.

### <a name="change-the-order-of-fields"></a>Modificare l'ordine dei campi

Alcune entità contengono più dettagli di altre. Se un'entità include i dati più recenti su un campo, puoi dare la priorità ad altre entità quando unisci i valori.

1. Seleziona il campo.
  
1. Scegli **Sposta su/giù** per impostare l'ordine o trascinare i campi nella posizione desiderata.

### <a name="combine-fields-manually"></a>Combinare i campi manualmente

Combina i campi separati per creare un attributo unito.

1. Seleziona **Combina** > **Campi**. Viene visualizzato il riquadro Combina campi.

1. Specifica i criteri prevalenti dell'unione nell'elenco a discesa **Combina campi per**.

1. Seleziona **Aggiungi campo** per combinare più campi.

1. Fornisci un **Nome** e un **Nome del campo di output**.

1. Seleziona **Fatto** per applicare le modifiche.

### <a name="combine-a-group-of-fields"></a>Combinare un gruppo di campi

Considera un gruppo di campi come una singola unità. Ad esempio, se i nostri record contengono i campi Indirizzo1, Indirizzo2, Città, Stato e CAP, non vogliamo unirli in Indirizzo2 di un record diverso, pensando che ciò renderebbe i nostri dati più completi.

1. Seleziona **Combina** > **Gruppo di campi**.

1. Specifica i criteri prevalenti dell'unione nell'elenco a discesa **Classifica gruppi per**.

1. Seleziona **Aggiungi** e scegli se vuoi aggiungere più campi o gruppi ai campi.

1. Fornire un **Nome** e un **Nome di output** per ogni campo combinato.

1. Specifica un **nome** per il gruppo di campi.

1. Seleziona **Fatto** per applicare le modifiche.

## <a name="configure-customer-id-generation"></a>Configura la generazione dell'ID cliente

Definisci come generare i valori ID cliente, ovvero gli identificatori univoci del profilo cliente. Il passaggio di unificazione dei campi nel processo di unificazione dei dati genera l'identificatore univoco del profilo cliente. L'identificatore è il *CustomerId* nell'entità *Cliente* generata dal processo di unificazione dei dati.

Il valore *CustomerId* si basa su un hash del primo valore delle chiavi primarie prevalenti non nulle. Tali chiavi provengono dalle entità utilizzate nell'unificazione dei dati e sono influenzate dall'ordine di corrispondenza.Pertanto, l'ID cliente generato può cambiare quando un valore di chiave primaria cambia nell'entità primaria dell'ordine di corrispondenza. Il valore della chiave primaria potrebbe non rappresentare sempre lo stesso cliente.

La configurazione di un ID cliente stabile permette di evitare questo comportamento.

1. Selezionare la scheda **Chiavi**.

1. Passa il mouse sulla riga **CustomerId** e seleziona **Configura**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Controllo per personalizzare la generazione dell'ID.":::

1. Seleziona fino a cinque campi che comprenderanno un ID cliente univoco e sono più stabili. I record che non corrispondono alla tua configurazione utilizzano invece un ID configurato dal sistema.  

1. Seleziona **Fatto**.

## <a name="group-profiles-into-households-or-clusters"></a>Raggruppa i profili in famiglie o cluster

Puoi definire regole per raggruppare i profili correlati in un cluster. Ci sono attualmente due tipi di cluster disponibili - cluster domestici e cluster personalizzati. Il sistema sceglie automaticamente una famiglia con regole predefinite se l'entità *Customer* contiene i campi semantici *Person.LastName* e *Location.Address*. Potete anche creare un cluster con le vostre regole e condizioni, simili alle [regole di corrispondenza](match-entities.md#define-rules-for-match-pairs).

1. Seleziona **Avanzate** > **Crea cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Controllo per creare un nuovo cluster.":::

1. Scegli tra un cluster **domestico** o un cluster **personalizzato** . Se i campi semantici *Person.LastName* e *Location.Address* esistono nell'entità *Customer* , la famiglia viene automaticamente selezionata.

1. Fornire un nome per il cluster e selezionare **Done**.

1. Seleziona la scheda **Cluster** per trovare il cluster che hai creato.

1. Specifica le regole e le condizioni per definire il tuo cluster.

1. Seleziona **Fatto**. Il cluster viene creato al termine del processo di unificazione. Gli identificatori del cluster vengono aggiunti come nuovi campi all'entità *Cliente*.

> [!div class="nextstepaction"]
> [Passaggio successivo: rivedi l'unificazione](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
