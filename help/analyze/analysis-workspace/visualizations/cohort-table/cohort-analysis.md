---
title: Panoramica della tabella coorte
description: Scopri come approfondire i dati sul pubblico e suddividerli in gruppi correlati con l’analisi per coorte. Utilizza l’analisi per coorte in Analysis Workspace.
feature: Visualizations
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 88%

---

# Panoramica delle tabelle coorte {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Tabella coorte"
>abstract="Crea una visualizzazione per coorte per raggruppare gli utenti in base al completamento di un evento e analizzare il coinvolgimento continuo e l’abbandono nel tempo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Tabella coorte"
>abstract="Raggruppa gli utenti in base al completamento di un evento, quindi analizza il coinvolgimento continuo e l’abbandono nel tempo.<br/><br/>**Parametri **<br/>**Criteri di inclusione**: i componenti utilizzati per definire le coorti di visitatori iniziali.<br/>**Criteri di ritorno**: i componenti utilizzati per determinare se un visitatore è tornato."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo documenta la tabella coorte in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulta la [tabella coorte](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis) per_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** versione di questo articolo._

>[!ENDSHADEBOX]



Una *coorte* è un gruppo di persone che condividono le stesse caratteristiche per un determinato periodo di tempo. Una visualizzazione **[!UICONTROL Cohort table]** ![TextNumbered](/help/assets/icons/TextNumbered.svg) è utile, ad esempio, quando vuoi scoprire in che modo una coorte si relaziona con un brand. Permette di individuare facilmente cambiamenti nelle tendenze e reagire di conseguenza. Puoi trovare informazioni sull’[!UICONTROL Cohort Analysis] su Internet, ad esempio [Cohort Analysis 101](https://it.wikipedia.org/wiki/Analisi_di_coorte).

Dopo aver generato un rapporto sulla coorte, puoi curarne i componenti (dimensioni, metriche e filtri specifici) e condividerlo con chiunque. Consulta [Cura e condivisione](/help/analyze/analysis-workspace/curate-share/curate.md).

Esempi di cosa è possibile fare con una [!UICONTROL Cohort table]:

* Lanciare campagne sviluppate per promuovere un’azione desiderata.
* Spostare il budget marketing nel momento giusto del ciclo di vita di un cliente.
* Riconoscere quando interrompere una versione di prova o un’offerta per massimizzare il valore.
* Sviluppare idee per il test A/B in aree come prezzo, percorso di upgrade ecc.

L’[!UICONTROL Cohort table] è disponibile per tutti i clienti Adobe Analytics con diritti di accesso ad [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analisi per coorte in Analysis Workspace](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] non supporta le metriche non filtrabili (comprese le metriche calcolate), le metriche non intere (come Entrate) o le occorrenze. Solo le metriche utilizzabili nei filtri possono essere utilizzate in [!UICONTROL Cohort Analysis] e possono essere incrementate solo di 1 alla volta.

Le tabelle coorte in Adobe Analytics supportano metriche basate sul doppio sistema (o su qualsiasi altro sistema numerico). Ad esempio, Purchase.Value (doppio) può essere utilizzato come metrica di inclusione/ritorno. Inoltre, anche tutte le metriche passate in Adobe Experience Platform tramite il connettore di origine di Analytics sono doppie.

## Funzionalità delle tabelle coorte

Le sezioni seguenti descrivono le funzioni di analisi per coorte che consentono un controllo accurato delle coorti che stai creando.

Per informazioni più dettagliate sulla creazione di una coorte e sull’esecuzione di un rapporto di [!UICONTROL Cohort Analysis], consulta [Configurare una tabella coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Tabella di conservazione

Una tabella coorte [!UICONTROL Retention] restituisce persone: ogni cella di dati mostra numeri e percentuali non elaborate di persone nella coorte che hanno eseguito un’azione in quel periodo di tempo. Puoi includere fino a 3 metriche e 10 filtri.

![Un rapporto di coorte Fidelizzazione che mostra le unità e la percentuale di persone nella coorte.](assets/retention-report.png)

### Tabella di abbandono

Una tabella coorte [!UICONTROL Churn] è l’inverso di una tabella Fidelizzazione e mostra le persone che durante un periodo non rientrano più o non sono mai rientrate nei criteri della coorte. Puoi includere fino a 3 metriche e 10 filtri.

![Una tabella Abbandono che mostra le unità e la percentuale di persone che non soddisfano i criteri di ritorno di una coorte.](assets/churn-report.png)

### Calcolo continuo

Puoi calcolare il livello di fidelizzazione o abbandono in base alla colonna precedenti, non alla colonna inclusi, a cui si fa riferimento come calcolo continuo.

![Un rapporto di fidelizzazione per coorte che mostra i calcoli basati su una colonna di dati precedenti.](assets/retention-report-rolling.png)

### Tabella di latenza

Una tabella di latenza misura il tempo trascorso prima e dopo il verificarsi dell’evento di inclusione. La misura della latenza è un ottimo strumento di analisi pre/post. La colonna **[!UICONTROL Included]** è al centro della tabella ed è preceduta e seguita dai periodi di tempo precedenti e successivi all’evento di inclusione.

![Un rapporto di coorte che mostra il tempo trascorso prima e dopo un evento.](assets/retention-report-latency.png)

### Coorte con dimensione personalizzata

Puoi creare le coorti in base a una dimensione selezionata anziché in base al tempo, che è l’impostazione predefinita. Utilizza dimensioni quali [!UICONTROL City geo], [!UICONTROL Marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region] o qualsiasi altra dimensione per mostrare come cambia la fidelizzazione. In base ai diversi valori di queste dimensioni.

![Un rapporto sulla coorte che mostra un rapporto personalizzato con dimensioni selezionate, non la coorte predefinita basata sul tempo.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configurare una tabella coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)
>



<!--
A *`cohort`* is a group of people sharing common characteristics over a specified period. [!UICONTROL Cohort Analysis] is useful, for example, when you want to learn how a cohort engages with a brand. You can easily spot changes in trends, then respond accordingly. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

After creating a cohort report, you can curate its components (specific dimensions, metrics, and segments), then share the cohort report with anyone. See [Curate and Share](/help/analyze/analysis-workspace/curate-share/curate.md).

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* Launch campaigns designed to spur a desired action.
* Shift marketing budget at exactly the right time in the customer lifecycle.
* Recognize when to end a trial or an offer, in order to maximize value.
* Gain ideas for A/B testing in areas such as pricing, upgrade path, and so on.

[!UICONTROL Cohort Analysis] is available for all Adobe Analytics customers with access rights to [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cohort analysis in Analysis Workspace](https://video.tv.adobe.com/v/25965?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] does not support non-segmentable metrics (including calculated metrics), non-integer metrics (such as Revenue), or Occurrences. 
>
>Only metrics that can be used in segments can be used in [!UICONTROL Cohort Analysis], and they can only be incremented by >1 at a time. 

## Cohort Analysis capabilities

The following sections describe Cohort Analysis features that allow for fine-tuned control over the cohorts you are building.

For more detailed information about creating a cohort and running a [!UICONTROL Cohort Analysis] report, see [Configure a Cohort Analysis report](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention] Table

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. You can include up to 3 metrics and up to 10 segments.

![](assets/retention-report.png)


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculate rolling retention](https://video.tv.adobe.com/v/25962?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



### [!UICONTROL Churn] Table

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. You can include up to 3 metrics and up to 10 segments.

![](assets/churn-report.png)

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Churn analysis](https://video.tv.adobe.com/v/25966?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


### [!UICONTROL Rolling Calculation]

Lets you calculate retention or churn based on the previous column, not the included column.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Table

Measures the time that has elapsed before and after the inclusion event occurred. This is an excellent tool for pre/post analysis. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Cohort

Create cohorts based on a selected dimension, and not time-based cohorts, which are the default. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

-->
