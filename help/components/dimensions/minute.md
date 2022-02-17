---
title: Minuto
description: Il minuto in cui si è verificata la metrica.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 1%

---

# Minuto

La dimensione &quot;Minuto&quot; indica il minuto in cui si è verificata una determinata metrica (arrotondata per difetto). Il primo elemento dimensione è il primo minuto nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo minuto nell’intervallo di date. Questa dimensione è utile per i rapporti con tendenze, in quanto consente di visualizzare le metriche nel tempo. Data la granularità di questa dimensione, Adobe consiglia di limitare l’intervallo di date del rapporto a uno o due giorni.

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Gli elementi di Dimension includono un dato minuto all’interno dell’intervallo di date di un rapporto accanto alla sua data. È formattato come `HH:MM YYYY-MM-DD`. Elementi Dimension che iniziano con `00:00` equivale alla mezzanotte di quel giorno, mentre i valori iniziano con `23:59` equivale alle 23:59 di quel giorno.
