---
description: 'I componenti in Analysis Workspace sono costituiti da dimensioni, metriche, segmenti e intervalli di date che puoi trascinare su un progetto. '
title: Panoramica dei componenti
feature: Workspace Basics
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 17%

---


# Panoramica dei componenti

I componenti in Analysis Workspace sono costituiti da dimensioni, metriche, segmenti e intervalli di date che puoi trascinare su un progetto.

Per accedere al menu Componenti, fai clic sull’icona **[!UICONTROL Components]** nella barra a sinistra. Puoi passare da [Pannelli](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it-IT), [Visualizzazioni](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) e Componenti dalle icone della barra a sinistra oppure utilizzando [tasti di scelta rapida](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

È inoltre possibile regolare le [impostazioni di densità di visualizzazione](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) per consentire al progetto di visualizzare più valori contemporaneamente nella barra a sinistra andando su **[!UICONTROL Project > Project Info & Settings > View Density]**.

## Dimensioni {#dimensions}

[****](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) Le dimensioni sono attributi di testo che descrivono il comportamento del visitatore e possono essere visualizzati, suddivisi e confrontati nell’analisi. Si trovano nella barra dei componenti a sinistra (sezione arancione) e vengono in genere applicati come righe di una tabella.

Esempi di dimensioni sono [!UICONTROL Page Name], [!UICONTROL Marketing Channels], [!UICONTROL Device Type] e [!UICONTROL Products]. I Dimension sono forniti da Adobe e vengono acquisiti tramite l’implementazione personalizzata (eVar, Prop, classificazioni, ecc.).

Ogni dimensione contiene anche **elementi dimensionali** al suo interno. Per trovare gli elementi del Dimension nella barra dei componenti a sinistra, fai clic sulla freccia destra accanto al nome di una dimensione (gli elementi sono gialli).

Esempi di elementi dimensionali includono [!UICONTROL Homepage] (all’interno della dimensione [!UICONTROL Page]), [!UICONTROL Paid Search] (all’interno della dimensione [!UICONTROL Marketing Channel]), [!UICONTROL Tablet] (all’interno della dimensione [!UICONTROL Mobile Device Type]) e così via.

![](assets/dimensions.png)

## Metriche {#metrics}

[****](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) Le metriche sono misure quantitative sul comportamento dei visitatori. Si trovano nella barra dei componenti a sinistra (sezione verde) e vengono in genere applicati come colonne di una tabella.

Esempi di metriche includono [!UICONTROL Page views], [!UICONTROL Visits], [!UICONTROL Orders], [!UICONTROL Average Time spent] e [!UICONTROL Revenue/Order]. Le metriche vengono fornite per Adobe, acquisite tramite l&#39;implementazione personalizzata ([!UICONTROL Success events]) o create utilizzando il [Generatore di metriche calcolate](https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).

![](assets/metrics.png)

## Segmenti {#segments}

[****](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) I segmenti sono filtri applicati all’analisi. Si trovano nella barra dei componenti a sinistra (sezione blu) e sono in genere applicati nella parte superiore di un pannello o sopra le colonne di metrica in una tabella.

Alcuni esempi di segmenti sono [!UICONTROL Mobile Device Visitors], [!UICONTROL Visits from Email] e [!UICONTROL Authenticated Hits]. I segmenti vengono forniti per Adobe, creati nella [zona di rilascio del pannello](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html) o creati utilizzando il [Generatore di segmenti](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/segmentation-workflow/seg-build.html).

![](assets/segments.png)

## Intervalli di date {#date-ranges}

[**Gli**](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) intervalli di date sono l’intervallo di date in cui esegui l’analisi. Si trovano nella barra dei componenti a sinistra (sezione viola) e vengono in genere applicati nel calendario di ciascun pannello.

Esempi di intervalli di date sono luglio 2019, [!UICONTROL Last 4 weeks] e [!UICONTROL This month]. Gli intervalli di date sono forniti per Adobe, applicati nel [calendario del pannello](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html) o creati utilizzando il [Generatore di intervalli di date](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html).

![](assets/date-ranges.png)

## Azioni dei componenti {#actions}

Puoi gestire i componenti (singolarmente o selezionandone più) direttamente nella barra a sinistra. Fai clic con il pulsante destro del mouse su un componente o fai clic sull’icona del punto Azione in alto nell’elenco dei componenti.

![](assets/component-actions.png)

| Azione del componente | Descrizione |
|--- |--- |
| Tag | Organizzare o gestire i componenti tramite l’applicazione di tag. Per eseguire la ricerca per tag nella barra a sinistra, fai clic sul filtro o digita #. I tag fungono anche da filtri nei gestori dei componenti. |
| Preferito | Aggiungere il componente all’elenco dei preferiti. Come per i tag, puoi cercare i Preferiti nella barra a sinistra e filtrarli nei gestori dei componenti. |
| Approva | Contrassegna i componenti come approvati per segnalare agli utenti che il componente è approvato dall’organizzazione. Come per i tag, puoi eseguire ricerche per Approvato nella barra a sinistra e filtrare in base a essi nei gestori dei componenti. |
| Condividi | Condividi i componenti con gli utenti della tua organizzazione. Questa opzione è disponibile solo per i componenti personalizzati, ad esempio segmenti o metriche calcolate. |
| Elimina | Elimina i componenti non più necessari. Questa opzione è disponibile solo per i componenti personalizzati, ad esempio segmenti o metriche calcolate. |

I componenti personalizzati possono essere gestiti anche tramite i rispettivi gestori di componenti. Ad esempio, il [Gestore segmenti](/help/components/segmentation/segmentation-workflow/seg-manage.md).
