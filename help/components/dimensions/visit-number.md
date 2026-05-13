---
title: Numero di visite
description: L’ennesima visita del visitatore.
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
TQID: https://experienceleague.adobe.com/C6fccfJFGSA4iLuhp2X80aPym4ZcwbrLMaUS2LUfosg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 100%

---

# Numero di visite

La [dimensione](overview.md) “Numero di visite” segnala a quale visita si trova attualmente il visitatore. Quando inizia una nuova visita, questo elemento dimensione aumenta di 1. Questa dimensione è utile quando desideri comprendere quanto sono coinvolti i visitatori quando ritornano sul sito. Si tratta di una dimensione basata sulle visite, il che significa che contiene lo stesso valore per l’intera visita e non può cambiare. Si applica al ciclo di vita del visitatore, indipendentemente dall’intervallo di date del progetto.

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi dimensionali includono la stringa `"Visit number"` seguita dalla rappresentazione numerica della visita in cui il visitatore si trova attualmente. Ad esempio, se il visitatore non è mai stato prima sul sito, la sua prima visita appartiene all’elemento dimensione `"Visit number 1"`. Se si tratta della tredicesima visita del visitatore nel sito, l’elemento appartiene alla dimensione `"Visit number 13"`.
