---
description: Usa i segmenti in Analysis Workspace.
title: Segmenti
feature: Segmentation
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 81%

---


# Segmenti {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

In Workspace puoi creare diversi tipi di segmento, a seconda della complessità, dell’applicabilità solo a un determinato progetto, ecc. Segue un riepilogo dei tipi di segmento:

| Tipo di segmento | Creato dove? | Applicabile dove? | Quando utilizzare |
| --- | --- | --- | --- |
| Segmento nell’elenco dei componenti | Fai clic su +, per passare al [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md) | Tutti i progetti Workspace | Per segmenti più complessi, segmenti sequenziali |
| Segmento rapido | [Generatore di segmenti rapidi](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | Solo progetto, ma può essere salvato e aggiunto all’elenco dei segmenti. | Può essere utilizzato per segmenti ad hoc a regola singola (con trascinamento della selezione) oppure per aggiungere/modificare più regole (facendo clic sull’icona Segmento) |
| Segmento basato su metriche calcolate | [Generatore di metrica calcolata](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html?lang=it) | Per singola metrica calcolata | Applicare segmenti nella definizione della metrica |
| Segmento basato su suite di rapporti virtuali | [Generatore suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html?lang=it) | Per singole suite di rapporti virtuali | Applicare segmenti nella definizione della suite di rapporti virtuali |

## Video

>[!BEGINSHADEBOX]

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Utilizzo di segmenti in Analysis Workspace](https://video.tv.adobe.com/v/23977?quality=12&learn=on){target="_blank"} per un video demo.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Ricerca e creazione di segmenti](https://video.tv.adobe.com/v/334092?quality=12&learn=on){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Intervalli di date continui nel segmento](https://video.tv.adobe.com/v/25403?quality=12&learn=on){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


## Creare un segmento {#section_693CFADA668B4542B982446C2B4CF0F5}

In Analysis Workspace puoi creare diversi tipi di segmenti:

* [Segmenti rapidi](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* Segmenti regolari dell’elenco di componenti creati nel Generatore di segmenti e che vengono inseriti nella libreria di segmenti (vedi di seguito)

### Creare segmenti per l’elenco dei componenti {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

La barra dei segmenti nel menu Componenti mostra

* Segmenti creati da te o dalla tua azienda
* Modelli di segmento, contrassegnati dall&#39;icona Adobe ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg):


Per creare un segmento di questo tipo, sono disponibili 2 opzioni. Entrambi ti portano al [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md) in Adobe Analytics, dove puoi trovare ulteriori istruzioni.

* Nella barra a sinistra, fai clic sul segno più (+) accanto a [!UICONTROL Segments]:

![](assets/create-seg.png)

oppure

* Scegli [!UICONTROL Components] > [!UICONTROL Segments], quindi fai clic su [!UICONTROL + Add].


### Altri metodi per applicare segmenti {#section_10FF2E309BA84618990EA5B473015894}


>[!BEGINSHADEBOX]

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Altri metodi per applicare segmenti](https://video.tv.adobe.com/v/30994?quality=12&learn=on){target="_blank"} per un video demo.

>[!ENDSHADEBOX]

Esistono molti altri metodi per applicare i segmenti a un pannello a forma libera.

| Azione | Descrizione |
|--- |--- |
| Crea segmenti dalla selezione | Crea un segmento in linea. Questo tipo di segmento si applica solo al progetto aperto e non viene salvato come segmento di Analytics. 1. Seleziona le righe.  2. Fai clic con il pulsante destro del mouse sulla selezione.  3. Fai clic su *Create Segment from selection* (Crea segmenti da selezione). |
| Components (Componenti) > New Segment (Nuovo segmento) | Visualizza il Segment Builder (Generatore di segmenti). Per ulteriori informazioni sulla segmentazione, consulta l’articolo su come [generare i segmenti](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=it). |
| Share (Condividi) > Share Project (Condividi progetto) or Share (Condividi) > Curate Project Data (Cura dati progetto) | In [Cura e condivisione](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=it#concept_4A9726927E7C44AFA260E2BB2721AFC6), scopri come i segmenti applicati al progetto sono disponibili al destinatario nelle analisi condivise. |
| Uso dei segmenti come dimensioni | Video: [Uso dei segmenti come dimensioni in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html?lang=it) |

## Segmento IQ

Il segmento IQ (noto anche come Confronto segmenti) include le seguenti funzionalità:

* [Pannello Confronto segmenti:](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) la funzione principale del segmento IQ. Trascina due segmenti nel pannello e visualizza un rapporto completo che mostra differenze statisticamente significative e sovrapposizioni tra i due pubblici.
* [Confronto di segmenti in Abbandono:](/help/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md) scopri in che modo diversi tipi di pubblico si confrontano tra loro nel contesto di una visualizzazione di abbandono.

## Ulteriori informazioni

Per una discussione approfondita sulla segmentazione in Adobe Analytics, visita [questa pagina](/help/components/segmentation/seg-overview.md).
