---
title: Settimana
description: La settimana in cui si è verificata la metrica.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 1%

---

# Settimana

La dimensione &quot;Settimana&quot; indica la settimana in cui si è verificata una determinata metrica. Il primo elemento dimensione è la prima settimana nell’intervallo di date e l’ultimo elemento dimensione è l’ultima settimana nell’intervallo di date. Questa dimensione è fondamentale per i rapporti con tendenze, in quanto consente di visualizzare le metriche nel tempo.

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

In Analysis Workspace, gli elementi dimensionali includono la data (mese, giorno e anno) del primo giorno della settimana.

Nella Data Warehouse, gli elementi dimensionali includono settimane numerate in base all’intervallo di date della richiesta. Ad esempio, la prima settimana completa è `"Week 1"`. Se una richiesta include una settimana parziale, i dati vengono raggruppati nell’elemento dimensione `"Week 0"`.
