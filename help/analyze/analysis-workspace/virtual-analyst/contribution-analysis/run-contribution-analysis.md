---
description: 'null'
title: Eseguire l’analisi dei contributi
uuid: 5282a5f9-0771-4974-93cb-335204bde114
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Eseguire l’analisi dei contributi

Contribution Analysis è un intenso processo di machine learning progettato per individuare i fattori che contribuiscono a un’anomalia osservata in Adobe Analytics. L&#39;obiettivo è quello di aiutare l&#39;utente a trovare aree di interesse o opportunità per ulteriori analisi molto più rapidamente di quanto sarebbe altrimenti possibile.

## Eseguire l’analisi dei contributi {#section_7D2C5E48A5664727941DF4C90976D9DC}

In un progetto, è possibile invocare l’analisi dei contributi in due modi:

* In una tabella a forma libera con granularità giornaliera, fai clic con il pulsante destro del mouse su una riga e seleziona **[!UICONTROL Run Contribution Analysis]** (Esegui analisi contributi). L’analisi può essere eseguita anche sulle righe in cui non sono visualizzate anomalie.

   >[!NOTE]
   >
   >Al momento l’analisi dei contributi è supportata solo per la granularità giornaliera.

   ![](assets/run_ca.png)

* In un grafico a linee, fai clic con il pulsante destro del mouse su un punto dati anomalo. Fai clic sul link **[!UICONTROL Analyze]** (Analizza) visualizzato.

   ![](assets/contribution-analysis.png)

1. (Facoltativo) Dopo aver fatto clic su **[!UICONTROL Run Contribution Analysis]** (Esegui analisi contributi) nel grafico a linee o in una tabella, puoi restringere l’ambito dell’analisi (e quindi velocizzarla) [escludendo alcune dimensioni](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC).

1. Attendi che venga caricata l’analisi dei contributi. L&#39;operazione potrebbe richiedere molto tempo, a seconda delle dimensioni della suite di rapporti e del numero di dimensioni. L’analisi dei contributi esegue l’analisi sui primi 50.000 elementi per dimensione.
1. Analysis Workspace carica quindi un nuovo pannello Analisi contributi direttamente nel progetto. Se hai già utilizzato Contribution Analysis in Reporting e analisi, i pannelli ti saranno familiari:

   * Visualizzazione che mostra il numero di **visite** in quel giorno.
   * Linea **di tendenza delle** visite mensili per il contesto.
   * **Elementi** principali che hanno contribuito a questa anomalia, ordinati per punteggio [di](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_contribution_score.html)contributo, più la metrica in questione, e una metrica Visitatori univoci per contestualizzare la metrica da una prospettiva di ridimensionamento.

   * La tabella dei [segmenti principali](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_workflow_premium.html) (cluster di elementi principali) identifica le associazioni di elementi principali in base al punteggio contributo, alle occorrenze di anomalie e alla percentuale complessiva che ha contribuito alla metrica anomala. Questo viene quindi acquisito come segmento di pubblico (segmento contributo 1, segmento contributo 2, ecc.). Facendo clic sul pulsante &quot;i&quot; (info), potrai vedere la definizione di ciascun segmento automatico, compresi gli elementi principali di cui è composto:

      ![](assets/auto_segment.png)

1. Poiché l’analisi dei contributi è ora integrata in Analysis Workspace, puoi accedere a numerose funzioni direttamente dal menu di scelta rapida di una tabella per rendere l’analisi ancora più significativa, ad esempio:

   * [Scomposizione di ogni elemento di dimensione per un’altra dimensione](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [Tendenza di una o più righe](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Aggiunta di nuove visualizzazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [Creazione di avvisi.](/help/components/c-alerts/intellligent-alerts.md)
   * [Creazione o confronto di segmenti.](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE] Un punto blu evidenzia l’anomalia nell’analisi dei contributi e nei relativi progetti di avvisi intelligenti. Questo offre un’indicazione più chiara dell’anomalia analizzata.

## Escludere alcune dimensioni dall’analisi dei contributi {#section_F6932F4BF74544B5872164E7B1E0C6FC}

In alcuni casi può essere utile escludere alcune dimensioni dall’analisi dei contributi. Ad esempio, potrebbe non interessarti delle dimensioni relative a browser o hardware e vuoi velocizzare l&#39;analisi rimuovendole.

1. Fai clic su **[!UICONTROL Run Contribution Analysis]** (Esegui analisi contributi) o su **[!UICONTROL Analyze]** (Analizza) in un grafico a linee per visualizzare il pannello **[!UICONTROL Excluded Dimensions]** (Dimensioni escluse).

1. Trascina le dimensioni da escludere nel pannello **[!UICONTROL Excluded Dimensions]** (Dimensioni escluse), quindi salva l’elenco facendo clic su **[!UICONTROL Set as Default]** (Imposta come predefinito). Oppure fai clic su **[!UICONTROL Clear All]** (Cancella tutto) per iniziare di nuovo selezionando le dimensioni da escludere.

   ![](assets/exclude_dimensions.png)

1. Dopo aver aggiunto le dimensioni da escludere (o scelto di non escluderne) fai di nuovo clic su **[!UICONTROL Run Contribution Analysis]** (Esegui analisi contributi).
1. Per modificare l’elenco delle dimensioni escluse, fai doppio clic su Dimensions (Dimensioni) per visualizzare l’elenco delle dimensioni escluse:

   ![](assets/excluded-dimensions.png)

1. Fai clic sulla x accanto alle dimensioni da eliminare, quindi salva il nuovo elenco facendo clic su **[!UICONTROL Set as Default]** (Imposta come predefinito).

