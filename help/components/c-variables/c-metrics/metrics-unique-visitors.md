---
description: Nella versione 14, un visitatore univoco si riferisce a un visitatore che visita un sito per la prima volta entro un periodo di tempo specificato. Ad esempio, il visitatore univoco può visitare un sito dieci volte alla settimana, ma se il periodo di tempo è settimana, un singolo visitatore unico viene conteggiato una sola volta per quella settimana. Dopo la fine della settimana, quel visitatore unico può essere conteggiato di nuovo per un periodo di tempo diverso.
solution: Analytics
title: Visitatori unici
topic: Metrics
uuid: ae210698-99f9-485e-a640-c7520807adc7
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visitatori unici

Nella versione 14, un visitatore univoco si riferisce a un visitatore che visita un sito per la prima volta entro un periodo di tempo specificato. Ad esempio, il visitatore univoco può visitare un sito dieci volte alla settimana, ma se il periodo di tempo è settimana, un singolo visitatore unico viene conteggiato una sola volta per quella settimana. Dopo la fine della settimana, quel visitatore unico può essere conteggiato di nuovo per un periodo di tempo diverso.

## Differenze tra le versioni 14 e 15

La versione 14 non rimuove duplicati [!UICONTROL Visits] e [!UICONTROL Unique Visitors] metriche dai report basati sulle classificazioni. Ad esempio, se due clip video condividevano la stessa classificazione, un singolo visitatore che visualizzava entrambe le clip ne generava due [!UICONTROL Visits] e [!UICONTROL Unique Visitors] nel rapporto basato sulla classificazione.

La versione 15 rimuove i duplicati [!UICONTROL Visits] e [!UICONTROL Unique Visitors] dal report basato sulla classificazione. Si tratta di una misura più accurata di [!UICONTROL Visits] e [!UICONTROL Visitors], ma in genere si traduce in una diminuzione delle [!UICONTROL Visits] metriche e delle [!UICONTROL Unique Visitors] metriche per i report basati sulla classificazione, se confrontati con i dati raccolti prima dell'aggiornamento.

| Usi | Descrizione |
|---|---|
| Traffico | Un visitatore è una persona che accede al sito Web. Non richiede un cookie persistente. |
| Conversione | Un visitatore è una persona che accede al sito Web. Viene conteggiato quando si verifica un evento o un’azione correlati alla conversione. |
| Ad Hoc Analysis | Un visitatore è una persona che accede al sito Web. Non richiede un cookie persistente. |

Consulta Rapporto [Visitatori unici - Versione 15 e Analisi](/help/components/c-variables/dimensionslist/reports-unique-visitors-v15-dsc.md)ad hoc.

>[!MORELIKETHIS]
>
>* [Visitatori giornalieri unici](/help/components/c-variables/c-metrics/metrics-daily-unique-visitors.md)

