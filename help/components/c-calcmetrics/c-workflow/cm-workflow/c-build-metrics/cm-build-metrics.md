---
description: Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare e rilasciare Dimension, metriche, segmenti e funzioni per creare metriche personalizzate basate sulla logica gerarchica del contenitore, sulle regole e sugli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o metriche calcolate avanzate complesse.
title: Creare metriche
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: a6b7622562ced9d28229e094f027c8d0ee79532b
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 7%

---

# Creare metriche

Adobe Analytics fornisce un’area di lavoro per trascinare e rilasciare dimensioni, metriche, segmenti e funzioni per creare metriche personalizzate in base alla logica gerarchica dei contenitori, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o complesse.

## Inizio della creazione di una metrica calcolata

Puoi iniziare a creare una metrica calcolata in uno dei seguenti modi:

* In Analysis Workspace, apri un progetto, quindi seleziona **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
* In Analysis Workspace, apri un progetto, quindi seleziona la **Più** accanto al simbolo [!UICONTROL **Metriche**] nella barra a sinistra.
* In entrata [!DNL Analytics], vai a **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**, quindi seleziona **[!UICONTROL + Add]** nella parte superiore della pagina Metriche calcolate.

## Aree del generatore di metriche calcolate

L’immagine seguente e la tabella che l’accompagna illustrano alcune delle aree e delle funzioni principali di Gestione metriche calcolate.

![](assets/cm_builder_ui.png)

| Posizione nell’immagine | Nome e funzione |
|---|---|
| 1 | **Titolo:** La denominazione della metrica è obbligatoria. Non puoi salvare la metrica a meno che non sia denominata. |
| 2 | **Descrizione:** Fornisci una descrizione intuitiva per mostrare a cosa serve e distinguerla da altre simili. <p>La descrizione viene visualizzata anche all’interno di un rapporto. È meglio NON inserire la formula nella descrizione, ma descrivere a cosa deve e non deve essere utilizzata questa metrica. La formula viene generata durante la creazione della metrica, sotto l’intestazione Riepilogo. Non è quindi necessario aggiungere la formula alla descrizione.) </p> |
| 3 | **Formato:** Le opzioni disponibili sono Decimale, Tempo, Percentuale e Valuta. |
| 4 | **Cifre decimali:** Mostra il numero di posizioni decimali da visualizzare nel rapporto. Il numero massimo di cifre decimali che è possibile specificare è 10. |
| 5 | **Mostra tendenza verso l&#39;alto come:** Questa impostazione di polarità della metrica indica se Analytics deve considerare una tendenza verso l’alto nella metrica come buona (verde) o cattiva (rossa). Di conseguenza, il grafico del rapporto verrà visualizzato in verde o rosso quando si procede verso l’alto. |
| 6 | **Tag:** L’assegnazione tag è un buon modo per organizzare le metriche. Tutti gli utenti possono creare tag e applicarne uno o più a una metrica. Tuttavia, puoi visualizzare solo i tag dei segmenti di tua proprietà o che sono stati condivisi con te. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:<ul><li>**Nomi team**, ad esempio Social Marketing e Mobile Marketing.</li><li>**Progetti** (tag di analisi), ad esempio Analisi per pagina di ingresso.</li><li>**Categorie**, ad esempio Donne; Geografia.</li><li>**Flussi di lavoro**, come Da approvare; Curato per (una specifica unità aziendale)</li></ul> |
| 7 | **Riepilogo:** <p>La formula di riepilogo viene aggiornata ogni volta che si apporta una modifica alla definizione della metrica. Questa formula viene visualizzata anche nella barra delle metriche a sinistra, quando passi il cursore su una metrica e fai clic su <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icona. </p> |
| 8 | **Definizione:** È qui che puoi trascinare metriche/metriche calcolate, segmenti e/o funzioni per creare la metrica calcolata. <ul><li>Se trascini una metrica calcolata, la relativa definizione di metrica verrà espansa automaticamente. </li> <li>È possibile nidificare le definizioni con i contenitori. Tuttavia, a differenza dei contenitori di segmenti, questi contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. </li> </ul> |
| 9 | **Operatore:** Diviso per ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) è l&#39;operatore predefinito e sono presenti gli operatori +, - e x. |
| 10 | **Anteprima:** Fornisce una lettura rapida su eventuali errori. L’anteprima copre gli ultimi 90 giorni. Questo è un modo per valutare inizialmente se hai selezionato i componenti giusti per la metrica. Un risultato imprevisto richiederebbe una seconda occhiata alla definizione della metrica. |
| 11 | **Compatibilità del prodotto:** <p>La compatibilità del prodotto mostra se la metrica è compatibile con <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html"  > Dati correnti </a>, con dati completamente elaborati o solo con rapporti sul canale di marketing (allocazione di primo contatto). <p>Nota: i dati correnti non supportano tutte le metriche. Le metriche che contengono segmenti o funzioni non sono compatibili con i dati correnti. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > Altro... </a> </p> </p> |
| 12 | **Aggiungi:** Per tutti i tipi di metriche calcolate, puoi aggiungere contenitori e numeri statici alla definizione. Per le metriche calcolate avanzate, puoi anche aggiungere segmenti e funzioni. <ul><li>I contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. Pertanto, qualsiasi elemento in un contenitore verrà elaborato prima dell’operazione successiva.</li><li>Trascinare un segmento in un contenitore segmenta tutto ciò che si trova in quel contenitore. (Solo metriche calcolate avanzate)</li><li>Puoi impilare più segmenti in un contenitore.</li></ul> |
| 13 | **Icona ingranaggio (tipo di metrica, attribuzione):** Selezionando l’icona a forma di ingranaggio accanto a una metrica puoi specificare <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > tipo di metrica e modelli di attribuzione </a>. |
| 14 | **Nuovo:** Consente di creare un nuovo componente, ad esempio un nuovo segmento, che ti porta al <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > Generatore di segmenti </a>.) |
| 15 | **Componenti di ricerca:** Questa barra di ricerca consente di cercare dimensioni, metriche, segmenti (solo per metriche calcolate avanzate) e funzioni (solo per metriche calcolate avanzate). |
| 16 | **Elenco dei Dimension:** Invece di uscire dal Generatore della metrica calcolata per creare un segmento semplice (nel Generatore di segmenti), ad esempio &quot;Pagina = Home page&quot;, puoi trascinare la pagina e selezionare la pagina iniziale direttamente dal Generatore della metrica calcolata.<p>Questo semplifica il flusso di lavoro per la creazione di metriche calcolate segmentate.</p> |
| 17 | **Elenco delle metriche:** Le metriche sono disponibili in 3 categorie: <ul> <li>Metriche standard (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Metriche calcolate ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Modelli di metriche ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) - in fondo all&#39;elenco. </li> </ul> <p>Quando passi il cursore su una metrica, puoi vedere l’icona Info a destra di essa: <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" /> (Autenticazione): Facendo clic su questa icona si ottengono le seguenti informazioni: </p><ul> <li>La formula di calcolo. </li><li>Tendenza di anteprima della metrica. </li><li>Icona di modifica (matita) <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> in alto a destra, per passare al Generatore di metriche calcolate, in cui è possibile modificare la metrica calcolata. </li></ul> |
| 18 | **Elenco dei segmenti:** Solo per metriche calcolate avanzate. In qualità di amministratore, questo elenco mostra tutti i segmenti creati nella società di accesso. Se non sei un utente amministratore, questo elenco mostra i segmenti che possiedi e quelli condivisi con te. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html"  > Altro... </a> |
| 19 | **Elenco delle funzioni:** (Solo per metriche calcolate avanzate) Le funzioni sono suddivise in due elenchi: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Base </a> (utilizzato più spesso) e <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Avanzate </a>. |
| 20 | **Selettore suite di rapporti:** Consente di passare a una suite di rapporti diversa. |

{style="table-layout:auto"}
