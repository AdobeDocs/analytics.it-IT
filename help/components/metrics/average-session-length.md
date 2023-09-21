---
title: Lunghezza media sessione (mobile)
description: La lunghezza media della sessione per il dispositivo mobile.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 14%

---

# Lunghezza media sessione (mobile)

La &quot;Lunghezza media della sessione (mobile)&quot; [metrica](overview.md) mostra il tempo medio di presenza di un dato elemento dimensione per elemento dimensione. È simile al [Tempo trascorso per visita [secondi]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) metrica, tranne per il fatto che questa metrica utilizza come parte del calcolo componenti specifici dell’SDK per dispositivi mobili.

## Come è calcolata questa metrica

Questa metrica viene calcolata utilizzando [metriche di mobile](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=it) `'Total session length' / ('Launches' - 'First launches'`.
