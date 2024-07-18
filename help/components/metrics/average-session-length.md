---
title: Lunghezza media sessione (mobile)
description: La lunghezza media della sessione per il dispositivo mobile.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 8%

---

# Lunghezza media sessione (mobile)

Il valore di &#39;Durata media sessione (dispositivi mobili)&#39; [metrica](overview.md) mostra il tempo medio di presenza di un dato elemento dimensione per elemento dimensione. È simile alla metrica [[!UICONTROL Time spent per visit (seconds)]](time-spent-per-visit.md), tranne per il fatto che questa metrica utilizza componenti specifici dell&#39;SDK mobile come parte del calcolo.

## Come è calcolata questa metrica

Questa metrica viene calcolata utilizzando [Metriche del ciclo di vita](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
