---
description: Usa i segmenti in Analysis Workspace.
title: Segmenti
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
feature: Workspace Basics
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: 9622131ebd4a856cb7756e6844d7d7979029e70e
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 49%

---

# Segmenti {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

Puoi creare diversi tipi di segmenti in Workspace, a seconda di quanto debbano essere complessi, se devono essere applicati solo a questo progetto e così via. Segue un riepilogo dei tipi di segmenti:

| Tipo di segmento | Creato dove? | Applicabile dove? | Quando utilizzare |
| --- | --- | --- | --- |
| Segmento elenco componenti | [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md) | Globale/Pubblico | Per segmenti complessi, segmenti sequenziali |
| Segmento rapido | [Generatore di segmenti rapido](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | A livello di progetto, ma può rendere pubblico | Flessibilità e controllo per aggiungere/modificare regole, nomi e regole multiple |
| Segmenti ad hoc: |  |  |  |
| - Segmento di progetto ad hoc Workspace | [Trascina nella zona di rilascio segmenti di un progetto](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md) | A livello di progetto, ma può rendere pubblico | Per impostazione predefinita, segmenti a regola singola |
| - Segmento basato su metriche calcolate | [Generatore di metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html) | Per una singola metrica calcolata | Applicare segmenti nella definizione della metrica |
| - Segmento basato su VRS | [Generatore di suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) | Per suite di rapporti virtuali individuali | Applicare segmenti all’interno della definizione VRS |

Per una discussione approfondita sulla segmentazione in Adobe Analytics, vai [qui](/help/components/segmentation/seg-overview.md).

## Creare un segmento {#section_693CFADA668B4542B982446C2B4CF0F5}

In Analysis Workspace puoi creare diversi tipi di segmenti:

* [Segmenti rapidi](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* [Segmenti ad hoc](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md)
* Segmenti elenco dei componenti regolari che finiscono nella libreria dei segmenti (vedi sotto)

### Creare segmenti elenco di componenti {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

La barra dei segmenti nel menu Components (Componenti) mostra i segmenti e i modelli di segmenti, come indicato da queste icone:

![](assets/segment_icons.png)

[Utilizzo dei segmenti in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-in-analysis-workspace.html?lang=it) (6:46)

### Altri metodi per applicare segmenti {#section_10FF2E309BA84618990EA5B473015894}

>[!VIDEO](https://video.tv.adobe.com/v/30994/?quality=12)

Esistono molti altri metodi per applicare i segmenti a un pannello a forma libera.

| Azione | Descrizione |
|--- |--- |
| Crea segmenti dalla selezione | Crea un segmento in linea. Questo tipo di segmento si applica solo al progetto aperto e non viene salvato come segmento di Analytics. 1. Seleziona le righe.  2. Fai clic con il pulsante destro del mouse sulla selezione.  3. Fai clic su *Create Segment from selection* (Crea segmenti da selezione). |
| Components (Componenti) > New Segment (Nuovo segmento) | Visualizza il Segment Builder (Generatore di segmenti). Per ulteriori informazioni sulla segmentazione, consulta l’articolo su come [generare i segmenti](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=it). |
| Share (Condividi) > Share Project (Condividi progetto) or Share (Condividi) > Curate Project Data (Cura dati progetto) | In [Cura e condivisione](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=it#concept_4A9726927E7C44AFA260E2BB2721AFC6), scopri come i segmenti applicati al progetto sono disponibili al destinatario nelle analisi condivise. |
| Uso dei segmenti come dimensioni | Video: [Uso dei segmenti come dimensioni in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html?lang=it) |


