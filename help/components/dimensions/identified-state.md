---
title: Stato identificato
description: Flag che determina il riconoscimento dal grafico dei dispositivi.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 5%

---

# Stato identificato

&#39;Stato identificato&#39; [dimensione](overview.md) è specifico di [Analytics tra dispositivi](../cda/overview.md) suite di rapporti virtuali. Segnala se gli hit sono identificati (uniti) o meno dal sistema al momento dell’esecuzione del rapporto. Questa dimensione è utile per comprendere il livello di unione o &quot;compressione&quot; dei dati da parte di CDA.

## Popola questa dimensione con i dati

Finché hai [Analytics tra dispositivi](../cda/overview.md) configurata per una suite di rapporti virtuale, questa dimensione funziona in modo predefinito.

## Elementi dimensionali

Gli elementi del Dimension includono `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: l’hit è mappato a una persona.
* **`"Unidentified"`**: l’hit non è mappato a una persona e non può essere mappato da alcun metodo di attribuzione.
