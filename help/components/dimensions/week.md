---
title: Settimana
description: La settimana in cui si è verificata la metrica.
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 1%

---


# Settimana

La dimensione Settimana indica la settimana in cui si è verificata una metrica specifica. Il primo elemento dimensione è la prima settimana nell&#39;intervallo di date e l&#39;ultimo elemento dimensione è l&#39;ultima settimana nell&#39;intervallo di date. Questa dimensione è fondamentale per i report con tendenze, in quanto consente di visualizzare le metriche nel tempo.

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

In  Analysis Workspace, gli elementi dimensionali includono la data (mese, giorno e anno) del primo giorno della settimana.

Nella Data Warehouse, gli elementi dimensione includono settimane numerate in base all&#39;intervallo di date della richiesta. Ad esempio, la prima settimana completa è `"Week 1"`. Se una richiesta include una settimana parziale, i dati vengono raggruppati nell’elemento dimensione `"Week 0"`.
