---
description: Calculated Metrics Builder (Generatore di metriche calcolate) fornisce un quadro per trascinare Dimension, metriche, segmenti e funzioni per creare metriche personalizzate in base alla logica, alle regole e agli operatori della gerarchia dei contenitori. Questo strumento di sviluppo integrato consente di creare e salvare semplici metriche calcolate o metriche calcolate avanzate complesse.
title: Creare metriche
uuid: 3f51e911-cafa-4af4-90dd-5a4cb42bf0a7
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 7%

---


# Creare metriche

Calculated Metrics Builder (Generatore di metriche calcolate) fornisce un quadro per trascinare Dimension, metriche, segmenti e funzioni per creare metriche personalizzate in base alla logica, alle regole e agli operatori della gerarchia dei contenitori. Questo strumento di sviluppo integrato consente di creare e salvare semplici metriche calcolate o metriche calcolate avanzate complesse.

Esistono diversi modi per accedere al Generatore di metriche calcolate:

* In  Analysis Workspace, aprite un progetto e fate clic su **[!UICONTROL + New]** > **[!UICONTROL Create Metric]** .
* In [!DNL Analytics], andate a **[!UICONTROL Components]** > **[!UICONTROL Calculated Metrics]**.

* Fare clic **[!UICONTROL + Add]** nella parte superiore del Gestore [della metrica](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)calcolata oppure

* Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, apri un rapporto e fai clic sull&#39;icona Metriche ![](assets/metrics_icon.png) per visualizzare la barra Metriche, quindi fai clic su **[!UICONTROL Add]**.

![](assets/cm_builder_ui.png)

## Componenti interfaccia {#section_9382AEEBA4244DD6A9F6C1DD3F6D076B}

<table id="table_60A82936321047D1A335331BF83B0972"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Campo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Title </span> </td> 
   <td colname="col3"> <p>Denominare la metrica è obbligatorio. Non puoi salvare la metrica a meno che non abbia un nome. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Descrizione </span> </td> 
   <td colname="col3"> <p>Fornire una descrizione semplice per mostrare il tipo di utilizzo e distinguerlo da quelli simili. </p> <p>La descrizione viene visualizzata anche all'interno di un rapporto. È meglio NON inserire la formula nella descrizione - invece, descrivere per cosa questa metrica dovrebbe e non dovrebbe essere utilizzata. (La formula viene generata durante la creazione della metrica, sotto l'intestazione Riepilogo. Di conseguenza, non è necessario aggiungere la formula alla descrizione.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Formato </span> </td> 
   <td colname="col3"> <p>Le scelte includono Decimale, Tempo, Percentuale e Valuta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Posti decimali </span> </td> 
   <td colname="col3"> <p>Mostra il numero di posizioni decimali da visualizzare nel rapporto. Il numero massimo di posizioni decimali che è possibile specificare è 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Mostra tendenza verso l'alto come... </span> </td> 
   <td colname="col3"> <p>Questa impostazione di polarità della metrica indica se Analytics deve considerare una tendenza al rialzo nella metrica buona (verde) o cattiva (rossa). Di conseguenza, il grafico del rapporto sarà visualizzato in verde o in rosso quando si alza. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Tag </span> </td> 
   <td colname="col3"> <p>L’assegnazione di tag è un buon modo per organizzare le metriche. Tutti gli utenti possono creare tag e applicare uno o più tag a una metrica. Tuttavia, potete visualizzare i tag solo per i segmenti che possedete o che sono stati condivisi con voi. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili: 
     <ul id="ul_9A6CE5F179424687A39F2D5C1A953258"> 
      <li id="li_A8815F2D8D284874AD701A7B103D82A3">Tags based on <b>team names</b>, such as Social Marketing, Mobile Marketing. </li> 
      <li id="li_A51A4515A541488E9D90296A955E9F4F"><b>Tag del progetto (tag di analisi), ad esempio Analisi per pagina di ingresso.</b> </li> 
      <li id="li_B4605470A7094026AC168420B64BBCC3"><b>Tag di categorie: maschile; geografia.</b> </li> 
      <li id="li_B6EAB0F2A96C41209C4EC97B9E64390B"><b>Tag del flusso di lavoro: Da approvare; Curato per (una specifica unità aziendale).</b> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Riepilogo </span> </td> 
   <td colname="col3"> <p>La formula <span class="uicontrol"> Riepilogo </span> viene aggiornata ogni volta che si apporta una modifica alla definizione della metrica. Questa formula viene visualizzata anche nella barra delle metriche a sinistra quando passi il puntatore del mouse su una metrica e fai clic sull' <img placement="inline"  src="assets/i_icon.png" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icona. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Definizione </span> </td> 
   <td colname="col3"> <p>Qui puoi trascinare metriche/metriche calcolate, segmenti e/o funzioni per creare la metrica calcolata. </p> <p> 
     <ul id="ul_B13401A266354DC594C6176025DB61CB"> 
      <li id="li_01776C32C7C5440AA1F847096CBED92B">Se trascinate in una metrica calcolata, la definizione della metrica viene automaticamente espansa. </li> 
      <li id="li_A483D352522E4572AB43042473053359">È possibile nidificare le definizioni con i contenitori. Tuttavia, a differenza dei contenitori dei segmenti, questi contenitori funzionano come un'espressione matematica e determinano l'ordine delle operazioni. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Operatore </span> </td> 
   <td colname="col3"> <p>Diviso da ( <img placement="inline"  src="assets/divided_icon.png" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) è l'operatore predefinito, più vi sono gli operatori +, - e x. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Anteprima </span> </td> 
   <td colname="col3"> <p>Fornisce una lettura rapida di eventuali errori. L’anteprima copre gli ultimi 90 giorni. Questo è un modo per verificare inizialmente se avete selezionato i componenti giusti per la metrica. Un risultato inatteso comporterebbe la necessità di rivedere la definizione della metrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Compatibilità prodotto </span> </td> 
   <td colname="col3"> <p>La compatibilità del prodotto mostra se la metrica è compatibile con i dati <a href="https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html"  > correnti </a>, con i dati elaborati completamente o solo con i rapporti sul canale di marketing (allocazione tramite primo tocco). <p>Nota:  Dati correnti non supporta tutte le metriche. Le metriche che contengono segmenti o funzioni non sono compatibili con i dati correnti. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > Altro... </a> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Add </span> </td> 
   <td colname="col3"> <p>Per tutti i tipi di metriche calcolate, puoi aggiungere contenitori e numeri statici alla definizione. Per le metriche calcolate avanzate, puoi anche aggiungere segmenti e funzioni. </p> <p> 
     <ul id="ul_607C1B303F334062BC620317667DE490"> 
      <li id="li_53462789B8AF4F1AA9B45565D37CF22B">I contenitori funzionano come un'espressione matematica e determinano l'ordine delle operazioni. Pertanto, tutto ciò che si trova in un contenitore viene elaborato prima dell'operazione successiva. </li> 
      <li id="li_401A9E0D8B3B468990289DBF66A06F63">Trascinate un segmento su un contenitore per segmentare tutti gli elementi presenti in tale contenitore. (solo metriche calcolate avanzate) </li> 
      <li id="li_F191B200D7A944F9ADC0573A9A82A6DA">Puoi impilare più segmenti in un contenitore. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Icona ingranaggio ( <span class="uicontrol"> Tipo metrica </span>, <span class="uicontrol"> Attribuzione </span>) </td> 
   <td colname="col3"> <p>Selezionando l'icona a forma di ingranaggio accanto a una metrica puoi specificare il tipo di <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > metrica e i modelli di attribuzione </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> + Nuovo </span> </td> 
   <td colname="col3"> <p>Consente di creare un nuovo componente, ad esempio un nuovo segmento (che porta al Generatore di <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > segmenti </a>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Componenti di ricerca </p> </td> 
   <td colname="col3"> <p>Questa barra di ricerca consente di cercare dimensioni, metriche, segmenti (solo metriche calcolate avanzate) e funzioni (solo metriche calcolate avanzate). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco di Dimension </p> </td> 
   <td colname="col3"> <p>Anziché uscire dal Generatore di metriche calcolate per creare un segmento semplice (nel Generatore di segmenti), ad esempio "Page = Homepage", puoi trascinare in Page e selezionare Homepage direttamente dal Calculated Metric Builder. </p> <p>Questo semplifica il flusso di lavoro per la creazione di metriche calcolate segmentate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco delle metriche </p> </td> 
   <td colname="col3"> <p>Le metriche sono suddivise in 3 categorie: </p> 
    <ul id="ul_7BF50F4964EF45858FBA1634FBFA45CF"> 
     <li id="li_90F2312927A6499CA1CE04F8FFC912CF">Metriche standard ( <img placement="inline"  src="assets/met_icon.png" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li> 
     <li id="li_A3F59083E79B4AC780D6F8CEDFFD20C9">Metriche calcolate ( <img placement="inline"  src="assets/calc_met_icon.png" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li> 
     <li id="li_8735E76637ED4C3F983731A66E04C93E">Modelli di metriche ( <img placement="inline"  src="assets/cm_template_icon.png" width="25px" id="image_D236601511CC4DD3828F223431E27E88" />) - in fondo all’elenco. </li> 
    </ul> <p>Quando passi il puntatore del mouse su una metrica, puoi vedere l’icona Informazioni a destra: <img placement="inline"  src="assets/info.png" width="150px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Facendo clic su questa icona potete ottenere le seguenti informazioni: </p> 
    <ul id="ul_DF35DDB9FBFA40C8A93FA0F2286A0BBE"> 
     <li id="li_4215AA9BF93F4C8B941002A7A4D2F50B">La formula di calcolo. </li> 
     <li id="li_6A8E39EB6DCE4377B0B594B6D4FC0294">Una tendenza di anteprima della metrica. </li> 
     <li id="li_44C1595E4BE64ED69D1DB3BB6655ED55">Un'icona di modifica (matita) in alto a destra che ti porterà al Generatore di metriche calcolate dove puoi modificare questa metrica calcolata. </li> 
    </ul> <p><img placement="break" align="center"  src="assets/info2.png" width="200px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco dei segmenti </p> </td> 
   <td colname="col3"> <p>(Solo metriche calcolate avanzate) In qualità di Amministratore, questo elenco mostra tutti i segmenti creati nella società di accesso. Se sei un utente non amministratore, questo elenco mostra i segmenti che possiedi e quelli condivisi con te. <a href="https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-rights.html"  > Altro... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco delle funzioni </p> </td> 
   <td colname="col3"> <p>(Solo metriche calcolate avanzate) Le funzioni sono suddivise in due elenchi: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Base </a> (utilizzato più spesso) e <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Advanced </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Selettore suite di rapporti </p> </td> 
   <td colname="col3"> <p>Consente di passare a un'altra suite di rapporti. </p> </td> 
  </tr> 
 </tbody> 
</table>

