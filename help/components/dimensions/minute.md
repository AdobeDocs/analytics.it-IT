---
title: Minuto
description: Il minuto in cui è avvenuta la metrica.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 20%

---

# Minuto

Il &#39;Minuto&#39; [dimensione](overview.md) segnala il minuto in cui si è verificata una particolare metrica (arrotondato per difetto). Il primo elemento dimensione è il primo minuto nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo minuto nell’intervallo di date. Questa dimensione è utile per i rapporti con tendenze, in quanto consente di visualizzare le metriche nel tempo. Data la granularità di questa dimensione, Adobe consiglia di limitare l’intervallo di date del rapporto a uno o due giorni.

## Popola questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi di Dimension includono un determinato minuto nell’intervallo di date di un rapporto insieme alla relativa data. È formattato come `HH:MM YYYY-MM-DD`. Elementi Dimension che iniziano con `00:00` equivale a mezzanotte di quel giorno, mentre i valori che iniziano con `23:59` alle 23:59 di quel giorno.
