---
title: Rimuovere i duplicati prima di unificare i dati
description: Il secondo passaggio nel processo di unificazione consente nel selezionare il record da conservare quando vengono trovati duplicati.
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
ms.openlocfilehash: a838fbdabdb3bfffc6d3835a3f0e97306a43964a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139434"
---
# <a name="remove-duplicates-before-unifying-data"></a>Rimuovere i duplicati prima di unificare i dati

Questo passaggio nell'unificazione consente facoltativamente di impostare regole per la gestione dei record duplicati all'interno di un'entità. La *deduplicazione* consente di identificare i record e di unirli in un unico record. I record di origine vengono collegati al record unito con ID alternativi. Se le regole non vengono configurate, verranno applicate le regole definite dal sistema.

## <a name="include-enriched-entities-preview"></a>Includere entità arricchite (anteprima)

Se hai arricchito le entità a livello di origine dati per migliorare i risultati dell'unificazione, selezionale. Per altre informazioni, vedi [Arricchimento per le origini dati](data-sources-enrichment.md).

1. Nella pagina **Record duplicati** seleziona **Utilizza entità arricchite** nella parte superiore della pagina.

1. Nel riquadro **Usa entità arricchite** scegli una o più entità arricchite.

1. Seleziona **Fatto**.

## <a name="define-deduplication-rules"></a>Definisci le regole di deduplicazione

1. Nella pagina **Record duplicati** seleziona un'entità e quindi **Aggiungi regola** per definire le regole di deduplicazione.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Screenshot delle pagine dei record duplicati con l'opzione Mostra altro evidenziata":::

   1. Nel riquadro **Aggiungi regola** immetti le informazioni seguenti:
      - **Seleziona campo**: scegli dall'elenco dei campi disponibili dell'entità di cui desideri verificare la presenza di duplicati. Scegli campi che sono probabilmente univoci per ogni singolo cliente. Ad esempio, un indirizzo e-mail o la combinazione di nome, città e numero di telefono.
      - **Normalizza**: Seleziona una delle seguenti opzioni di normalizzazione per gli attributi selezionati.
        - **Numeri**: converte altri sistemi numerici, come i numeri romani, in numeri arabi. *VIII* diventa *8*.
        - **Simboli**: rimuove tutti i simboli e i caratteri speciali. *Head&Shoulder* diventa *HeadShoulder*.
        - **Testo in minuscolo**: converte tutti i caratteri in minuscolo. *TUTTO MAIUSCOLO e titolo* diventa *tutto maiuscolo e titolo*.
        - **Tipo (telefono, nome, indirizzo, organizzazione)**: standardizza nomi, titoli, numeri di telefono, indirizzi e così via.
        - **Unicode in ASCII**: converte la notazione Unicode in caratteri ASCII. */u00B2* diventa *2*.
        - **Spazio vuoto**: rimuove tutti gli spazi. *Hello World* diventa *HelloWorld*.
      - **Precisione**: Consente di impostare il livello di precisione da applicare per questa condizione.
        - **Di base**: Scegli tra *Basso (30%)*, *Medio (60%)*, *Alto (80%)* ed *Esatto (100%)*. Seleziona **Esatto** per abbinare solo i record che corrispondono al 100 percento.
        - **Personalizzato**: Consente di impostare una percentuale per la corrispondenza dei record. Il sistema metterà in corrispondenza solo i record che superano questa soglia.
      - **Nome**: nome della regola.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Screenshot del riquadro Aggiungi regole per rimuovere i duplicati.":::

   1. Facoltativamente, seleziona **Aggiungi** > **Aggiungi condizione** per aggiungere più condizioni alla regola. Le condizioni sono collegate a un operatore logico AND e quindi eseguite solo se tutte le condizioni sono soddisfatte.

   1. Facoltativamente, scegli **Aggiungi** > **Aggiungi eccezione** per [aggiungere eccezioni alla regola](match-entities.md#add-exceptions-to-a-rule). Le eccezioni vengono utilizzate per affrontare rari casi di falsi positivi e falsi negativi.

   1. Seleziona **Fine** per creare la regola.

1. Facoltativamente, [aggiungi altre regole](#define-deduplication-rules).

1. Seleziona un'entità e quindi **Modifica preferenze di unione**.

1. Nel riquadro **Preferenze unione**:
   1. Scegli una delle tre opzioni per determinare quale record conservare se viene trovato un duplicato:
      - **Con più dati**: identifica il record con i campi di attributo con più dati come record vincitore. È l'opzione di unione predefinita.
      - **Piu recente**: il record vincitore è quello più recente. Richiede una data o un campo numerico per definire la recency.
      - **Meno recente**: il record vincitore è quello meno recente. Richiede una data o un campo numerico per definire la recency.
      
      In caso di parità, il record vincitore è quello con il valore della chiave primaria MAX(PK) o maggiore.
      
   1. Facoltativamente, per definire le preferenze di unione sui singoli attributi di un'entità, seleziona **Avanzate** nella parte inferiore del riquadro. Ad esempio, puoi scegliere di conservare il messaggio e-mail più recente E l'indirizzo più completo da record diversi. Espandi l'entità per vedere tutti i suoi attributi e definisci quale opzione utilizzare per i singoli attributi. Se scegli un'opzione basata sulla recency, devi anche specificare un campo data/ora che definisca la recency.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Riquadro delle preferenze di unione avanzate che mostrano l'indirizzo e-mail più recente e l'indirizzo più completo":::

   1. Seleziona **Fine** per applicare le preferenze di unione.

1. Dopo aver definito le regole di deduplicazione e le preferenze di unione, seleziona **Avanti**.
  
> [!div class="nextstepaction"]
> [Passaggio successivo per una singola entità: unifica i campi](merge-entities.md)

> [!div class="nextstepaction"]
> [Passaggio successivo per più entità: condizioni corrispondenti](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Output di deduplicazione come entità

Il processo di deduplicazione crea una nuova entità deduplicata per ciascuna delle entità di origine. Queste entità possono essere trovate insieme a **ConflationMatchPairs:CustomerInsights** nella sezione **Sistema** della pagina **Entità**, con il nome **Deduplication_DataSource_Entity**.

Un'entità di output della deduplicazione contiene le seguenti informazioni:

- ID/chiavi
  - Campi chiave primaria e ID alternativo. Il campo ID alternativo è costituito da tutti gli ID alternativi identificati per un record.
  - Il campo Deduplication_GroupId mostra il gruppo o il cluster identificato all'interno di un'entità che raggruppa tutti i record simili in base ai campi di deduplicazione specificati. È utilizzato per scopi di elaborazione del sistema. Se non sono state specificate regole di deduplicazione manuale e si applicano regole di deduplicazione definite dal sistema, potresti non trovare questo campo nell'entità di output della deduplicazione.
  - Deduplication_WinnerId: questo campo contiene l'ID vincitore dei gruppi o cluster identificati. Se Deduplication_WinnerId è uguale al valore della chiave primaria per un record, significa che il record è il record vincitore.
- Campi utilizzati per definire le regole di deduplicazione.
- I campi Regola e Punteggio per indicare quale delle regole di deduplicazione è stata applicata e il punteggio restituito dall'algoritmo di corrispondenza.

[!INCLUDE[footer-include](includes/footer-banner.md)]
