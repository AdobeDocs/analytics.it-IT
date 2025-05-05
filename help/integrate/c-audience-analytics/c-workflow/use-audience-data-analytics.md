---
description: Puoi utilizzare le dimensioni Pubblico di Adobe Audience Manager in tutte le aree di Analytics. I segmenti integrati sono nuove dimensioni di Analytics denominate ID pubblico e Nome pubblico e possono essere utilizzati come qualsiasi altra dimensione raccolta da Analytics. Nei feed di dati, gli ID del pubblico sono memorizzati nella colonna "mc_audiences". Queste dimensioni non sono attualmente disponibili in Data Workbench o Livestream. Alcuni esempi di come è possibile sfruttare le dimensioni di Audiences includono
solution: Experience Cloud
title: Uso dei dati del pubblico in Analytics
feature: Audience Analytics
exl-id: c1c0a9de-4051-4073-82c1-5615b0f01fa9
source-git-commit: c947de8eaa4e4dc3a0c10989ef6ae450cebc1f3e
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 5%

---

# Uso dei dati del pubblico in Analytics

Puoi utilizzare le dimensioni Pubblico di Adobe Audience Manager in tutte le aree di Analytics. I segmenti integrati sono nuove dimensioni di Analytics denominate ID pubblico e Nome pubblico e possono essere utilizzati come qualsiasi altra dimensione raccolta da Analytics. Nei feed di dati, gli ID del pubblico sono memorizzati nella colonna &quot;mc_audiences&quot;. Queste dimensioni non sono attualmente disponibili in Data Workbench o Livestream. Alcuni esempi di come è possibile sfruttare le dimensioni di Audiences includono:

## Analysis Workspace {#workspace}

In Analysis Workspace, i segmenti di Adobe Audience Manager vengono visualizzati come due dimensioni.

1. Vai a **[!UICONTROL Workspace]**.
1. Dall&#39;elenco di **[!UICONTROL Dimensions]**, selezionare le dimensioni **[!UICONTROL Audience ID]** o **[!UICONTROL Audience Name]**. Il nome è una classificazione dell’ID intuitiva.

   ![](assets/aw-mcaudiences.png)

## Confronto fra segmenti {#compare}

[Segment Comparison](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html?lang=it) rileva le differenze più importanti dal punto di vista statistico tra due segmenti. I dati sui tipi di pubblico possono essere utilizzati in Segment Comparison (Confronto fra segmenti) in due modi: 1) come i 2 segmenti che vengono confrontati e 2) come elementi nella tabella &quot;Elementi principali del Dimension&quot;.

1. Vai a **[!UICONTROL Workspace]** e seleziona il pannello **[!UICONTROL Segment Comparison]** dalla barra a sinistra.

1. Cerca [!UICONTROL Audiences Name] nel menu **[!UICONTROL Component]**.

1. Apri [!UICONTROL Audiences Name] in modo che vengano visualizzati gli elementi dimensionali correlati.
1. Trascina i tipi di pubblico da confrontare nel Generatore di confronto segmenti.
1. (Facoltativo): puoi inserire anche altri elementi o segmenti di dimensione; è possibile confrontare fino a 2 elementi.
1. Fai clic su **[!UICONTROL Build]**.

   Le dimensioni ID pubblico e Nome verranno visualizzate automaticamente nella tabella &quot;Elementi principali del Dimension&quot;, in quanto si tratta di dati di profilo aggiuntivi per i due segmenti confrontati.

   ![](assets/aud-segcompare.png)

## Percorso di clienti (Flusso) in Analysis Workspace {#flow}

I dati dei segmenti di Adobe Audience Manager vengono trasmessi in Analytics hit per hit e rappresentano l’iscrizione del pubblico di un visitatore in quel momento. Ciò significa che un visitatore potrebbe rientrare in un segmento (ad esempio, &quot;Consapevolezza&quot;) e qualificarsi successivamente per un segmento più qualificato (ad esempio, &quot;Considerazione&quot;). Puoi utilizzare [Flusso](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=it) in Analysis Workspace per visualizzare il percorso che un visitatore assume tra i tipi di pubblico.

1. Vai a **[!UICONTROL Workspace]** e seleziona la visualizzazione **[!UICONTROL Flow]** dalla barra a sinistra.

1. Trascina la dimensione [!UICONTROL Audience Name] nel Generatore di flussi.
1. Fai clic su **[!UICONTROL Build]**.
1. (Facoltativo): trascina un&#39;altra dimensione nella visualizzazione Flusso per creare un [flusso interdimensionale](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/multi-dimensional-flow.html?lang=it).

![](assets/flow-aamaudiences.png)

I tipi di pubblico possono essere utilizzati anche in [Visualizzazioni di fallout](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=it).

## Visualizzazione Venn in Analysis Workspace {#venn}

[Le visualizzazioni di Venn](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/venn.html?lang=it) mostrano la sovrapposizione tra un massimo di 3 segmenti.

1. Vai a **[!UICONTROL Workspace]** e seleziona la visualizzazione **[!UICONTROL Venn]** dalla barra a sinistra.

1. Cerca [!UICONTROL Audience Name] nel menu del componente.
1. Aprire [!UICONTROL Audience Name] in modo che vengano visualizzati gli elementi dimensionali correlati.
1. Trascina i tipi di pubblico da confrontare nel Generatore di Venn.
1. (Facoltativo): puoi inserire anche altri elementi o segmenti di dimensione; è possibile confrontare fino a 3.
1. Fai clic su **[!UICONTROL Build]**.

![](assets/venn-viz.png)

## Generatore di segmenti {#builder}

Puoi incorporare le dimensioni Audiences nel [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md) di Analytics, insieme alle informazioni comportamentali raccolte da Analytics.

1. Vai a **[!UICONTROL Components]** > **[!UICONTROL Segments]** .
1. Fare clic su **[!UICONTROL Add]** per creare un nuovo segmento.
1. Dopo aver denominato il segmento, trascina la dimensione [!UICONTROL Audience Name] nel pannello Definizioni.
1. (Facoltativo): aggiungi altri criteri al segmento.
1. Salva il segmento.

   ![](assets/aud-segbuilder.png)

