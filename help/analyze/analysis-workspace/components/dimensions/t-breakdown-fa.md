---
description: Scopri come suddividere dimensioni ed elementi dimensionali in Analysis Workspace.
keywords: Analysis Workspace
title: Suddividere dimensioni
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 46%

---

# Suddividere dimensioni

Puoi suddividere i dati in Analysis Workspace in modo illimitato in base alle tue esigenze specifiche; puoi creare query utilizzando metriche, dimensioni, segmenti, linee temporali e altri valori di suddivisione dell’analisi pertinenti.

1. In una [tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) selezionare **[!UICONTROL Breakdown]** ![ChevronRight](/help/assets/icons/ChevronRight.svg) dal menu di scelta rapida di una o più righe selezionate.

   ![Risultato passaggio che mostra l&#39;avviso di creazione dalla selezione selezionata.](assets/breakdown.png)

1. Dal sottomenu selezionare **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]**, **[!UICONTROL Segments]** o **[!UICONTROL Date ranges]** e quindi selezionare un elemento. Oppure cerca semplicemente un componente nel campo **[!UICONTROL *Cerca *]**.

Puoi analizzare metriche per elementi dimensionali o segmenti di pubblico in diversi periodi di tempo selezionati. Puoi anche effettuare analisi molto più dettagliate.

>[!NOTE]
>
>È possibile mostrare nella tabella un massimo di 200 raggruppamenti. Questo limite aumenta per l’esportazione di raggruppamenti.

## Raggruppamento per posizione

Per impostazione predefinita, le suddivisioni sono fissate a elementi di riga statici. Ad esempio, immagina di suddividere i primi 3 elementi dimensionali di pagina (Home page, Risultati ricerca, Pagamento) per canale di marketing. Poi abbandoni il progetto per due settimane. Quando lo riapri, le prime 3 pagine sono cambiate e ora Home page, Risultati ricerca e Pagamento sono le prime 4-6 pagine. Per impostazione predefinita, i raggruppamenti per canale di marketing vengono ancora visualizzati in Home page, Risultati ricerca e Pagamento, anche se ora si trovano nelle righe 4-6.

Al contrario, **Raggruppamento per posizione**, raggruppa sempre i primi 3 elementi, indipendentemente da quali siano. Facendo riferimento all’esempio, quando riapri il progetto, i raggruppamenti per canale di marketing sono legati alle prime 3 pagine della tabella. E non alla homepage, ai risultati della ricerca e al checkout, che ora si trovano nelle righe 4-6. Consulta [Impostazioni riga](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md) per informazioni su come configurare questa impostazione.



## Applicare modelli di attribuzione ai raggruppamenti

A qualsiasi raggruppamento all’interno di una tabella può essere applicato anche qualsiasi modello di attribuzione. Tale modello di attribuzione può essere lo stesso o diverso dalla colonna principale. Ad esempio, puoi analizzare gli ordini lineari sulla dimensione canali di marketing, ma applicare ordini a forma di U agli specifici codici di tracciamento all’interno di un canale. Per modificare il modello di attribuzione applicato a un raggruppamento, passa il cursore sul modello di raggruppamento e seleziona **[!UICONTROL Edit]**.

![Confronto attributi ordine con le impostazioni di raggruppamento](assets/breakdown-attribution.png)

Questo è il comportamento previsto quando si applicano modelli di attribuzione ai raggruppamenti o quando questi vengono modificati:

* Se applichi un’attribuzione quando non esistono altre attribuzioni, questa si applica all’intera struttura ad albero della colonna.

* Se aggiungi un raggruppamento dopo aver applicato un’attribuzione, utilizzerà l’impostazione predefinita per il raggruppamento specificato che è stato aggiunto (se tale dimensione ha un valore predefinito). In caso contrario, utilizzerà il raggruppamento dalla colonna padre. Alcune dimensioni hanno un’allocazione predefinita. Ad esempio, le dimensioni di Tempo e Referrer utilizzano Same Touch (Stesso contatto). La dimensione Prodotto utilizza Last Touch (Ultimo contatto). Altre dimensioni non hanno un valore predefinito e utilizzeranno l’allocazione della colonna padre.

* Se la struttura ad albero della colonna contiene già delle attribuzioni, la modifica dell’attribuzione ha effetto solo su quella che si sta modificando.

>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimension in Analysis Workspace](https://video.tv.adobe.com/v/23971?quality=12&learn=on){target="_blank"}.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Per un video dimostrativo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimension breakdown](https://video.tv.adobe.com/v/23969?quality=12&learn=on){target="_blank"}.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Aggiunta di dimensioni e metriche](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/dimensions/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace){target="_blank"} per un video dimostrativo.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Per un video dimostrativo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Utilizzo delle dimensioni in una tabella a forma libera](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table){target="_blank"}.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Per un video dimostrativo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Suddivisione Dimension per posizione](https://video.tv.adobe.com/v/24033){target="_blank"}.


>[!ENDSHADEBOX]



<!--
# Break down dimensions

Break down dimensions and dimension items in Analysis Workspace.

Break down your data in unlimited ways for your specific needs; build queries using relevant metrics, dimensions, segments, time lines, and other analysis breakdown values.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table.
1. In the data table, right-click a line item and select **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Step Result](assets/fa_data_table_actions.png)

   You can break down metrics by dimension items or audience segments across selected time periods. You can also drill down further to a more granular level.

   >[!NOTE]
   >
   >The number of breakdowns to show in the table is limited to 200. This limit will increase for exporting breakdowns.

## Apply attribution models to breakdowns

Any breakdown within a table can also have any attribution model applied to it. This attribution model can be the same or different from the parent column. For example, you can analyze linear Orders on your Marketing Channels dimension but apply U-Shaped Orders to the specific tracking codes within a Channel. To edit the attribution model applied to a breakdown, hover over the breakdown model and click **[!UICONTROL Edit]**:

![Breakdown settings](assets/breakdown_settings.png)

This is the expected behavior when applying attribution models to breakdowns or editing them:

* If you apply an attribution when no other attributions exist, then the attribution applies to the entire column tree.

* If you add a breakdown after an attribution has been applied, it will use the default for the given breakdown that was added, if that dimension has a default. Otherwise it will use the breakdown from the parent column. Some dimensions have a default allocation.  For example, [!UICONTROL Time] dimensions and [!UICONTROL Referrer] use [!UICONTROL Same Touch]. The [!UICONTROL Product] dimension uses [!UICONTROL Last Touch]. Other dimensions don't have a default, and will use the parent column allocation.

* If there are already attributions in the column tree, changing the attribution only impacts the one you are editing.

## Videos


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding dimensions and metrics to your project in Analysis Workspace](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/dimensions/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Working with dimensions in a Freeform Table](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [dimension breakdowns by position](https://video.tv.adobe.com/v/24033?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


-->