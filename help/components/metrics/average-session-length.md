---
title: Lunghezza media sessione (mobile)
description: La lunghezza media della sessione per il dispositivo mobile.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: 47d5a532505aff48d43972836c78620870bd8221
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 8%

---

# Lunghezza media sessione (mobile)

La metrica &quot;Lunghezza media sessione (mobile)&quot; mostra il tempo medio di presenza di un dato elemento dimensione per elemento dimensione. È simile al [Tempo trascorso per visita [secondi]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) metrica, tranne per il fatto che questa metrica utilizza come parte del calcolo componenti specifici dell’SDK per dispositivi mobili.

## Modalità di calcolo di questa metrica

Questa metrica viene calcolata utilizzando [metriche di mobile](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=it) `'Total session length' / ('Launches' - 'First launches'`.
