---
description: 'Puoi utilizzare le dimensioni AAM Audience in tutta Analytics. I segmenti integrati sono nuove dimensioni di Analytics denominate ID pubblico e Nome audience e possono essere utilizzati come qualsiasi altra dimensione raccolta da Analytics. In Feed dati, gli ID audience sono memorizzati nella colonna "mc_audiences". Queste dimensioni non sono attualmente disponibili in Workbench dati o Livestream. Alcuni esempi di come sfruttare le dimensioni Audiences includono '
seo-description: 'Puoi utilizzare le dimensioni AAM Audience in tutta Analytics. I segmenti integrati sono nuove dimensioni di Analytics denominate ID pubblico e Nome audience e possono essere utilizzati come qualsiasi altra dimensione raccolta da Analytics. In Feed dati, gli ID audience sono memorizzati nella colonna "mc_audiences". Queste dimensioni non sono attualmente disponibili in Workbench dati o Livestream. Alcuni esempi di come sfruttare le dimensioni Audiences includono '
seo-title: Uso dei dati di audience in Analytics
solution: Experience Cloud
title: Uso dei dati di audience in Analytics
uuid: 203925fb-f070-441c-813a-43099cb9b2b9
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Uso dei dati di audience in Analytics

Puoi utilizzare le dimensioni AAM Audience in tutta Analytics. I segmenti integrati sono nuove dimensioni di Analytics denominate ID pubblico e Nome audience e possono essere utilizzati come qualsiasi altra dimensione raccolta da Analytics. In Feed dati, gli ID audience sono memorizzati nella colonna "mc_audiences". Queste dimensioni non sono attualmente disponibili in Workbench dati o Livestream. Alcuni esempi di come sfruttare le dimensioni Audiences sono:

## Analysis Workspace {#section_C70837499BEA4DED885B3486C9E02C68}

In Analysis Workspace, i segmenti AAM sono visualizzati come due dimensioni.

1. Vai a **[!UICONTROL Workspace]**.
1. Dall’elenco di **[!UICONTROL Dimensions]**, selezionate le dimensioni **[!UICONTROL Audience ID]** o **[!UICONTROL Audience Name]**. Nome è una classificazione semplice dell’ID.

   ![](assets/aw-mcaudiences.png)

## Confronto segmenti {#section_E72B80B6470C42D4B9B19BE90E6070A2}

[Confronto](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/segment-comparison.html) segmenti rileva le differenze più importanti dal punto di vista statistico tra due segmenti. I dati sui tipi di pubblico possono essere utilizzati in Confronto segmenti in due modi: 1) come i 2 segmenti che vengono confrontati, e 2) come elementi nella tabella "Elementi dimensione principali".

1. Vai a **[!UICONTROL Workspace]** e seleziona il **[!UICONTROL Segment Comparison]** pannello dalla barra a sinistra.

1. Cercare [!UICONTROL Audiences Name] nel **[!UICONTROL Component]** menu.

1. Apri [!UICONTROL Audiences Name]in modo che vengano visualizzati gli elementi di dimensione correlati.
1. Trascina le audience da confrontare nel generatore di confronto segmenti.
1. (Facoltativo): Puoi anche inserire altri elementi o segmenti di dimensione, fino a 2.
1. Fai clic su **[!UICONTROL Build]**.

   Le dimensioni ID e Nome dell'audience verranno visualizzate automaticamente nella tabella "Elementi dimensione principali", in quanto si tratta di dati di profilo aggiuntivi per i due segmenti confrontati.

   ![](assets/aud-segcompare.png)

## Percorso del cliente (flusso) in Analysis Workspace {#section_FC30E5795C9D4539838E30FE11FAEA6E}

I dati del segmento AAM vengono passati ad Analytics in base all'hit e rappresentano l'appartenenza al pubblico di un visitatore in quel momento. Ciò significa che un visitatore potrebbe trovarsi in un segmento (ad es. "Consapevolezza"), quindi qualificarsi per un segmento più qualificato (ad esempio "Considerazione"). Puoi usare [Flusso](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html) in Analysis Workspace per visualizzare il percorso che un visitatore compie tra un pubblico e l’altro.

1. Vai a **[!UICONTROL Workspace]** e seleziona la **[!UICONTROL Flow]** visualizzazione dalla barra a sinistra.

1. Trascina la [!UICONTROL Audience Name] dimensione nel generatore di flussi.
1. Fai clic su **[!UICONTROL Build]**.
1. (Facoltativo): Trascina qualsiasi altra dimensione nella visualizzazione Flusso per creare un Flusso [](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/multi-dimensional-flow.html)interdimensionale.

![](assets/flow-aamaudiences.png)

Le audience possono essere utilizzate anche nelle visualizzazioni [Abbandono](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/fallout_flow.html).

## Visualizzazione Venn in Analysis Workspace {#section_E78AB764FB5047148B51DC1526B0DF89}

[Le visualizzazioni](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/venn.html) Venn mostrano la sovrapposizione tra un massimo di 3 segmenti.

1. Vai a **[!UICONTROL Workspace]** e seleziona la **[!UICONTROL Venn]** visualizzazione dalla barra a sinistra.

1. Cercare [!UICONTROL Audience Name] nel menu dei componenti.
1. Aprite [!UICONTROL Audience Name] in modo che vengano visualizzati gli elementi di dimensione correlati.
1. Trascinate le audience da confrontare nel generatore di Venn.
1. (Facoltativo): Puoi anche importare altri elementi o segmenti di dimensione; si possono confrontare fino a 3.
1. Fai clic su **[!UICONTROL Build]**.

![](assets/venn-viz.png)

## Generatore di segmenti {#section_2AA81852A1404AB894472CA8959461B6}

Puoi includere le dimensioni Audiences nel Generatore [](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html)segmenti di Analytics, insieme alle informazioni comportamentali raccolte da Analytics.

1. Vai a **[!UICONTROL Components]** &gt; **[!UICONTROL Segments]** .
1. Click **[!UICONTROL Add]** to create a new segment.
1. After naming the segment, drag the [!UICONTROL Audience Name] dimension into the Definitions panel.
1. (Facoltativo): Aggiungi altri criteri al segmento.
1. Salva il segmento.

   ![](assets/aud-segbuilder.png)

## Reporting e analisi e Generatore di report {#section_04E8FD30F73344D7937AD3C6CD19E34A}

1. Per visualizzare il rapporto di Analytics, andate a **[!UICONTROL Reports]** &gt; **[!UICONTROL Visitor Profile]** &gt; **[!UICONTROL Audience ID Reports]** .
1. Da questa cartella potete accedere sia alle dimensioni ID pubblico che Nome pubblico.

   ![](assets/mc-audiences.png)

