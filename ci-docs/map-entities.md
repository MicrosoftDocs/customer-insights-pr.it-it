---
title: Selezionare i campi di origine per l'unificazione dei dati
description: Il primo passaggio nel processo di unificazione consiste nella selezione di entità, attributi, chiavi primarie e tipi semantici per mappare i dati al profilo cliente unificato.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139787"
---
# <a name="select-source-fields-for-data-unification"></a>Selezionare i campi di origine per l'unificazione dei dati

Il primo passaggio nell'unificazione è quello di selezionare le entità e i campi all'interno dei set di dati che desideri unificare. Seleziona le entità che contengono dettagli relativi al cliente come nome, indirizzo, numero di telefono e indirizzo e-mail. È possibile selezionare uno o più entità.

## <a name="select-entities-and-fields"></a>Seleziona entità e campi

1. Vai a **Dati** > **Unifica**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Screenshot della pagina di destinazione per l'unificazione per l'esperienza di prima esecuzione con Richiedi una demo evidenziato.":::

1. Selezionare **Richiedi una demo**.

1. Nella pagina **Campi di origine** selezionare **Seleziona entità e campi**. Viene visualizzato il riquadro **Seleziona entità e campi**.

1. Seleziona almeno un'entità.

1. Per ogni entità selezionata, identifica i campi da utilizzare per abbinare i record dei clienti e i campi da includere nel profilo unificato. Questi campi sono chiamati *Attributi*. È possibile selezionare gli attributi richiesti individualmente da un'entità o includere tutti gli attributi di un'entità selezionando la casella di controllo a livello di entità. Puoi cercare parole chiave in tutti gli attributi e le entità per selezionare gli attributi richiesti che desideri mappare.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Screenshot delle entità e degli attributi selezionati.":::

   In questo esempio aggiungiamo le entità **Contatti** e **CustomerLoyalty**. Scegliendo queste entità, puoi ottenere informazioni dettagliate che ti indicano quali clienti online sono membri del programma fedeltà.

1. Seleziona **Applica** per confermare le selezioni. Vengono visualizzati le entità e gli attributi selezionati.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Selezionare la chiave primaria e il tipo semantico per gli attributi

   :::image type="content" source="media/m3_select_primary.png" alt-text="Screenshot delle entità selezionate con la chiave primaria non selezionata." lightbox="media/m3_select_primary.png":::

Per ogni entità, esegui i passaggi seguenti.

1. Scegli la **chiave primaria**. La chiave primaria è un attributo univoco per l'entità. Affinché un attributo sia una chiave primaria valida, non deve includere valori duplicati, valori mancanti o valori null. Gli attributi del tipo di dati String, Integer e GUID sono supportati come chiavi primarie.

1. Per utilizzare i modelli di intelligenza artificiale per previsione intelligenti della semantica, risparmiare tempo e migliorare la precisione, verifica che l'opzione **Mapping intelligente** sia selezionata. Il mapping intelligente evidenzia l'elemento consigliato semantico basato su AI nel campo **Tipo**. È possibile ignorare la selezione suggerita scegliendo qualsiasi tipo semantico dall'elenco di opzioni disponibile.

1. Per ogni attributo, scegli un **Tipo** semantico che meglio descrive quell'attributo, come nome, città o indirizzo e-mail.

   > [!NOTE]
   > Un campo dovrebbe essere mappato al tipo semantico *Person.FullName* per inserire il nome del cliente nella scheda cliente. Altrimenti, le schede cliente appariranno senza nome.

   1. Per modificare un tipo di attributo identificato dal sistema, seleziona un altro tipo. Se il tipo non esiste, crea un tipo semantico personalizzato selezionando il campo **Tipo** per l'attributo e immettendo il nome del tipo semantico personalizzato.

   1. Per aggiungere un attributo che contiene un URL alle immagini del profilo oppure ai loghi disponibili pubblicamente, seleziona l'entità e il campo che contiene l'URL. Nel campo **Tipo** effettua le operazioni seguenti:
      - Per una persona: Person.ProfileImage
      - Per un'organizzazione: Organization.LogoImage

   1. Per un attributo del nome dell'account, inserisci "Organization.Name" nel campo **Tipo**.

1. Esamina gli attributi in cui un tipo semantico viene identificato automaticamente. Questi attributi sono elencati in **Rivedi i campi mappati**. Solo gli attributi con lo stesso tipo possono essere combinati nel passaggio **Campi cliente unificati**. I tipi semantici vengono utilizzati per suggerire automaticamente approfondimenti. Assicurati che i tipi scelti siano coerenti in tutte le entità selezionate.

1. Per gli attributi che non sono mappati automaticamente a un tipo semantico, seleziona un campo del tipo semantico, inserisci il nome del tipo di attributo personalizzato o lasciali non mappati. Questi attributi sono elencati in **Definisci i dati nei campi non mappati**.

1. Dopo aver completato i passaggi per ciascuna entità, seleziona **Salva campi di origine**.

1. Selezionare **Avanti**.

> [!div class="nextstepaction"]
> [Passaggio successivo: rimuovi i duplicati](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
