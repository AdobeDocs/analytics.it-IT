---
title: Settimana
description: La settimana in cui si verifica la metrica.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 19%

---

# Settimana

La [dimensione](overview.md) di &#39;Settimana&#39; segnala la settimana in cui si è verificata una determinata metrica. Il primo elemento dimensione è la prima settimana nell’intervallo di date e l’ultimo elemento dimensione è l’ultima settimana nell’intervallo di date. Questa dimensione è fondamentale per i rapporti con tendenze, in quanto consente di visualizzare le metriche nel tempo.

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

In Analysis Workspace, gli elementi dimensionali includono la data (mese, giorno e anno) del primo giorno della settimana.

In Data Warehouse, gli elementi dimensionali includono settimane numerate in base all’intervallo di date della richiesta. Ad esempio, la prima settimana completa è `"Week 1"`. Se una richiesta include una settimana parziale, i dati vengono raggruppati nell&#39;elemento dimensione `"Week 0"`.
