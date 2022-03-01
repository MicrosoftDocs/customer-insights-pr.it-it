---
title: Esportare dati di Customer Insights in Gestione inserzioni di Facebook
description: Scopri come configurare la connessione a Gestione inserzioni di Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643688"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Connettore per Gestione inserzioni di Facebook (anteprima)

Esporta segmenti di profili cliente unificati in Gestione inserzioni di Facebook per creare campagne in Facebook e Instagram.

## <a name="prerequisites"></a>Prerequisiti

- Devi avere un [account inserzionista **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) che include un [account **Facebook Business**](https://business.facebook.com/).
- Devi essere un amministratore nell'[account inserzionista **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Connessione a Gestione inserzioni di Facebook

1. Passa a **Amministratore** > **Destinazioni di esportazione**.

1. In **Gestione inserzioni di Facebook**, seleziona **Configura**.

1. Assegna alla tua destinazione di esportazione un nome riconoscibile nel campo **Nome visualizzato**.

1. Seleziona **Continua con Facebook** per accedere al tuo account inserzionista Facebook.

1. Consenti l'autorizzazione **ads_management** dopo l'autenticazione con Facebook.

1. Seleziona l'**account inserzionista Facebook** che vuoi utilizzare.

1. Seleziona i **destinatari personalizzati esistenti** dall'elenco a discesa o crea **nuovi destinatari personalizzati**. Per ulteriori informazioni, vedi [**Destinatari in Gestione inserzioni di Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Seleziona **Accetto** per confermare **Conformità e privacy dei dati**.

1. Seleziona **Avanti** per configurare l'esportazione.

## <a name="configure-the-connector"></a>Configurare il connettore

1. Nel **campo Scegli identificatore chiave**, seleziona **E-mail**, **Nome e indirizzo** o **Telefono** per inviare a Gestione inserzioni di Facebook.

1. Mappa gli attributi corrispondenti dall'entità cliente unificata per l'identificatore chiave selezionato.
   > [SUGGERIMENTO] Le migliori possibilità di corrispondenza si hanno se selezioni **E-mail** come identificatore chiave. L'aggiunta di identificatori aggiuntivi può migliorare la corrispondenza.

1. Seleziona **Aggiungi attributo** per mappare ulteriori attributi da inviare a Gestione inserzioni di Facebook. Gli attributi di Gestione inserzioni di Facebook sono mapping ai seguenti nomi descrittivi per l'utente: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**

1. Seleziona i segmenti da esportare.

1. Seleziona **Salva**.

## <a name="export-the-data"></a>Esportare i dati

Puoi [esportare dati su richiesta](export-destinations.md). L'esportazione verrà eseguita anche con ogni [aggiornamento pianificato](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Conformità e privacy dei dati

Quando abiliti Dynamics 365 Customer Insights per trasmettere dati a Gestione inserzioni di Facebook, autorizzi il trasferimento di dati al di fuori dei limiti di conformità di Dynamics 365 Customer Insights, inclusi dati potenzialmente sensibili come i dati personali. Microsoft trasferirà tali dati secondo le tue istruzioni, ma devi assicurarti che Facebook rispetti gli obblighi di privacy o sicurezza che ti incombono. Per ulteriori informazioni, vedi [Informativa sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'amministratore di Dynamics 365 Customer Insights può rimuovere questa destinazione di esportazione in qualsiasi momento per interrompere l'utilizzo di questa funzionalità.
