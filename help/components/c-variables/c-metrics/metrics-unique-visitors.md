---
description: Nella versione 14, un visitatore univoco fa riferimento a un visitatore che accede per la prima volta a un sito entro un periodo di tempo specificato. Ad esempio, l'unico visitatore può visitare un sito dieci volte in settimana, ma se il periodo di tempo è settimana, un singolo visitatore unico viene conteggiato solo una volta per quella settimana. Dopo che la settimana sarà terminata, quel visitatore unico potrà essere conteggiato di nuovo per un periodo di tempo diverso.
seo-description: Nella versione 14, un visitatore univoco fa riferimento a un visitatore che accede per la prima volta a un sito entro un periodo di tempo specificato. Ad esempio, l'unico visitatore può visitare un sito dieci volte in settimana, ma se il periodo di tempo è settimana, un singolo visitatore unico viene conteggiato solo una volta per quella settimana. Dopo che la settimana sarà terminata, quel visitatore unico potrà essere conteggiato di nuovo per un periodo di tempo diverso.
seo-title: Visitatori univoci
solution: Analytics
title: Visitatori univoci
topic: Metrics (Metriche)
uuid: ae 210698-99 f 9-485 e-a 640-c 7520807 adc 7
translation-type: tm+mt
source-git-commit: ecc762f73f9a303cebf48668b807fef9a2f055c5

---


# Visitatori univoci

Nella versione 14, un visitatore univoco fa riferimento a un visitatore che accede per la prima volta a un sito entro un periodo di tempo specificato. Ad esempio, l'unico visitatore può visitare un sito dieci volte in settimana, ma se il periodo di tempo è settimana, un singolo visitatore unico viene conteggiato solo una volta per quella settimana. Dopo che la settimana sarà terminata, quel visitatore unico potrà essere conteggiato di nuovo per un periodo di tempo diverso.

## Differenze tra le versioni 14 e 15

Version 14 does not remove duplicate [!UICONTROL Visits] and [!UICONTROL Unique Visitors] metrics from classifications-based reports. For example, if two video clips shared the same classification, a single visitor that viewed both clips generated two [!UICONTROL Visits] and [!UICONTROL Unique Visitors] in the classification-based report.

Version 15 removes duplicate [!UICONTROL Visits] and [!UICONTROL Unique Visitors] from the classification-based report. This is a more accurate measure of [!UICONTROL Visits] and [!UICONTROL Visitors], but typically results in a decrease in your [!UICONTROL Visits] and [!UICONTROL Unique Visitors] metrics for classification-based reports, when compared to data collected prior to upgrade.

| Usi | Descrizione |
|---|---|
| Traffic (Traffico) | Un visitatore è una persona che accede al tuo sito web. Non richiede un cookie persistente. |
| Conversione   | Un visitatore è una persona che accede al tuo sito web. Viene conteggiato quando si verifica un evento o un'azione correlata alla conversione. |
| Ad Hoc Analysis | Un visitatore è una persona che accede al tuo sito web. Non richiede un cookie persistente. |

See [Unique Visitors Report - Version 15 and Ad Hoc Analysis](../../../components/c-variables/dimensionslist/reports-unique-visitors-v15-dsc.md#concept_877141D6D1E743DA9FAB41C72A8121C7).

>[!MORE_ LIKE_ THIS]
>
>* [Visitatori giornalieri univoci](/help/components/c-variables/c-metrics/metrics-daily-unique-visitors.md)

