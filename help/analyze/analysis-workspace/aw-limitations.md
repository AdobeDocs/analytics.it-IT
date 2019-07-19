---
description: nulle
seo-description: nulle
seo-title: Limitazioni di Workspace, limitazioni note in Analysis Workspace
title: Limitazioni noti in Analysis Workspace
translation-type: tm+mt
source-git-commit: 9d6b35c7c6de6fcb49fea3b662ff8bc9044b5e29

---


# Limitazioni noti in Analysis Workspace

Elenco delle limitazioni note in Analysis Workspace e sui relativi componenti:

## Tabelle

* Non è possibile aggiungere colonne di confronto date quando gli intervalli di date o le metriche vengono utilizzati come righe di una tabella.
* L'opzione Crea metrica dalla selezione è disattivata quando i segmenti vengono utilizzati come righe di una tabella. Inoltre, l'opzione Crea metrica dalla selezione non deve essere applicata alle colonne allineate alla data.
* La formattazione condizionale per le righe suddivisioni non può utilizzare intervalli personalizzati.
* Le righe totali della tabella non possono essere tendenze quando calcola i totali di riga, sommando i valori delle righe (in genere utilizzate con elementi di riga statici).
* [!UICONTROL Contribution Analysis] può essere eseguito solo a [!UICONTROL daily] granularità __. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualizzazioni

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]: Le dimensioni di entrata/uscita, ad es [!UICONTROL Entry page]., non possono essere utilizzate in Flusso.
* [!UICONTROL Cohort]: Non è possibile utilizzare numeri interi come criteri coorte.

## Pannelli

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Componenti &gt; Segmenti

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). Ad esempio, Indirizzo IP.

## Componenti &gt; Metriche calcolate

* Le metriche calcolate non possono essere utilizzate in determinate visualizzazioni. Vedì Visualizzazionì sopra.
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). Ad esempio, [!UICONTROL IP Address].

## Componenti &gt; Intervalli di date

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## Componenti &gt; Suite di rapporti virtuali

* Quando l'elaborazione dei tempi di rapporto è abilitata, alcuni componenti non sono supportati. For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## Componenti &gt; Impostazioni rapporto

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## Attribution IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. For a full list, see the [Attribution IQ FAQ](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md).