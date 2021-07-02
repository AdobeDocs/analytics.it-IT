---
description: 'I componenti in Analysis Workspace sono metriche, dimensioni, segmenti e intervalli temporali da trascinare su un progetto. '
title: Panoramica dei componenti
feature: Concetti di base di Workspace
role: Business Practitioner, Administrator
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '668'
ht-degree: 100%

---

# Panoramica dei componenti

I componenti in Analysis Workspace sono metriche, dimensioni, segmenti e intervalli temporali da trascinare su un progetto.

Per accedere al menu Componenti, fai clic sull’icona **[!UICONTROL Components]** nella barra a sinistra. Puoi passare da [Pannelli](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it), [Visualizzazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=it) e Componenti dalle icone della barra a sinistra oppure utilizzando [tasti di scelta rapida](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

È inoltre possibile regolare le [impostazioni di densità di visualizzazione](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=it) per consentire al progetto di visualizzare più valori contemporaneamente nella barra a sinistra, da **[!UICONTROL Project > Project Info & Settings > View Density]**.

## Dimensioni {#dimensions}

Le [**dimensioni**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html?lang=it) sono attributi di testo che descrivono il comportamento del visitatore e possono essere visualizzate, suddivise e confrontate nell’analisi. Si trovano nella barra dei componenti a sinistra (sezione arancione) e vengono in genere applicate come righe di una tabella.

Esempi di dimensioni includono [!UICONTROL Page Name], [!UICONTROL Marketing Channels], [!UICONTROL Device Type] e [!UICONTROL Products]. Le dimensioni sono fornite da Adobe e vengono acquisite tramite l’implementazione personalizzata (eVar, Prop, classificazioni, ecc.).

Ogni dimensione contiene anche **elementi dimensionali** al suo interno. Per trovare gli elementi dimensionali nella barra dei componenti a sinistra, fai clic sulla freccia destra accanto al nome di una dimensione (gli elementi sono in giallo).

Esempi di elementi dimensionali includono [!UICONTROL Homepage] (nella dimensione [!UICONTROL Page]), [!UICONTROL Paid Search] (nella dimensione [!UICONTROL Marketing Channel]), [!UICONTROL Tablet] (nella dimensione [!UICONTROL Mobile Device Type]) e così via.

![](assets/dimensions.png)

## Metriche {#metrics}

Le [**metriche**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html?lang=it) sono misure quantitative sul comportamento dei visitatori. Si trovano nella barra dei componenti a sinistra (sezione verde) e vengono in genere applicate come colonne di una tabella.

Esempi di metriche includono [!UICONTROL Page views], [!UICONTROL Visits], [!UICONTROL Orders], [!UICONTROL Average Time spent] e [!UICONTROL Revenue/Order]. Le metriche vengono fornite per Adobe, acquisite tramite l’implementazione personalizzata ([!UICONTROL Success events]) o create utilizzando il [Generatore di metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=it).

![](assets/metrics.png)

## Segmenti {#segments}

I [**segmenti**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html?lang=it) sono filtri di pubblico applicati all’analisi. Si trovano nella barra dei componenti a sinistra (sezione blu) e sono in genere applicati nella parte superiore di un pannello o sopra le colonne di metrica in una tabella.

Esempi di segmenti includono [!UICONTROL Mobile Device Visitors], [!UICONTROL Visits from Email] e [!UICONTROL Authenticated Hits]. I segmenti vengono forniti da Adobe oppure possono essere creati nella [zona di rilascio del pannello](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it) o mediante il [Generatore di segmenti](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=it).

![](assets/segments.png)

## Intervalli di date {#date-ranges}

Gli [**intervalli di date**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html?lang=it) sono l’intervallo di date in cui esegui l’analisi. Si trovano nella barra dei componenti a sinistra (sezione viola) e vengono in genere applicati nel calendario di ciascun pannello.

Esempi di intervalli di date includono luglio 2019, [!UICONTROL Last 4 weeks] e [!UICONTROL This month]. Gli intervalli di date sono forniti da Adobe, possono essere applicati nel [calendario del pannello](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it) o creati mediante il [Generatore di intervalli di date](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=it).

![](assets/date-ranges.png)

## Azioni dei componenti {#actions}

Puoi gestire i componenti (singolarmente o selezionandone più d’uno) direttamente nella barra a sinistra. Fai clic con il pulsante destro del mouse su un componente oppure fai clic sull’icona delle azioni (tre punti in verticale) in alto nell’elenco dei componenti.

![](assets/component-actions.png)

| Azione del componente | Descrizione |
|--- |--- |
| Tag | Organizzare o gestire i componenti tramite l’applicazione di tag. Per eseguire la ricerca per tag nella barra a sinistra, fai clic sul filtro o digita #. I tag fungono anche da filtri nei gestori dei componenti. |
| Preferito | Aggiungere il componente all’elenco dei preferiti. Come per i tag, puoi cercare i Preferiti nella barra a sinistra e filtrarli nei gestori dei componenti. |
| Approva | Contrassegna i componenti come approvati per segnalare agli utenti che sono approvati dall’organizzazione. Come per i tag, puoi eseguire ricerche per compomenti approvati nella barra a sinistra e filtrarli nei gestori dei componenti. |
| Condividi | Condividi i componenti con gli utenti della tua organizzazione. Questa opzione è disponibile solo per i componenti personalizzati, ad esempio segmenti o metriche calcolate. |
| Elimina | Elimina i componenti non più necessari. Questa opzione è disponibile solo per i componenti personalizzati, ad esempio segmenti o metriche calcolate. |

I componenti personalizzati possono essere gestiti anche tramite i rispettivi gestori di componenti. Ad esempio, il [Gestore segmenti](/help/components/segmentation/segmentation-workflow/seg-manage.md).
