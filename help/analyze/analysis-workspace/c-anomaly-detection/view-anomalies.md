---
description: È possibile visualizzare le anomalie sotto forma di tabella o grafico a linee.
title: Visualizzare le anomalie in Analysis Workspace
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
source-git-commit: d37fa0aff0b1bbe196b943bc26e86b1e79936184
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 53%

---

# Visualizzare le anomalie

In Analysis Workspace puoi visualizzare le anomalie in una tabella o in un grafico a linee.

## Visualizzazione delle anomalie in una tabella {#section_869A87B92B574A38B017A980ED8A29C5}

È possibile visualizzare le anomalie in una tabella a forma libera della serie temporale.

1. Seleziona ![Impostazione](/help/assets/icons/Setting.svg)nell&#39;intestazione della colonna, quindi accertati che l&#39;opzione **[!UICONTROL Anomalies]** sia selezionata nell&#39;elenco delle opzioni. Per ulteriori informazioni, consulta la sezione [Impostazioni delle colonne](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Le anomalie sono mostrate nella tabella come segue:

   ![Anomalie rilevate](assets/anomaly-detected.png)

   ◥ viene visualizzato nell&#39;angolo superiore destro di ogni riga in cui viene rilevata un&#39;anomalia di dati.

   La **linea verticale colorata** in ogni riga ➋ indica il valore previsto. L&#39;**area ombreggiata colorata** in ogni riga ➊ indica il valore effettivo. Il modo in cui la linea (valore previsto) viene confrontata con l’area ombreggiata (valore effettivo) determina se vi è un’anomalia. Un&#39;osservazione è considerata anomala in base alle tecniche statistiche avanzate descritte in [Tecniche statistiche utilizzate nel rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

1. Selezionare ◥ nell&#39;angolo superiore destro di una riga per visualizzare i dettagli sull&#39;anomalia. Mostra la misura (in percentuale) in cui il valore effettivo si discosta al di sopra o al di sotto del valore previsto.
1. Seleziona [Apri analisi contributi](run-contribution-analysis.md) per avviare l&#39;analisi dei contributi.

## Visualizzare le anomalie in un grafico a linee

I grafici a linee sono l’unica visualizzazione che consente di visualizzare le anomalie.

Per visualizzare le anomalie in un grafico a linee:

1. Seleziona ![Impostazione](/help/assets/icons/Setting.svg) nell&#39;intestazione della visualizzazione, quindi accertati che l&#39;opzione [!UICONTROL **Mostra anomalie**] sia selezionata nell&#39;elenco delle opzioni. Per ulteriori informazioni, consulta la sezione [Linea](/help/analyze/analysis-workspace/visualizations/line.md).

1. (Facoltativo) Per consentire all&#39;intervallo di attendibilità di ridimensionare il grafico, seleziona ![Impostazione](/help/assets/icons/Setting.svg) nell&#39;intestazione della visualizzazione, quindi seleziona l&#39;opzione, **[!UICONTROL Allow anomalies to Scale Y-axis]**.

   Questa opzione non è selezionata per impostazione predefinita perché a volte può rendere il grafico meno leggibile.

   Le anomalie vengono mostrate nel grafico a linee come segue:

   ![Visualizzazione riga rilevata anomalia](assets/anomaly-detected-line.gif)

   Sulla riga compare un **punto bianco** ogni volta che viene rilevata un’anomalia nei dati. Un&#39;osservazione è considerata anomala in base alle tecniche statistiche avanzate descritte in [Tecniche statistiche utilizzate nel rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

   L’**area ombreggiata chiara** è la banda di confidenza, o l’intervallo previsto, in cui devono trovarsi i valori. Qualsiasi valore che non rientra nell’intervallo previsto è un’anomalia.

   Nei grafici a linee per più metriche, sono mostrate solo le anomalie; quando si passa il puntatore su un valore anomalo viene visualizzata la relativa banda di valori affidabili.

   La **linea tratteggiata** è il valore previsto esatto.

1. Seleziona un’anomalia (punto bianco) per visualizzare le seguenti informazioni:

   * La data in cui si è verificata l’anomalia.

   * Il valore non elaborato dell’anomalia.

   * la percentuale superiore o inferiore al valore previsto rappresentata dalla linea verde continua.

   * Il collegamento **[!UICONTROL Analyze]** per avviare Analisi contributi






