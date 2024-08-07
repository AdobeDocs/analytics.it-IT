---
description: Esegui un rapporto di analisi dei contributi in un progetto Workspace.
title: Eseguire l’analisi dei contributi
role: User, Admin
exl-id: 20d1ba8d-3e4e-4702-ae28-5eb6bf00847b
feature: Anomaly Detection
source-git-commit: ee4772913c8b702658646755a2a11598c8530236
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 100%

---

# Eseguire l’analisi dei contributi

L’[analisi dei contributi](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) è un potente processo di machine learning progettato per individuare i fattori che contribuiscono a un’anomalia osservata in Adobe Analytics. Questa funzione è utile per individuare aree di interesse o opportunità per ulteriore analisi, in modo molto più rapido di quanto sarebbe altrimenti possibile.

## Eseguire l’analisi dei contributi {#run}

In un progetto, è possibile invocare l’analisi dei contributi in due modi:

* In una tabella a forma libera con granularità giornaliera, fai clic con il pulsante destro del mouse su una riga e seleziona **[!UICONTROL Run Contribution Analysis]**. L’analisi può essere eseguita anche sulle righe in cui non sono visualizzate anomalie.

  >[!NOTE]
  >
  >Al momento l’analisi dei contributi è supportata solo per la granularità giornaliera.

  ![](assets/run_ca.png)

* In un grafico a linee, fai clic con il pulsante destro del mouse su un punto dati anomalo. Fai clic sul link **[!UICONTROL Analyze]** visualizzato.

  ![](assets/contribution-analysis.png)

1. (Facoltativo) Dopo aver fatto clic su **[!UICONTROL Run Contribution Analysis]** nel grafico a linee o in una tabella, puoi restringere l’ambito dell’analisi (e quindi velocizzarla) [escludendo alcune dimensioni](#exclude).

1. Attendi che venga caricata l’analisi dei contributi. Il tempo richiesto dipende dalla dimensione della suite per rapporti e dal numero di dimensioni, e potrebbe essere piuttosto lungo. L’analisi dei contributi viene eseguita su 50.000 elementi per dimensione.
1. Analysis Workspace carica quindi un nuovo pannello Analisi contributi direttamente nel progetto.

   * Visualizzazione del numero di **Visite** in un dato giorno.
   * **Linea delle tendenze di visita** mensile per contesto.
   * **Elementi principali** che hanno contribuito a questa anomalia, ordinati per [punteggio contributo](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis), e la metrica in questione, più una metrica di visitatori univoci per contestualizzarla dal punto di vista delle dimensioni.

   * La tabella dei [segmenti principali](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=it) (cluster di elementi principali) identifica le associazioni di elementi principali in base al punteggio contributo, alle occorrenze di anomalie e alla percentuale complessiva che ha contribuito alla metrica anomala. Questo viene quindi acquisito come segmento di pubblico (segmento contributo 1, segmento contributo 2, ecc...). Fai clic sul pulsante “i” (Info) per visualizzare la definizione di ciascun segmento automatico e dei principali elementi che lo compongono:

     ![](assets/auto_segment.png)

1. Poiché l’analisi dei contributi è ora integrata in Analysis Workspace, puoi accedere a numerose funzioni direttamente con un clic del pulsante destro del mouse su una tabella, per un’analisi ancora più significativa, ad esempio:

   * [Scomposizione di ogni elemento di dimensione per un’altra dimensione](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [Tendenza di una o più righe](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Aggiunta di nuove visualizzazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [Creazione di avvisi.](/help/components/c-alerts/intellligent-alerts.md)
   * [Creazione o confronto di segmenti.](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]
>
>Un punto blu evidenzia l’anomalia nell’analisi dei contributi e nei relativi progetti di avvisi intelligenti. Questo offre un’indicazione più chiara dell’anomalia analizzata.

## Escludere alcune dimensioni dall’analisi dei contributi {#exclude}

In alcune situazioni può essere utile escludere delle dimensioni dall’analisi dei contributi. Ad esempio, se non ti interessano le dimensioni relative a browser o hardware, puoi escluderle per velocizzare l’analisi.

1. Fai clic su **[!UICONTROL Run Contribution Analysis]** o su **[!UICONTROL Analyze]** in un grafico a linee per visualizzare il pannello **[!UICONTROL Excluded Dimensions]**.

1. Trascina le dimensioni da escludere nel pannello **[!UICONTROL Excluded Dimensions]**, quindi salva l’elenco facendo clic su **[!UICONTROL Set as Default]**. Oppure fai clic su **[!UICONTROL Clear All]** per iniziare di nuovo selezionando le dimensioni da escludere.

   ![](assets/exclude_dimensions.png)

1. Dopo aver aggiunto le dimensioni da escludere (o scelto di non escluderne) fai di nuovo clic su **[!UICONTROL Run Contribution Analysis]**.
1. Per modificare l’elenco delle dimensioni escluse, fai doppio clic su Dimensions (Dimensioni) per visualizzare l’elenco delle dimensioni escluse:

   ![](assets/excluded-dimensions.png)

1. Fai clic sulla x accanto alle dimensioni da eliminare, quindi salva il nuovo elenco facendo clic su **[!UICONTROL Set as Default]**.
