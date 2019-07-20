---
description: 'Puoi utilizzare le dimensioni di AAM Audience in Analytics. I segmenti integrati sono nuove dimensioni di Analytics denominate ID audience e Nome pubblico e possono essere utilizzati come qualsiasi altra dimensione raccolta da Analytics. Nei feed di dati, gli ID audience sono memorizzati nella colonna «mc_ audiences». Queste dimensioni non sono attualmente disponibili in Workbench dati o Livestream. Alcuni esempi di come possono essere sfruttate le dimensioni Audiences '
seo-description: 'Puoi utilizzare le dimensioni di AAM Audience in Analytics. I segmenti integrati sono nuove dimensioni di Analytics denominate ID audience e Nome pubblico e possono essere utilizzati come qualsiasi altra dimensione raccolta da Analytics. Nei feed di dati, gli ID audience sono memorizzati nella colonna «mc_ audiences». Queste dimensioni non sono attualmente disponibili in Workbench dati o Livestream. Alcuni esempi di come possono essere sfruttate le dimensioni Audiences '
seo-title: Utilizzo dei dati del pubblico in Analytics
solution: Marketing Cloud
title: Utilizzo dei dati del pubblico in Analytics
uuid: 203925 fb-f 070-441 c -813 a -43099 cb 9 b 2 b 9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Utilizzo dei dati del pubblico in Analytics

Puoi utilizzare le dimensioni di AAM Audience in Analytics. I segmenti integrati sono nuove dimensioni di Analytics denominate ID audience e Nome pubblico e possono essere utilizzati come qualsiasi altra dimensione raccolta da Analytics. Nei feed di dati, gli ID audience sono memorizzati nella colonna «mc_ audiences». Queste dimensioni non sono attualmente disponibili in Workbench dati o Livestream. Alcuni esempi di come possono essere sfruttate le dimensioni Audience includono:

## Analysis Workspace {#section_C70837499BEA4DED885B3486C9E02C68}

In Analysis Workspace, i segmenti AAM appaiono come due dimensioni.

1. **[!UICONTROL Workspace]** Vai a.
1. From the list of **[!UICONTROL Dimensions]**, select the dimensions **[!UICONTROL Audience ID]** or **[!UICONTROL Audience Name]**. Nome è una classificazione intuitiva dell'ID.

   ![](assets/aw-mcaudiences.png)

## Confronto segmenti {#section_E72B80B6470C42D4B9B19BE90E6070A2}

[Confronto segmenti](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/segment-comparison.html) rileva le differenze più importanti dal punto di vista statistico tra due segmenti. I dati sui tipi di pubblico possono essere utilizzati in Confronto segmenti in due modi: 1) dei 2 segmenti che vengono confrontati e 2) come elementi nella tabella «Elementi dimensione principali».

1. Go to **[!UICONTROL Workspace]** and select the **[!UICONTROL Segment Comparison]** panel from the left rail.

1. Search for [!UICONTROL Audiences Name] in the **[!UICONTROL Component]** menu.

1. Open [!UICONTROL Audiences Name]so that the related dimension items appear.
1. Trascina le audience da confrontare nel generatore di segmenti di segmenti.
1. (Facoltativo): Puoi anche importare altri elementi dimensione o segmenti, è possibile confrontare fino a 2.
1. Fai clic su **[!UICONTROL Build]**.

   Le dimensioni ID e Nome del pubblico verranno automaticamente visualizzate nella tabella «Elementi dimensione principali», in quanto sono dati di profilo aggiuntivi per i due segmenti confrontati.

   ![](assets/aud-segcompare.png)

## Customer Journey (Flow) in Analysis Workspace {#section_FC30E5795C9D4539838E30FE11FAEA6E}

I dati del segmento AAM vengono passati in Analytics ogni volta che sono hit, e rappresentano l'appartenenza al pubblico per un visitatore in quel momento. Questo significa che un visitatore può cadere in un segmento (ad esempio "Consapevolezza"), quindi più tardi idoneo a un segmento più qualificato (ad es. "Considerazioni"). You can use [Flow](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html) in Analysis Workspace to visualize the journey a visitor takes between audiences.

1. Go to **[!UICONTROL Workspace]** and select the **[!UICONTROL Flow]** visualization from the left rail.

1. Drag the [!UICONTROL Audience Name] dimension into the Flow builder.
1. Fai clic su **[!UICONTROL Build]**.
1. (Optional): Drag any other dimension into the Flow visualization to create an [inter-dimensional Flow](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/multi-dimensional-flow.html).

![](assets/flow-aamaudiences.png)

Audiences can also be used in [Fallout visualizations](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/fallout_flow.html).

## Venn Visualization in Analysis Workspace {#section_E78AB764FB5047148B51DC1526B0DF89}

[Le visualizzazioni di Venn](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/venn.html) mostrano la sovrapposizione tra un massimo di 3 segmenti.

1. Go to **[!UICONTROL Workspace]** and select the **[!UICONTROL Venn]** visualization from the left rail.

1. Search for [!UICONTROL Audience Name] in the component menu.
1. Open [!UICONTROL Audience Name] so that the related dimension items appear.
1. Trascinate le audience che desiderate confrontare nel generatore di Venn.
1. (Facoltativo): Potete importare anche altri elementi dimensione o segmenti; è possibile confrontare fino a 3.
1. Fai clic su **[!UICONTROL Build]**.

![](assets/venn-viz.png)

## Generatore di segmenti {#section_2AA81852A1404AB894472CA8959461B6}

You can incorporate the Audiences dimensions in the Analytics [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html), along with the behavioral information that Analytics collects.

1. Go to  **[!UICONTROL Components]** &gt; **[!UICONTROL Segments]** .
1. Click **[!UICONTROL Add]** to create a new segment.
1. After naming the segment, drag the [!UICONTROL Audience Name] dimension into the Definitions panel.
1. (Facoltativo): Aggiungete altri criteri al segmento.
1. Salva il segmento.

   ![](assets/aud-segbuilder.png)

## Reports &amp; Analytics and Report Builder {#section_04E8FD30F73344D7937AD3C6CD19E34A}

1. To view the Analytics report, go to  **[!UICONTROL Reports]** &gt; **[!UICONTROL Visitor Profile]** &gt; **[!UICONTROL Audience ID Reports]** .
1. Da questa cartella puoi accedere alle dimensioni ID audience e Nome pubblico.

   ![](assets/mc-audiences.png)

