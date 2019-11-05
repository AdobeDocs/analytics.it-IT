---
description: È possibile visualizzare le anomalie sotto forma di tabella o grafico a linee.
seo-description: È possibile visualizzare le anomalie sotto forma di tabella o grafico a linee.
seo-title: Visualizzare le anomalie in Analysis Workspace
title: Visualizzare le anomalie in Analysis Workspace
uuid: 270a7ea9-6485-4c83-8220-5a2200bd7200
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Visualizzare le anomalie in Analysis Workspace

È possibile visualizzare le anomalie sotto forma di tabella o grafico a linee.

## View anomalies in a table {#section_869A87B92B574A38B017A980ED8A29C5}

In una tabella a forma libera su serie temporale, ogni riga viene ora segnalata con un punto esclamativo grigio scuro se viene rilevata un’anomalia nei dati.

![](assets/anomaly_detected.png)

La linea grigia verticale in ogni riga indica il valore previsto. Quando si passa il cursore sul punto esclamativo, viene indicato di quanto l’anomalia si scosta dal valore previsto (sotto forma di +/- %).

## View anomalies in a line chart {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

Il grafico a linee mostra la banda di valori affidabili in verde chiaro e i valori anomali come punti bianchi. 

Se fai clic su un punto bianco, questo diventerà verde e mostrerà:

* la data in cui si è verificata l'anomalia
* il valore non elaborato dell'anomalia
* La percentuale superiore o inferiore al valore previsto rappresentata dalla linea verde continua.
* Collegamento Analizza per iniziare un’[Analisi contributi](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md).

![](assets/anomaly_linechart.png)

Nei grafici a linee per più metriche, sono rappresentate solo le anomalie; quando si passa il mouse su un valore anomalo viene visualizzata la relativa banda di valori affidabili.

L’intervallo di attendibilità per il rilevamento delle anomalie non ridimensiona automaticamente l’asse Y di una visualizzazione per rendere potenzialmente più leggibile il grafico.

Un’opzione consente all’intervallo di attendibilità di ridimensionare il grafico. Fai clic sull'icona Impostazioni (ingranaggio) e seleziona **[!UICONTROL Allow Anomaly Detection to Scale Y Axis]**.

![](assets/scale-y-axis.png)

