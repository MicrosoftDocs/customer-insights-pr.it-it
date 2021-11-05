---
title: Mappare entità e attributi per l'unificazione dei dati
description: Seleziona entità, attributi, chiavi primarie e tipi semantici per mappare i dati nel profilo cliente unificato.
ms.date: 10/18/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
ms.openlocfilehash: 8b84ed1a860e383e4eb3f7499be6d397ba3f1db1
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673268"
---
# <a name="map-entities-and-attributes"></a>Mappare entità e attributi

Un **mapping** è la prima fase del processo di unificazione di Informazioni dettagliate sul gruppo di destinatari. Il mapping comporta tre fasi:

- *Selezione entità*: identifica le entità combinabili che portano a un set di dati con informazioni più complete sui clienti.
- *Selezione attributi*: per ogni entità, identifica le colonne che vuoi combinare e riconciliare nelle fasi di *corrispondenza* e *unione*. Queste colonne sono denominate *Attributi*.
- *Selezione chiave primaria e tipo semantico*: per ogni entità, identifica un attributo che desideri definire come chiave primaria per quell'entità, e per ogni attributo, identifica un tipo semantico che meglio descrive quell'attributo.

Per ulteriori informazioni sul flusso generale di unificazione dei dati, vedi [Unificare](data-unification.md).

## <a name="select-the-first-entities"></a>Selezionare le prime entità

1. In Informazioni dettagliate sul gruppo di destinatari, vai a **Dati** > **Unifica** > **Mapping**.

2. Inizia la fase di mapping selezionando **Seleziona entità**.

3. Seleziona le entità e gli attributi che desideri utilizzare nelle fasi *corrispondenza* e *unione*. Puoi selezionare gli attributi necessari individualmente da un'entità o includere tutti gli attributi da un'entità selezionando la casella di controllo **Includi tutti i campi** a livello di entità. È consigliabile selezionare almeno due entità per trarre vantaggio dal processo di unificazione dei dati.

   > [!div class="mx-imgBorder"]
   > ![Esempio di Aggiungi entità.](media/data-manager-configure-map-add-entities-example.png "Esempio di Aggiungi entità")

   In questo esempio, stiamo aggiungendo le entità **eCommerceContacts** e **loyCustomers**. Scegliendo queste entità, puoi ottenere informazioni dettagliate che ti indicano quali clienti online sono membri del programma fedeltà.
   
   Puoi cercare parole chiave in tutti gli attributi e le entità per selezionare gli attributi richiesti che desideri mappare.
   
     > [!div class="mx-imgBorder"]
   > ![Esempio di campi di ricerca.](media/data-manager-configure-map-search-fields-example.png "Esempio di campi di ricerca")

4. Seleziona **Applica** per confermare le selezioni.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Selezionare la chiave primaria e il tipo semantico per gli attributi

Dopo aver selezionato le entità, la pagina **Mapping** elenca le entità selezionate per la revisione. Definisci la chiave primaria per un'entità e identifica il tipo semantico per un attributo nell'entità.

- **Chiave primaria** : seleziona un attributo come chiave primaria per ogni entità. Affinché un attributo sia una chiave primaria valida, non deve includere valori duplicati, valori mancanti o valori null. Gli attributi del tipo di dati String, integer e GUID sono supportati come chiavi primarie e verranno visualizzati in un campo da cui scegliere.

- **Tipo semantico attributi**: categorie degli attributi, ad esempio indirizzo e-mail o nome. Per utilizzare modelli di intelligenza artificiale per previsione intelligente della semantica, risparmiare tempo e migliorare la precisione, imposta **Mappatura intelligente** su **Attivato**. La mappatura intelligente evidenzia l'elemento consigliato semantico basato su AI nel campo **Tipo**. Se lo imposti su **Disattivato**, vedrai gli elementi consigliati sulle mappe regolari. È possibile selezionare qualsiasi tipo semantico dall'elenco di opzioni disponibile e sovrascrivere la selezione suggerita.

> [!div class="mx-imgBorder"]
> ![Tipo di attributo e previsione semantica.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipo di attributo e previsione semantica")

È anche possibile aggiungere un tipo semantico personalizzato. Seleziona il campo del tipo per un attributo e digita il nome del tipo semantico personalizzato. In tal modo, puoi anche modificare i tipi di attributo identificati dal sistema.

Tutti gli attributi per i quali un tipo semantico viene identificato automaticamente sono raggruppati nella sezione **Rivedi campi mappati**. Esamina questi attributi e i relativi tipi semantici in quanto verranno utilizzati per combinare le tue entità nella fase di unione deell'unificazione dei dati.

Gli attributi che non vengono mappati automaticamente a un tipo semantico vengono raggruppati nella sezione **Definisci i dati nei campi non mappati**. Seleziona il campo del tipo semantico per gli attributi non mappati o immetti il nome del tipo di attributo personalizzato.

> [!div class="mx-imgBorder"]
> ![Chiave primaria e tipo di attributo.](media/data-manager-configure-map-add-attributes.png "Chiave primaria e tipo di attributo")

> [!NOTE]
> Un campo deve essere mappato al tipo semantico Person.FullName per popolare il nome del cliente nella scheda cliente. Altrimenti, le schede cliente appariranno senza nome. 

## <a name="add-and-remove-attributes-and-entities"></a>Aggiungere e rimuovere attributi ed entità

1. In **Unifica** > **Mapping**, seleziona **Modifica campi**.

2. Nel riquadro **Modifica campi**, aggiungi o rimuovi attributi ed entità. Usa la funzionalità di ricerca o scorri per trovare e selezionare gli attributi e le entità che ti interessano. Non puoi rimuovere un attributo o un'entità se è già stata trovata una corrispondenza.

   > [!div class="mx-imgBorder"]
   > ![Aggiungere o rimuovere attributi.](media/configure-data-map-edit.png "Aggiungere o rimuovere attributi")

3. Selezionare **Applica**.

## <a name="add-images-to-profiles"></a>Aggiungere immagini ai profili

Se un'entità contiene URL per immagini o loghi di profilo disponibili pubblicamente, puoi aggiungerli al profilo cliente unificato.

Seleziona l'entità e trova il campo che contiene l'URL dell'immagine del profilo. Nel campo di input **Tipo**, immetti manualmente il valore seguente: 
- Per una persona: Person.ProfileImage
- Per un'organizzazione: Organization.LogoImage

Continua con i passaggi di unificazione e assicurati che l'attributo che contiene l'URL dell'immagine venga aggiunto anche nel passaggio [Unione](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Impostare attributi per le organizzazioni

Per le organizzazioni (anteprima), il tipo di attributo deve essere mappato a "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Chiave primaria e tipo di attributo B2B.](media/configure-data-map-edit-b2b.png "Chiave primaria e tipo di attributo B2B")

## <a name="next-step"></a>Passaggio successivo

Come parte del processo di unificazione dei dati, vai alla pagina **Corrispondenza**. Visita [**Corrispondenza**](match-entities.md) per informazioni su questa fase.

> [!TIP]
> Guarda il seguente video: [Guida introduttiva: Creazione di un profilo cliente unificato](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]