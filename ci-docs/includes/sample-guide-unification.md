---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755549"
---
Dopo aver importato i dati, inizia il processo di unificazione dei dati per creare un profilo cliente unificato. Per ulteriori informazioni, vedi [Unificazione dei dati](../data-unification.md).

### <a name="select-source-fields"></a>Selezionare i campi di origine

1. Dopo l'inserimento dei dati, esegui il mapping dei dati di eCommerce e Fedeltà ai tipi di dati comuni. Vai a **Dati** > **Unifica**.

1. Seleziona le entità che rappresentano il profilo cliente, ovvero **eCommerceContacts** e **loyCustomers**.

   ![Unificare le origini dati di e-commerce e fedeltà.](../media/unify-ecommerce-loyalty.png)

1. Seleziona **ContactId** come chiave primaria per **eCommerceContacts** e **LoyaltyID** come chiave primaria per **loyCustomers**.

1. Selezionare **Avanti**. Salta i record duplicati e seleziona **Avanti**.

### <a name="match-conditions"></a>Condizioni di corrispondenza

1. Scegli **eCommerceContacts : eCommerce** come entità primaria e includi tutti i record.

1. Scegli **loyCustomers : LoyaltyScheme** e includi tutti i record.

1. Aggiungi una regola:
   - Seleziona **FullName** sia per eCommerceContacts che per loyCustomers.
   - Seleziona **Tipo (telefono, nome, indirizzo, ...)** per **Normalizza**.
   - Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.
   - Immetti **FullName, Email** per il nome.

1. Aggiungi una seconda condizione per l'indirizzo e-mail:
   - Seleziona **Email** sia per eCommerceContacts che per loyCustomers.
   - Lascia vuoto il campo Normalizza.
   - Imposta **Livello di precisione** su **Di base** e **Valore** su **Alto**.

   ![Unificare la regola di corrispondenza per nome ed e-mail.](../media/unify-match-rule.png)

1. Seleziona **Fatto**.

1. Selezionare **Avanti**.

### <a name="unify-fields"></a>Unifica i campi

1. Rinomina **ContactId** per l'entità **loyCustomers** su **ContactIdLOYALTY** per differenziarlo dagli altri ID inseriti.

1. Seleziona **Avanti** per esaminare e quindi seleziona **Crea profili cliente**.
