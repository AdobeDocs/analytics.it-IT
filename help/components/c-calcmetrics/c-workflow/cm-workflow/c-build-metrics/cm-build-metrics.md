---
description: Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare e rilasciare Dimension, metriche, segmenti e funzioni per creare metriche personalizzate basate sulla logica gerarchica del contenitore, sulle regole e sugli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o metriche calcolate avanzate complesse.
title: Creare metriche
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: c64b4199d93443b14e2012459a4d33fdd847eca1
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 10%

---

# Creare metriche

Adobe Analytics fornisce un’area di lavoro per trascinare e rilasciare dimensioni, metriche, segmenti e funzioni per creare metriche personalizzate in base alla logica gerarchica dei contenitori, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o complesse.

Puoi iniziare a creare una metrica calcolata in uno dei seguenti modi:

* In Analysis Workspace, apri un progetto, quindi seleziona **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
* In Analysis Workspace, apri un progetto, quindi seleziona la **Più** accanto al simbolo [!UICONTROL **Metriche**] nella barra a sinistra.
* In entrata [!DNL Analytics], vai a **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**, quindi seleziona **[!UICONTROL + Add]** nella parte superiore della pagina Metriche calcolate.

![](assets/cm_builder_ui.png)

## Campi e aree disponibili {#section_9382AEEBA4244DD6A9F6C1DD3F6D076B}

<table id="table_60A82936321047D1A335331BF83B0972"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Campo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Titolo </span> </td> 
   <td colname="col3"> <p>La denominazione della metrica è obbligatoria. Non puoi salvare la metrica a meno che non sia denominata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Descrizione </span> </td> 
   <td colname="col3"> <p>Fornisci una descrizione intuitiva per mostrare a cosa serve e distinguerla da altre simili. </p> <p>La descrizione viene visualizzata anche all’interno di un rapporto. È meglio NON inserire la formula nella descrizione, ma descrivere a cosa deve e non deve essere utilizzata questa metrica. La formula viene generata durante la creazione della metrica, sotto l’intestazione Riepilogo. Non è quindi necessario aggiungere la formula alla descrizione.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Formato </span> </td> 
   <td colname="col3"> <p>Le opzioni disponibili sono Decimale, Tempo, Percentuale e Valuta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Cifre decimali </span> </td> 
   <td colname="col3"> <p>Mostra il numero di posizioni decimali da visualizzare nel rapporto. Il numero massimo di cifre decimali che è possibile specificare è 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Mostra tendenza verso l'alto come... </span> </td> 
   <td colname="col3"> <p>Questa impostazione di polarità della metrica indica se Analytics deve considerare una tendenza verso l’alto nella metrica come buona (verde) o cattiva (rossa). Di conseguenza, il grafico del rapporto verrà visualizzato in verde o rosso quando si procede verso l’alto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Tag </span> </td> 
   <td colname="col3"> <p>L’assegnazione tag è un buon modo per organizzare le metriche. Tutti gli utenti possono creare tag e applicarne uno o più a una metrica. Tuttavia, puoi visualizzare solo i tag dei segmenti di tua proprietà o che sono stati condivisi con te. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili: 
     <ul id="ul_9A6CE5F179424687A39F2D5C1A953258"> 
      <li id="li_A8815F2D8D284874AD701A7B103D82A3">Tag basati sui <b>nomi dei team</b>, ad esempio Social Marketing e Mobile Marketing. </li> 
      <li id="li_A51A4515A541488E9D90296A955E9F4F">Tag del <b>progetto</b> (tag di analisi), ad esempio Analisi per pagina di ingresso. </li> 
      <li id="li_B4605470A7094026AC168420B64BBCC3">Tag di <b>categorie</b>: maschile, geografia. </li> 
      <li id="li_B6EAB0F2A96C41209C4EC97B9E64390B">Tag del <b>flusso di lavoro</b>: Da approvare, Curato per (una specifica unità aziendale) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Riepilogo </span> </td> 
   <td colname="col3"> <p>Il <span class="uicontrol"> Riepilogo </span> La formula viene aggiornata ogni volta che si apporta una modifica alla definizione della metrica. Questa formula viene visualizzata anche nella barra delle metriche a sinistra, quando passi il cursore su una metrica e fai clic su <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icona. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Definizione </span> </td> 
   <td colname="col3"> <p>È qui che puoi trascinare metriche/metriche calcolate, segmenti e/o funzioni per creare la metrica calcolata. </p> <p> 
     <ul id="ul_B13401A266354DC594C6176025DB61CB"> 
      <li id="li_01776C32C7C5440AA1F847096CBED92B">Se trascini una metrica calcolata, la relativa definizione di metrica verrà espansa automaticamente. </li> 
      <li id="li_A483D352522E4572AB43042473053359">È possibile nidificare le definizioni con i contenitori. Tuttavia, a differenza dei contenitori di segmenti, questi contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Operatore </span> </td> 
   <td colname="col3"> <p>Diviso per ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) è l'operatore predefinito e sono presenti gli operatori +, - e x. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Anteprima </span> </td> 
   <td colname="col3"> <p>Fornisce una lettura rapida su eventuali errori. L’anteprima copre gli ultimi 90 giorni. Questo è un modo per valutare inizialmente se hai selezionato i componenti giusti per la metrica. Un risultato imprevisto richiederebbe una seconda occhiata alla definizione della metrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Compatibilità dei prodotti </span> </td> 
   <td colname="col3"> <p>La compatibilità del prodotto mostra se la metrica è compatibile con <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html"  > Dati correnti </a>, con dati completamente elaborati o solo con rapporti sul canale di marketing (allocazione di primo contatto). <p>Nota: i dati correnti non supportano tutte le metriche. Le metriche che contengono segmenti o funzioni non sono compatibili con i dati correnti. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > Altro... </a> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Aggiungi </span> </td> 
   <td colname="col3"> <p>Per tutti i tipi di metriche calcolate, puoi aggiungere contenitori e numeri statici alla definizione. Per le metriche calcolate avanzate, puoi anche aggiungere segmenti e funzioni. </p> <p> 
     <ul id="ul_607C1B303F334062BC620317667DE490"> 
      <li id="li_53462789B8AF4F1AA9B45565D37CF22B">I contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. Pertanto, qualsiasi elemento in un contenitore verrà elaborato prima dell’operazione successiva. </li> 
      <li id="li_401A9E0D8B3B468990289DBF66A06F63">Trascinare un segmento in un contenitore segmenta tutto ciò che si trova in quel contenitore. (Solo metriche calcolate avanzate) </li> 
      <li id="li_F191B200D7A944F9ADC0573A9A82A6DA">Puoi impilare più segmenti in un contenitore. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Icona ingranaggio ( <span class="uicontrol"> Tipo di metrica </span>, <span class="uicontrol"> Attribuzione </span>) </td> 
   <td colname="col3"> <p>Selezionando l’icona a forma di ingranaggio accanto a una metrica puoi specificare <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > tipo di metrica e modelli di attribuzione </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> + Nuovo </span> </td> 
   <td colname="col3"> <p>Consente di creare un nuovo componente, ad esempio un nuovo segmento, che ti porta al <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > Generatore di segmenti </a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Componenti ricerca </p> </td> 
   <td colname="col3"> <p>Questa barra di ricerca consente di cercare dimensioni, metriche, segmenti (solo per metriche calcolate avanzate) e funzioni (solo per metriche calcolate avanzate). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco dei Dimension </p> </td> 
   <td colname="col3"> <p>Invece di uscire dal Generatore della metrica calcolata per creare un segmento semplice (nel Generatore di segmenti), ad esempio "Pagina = Home page", puoi trascinare la pagina e selezionare la pagina iniziale direttamente dal Generatore della metrica calcolata. </p> <p>Questo semplifica il flusso di lavoro per la creazione di metriche calcolate segmentate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco delle metriche </p> </td> 
   <td colname="col3"> <p>Le metriche sono disponibili in 3 categorie: </p> 
    <ul id="ul_7BF50F4964EF45858FBA1634FBFA45CF"> 
     <li id="li_90F2312927A6499CA1CE04F8FFC912CF">Metriche standard ( <img placement="inline"  src="assets/met_icon.png" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li> 
     <li id="li_A3F59083E79B4AC780D6F8CEDFFD20C9">Metriche calcolate ( <img placement="inline"  src="assets/calc_met_icon.png" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li> 
     <li id="li_8735E76637ED4C3F983731A66E04C93E">Modelli di metriche ( <img placement="inline"  src="assets/cm_template_icon.png" width="25px" id="image_D236601511CC4DD3828F223431E27E88" />) - in fondo all'elenco. </li> 
    </ul> <p>Quando passi il cursore su una metrica, puoi vedere l’icona Info a destra di essa: <img placement="inline"  src="assets/info.png" width="150px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Facendo clic su questa icona si ottengono le seguenti informazioni: </p> 
    <ul id="ul_DF35DDB9FBFA40C8A93FA0F2286A0BBE"> 
     <li id="li_4215AA9BF93F4C8B941002A7A4D2F50B">La formula di calcolo. </li> 
     <li id="li_6A8E39EB6DCE4377B0B594B6D4FC0294">Tendenza di anteprima della metrica. </li> 
     <li id="li_44C1595E4BE64ED69D1DB3BB6655ED55">Un’icona di modifica (matita) in alto a destra che ti porta al Generatore di metriche calcolate dove puoi modificare questa metrica calcolata. </li> 
    </ul> <p><img placement="break" align="center"  src="assets/info2.png" width="200px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco dei segmenti </p> </td> 
   <td colname="col3"> <p>Solo per metriche calcolate avanzate. In qualità di amministratore, questo elenco mostra tutti i segmenti creati nella società di accesso. Se non sei un utente amministratore, questo elenco mostra i segmenti che possiedi e quelli condivisi con te. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html"  > Altro... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco delle funzioni </p> </td> 
   <td colname="col3"> <p>(Solo per metriche calcolate avanzate) Le funzioni sono suddivise in due elenchi: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Base </a> (utilizzato più spesso) e <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Avanzate </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Selettore suite di rapporti </p> </td> 
   <td colname="col3"> <p>Consente di passare a una suite di rapporti diversa. </p> </td> 
  </tr> 
 </tbody> 
</table>
