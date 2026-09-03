---
title: Lunghezza media sessione (mobile)
description: La lunghezza media della sessione per il dispositivo mobile.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
TQID: https://experienceleague.adobe.com/4TaQP7sH0pADpnwoQR-aqOpKqKvcuUXU1vmE3-ETOzM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 78
ht-degree: 17%

---

# Lunghezza media sessione (mobile)

Il valore di &#39;Durata media sessione (dispositivi mobili)&#39; [metrica](overview.md) mostra il tempo medio di presenza di un dato elemento dimensione per elemento dimensione. È simile alla metrica [[!UICONTROL Time spent per visit (seconds)]](time-spent-per-visit.md), con la differenza che questa metrica utilizza componenti specifici per SDK mobile come parte del calcolo.

## Come è calcolata questa metrica

Questa metrica viene calcolata utilizzando [Metriche del ciclo di vita](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
