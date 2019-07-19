---
description: nulle
seo-description: nulle
seo-title: Eseguire l’analisi dei contributi
title: Eseguire l’analisi dei contributi
uuid: 5282 a 5 f 9-0771-4974-93 cb -335204 bde 114
translation-type: tm+mt
source-git-commit: 8b2feced9fd503395d06dc12c8e5d7985ca89161

---


# Eseguire l’analisi dei contributi

L’analisi dei contributi è un potente processo di machine learning progettato per individuare i fattori che contribuiscono a un’anomalia osservata in Adobe Analytics. Questa funzione è utile per individuare aree di interesse o opportunità per ulteriore analisi, in modo molto più rapido di quanto sarebbe altrimenti possibile.

## Eseguire l’analisi dei contributi {#section_7D2C5E48A5664727941DF4C90976D9DC}

In un progetto, è possibile invocare l’analisi dei contributi in due modi:

* In a freeform table with daily granularity, right-click any row and select **[!UICONTROL Run Contribution Analysis]**. L’analisi può essere eseguita anche sulle righe in cui non sono visualizzate anomalie.

   >[!NOTE]
   >
   >Al momento l'analisi dei contributi è supportata solo con granularità giornaliera.

   ![](assets/run_ca.png)

* In un grafico a linee, fai clic con il pulsante destro del mouse su un punto dati anomalo. Click the **[!UICONTROL Analyze]** link that appears.

   ![](assets/contribution-analysis.png)

1. (Facoltativo) Dopo aver fatto clic su **[!UICONTROL Run Contribution Analysis]** (Esegui analisi contributi) nel grafico a linee o in una tabella, puoi restringere l’ambito dell’analisi (e quindi velocizzarla) [escludendo alcune dimensioni](../../../../analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC).

1. Attendi che venga caricata l’analisi dei contributi. Il tempo richiesto dipende dalla dimensione della suite per rapporti e dal numero di dimensioni, e potrebbe essere piuttosto lungo. L’analisi dei contributi viene eseguita su 50.000 elementi per dimensione.
1. Analysis Workspace carica quindi un nuovo pannello Analisi contributi direttamente nel progetto. Se hai già avuto modo di usare la funzione di analisi contributi di Reports &amp; Analytics, i pannelli ti saranno familiari:

   * Visualizzazione del numero di **Visite** in un dato giorno.
   * **Linea delle tendenze di visita** mensile per contesto.
   * **Elementi principali** che hanno contribuito a questa anomalia, ordinati per [punteggio contributo](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_contribution_score.html), e la metrica in questione, più una metrica di visitatori univoci per contestualizzarla dal punto di vista delle dimensioni.

   * La tabella dei [segmenti principali](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_workflow_premium.html) (cluster di elementi principali) identifica le associazioni di elementi principali in base al punteggio contributo, alle occorrenze di anomalie e alla percentuale complessiva che ha contribuito alla metrica anomala. Questo viene quindi acquisito come segmento di pubblico (segmento contributo 1, segmento contributo 2, ecc...). Fai clic sul pulsante “i” (Info) per visualizzare la definizione di ciascun segmento automatico e dei principali elementi che lo compongono:

      ![](assets/auto_segment.png)

1. Poiché l’analisi dei contributi è ora integrata in Analysis Workspace, puoi accedere a numerose funzioni direttamente con un clic del pulsante destro del mouse su una tabella, per un’analisi ancora più significativa, ad esempio:

   * [Scomposizione di ogni elemento di dimensione per un’altra dimensione](../../../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md#task_B594DA2476E84DFDA8279E831F0BD9C4)
   * [Tendenza di una o più righe](../../../../analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Aggiunta di nuove visualizzazioni](../../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276)
   * [Creazione di avvisi.](/help/components/c-alerts/intellligent-alerts.md)
   * [Creazione o confronto di segmenti.](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md#concept_74FAC1C6D0204F9190A110B0D9005793)

>[!NOTE]
>
>L'anomalia viene analizzata con un punto blu nell'analisi dei contributi e nei relativi progetti di avvisi intelligenti. Questo offre un’indicazione più chiara dell’anomalia analizzata.

## Exclude dimensions from Contribution Analysis {#section_F6932F4BF74544B5872164E7B1E0C6FC}

In alcune situazioni può essere utile escludere delle dimensioni dall’analisi dei contributi. Ad esempio, se non ti interessano le dimensioni relative a browser o hardware, puoi escluderle per velocizzare l’analisi.

1. After you have clicked **[!UICONTROL Run Contribution Analysis]** (or **[!UICONTROL Analyze]** in a line chart), the **[!UICONTROL Excluded Dimensions]** panel displays.

1. Just drag any unwanted dimensions into the **[!UICONTROL Excluded Dimensions]** panel, then save the list by clicking **[!UICONTROL Set as Default]**. Oppure fai clic su **[!UICONTROL Clear All](Cancella tutto) per iniziare di nuovo selezionando le dimensioni da escludere.**

   ![](assets/exclude_dimensions.png)

1. Dopo aver aggiunto le dimensioni da escludere (o scelto di non escluderne) fai di nuovo clic su **[!UICONTROL Run Contribution Analysis](Esegui analisi contributi).**
1. Per modificare l’elenco delle dimensioni escluse, fai doppio clic su Dimensions (Dimensioni) per visualizzare l’elenco delle dimensioni escluse:

   ![](assets/excluded-dimensions.png)

1. Just delete any unwanted dimensions by clicking the x next to them, then save the list by clicking **[!UICONTROL Set as Default]**.

