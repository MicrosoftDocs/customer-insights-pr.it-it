---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611104"
---
- **Prestazioni modello di training**: i voti A, B o C indicano le prestazioni della previsione e possono aiutarti a prendere la decisione di usare i risultati archiviati nell'entità di output.

  I voti sono determinati in base alle seguenti regole:
  - **A** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è superiore al tasso di riferimento di almeno il 10%.
  - **B** quando il modello ha previsto con precisione almeno il 50% delle previsioni totali e quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è fino al 10% superiore al tasso di riferimento.
  - **C** quando il modello ha previsto con precisione meno del 50% delle previsioni totali o quando la percentuale di previsioni accurate per i clienti che hanno abbandonato è inferiore al tasso di riferimento.
  - **Baseline** prende l'input della finestra temporale di previsione per il modello (per esempio, un anno), e crea diverse frazioni di tempo dividendolo per 2 fino a raggiungere un mese o meno. Utilizza queste frazioni per creare una regola aziendale per i clienti che non hanno effettuato acquisti durante tale periodo di tempo. Questi clienti vengono considerati come persi. La regola di business basata sul tempo con la più alta capacità di prevedere chi può abbandonare viene scelta come modello di base.

- **Probabilità di abbandono (numero di clienti)**: Gruppi di clienti basati sul loro rischio previsto di abbandono. Facoltativamente, [crea segmenti di clienti](../prediction-based-segment.md) con rischio elevato di abbandono. Tali segmenti aiutano a capire dove dovrebbe posizionare il limite per l'appartenenza al segmento.

- I **fattori più influenti**: Ci sono molti fattori che vengono presi in considerazione quando si crea la tua previsione. Ciascuno dei fattori ha la sua importanza calcolata per le previsioni aggregate create da un modello. Usa questi fattori per convalidare i risultati della previsione. Oppure, usa queste informazioni in seguito per [creare segmenti](../prediction-based-segment.md) che potrebbero contribuire a influenzare il rischio di abbandono per i clienti.