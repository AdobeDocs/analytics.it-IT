---
title: Pannello Attribution
description: Come utilizzare e interpretare il pannello Attribution in Analysis Workspace.
feature: Attribution
role: User, Admin
exl-id: 96ce3cb9-7753-4ec0-b551-e70a1508e3b7
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 48%

---

# Pannello Attribution {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="Attribuzione"
>abstract="Confronta e visualizza rapidamente un numero qualsiasi di modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Pannello Attribution IQ"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="Pannello Attribution"
>abstract="Confronta e visualizza rapidamente più modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione.<br/><br/>**Parametri &#x200B;**<br/>**Canale**<br/> La dimensione a cui attribuire. Questa dimensione può essere un canale di marketing, una campagna o qualsiasi altra dimensione.<br/>**Modelli**<br/> Il modello determina come viene assegnato il credito ai punti di contatto.<br/>**Intervallo di lookback**<br/> Questa impostazione determina la finestra di attribuzione dei dati che viene applicata a ogni conversione."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Pannello Attribution IQ"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Questo articolo documenta il pannello Attribuzione in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Consulta [Pannello di attribuzione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/panels/attribution) per la_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**versione del Customer Journey Analytics** di questo articolo._

>[!ENDSHADEBOX]

Il pannello **[!UICONTROL Attribution]** permette di strutturare facilmente un’analisi confrontando diversi modelli di attribuzione. Il pannello offre un’area di lavoro dedicata per utilizzare e confrontare modelli di attribuzione.

Adobe Analytics migliora l’attribuzione consentendo di:

* Definire l’attribuzione oltre i paid media: è possibile applicare ai modelli qualsiasi dimensione, metrica, canale o evento (ad esempio, ricerca interna), non solo le campagne di marketing.
* Utilizza confronto illimitato tra modelli di attribuzione: confronta dinamicamente tutti i modelli che desideri.
* Evitare le modifiche di implementazione: con l’elaborazione al momento del reporting e le sessioni in base al contesto, è possibile integrare e applicare il contesto di percorso del cliente in fase di esecuzione.
* Costruire la sessione che si adatta al meglio allo scenario di attribuzione.
* Suddividere l’attribuzione per segmenti: è possibile confrontare facilmente le prestazioni dei canali di marketing in qualsiasi segmento importante (ad esempio, clienti nuovi rispetto a clienti di ritorno, prodotto X rispetto a prodotto Y, livello di fedeltà rispetto a Customer Lifetime Value).
* Ispezionare l’analisi incrociata e a più contatti dei canali: è possibile utilizzare diagrammi di Venn, istogrammi e risultati di attribuzione di tendenze.
* Analizzare visivamente sequenze di marketing principali: è possibile esplorare in modo visivo i percorsi che hanno condotto alla conversione, con visualizzazioni di abbandono e di flusso a più nodi.
* Costruire metriche calcolate: è possibile utilizzare un qualsiasi numero di metodi di allocazione di attribuzione.

## Utilizzo

Per utilizzare un pannello **[!UICONTROL Attribution]**:

1. Crea un pannello **[!UICONTROL Attribution]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.

### Input del pannello

Puoi configurare il pannello Attribuzione utilizzando le seguenti impostazioni di input:

1. Aggiungere **[!UICONTROL Success metric]** e una dimensione da **[!UICONTROL Channel]** a cui si desidera attribuire l&#39;attributo. Alcuni esempi includono Marketing Channels o dimensioni personalizzate, ad esempio promozioni interne.

   ![La finestra del pannello Attribuzione mostra diverse dimensioni e metriche selezionate.](assets/attribution-panel.png)

1. Selezionare uno o più [modelli di attribuzione](#attribution-models) da **[!UICONTROL Included models]** e un [intervallo di lookback](#lookback-window) da **[!UICONTROL Lookback window]** che si desidera utilizzare per il confronto.

1. Seleziona **[!UICONTROL Build]** per creare le visualizzazioni nel pannello.

### Output del pannello

Il pannello **[!UICONTROL Attribution]** restituisce un set completo di dati e visualizzazioni che confrontano l&#39;attribuzione per la dimensione e la metrica selezionate.

![Visualizzazioni del pannello Attribuzione che confrontano le metriche e le dimensioni selezionate.](assets/attr_panel_vizs.png)

### Visualizzazioni di Attribution

La visualizzazione seguente fa parte dell’output del pannello.

* **Metrica totale**: il numero totale di conversioni che si sono verificate nell&#39;intervallo di tempo di reporting e sono attribuite alla dimensione selezionata.
* **Barra di confronto attribuzione**: confronta visivamente le conversioni attribuite per ciascun elemento dimensionale dalla dimensione selezionata. Ogni colore della barra rappresenta un modello di attribuzione distinto.
* **Tabella di confronto attribuzione**: mostra gli stessi dati del grafico a barre, rappresentandoli sotto forma di tabella. Se si selezionano colonne o righe diverse in questa tabella, il grafico a barre e diverse altre visualizzazioni nel pannello vengono filtrate. Questa tabella funziona come qualsiasi altra tabella a forma libera in Workspace e consente di aggiungere componenti quali metriche, segmenti o raggruppamenti.
* **Diagramma di sovrapposizione**: una visualizzazione di Venn che mostra i primi tre elementi dimensionali e la frequenza con cui partecipano congiuntamente a una conversione. Ad esempio, le dimensioni della sovrapposizione a bolla indicano quanto spesso si è verificata una conversione quando una persona è stata esposta a entrambi gli elementi dimensionali. Quando si selezionano altre righe nella tabella a forma libera adiacente, la visualizzazione si aggiorna in base alla selezione.
* **Dettagli delle prestazioni**: una visualizzazione a dispersione per confrontare visivamente fino a tre modelli di attribuzione.
* **Prestazioni con tendenze**: mostra la tendenza delle conversioni attribuite per l’elemento della dimensione superiore. Quando si selezionano altre righe nella tabella a forma libera adiacente, la visualizzazione si aggiorna in base alla selezione.
* **Flusso**: consente di vedere con quali canali si interagisce più comunemente e in quale ordine nel percorso di una persona.

## Modelli di attribuzione

{{attribution-models-details}}

## Intervallo di lookback

{{attribution-lookback-window}}

>[!MORELIKETHIS]
>
> [Creare un pannello](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>

<!--
# Attribution panel

The [!UICONTROL Attribution] panel is an easy way to build an analysis comparing various attribution models. It is a feature in [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) that gives you a dedicated workspace to use and compare attribution models.

>[!VIDEO](https://video.tv.adobe.com/v/41429/?quality=12&captions=ita)

## Create an attribution panel

1. Click the panel icon on the left.
1. Drag the [!UICONTROL Attribution] panel into your Analysis Workspace Project.

   ![New attribution panel](assets/Attribution_Panel_1.png)

1. Add a metric that you want to attribute and add any dimension to attribute against. Examples include Marketing Channels or custom dimensions, such as internal promotions.

   ![Select dimension and metric](assets/attribution_panel2.png)

1. Select the [attribution models and lookback window](../attribution/models.md) you want to compare.

1. The Attribution panel returns a rich set of data and visualizations that compare attribution for the selected dimension and metric.

   ![Attribution visualizations](assets/attr_panel_vizs.png)

## Attribution visualizations

* **Total metric**: The total number of conversions that occurred over the reporting time window. These are the conversions that are attributed across the dimension that you selected.
* **Attribution Comparison Bar**: Visually compares the attributed conversions across each of the dimension items from your selected dimension. Each bar color represents a distinct attribution model.
* **Attribution Comparison Table**: Shows the same data as the bar chart, represented as a table. Selecting different columns or rows in this table filters the bar chart as well as several of the other visualizations in the panel. This table acts similar to any other Freeform Table in Workspace - allowing you to add components such as metrics, segments, or breakdowns.
* **Overlap Diagram**: A Venn Diagram showing the top three dimension items and how often they participate jointly in a conversion. For example, the size of the bubble overlap indicates how often conversions occurred when a visitor was exposed to both dimension items. Selecting other rows in the adjacent Freeform table updates the visualization to reflect your selection.
* **Performance Detail**: Lets you to compare up to three attribution models visually using a scatter plot.
* **Trended Performance**: By default, shows the conversion performance trend by attribution model for the first dimension listed in the adjacent Freeform table. You can select different dimension rows in the Freeform table to show the trend for the selected dimensions (such as Total Revenue for each attribution model for Social Campaigns and Paid Search). Alternately, you can select cells in the columns for any metric and attribution type combinations in the Freeform table to see the trended performance by dimension value for the specified attribution models (such as Total Revenue by Marketing Channel using Last Touch and First Touch attribution).
* **Flow**: Lets you see which channels are interacted with most commonly, and in what order across a visitor's journey.

-->