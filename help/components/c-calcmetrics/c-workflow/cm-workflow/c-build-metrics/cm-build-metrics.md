---
description: Scopri il generatore di metriche calcolate, che fornisce un’area di lavoro per trascinare dimensioni, metriche, segmenti e funzioni e creare metriche personalizzate in base alla logica gerarchica dei contenitori, alle regole e agli operatori.
title: Creare metriche
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '1338'
ht-degree: 87%

---

# Generare metriche calcolate {#build-metrics}

Adobe Analytics fornisce un’area di lavoro per trascinare e rilasciare dimensioni, metriche, segmenti e funzioni per creare metriche personalizzate in base alla logica gerarchica dei contenitori, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o complesse.

Puoi utilizzare il generatore di metriche calcolate per creare o modificare le metriche calcolate. Quando vengono create in questo modo, le metriche calcolate sono disponibili nell’elenco dei componenti e possono quindi essere utilizzate nei progetti di tutta l’organizzazione. In alternativa, è possibile creare rapidamente una metrica calcolata disponibile solo per il progetto in cui è stata creata, nel modo descritto in [Creare metriche calcolate per un singolo progetto](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) in [Metriche](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

[Creare una metrica calcolata](../cm-workflow.md) descrive le diverse opzioni disponibili per creare una nuova metrica calcolata.

## Aree del generatore di metriche calcolate

La finestra di dialogo **[!UICONTROL Calculated metric builder]** viene utilizzata per creare nuove metriche calcolate o modificare quelle esistenti. La finestra di dialogo si chiama **[!UICONTROL New calculated metric]** o **[!UICONTROL Edit calculated metric]** per le metriche create o gestite dal gestore [[!UICONTROL Calculated metrics]](../cm-manager.md).

>[!BEGINTABS]

>[!TAB Generatore di metrica calcolata]

![Finestra dei dettagli della metrica calcolata con i campi e le opzioni descritti nella sezione successiva.](assets/calculated-metric-builder.png)

>[!TAB Crea o modifica metrica calcolata]

![Finestra dei dettagli della metrica calcolata con i campi e le opzioni descritti nella sezione successiva.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Specifica i dettagli seguenti (![Obbligatorio](/help/assets/icons/Required.svg) indica i dati obbligatori):

   | Elemento | Descrizione |
   | --- | --- |
   | **[!UICONTROL Report suite]** | Puoi selezionare la suite di rapporti per la metrica calcolata.  La metrica calcolata definita è disponibile nei progetti Workspace in base alla suite di rapporti selezionata. |
   | **[!UICONTROL Project-only metric]** | Nella parte superiore di questa finestra di dialogo, quando modifichi una metrica calcolata per un singolo progetto, viene visualizzata una casella di informazioni, come descritto in [Creare metriche calcolate per un singolo progetto](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). <p>Se desideri rendere disponibile questa metrica calcolata per tutti i progetti, seleziona l’opzione **[!UICONTROL Make this metric available to all your projects and add it to your component list]**.</p> |
   | **[!UICONTROL Title]** ![Obbligatorio](/help/assets/icons/Required.svg) | Assegna un nome alla metrica calcolata, ad esempio `Conversion Rate`. |
   | **[!UICONTROL Description]** | Fornisci una descrizione per il segmento, ad esempio `Calculated metric to define the conversion rate.` Non è necessario descrivere la formula per la metrica calcolata in quanto la formula è già disponibile automaticamente in [!UICONTROL Summary]. |
   | **[!UICONTROL Format]** | Seleziona un formato per la metrica calcolata: puoi selezionare tra **[!UICONTROL Decimal]**, **[!UICONTROL Time]**, **[!UICONTROL Percent]** e **[!UICONTROL Currency]**. |
   | **[!UICONTROL Decimal places]** | Specifica il numero di posizioni decimali per il formato selezionato. La scelta è possibile solo se il formato selezionato è Decimale, Valuta e Percentuale. |
   | **[!UICONTROL Show upward trend as]** | Specificare se una tendenza verso l&#39;alto della metrica calcolata viene visualizzata come ▲ **[!UICONTROL Good (Green)]** o come ▼ **[!UICONTROL Bad (Red)]**. |
   | **[!UICONTROL Currency]** | Specifica la valuta della metrica calcolata. La scelta è possibile solo se il formato selezionato è Valuta. |
   | **[!UICONTROL Tags]** | Organizza la metrica calcolata creando o applicando uno o più tag. Inizia a digitare per trovare i tag esistenti che puoi selezionare. Oppure premi **[!UICONTROL ENTER]** per aggiungere un nuovo tag. Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un tag. |
   | **[!UICONTROL Preview]** | L’anteprima copre gli ultimi 90 giorni ed è un modo per verificare se la metrica è stata definita correttamente. |
   | **[!UICONTROL Summary]** | Visualizza un riepilogo della definizione della metrica calcolata. <br/>Ad esempio: ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Total Orders]** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]**. |
   | **[!UICONTROL Definition]** ![Obbligatorio](/help/assets/icons/Required.svg) | Definisci il segmento utilizzando il [Generatore di definizioni](#definition-builder). |

1. Per verificare se la definizione della metrica calcolata è corretta, utilizza l’**[!UICONTROL Preview]** costantemente aggiornata dei risultati della metrica calcolata. **[!UICONTROL Preview]** copre gli ultimi 90 giorni e valuta continuamente la definizione della metrica calcolata.

   **[!UICONTROL Product compatibility]** indica la compatibilità della metrica calcolata con le funzionalità di Adobe Analytics. Per ulteriori informazioni, vedere [Compatibilità delle metriche](/help/components/c-calcmetrics/cm-compatibility.md).

1. Seleziona:
   * **[!UICONTROL Save]** per salvare la metrica calcolata.
   * **[!UICONTROL Save As]** per salvare una copia della metrica calcolata.
   * **[!UICONTROL Cancel]** per annullare le modifiche apportate a una metrica calcolata o per annullare la creazione di una nuova metrica calcolata.


## Generatore di definizioni

Il Generatore di definizioni consente di trascinare dimensioni, metriche, segmenti e funzioni per creare metriche personalizzate basate su logica gerarchica, regole e operatori del contenitore. In tale struttura, puoi utilizzare metriche standard, metriche definite da Adobe, metriche calcolate, segmenti, dimensioni e funzioni. Tutti questi componenti sono disponibili accedendo al pannello dei componenti del generatore di metriche calcolate. Puoi inoltre inserire operatori e contenitori nella definizione.

![Creare una metrica calcolata](assets/create-calculated-metric.gif)

Solo le metriche sono definite come singoli componenti nell’area **[!UICONTROL Definition]**. Tutti gli altri componenti sono definiti come contenitore, metriche di wrapping o altri contenitori. Per ulteriori informazioni, consulta [Contenitori](#containers).

### Metriche

Per aggiungere una metrica:

* Trascina un componente ![Eventi](/help/assets/icons/Event.svg) **[!UICONTROL Metrics]** dal pannello dei componenti in **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Puoi usare l’opzione ![Cerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare componenti specifici.

Quando utilizzi una metrica calcolata nell’ambito della definizione, la metrica calcolata viene espansa.

Per modificare una metrica:

1. Seleziona ![Impostazione](/help/assets/icons/Setting.svg) in un componente metrica nell’area **[!UICONTROL Definition]**.
1. Nella finestra di dialogo popup puoi definire il tipo di metrica e un modello di attribuzione. Consulta [Tipo di metrica e attribuzione](m-metric-type-alloc.md).

Per eliminare una metrica:

* Seleziona ![Chiudi](/help/assets/icons/Close.svg) nella metrica.

### Operatori

Gli operatori consentono di specificare l’operatore desiderato tra componenti o contenitori. Gli operatori vengono visualizzati automaticamente tra

* due o più metriche in un contenitore,
* due o più contenitori in un contenitore,
* una o più metriche e uno o più contenitori in un contenitore.

È possibile selezionare:

| Simbolo | Operatore |
|:---:|---|
| ![Dividi](/help/assets/icons/Divide.svg) | Dividi (predefinito) |
| ![Chiudi](/help/assets/icons/Close.svg) | Moltiplica |
| ![Rimuovi](/help/assets/icons/Remove.svg) | Sottrai |
| ![Aggiungi](/help/assets/icons/Add.svg) | Add |

### Numero statico

Puoi aggiungere un numero statico alla definizione della metrica calcolata. Per aggiungere un numero statico:

* Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** dall’interno di un contenitore.
* Seleziona **[!UICONTROL Static number]**. Viene visualizzato un contenitore di numeri statici.
* Seleziona [!UICONTROL *Fai clic per aggiungere un valore*] e digita un valore.


### Contenitori

Puoi aggiungere dimensioni, segmenti e funzioni come contenitori a una definizione di metrica calcolata. Puoi anche aggiungere un contenitore generico. I contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. Qualsiasi elemento all’interno di un contenitore viene elaborato prima del componente o del contenitore successivo.


#### Contenitore di segmenti

Utilizza il concetto di un contenitore di segmenti per creare una [metrica segmentata](metrics-with-segments.md). Puoi creare un contenitore di segmenti utilizzando un segmento o un segmento creato da una dimensione.

* Per aggiungere un contenitore di segmenti da una dimensione:

   1. Trascina un componente ![Dimensions](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensions]** dal pannello dei componenti in **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Puoi usare ![Ricerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare componenti specifici.
   1. Nel popup **[!UICONTROL Create Segment from Dimension]**, definisci la condizione per il segmento. Seleziona dall’elenco degli operatori un valore oppure immetti un valore. Ad esempio, **[!UICONTROL Month]** **[!UICONTROL equals]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
   1. Seleziona **[!UICONTROL Done]**. Un contenitore di segmenti viene aggiunto a **[!UICONTROL Definition]**.


* Per aggiungere un contenitore di segmenti da un segmento, puoi:

   * Trascinare un componente ![Segmentazione](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** dal pannello dei componenti in **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Puoi utilizzare ![Ricerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare segmenti specifici.
Un contenitore di segmenti viene aggiunto automaticamente a **[!UICONTROL Definition]**, utilizzando il nome del segmento.

   * Trascinare un componente ![Segmentazione](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segment]** dal pannello dei componenti in un contenitore generico. Il contenitore viene modificato in un contenitore di segmenti.

   * Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** dall’interno di un contenitore:

      1. Seleziona **[!UICONTROL Segment]**. Un contenitore di segmenti viene aggiunto a **[!UICONTROL Definition]**.
      1. Nel nuovo contenitore di segmenti, seleziona un segmento dal menu a discesa [!UICONTROL *Seleziona...*].

  >[!TIP]
  >
  >Puoi aggiungere più di un segmento a un contenitore.

  I segmenti nel contenitore prendono il nome dal componente del segmento. Ad esempio: ![Segmentazione](/help/assets/icons/Segmentation.svg) **[!UICONTROL Web sessions]**. Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare un popup con i dettagli sul segmento. Nel popup, seleziona ![Modifica](/help/assets/icons/Edit.svg) per modificare la definizione del segmento.

Per rimuovere un filtro da un contenitore:

* Seleziona ![Chiudi](/help/assets/icons/Close.svg) accanto al nome del segmento.

Per ulteriori dettagli ed esempi, vedi [Metriche segmentate](metrics-with-segments.md).

#### Contenitore funzione

Per aggiungere un contenitore funzione, puoi utilizzare:

* Trascina:

   1. Trascina un componente ![Function](/help/assets/icons/Effect.svg) **[!UICONTROL Functions]** dal pannello dei componenti in **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Puoi usare ![Ricerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare funzioni specifiche.
   1. Automaticamente un contenitore funzione viene aggiunto alla **[!UICONTROL Definition]** utilizzando il nome della funzione.

* Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** dall’interno di un contenitore:

   1. Seleziona **[!UICONTROL Function]**.
   1. Nel contenitore, selezionare una funzione dal menu a discesa [!UICONTROL *Seleziona...*].

Il contenitore funzione prende il nome dal componente funzione. Ad esempio: ![Function](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT (metric)]**. Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare un popup con ulteriori dettagli sulla funzione. Seleziona **[!UICONTROL Learn more]** per ulteriori informazioni sulla funzione.

Per informazioni dettagliate su come utilizzare le funzioni e quali funzioni sono disponibili per creare una metrica calcolata, consulta [Utilizzare le funzioni](cm-using-functions.md).


#### Contenitore generico

Per aggiungere un contenitore generico:

* Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** da un contenitore
* Seleziona **[!UICONTROL Container]**. Un nuovo contenitore generico vuoto viene aggiunto a **[!UICONTROL Definition]**. Puoi utilizzare un contenitore generico per nidificare o creare una gerarchia nella definizione della metrica calcolata.


#### Eliminare un contenitore

Per eliminare un contenitore, seleziona ![Close](/help/assets/icons/Close.svg) a livello di contenitore.

>[!MORELIKETHIS]
>
>[Usare le funzioni](cm-using-functions.md)
>>[Segmenti](/help/components/segmentation/seg-overview.md)
>


<!--

Adobe Analytics provides a canvas to drag and drop dimensions, metrics, segments, and functions to create custom metrics based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple or complex calculated metrics.

## Begin building a calculated metric

You can use the calculated metric builder to create or edit calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. Alternatively, you can quickly create a calculated metric that is available only for the project where it was created, as described in [Create calculated metrics for a single project](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

Access the calculated metric builder to begin creating a calculated metric that is available in the component list. 

1. Access the calculated metric builder in any of the follows ways:

   * In Analysis Workspace, open a project, then select **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
   * In Analysis Workspace, open a project, then select the **Plus** icon next to the [!UICONTROL **Metrics**] section in the left rail.
   * In [!DNL Adobe Analytics], go to **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**, then select **[!UICONTROL + Add]** at the top of the Calculated metrics page.

1. Continue with [Areas of the calculated metric builder](#areas-of-the-calculated-metrics-builder).

## Areas of the Calculated metrics builder

The following image and accompanying table explain some of the main areas and features of the Calculated metrics builder.

![](assets/cm_builder_ui.png)

| Location in image  | Name and function  |
|---|---|
| 1 | **Title:** Naming the metric is mandatory. You cannot save the metric unless it is named.  |
| 2 | **Description:** Give it a user-friendly description to show what it's used for and to distinguish it from similar ones. <p>The description also appears within a report. It's best NOT to put the formula into the description - instead, describe what this metric should and should not be used for. (The formula is generated as you build the metric, underneath the Summary heading. As a result, there is no need to add the formula to the description.) </p>  |
| 3 | **Format:** Choices include Decimal, Time, Percent, and Currency.  |
| 4 | **Decimal Places:** Shows how many decimal places will be shown in the report. The maximum number of decimal places you can specify is 10.  |
| 5| **Show Upward Trend As:** This metric polarity setting shows whether Analytics should consider an upward trend in the metric as good (green) or bad (red). As a result, the report's graph will show as green or red when it's going up.  |
| 6 | **Tags:** Tagging is a good way to organize metrics. All users can create tags and apply one or more tags to a metric. However, you can see tags only for those segments that you own or that have been shared with you. What kinds of tags should you create? Here are some suggestions for useful tags:<ul><li>**Team names**, such as Social Marketing, Mobile Marketing.</li><li>**Projects** (analysis tags), such as Entry-page analysis.</li><li>**Categories**, such as Women's; Geography.</li><li>**Workflows**, such as To be approved; Curated for (a specific business unit)</li></ul> |
| 7 | **Summary:** <p>The Summary formula updates anytime you make a change to the metric definition. This formula also shows up in the metrics rail on the left when you hover over a metric and click the <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icon. </p>  |
| 8 | **Definition:** This is where you drag in metrics/calculated metrics, segments, and/or functions to build the calculated metric. <ul><li>If you drag in a calculated metric, it will expand its metric definition automatically. </li> <li>You can nest definitions with containers. However, unlike segment containers, these containers function like a math expression and determine the order of operations. </li> </ul>  |
| 9 | **Operator:** Divided by ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) is the default operator, plus there are the +, -, and x operators. |
| 10 | **Preview:** Provides a quick read on any possible errors. The preview covers the last 90 days. This is a way of initially gauging whether you have selected the right components for your metric. An unexpected result would mean you need to take a second look at the metric definition.  |
| 11 | **Product compatibility:** Product compatibility shows you whether the metric is compatible with <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html"  > Current Data </a>, with Fully Processed Data, or only with Marketing Channel reports (first-touch allocation). <p>Note:  Current Data does not support all metrics. Metrics that contain segments or functions are not compatible with current data. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > More... </a> </p> </p>  |
| 12 | **Add:** For all types of calculated metrics, you can add containers and static numbers to the definition. For advanced calculated metrics, you can also add segments and functions. <ul><li>Containers function like a math expression and determine the order of operations. So anything in a container will get processed before the next operation.</li><li>Dragging a segment onto a container segments everything in that container. (Advanced calculated metrics only)</li><li>You can stack multiple segments in a container.</li></ul> |
| 13 | **Gear icon (Metric Type, Attribution):** Selecting the gear icon next to a metric lets you specify the <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > metric type and attribution models </a>. |
| 14 | **New:** Lets you create a new component, such as a new segment (which takes you to the <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > Segment Builder </a>.) |
| 15 | **Search Components:** This search bar lets you search for dimensions, metrics, segments (advanced calculated metrics only), and functions (advanced calculated metrics only). |
| 16 | **List of Dimensions:** Rather than leaving the Calculated Metric Builder in order to build a simple segment (in the Segment Builder), e.g. "Page = Homepage", you can drag in Page and select Homepage directly from the Calculated Metric Builder.<p>This results in a much more streamlined workflow for creating segmented calculated metrics.</p> |
| 17 | **List of Metrics:** Metrics come in 3 categories: <ul> <li>Standard metrics (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Calculated metrics ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Metrics templates ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) - at the bottom of the list. </li> </ul> <p>When you hover over a metric, you can see the Info icon to the right of it: <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Clicking this icon gives you the following information: </p><ul> <li>The formula of how it is calculated. </li><li>A preview trend of the metric. </li><li>An edit (pencil) icon <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> at the top right that will take you to the Calculated Metrics Builder where you can edit this calculated metric. </li></ul> |
| 18 | **List of Segments:** (Advanced calculated metrics only) As an Admin, this list shows all segments created in your login company. If you are a non-Admin user, this list shows segments you own and those shared with you. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html"  > More... </a> |
| 19 | **List of Functions:** (Advanced calculated metrics only) Functions are divided into two lists: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Basic </a> (used most often) and <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Advanced </a>. |
| 20 | **Report Suite selector:** Lets you switch to a different report suite. |

{style="table-layout:auto"}

-->
