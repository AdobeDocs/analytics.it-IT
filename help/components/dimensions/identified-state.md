---
title: Stato identificato
description: Flag che determina il riconoscimento tramite il grafico del dispositivo.
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%

---


# Stato identificato

La dimensione &#39;Stato identificato&#39; è specifica per le suite di rapporti virtuali [Analytics multi-dispositivo](../cda/overview.md). Indica se l&#39;ID Experience Cloud  viene riconosciuto dal grafico del dispositivo al momento dell&#39;esecuzione del rapporto. Questa dimensione è utile per comprendere l’efficacia dei punti CDA o dei dati di &quot;compressione&quot;.

## Compilare questa dimensione con i dati

Finché [Analytics multi-dispositivo](../cda/overview.md) è stato configurato per una suite di rapporti virtuale, questa dimensione non è disponibile.

## Elementi Dimension

Gli elementi di Dimension includono `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: Il grafico del dispositivo riconosce l’ID Experience Cloud  associato all’hit.
* **`"Unidentified"`**: Il grafico del dispositivo non riconosce l&#39;ID Experience Cloud , oppure l&#39;hit non ha un ID Experience Cloud .
