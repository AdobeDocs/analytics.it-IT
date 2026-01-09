---
title: Stato identificato
description: Flag che determina il riconoscimento per l'unione.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: f75a1f6d9f08f422595c24760796abf0f8332ddb
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%

---

# Stato identificato

La &#39;dimensione dello stato identificato&#39; [](overview.md) è specifica per le [suite di rapporti virtuali di Analytics](../cda/overview.md) cross-device. Segnala se gli hit sono identificati (uniti) o meno dal sistema al momento dell’esecuzione del rapporto. Questa dimensione è utile per comprendere il livello di unione o &quot;compressione&quot; dei dati da parte di CDA.

## Popolare questa dimensione con i dati

Se hai configurato [Analisi multidispositivo](../cda/overview.md) per una suite di rapporti virtuale, questa dimensione funziona in modo predefinito.

## Elementi dimensionali

Gli elementi Dimension includono `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: l&#39;hit è mappato a una persona.
* **`"Unidentified"`**: l&#39;hit non è mappato a una persona e non può essere mappato da alcun metodo di attribuzione.
