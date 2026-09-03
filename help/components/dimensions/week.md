---
title: Settimana
description: La settimana in cui si verifica la metrica.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
TQID: https://experienceleague.adobe.com/Vvr0Svg2khSzWbtWR5hLfveyctOEM-62WU6oxIsvzXs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 141
ht-degree: 37%

---

# Settimana

La [dimensione](overview.md) di &#39;Settimana&#39; segnala la settimana in cui si è verificata una determinata metrica. Il primo elemento dimensione è la prima settimana nell’intervallo di date e l’ultimo elemento dimensione è l’ultima settimana nell’intervallo di date. Questa dimensione è fondamentale per i rapporti con tendenze, in quanto consente di visualizzare le metriche nel tempo.

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

In Analysis Workspace, gli elementi dimensionali includono la data (mese, giorno e anno) del primo giorno della settimana.

In Data Warehouse, gli elementi dimensionali includono settimane numerate in base all’intervallo di date della richiesta. Ad esempio, la prima settimana completa è `"Week 1"`. Se una richiesta include una settimana parziale, i dati vengono raggruppati nell&#39;elemento dimensione `"Week 0"`.
