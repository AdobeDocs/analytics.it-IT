---
title: Lunghezza media della sessione (mobile)
description: Lunghezza media della sessione per il dispositivo mobile.
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 0%

---

# Lunghezza media della sessione (mobile)

La metrica &quot;Lunghezza media della sessione (mobile)&quot; mostra la quantità media di tempo in cui un dato elemento dimensione è presente per elemento dimensione. È simile alla metrica [Tempo medio sul sito](average-time-on-site.md), ma questa metrica utilizza componenti specifici dell’SDK mobile come parte del suo calcolo.

## Calcolo di questa metrica

Questa metrica viene calcolata utilizzando le [metriche mobili](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) `'Total session length' / ('Launches' - 'First launches'`.
