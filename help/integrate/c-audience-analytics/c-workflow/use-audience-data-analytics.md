---
description: Puoi utilizzare le dimensioni Pubblico di Adobe Audience Manager in tutte le aree di Analytics. I segmenti integrati sono nuove dimensioni di Analytics denominate ID pubblico e Nome pubblico e possono essere utilizzati come qualsiasi altra dimensione raccolta da Analytics. Nei feed di dati, gli ID del pubblico sono memorizzati nella colonna "mc_audiences". Queste dimensioni non sono attualmente disponibili in Data Workbench o Livestream. Alcuni esempi di come è possibile sfruttare le dimensioni di Audiences includono
solution: Experience Cloud
title: Utilizzare i dati sul pubblico in Analytics
feature: Audience Analytics
exl-id: c1c0a9de-4051-4073-82c1-5615b0f01fa9
source-git-commit: c947de8eaa4e4dc3a0c10989ef6ae450cebc1f3e
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---

# Utilizzare i dati sul pubblico in Analytics

Puoi utilizzare le dimensioni Pubblico di Adobe Audience Manager in tutte le aree di Analytics. I segmenti integrati sono nuove dimensioni di Analytics denominate ID pubblico e Nome pubblico e possono essere utilizzati come qualsiasi altra dimensione raccolta da Analytics. Nei feed di dati, gli ID del pubblico sono memorizzati nella colonna &quot;mc_audiences&quot;. Queste dimensioni non sono attualmente disponibili in Data Workbench o Livestream. Alcuni esempi di come è possibile sfruttare le dimensioni di Audiences includono:

## Analysis Workspace {#workspace}

In Analysis Workspace, i segmenti di Adobe Audience Manager vengono visualizzati come due dimensioni.

1. Vai a **[!UICONTROL Workspace]**.
1. Dall’elenco di **[!UICONTROL Dimensions]**, seleziona le dimensioni **[!UICONTROL Audience ID]** o **[!UICONTROL Audience Name]**. Il nome è una classificazione dell’ID intuitiva.

   ![](assets/aw-mcaudiences.png)

## Confronto fra segmenti {#compare}

[Confronto segmenti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) rileva le differenze più importanti dal punto di vista statistico tra due segmenti. I dati sui tipi di pubblico possono essere utilizzati in Segment Comparison (Confronto fra segmenti) in due modi: 1) come i 2 segmenti che vengono confrontati e 2) come elementi nella tabella &quot;Elementi principali del Dimension&quot;.

1. Vai a **[!UICONTROL Workspace]** e seleziona la **[!UICONTROL Segment Comparison]** dalla barra a sinistra.

1. Cerca [!UICONTROL Audiences Name] nel **[!UICONTROL Component]** menu.

1. Apri [!UICONTROL Audiences Name]in modo che vengano visualizzati gli elementi dimensionali correlati.
1. Trascina i tipi di pubblico da confrontare nel Generatore di confronto segmenti.
1. (Facoltativo): puoi inserire anche altri elementi o segmenti di dimensione; è possibile confrontare fino a 2 elementi.
1. Fai clic su **[!UICONTROL Build]** (Usa modello di attribuzione non predefinito).

   Le dimensioni ID pubblico e Nome verranno visualizzate automaticamente nella tabella &quot;Elementi principali del Dimension&quot;, in quanto si tratta di dati di profilo aggiuntivi per i due segmenti confrontati.

   ![](assets/aud-segcompare.png)

## Percorso di clienti (Flusso) in Analysis Workspace {#flow}

I dati dei segmenti di Adobe Audience Manager vengono trasmessi in Analytics hit per hit e rappresentano l’iscrizione del pubblico di un visitatore in quel momento. Ciò significa che un visitatore potrebbe rientrare in un segmento (ad esempio, &quot;Consapevolezza&quot;) e qualificarsi successivamente per un segmento più qualificato (ad esempio, &quot;Considerazione&quot;). È possibile utilizzare [Flusso](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=it) in Analysis Workspace per visualizzare il percorso che un visitatore segue tra i diversi tipi di pubblico.

1. Vai a **[!UICONTROL Workspace]** e seleziona la **[!UICONTROL Flow]** dalla barra a sinistra.

1. Trascina [!UICONTROL Audience Name] nel Generatore di flussi.
1. Fai clic su **[!UICONTROL Build]** (Usa modello di attribuzione non predefinito).
1. (Facoltativo): trascina un’altra dimensione nella visualizzazione Flusso per creare un [Flusso interdimensionale](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/multi-dimensional-flow.html).

![](assets/flow-aamaudiences.png)

Il pubblico può essere utilizzato anche in [Visualizzazioni di abbandono](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=it).

## Visualizzazione Venn in Analysis Workspace {#venn}

[Visualizzazioni di Venn](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/venn.html?lang=it) mostra la sovrapposizione tra un massimo di 3 segmenti.

1. Vai a **[!UICONTROL Workspace]** e seleziona la **[!UICONTROL Venn]** dalla barra a sinistra.

1. Cerca [!UICONTROL Audience Name] nel menu del componente.
1. Apri [!UICONTROL Audience Name] in modo che vengano visualizzati gli elementi dimensionali correlati.
1. Trascina i tipi di pubblico da confrontare nel Generatore di Venn.
1. (Facoltativo): puoi inserire anche altri elementi o segmenti di dimensione; è possibile confrontare fino a 3.
1. Fai clic su **[!UICONTROL Build]** (Usa modello di attribuzione non predefinito).

![](assets/venn-viz.png)

## Generatore di segmenti {#builder}

Puoi incorporare le dimensioni Audiences in Analytics. [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md), insieme alle informazioni comportamentali raccolte da Analytics.

1. Vai a  **[!UICONTROL Components]** > **[!UICONTROL Segments]** .
1. Clic **[!UICONTROL Add]** per creare un nuovo segmento.
1. Dopo aver denominato il segmento, trascina [!UICONTROL Audience Name] nel pannello Definizioni.
1. (Facoltativo): aggiungi altri criteri al segmento.
1. Salva il segmento.

   ![](assets/aud-segbuilder.png)

