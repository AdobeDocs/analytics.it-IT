---
description: Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare dimensioni, metriche, segmenti e funzioni e creare metriche personalizzate in base alla logica gerarchica del contenitore, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o metriche calcolate avanzate complesse.
title: Creare metriche
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: a1567366c9fad42b3836f43c681d5380e97b09f3
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 11%

---

# Creare metriche {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Compatibilità prodotto"
>abstract="Indica dove in Customer Journey Analytics può essere utilizzata la metrica calcolata, ad esempio in Analysis Workspace, Report Builder e così via. Alcune metriche calcolate non possono essere utilizzate con la sperimentazione."
>additional-url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Utilizzare le metriche calcolate nella sperimentazione"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="ID esterno"
>abstract="La modifica dell’ID esterno potrebbe influire sul modo in cui la metrica calcolata appare nelle origini esterne, come gli strumenti di business intelligence"

<!-- markdownlint-enable MD034 -->

Adobe Analytics fornisce un’area di lavoro per trascinare e rilasciare dimensioni, metriche, segmenti e funzioni per creare metriche personalizzate in base alla logica gerarchica dei contenitori, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o complesse.

## Inizio della creazione di una metrica calcolata

Puoi utilizzare il generatore di metriche calcolate per creare o modificare le metriche calcolate. Quando vengono create in questo modo, le metriche calcolate sono disponibili nell’elenco dei componenti e possono quindi essere utilizzate nei progetti di tutta l’organizzazione. In alternativa, è possibile creare rapidamente una metrica calcolata disponibile solo per il progetto in cui è stata creata, come descritto in [Creare metriche calcolate per un singolo progetto](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) in [Metriche](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

Accedi al generatore di metriche calcolate per iniziare a creare una metrica calcolata disponibile nell’elenco dei componenti.

1. Accedi al generatore di metriche calcolate in uno dei seguenti modi:

   * In Analysis Workspace, apri un progetto, quindi seleziona **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
   * In Analysis Workspace, apri un progetto, quindi seleziona l&#39;icona **Plus** accanto alla sezione [!UICONTROL **Metriche**] nella barra a sinistra.
   * In [!DNL Adobe Analytics], vai a **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**, quindi seleziona **[!UICONTROL + Add]** nella parte superiore della pagina Metriche calcolate.

1. Continua con [Aree del generatore di metriche calcolate](#areas-of-the-calculated-metrics-builder).

## Aree del generatore di metriche calcolate

L’immagine seguente e la tabella che l’accompagna illustrano alcune delle aree e delle funzioni principali del generatore di metriche calcolate.

![](assets/cm_builder_ui.png)

| Posizione nell’immagine | Nome e funzione |
|---|---|
| 1 | **Titolo:** La denominazione della metrica è obbligatoria. Non puoi salvare la metrica a meno che non sia denominata. |
| 2 | **Descrizione:** Fornisci una descrizione intuitiva per mostrare a cosa serve e distinguerla da altre simili. <p>La descrizione viene visualizzata anche all’interno di un rapporto. È meglio NON inserire la formula nella descrizione, ma descrivere a cosa deve e non deve essere utilizzata questa metrica. La formula viene generata durante la creazione della metrica, sotto l’intestazione Riepilogo. Di conseguenza, non è necessario aggiungere la formula alla descrizione.) </p> |
| 3 | **Formato:** Le opzioni disponibili sono Decimale, Ora, Percentuale e Valuta. |
| 4 | **Cifre decimali:** mostra il numero di cifre decimali che verranno visualizzate nel report. Il numero massimo di cifre decimali che è possibile specificare è 10. |
| 5 | **Mostra tendenza verso l&#39;alto come:** Questa impostazione di polarità della metrica indica se Analytics deve considerare una tendenza verso l&#39;alto nella metrica come buona (verde) o cattiva (rossa). Di conseguenza, il grafico del rapporto verrà visualizzato in verde o rosso quando si procede verso l’alto. |
| 6 | **Tag:** L&#39;assegnazione di tag è un modo efficace per organizzare le metriche. Tutti gli utenti possono creare tag e applicarne uno o più a una metrica. Tuttavia, puoi visualizzare solo i tag dei segmenti di tua proprietà o che sono stati condivisi con te. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:<ul><li>**Nomi team**, ad esempio Social Marketing e Mobile Marketing.</li><li>**Progetti** (tag di analisi), ad esempio Analisi per pagina di ingresso.</li><li>**Categorie**, ad esempio Donne; Geografia.</li><li>**Flussi di lavoro**, ad esempio Da approvare; Curato per (una specifica unità aziendale)</li></ul> |
| 7 | **Riepilogo:** <p>La formula di riepilogo viene aggiornata ogni volta che si apporta una modifica alla definizione della metrica. Questa formula viene visualizzata anche nella barra delle metriche a sinistra, quando passi il cursore su una metrica e fai clic su Icona <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />. </p> |
| 8 | **Definizione:** Trascinare metriche/metriche calcolate, segmenti e/o funzioni per generare la metrica calcolata. <ul><li>Se trascini una metrica calcolata, la relativa definizione di metrica verrà espansa automaticamente. </li> <li>È possibile nidificare le definizioni con i contenitori. Tuttavia, a differenza dei contenitori di segmenti, questi contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. </li> </ul> |
| 9 | **Operatore:** diviso per ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) è l&#39;operatore predefinito, oltre agli operatori +, - e x. |
| 10 | **Anteprima:** Fornisce una lettura rapida di eventuali errori. L’anteprima copre gli ultimi 90 giorni. Questo è un modo per valutare inizialmente se hai selezionato i componenti giusti per la metrica. Un risultato imprevisto richiederebbe una seconda occhiata alla definizione della metrica. |
| 11 | **Compatibilità prodotto:** La compatibilità prodotto indica se la metrica è compatibile con <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=it"  > dati correnti </a>, con dati completamente elaborati o solo con rapporti Canale di marketing (allocazione di primo contatto). <p>Nota: i dati correnti non supportano tutte le metriche. Le metriche che contengono segmenti o funzioni non sono compatibili con i dati correnti. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > Altro... </a> </p> </p> |
| 12 | **Aggiungi:** Per tutti i tipi di metriche calcolate, è possibile aggiungere contenitori e numeri statici alla definizione. Per le metriche calcolate avanzate, puoi anche aggiungere segmenti e funzioni. <ul><li>I contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. Pertanto, qualsiasi elemento in un contenitore verrà elaborato prima dell’operazione successiva.</li><li>Trascinare un segmento in un contenitore segmenta tutto ciò che si trova in quel contenitore. (Solo metriche calcolate avanzate)</li><li>Puoi impilare più segmenti in un contenitore.</li></ul> |
| 13 | **Icona ingranaggio (tipo di metrica, attribuzione):** La selezione dell&#39;icona ingranaggio accanto a una metrica consente di specificare il tipo di metrica <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > e i modelli di attribuzione </a>. |
| 14 | **Nuovo:** consente di creare un nuovo componente, ad esempio un nuovo segmento (che porta al Generatore di segmenti <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > </a>). |
| 15 | **Componenti di ricerca:** Questa barra di ricerca consente di cercare dimensioni, metriche, segmenti (solo metriche calcolate avanzate) e funzioni (solo metriche calcolate avanzate). |
| 16 | **Elenco dimensioni:** Anziché uscire dal Generatore di metriche calcolate per creare un segmento semplice (nel Generatore di segmenti), ad esempio &quot;Pagina = Home page&quot;, è possibile trascinare la pagina e selezionare la home page direttamente dal Generatore di metriche calcolate.<p>Questo semplifica il flusso di lavoro per la creazione di metriche calcolate segmentate.</p> |
| 17 | **Elenco delle metriche:** Le metriche sono disponibili in 3 categorie: <ul> <li>Metriche standard (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Metriche calcolate ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Modelli di metriche ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) - in fondo all&#39;elenco. </li> </ul> <p>Quando passi il cursore su una metrica, puoi vedere l’icona Info a destra di essa: <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Facendo clic su questa icona si ottengono le seguenti informazioni: </p><ul> <li>La formula di calcolo. </li><li>Tendenza di anteprima della metrica. </li><li>Icona di modifica (matita) <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> in alto a destra che ti porterà al Generatore di metriche calcolate dove puoi modificare questa metrica calcolata. </li></ul> |
| 18 | **Elenco segmenti:** (solo metriche calcolate avanzate) In qualità di amministratore, questo elenco mostra tutti i segmenti creati nella società di accesso. Se non sei un utente amministratore, questo elenco mostra i segmenti che possiedi e quelli condivisi con te. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html?lang=it"  > Altro... </a> |
| 19 | **Elenco funzioni:** (solo metriche calcolate avanzate) Le funzioni sono suddivise in due elenchi: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Base </a> (utilizzata più spesso) e <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Avanzata </a>. |
| 20 | **Selettore suite di rapporti:** consente di passare a una suite di rapporti diversa. |

{style="table-layout:auto"}
