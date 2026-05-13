---
title: Stato identificato
description: Flag che determina il riconoscimento per l'unione.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 111
ht-degree: 9%

---

# Stato identificato

La &#39;dimensione dello stato identificato&#39; [&#128279;](overview.md) è specifica per le [suite di rapporti virtuali di Analytics](../cda/overview.md) cross-device. Segnala se gli hit sono identificati (uniti) o meno dal sistema al momento dell’esecuzione del rapporto. Questa dimensione è utile per comprendere il livello di unione o &quot;compressione&quot; dei dati da parte di CDA.

## Popolare questa dimensione con i dati

Se hai configurato [Analisi multidispositivo](../cda/overview.md) per una suite di rapporti virtuale, questa dimensione funziona in modo predefinito.

## Elementi dimensionali

Gli elementi Dimension includono `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: l&#39;hit è mappato a una persona.
* **`"Unidentified"`**: l&#39;hit non è mappato a una persona e non può essere mappato da alcun metodo di attribuzione.
