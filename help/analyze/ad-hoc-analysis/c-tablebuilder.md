---
description: Usa il Generatore tabella per creare un report con qualsiasi configurazione di metriche, dimensioni e segmenti. Ad esempio, puoi aggiungere più metriche al Generatore tabella, quindi applicarle a tutte contemporaneamente. È possibile applicare elementi dai riquadri degli strumenti come righe e suddivisioni o come colonne, e ruotare con facilità la tabella per una vista differente. Dopo aver creato la tabella, potete interagire direttamente con la tabella di dati risultante per un'ulteriore analisi. Tenere presente che generare una tabella dati da Generatore tabella esegue una query e crea una nuova tabella di dati.
seo-description: Usa il Generatore tabella per creare un report con qualsiasi configurazione di metriche, dimensioni e segmenti. Ad esempio, puoi aggiungere più metriche al Generatore tabella, quindi applicarle a tutte contemporaneamente. È possibile applicare elementi dai riquadri degli strumenti come righe e suddivisioni o come colonne, e ruotare con facilità la tabella per una vista differente. Dopo aver creato la tabella, potete interagire direttamente con la tabella di dati risultante per un'ulteriore analisi. Tenere presente che generare una tabella dati da Generatore tabella esegue una query e crea una nuova tabella di dati.
seo-title: Generatore tabella
title: Generatore tabella
uuid: d 5 dbd 05 e -9 ebd -4571-b 3 a 5-3856 c 28 b 65 f 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Generatore tabella

Usa il Generatore tabella per creare un report con qualsiasi configurazione di metriche, dimensioni e segmenti. Ad esempio, puoi aggiungere più metriche al Generatore tabella, quindi applicarle a tutte contemporaneamente. È possibile applicare elementi dai riquadri degli strumenti come righe e suddivisioni o come colonne, e ruotare con facilità la tabella per una vista differente. Dopo aver creato la tabella, potete interagire direttamente con la tabella di dati risultante per un'ulteriore analisi. Tenere presente che generare una tabella dati da Generatore tabella esegue una query e crea una nuova tabella di dati.

## Table Builder {#concept_574FEDC73B244101935D3C86C39DB70F}

Usa il Generatore tabella per creare un report con qualsiasi configurazione di metriche, dimensioni e segmenti. Ad esempio, puoi aggiungere più metriche al Generatore tabella, quindi applicarle a tutte contemporaneamente. È possibile applicare elementi dai riquadri degli strumenti come righe e suddivisioni o come colonne, e ruotare con facilità la tabella per una vista differente. Dopo aver creato la tabella, potete interagire direttamente con la tabella di dati risultante per un'ulteriore analisi. Tenere presente che generare una tabella dati da Generatore tabella esegue una query e crea una nuova tabella di dati.

The [!UICONTROL Table Builder] is not available for certain pathing reports like [!UICONTROL Site Analysis], [!UICONTROL Fallout], [!UICONTROL Flow] and [!UICONTROL Virtual Focus].

## Table Builder Descriptions {#section_4B7B96546B864142AB91DF3996918590}

<table id="table_C11D78E62DEF48A78B50EFB8669817BC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Righe/suddivisioni</span> </td> 
   <td colname="col2"> <p>Crea righe e suddivisioni dagli elementi aggiunti. The first item you drag to <span class="wintitle"> Rows / Breakdowns</span> becomes the left column in the data table, or the parent item in a breakdown. L'aggiunta di elementi successivi crea suddivisioni. </p> <p>Ad esempio, se aggiungi dimensioni Pagina e Città, il rapporto suddivide la pagina per città. Configurate il numero di righe e suddivisioni da visualizzare per ogni elemento, utilizzando i seguenti menu: </p> 
    <ul id="ul_702F215DFB814398B8F1879EDFEC103F"> 
     <li id="li_95C4DF2B33524C94BBD2E07397393300"> <span class="uicontrol"> Mostra</span> e <span class="uicontrol"> suddivisione</span>: Consente di specificare il numero di elementi e suddivisioni da visualizzare. </li> 
     <li id="li_D594C7F31A094D1EA1A070B80794E006"> <span class="uicontrol"> Predefinito</span>: Utilizza le impostazioni configurate in <span class="wintitle"> Proprietà suddivisione</span>. </li> 
    </ul> <p>Puoi anche configurare un elenco di valori fisso in modo, ad esempio, suddividere una metrica in base a più metriche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Proprietà suddivisione</span> </td> 
   <td colname="col2"> <p><img placement="inline"  src="assets/Settings_Illustrative.png" id="image_C46860621CF94E88AF592B8660F28E57"> </img> </p> <p>Consente di specificare le impostazioni predefinite per il numero di righe e analisi da visualizzare, in base all'ordine in cui si aggiungono gli elementi. Puoi specificare il numero totale di risultati per pagina e il numero di righe da suddividere. </p> <p>Settings you make in the <span class="wintitle"> Table Builder</span> override the default settings in the <span class="wintitle"> Breakdown Properties</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Modifica elementi</span> </td> 
   <td colname="col2"> <p><img  src="assets/Edit_Buttcon.png" id="image_E44BCC4B0BFF453D8564047E3DA2501A"> </img> </p> <p>Scegliete un elenco di elementi dimensionali per creare un elenco fisso per le suddivisioni. Quando si aggiungono elementi a questo elenco, questi diventano permanenti in un rapporto salvato e non saranno compressi quando si apre un rapporto salvato o pianificato. </p> <p>See <a href="../../analyze/ad-hoc-analysis/c-reports-configure.md#task_29BEE0AF09DA4625B9B44BAB77D7C841" format="dita" scope="local"> Break Down Table Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Colonne</span> </td> 
   <td colname="col2"> <p>Consente di creare colonne con elementi provenienti da dimensioni, segmenti e metriche. Potete anche ruotare le colonne utilizzando l'icona freccia, per ruotare gli assi X e Y. </p> <p> <span class="uicontrol"> Mostra</span>: Consente di limitare il numero di colonne generate nella tabella di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Riepilogo</span> </td> 
   <td colname="col2"> <p>Mostra il layout strutturale del report per sapere il numero di righe e colonne che verranno create. The summary reflects the configuration specified in the <span class="uicontrol"> Rows / Breakdowns</span> and <span class="uicontrol"> Columns</span> groups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Sostituisci tabella</span> </td> 
   <td colname="col2"> <p>Builds (and overrides) the existing table, based on your <span class="wintitle"> Table Builder</span> configuration. </p> <p>Note: Clicking <span class="uicontrol"> Replace Table</span> reruns the report and overrides the data in the table grid. If you add items to the table grid, the correlation between the table and the <span class="wintitle"> Table Builder</span> is no longer valid. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Attenzione </td> 
   <td colname="col2"> <p><img id="image_619E1068C6084D41853DA3DD6B85DFC9"  src="assets/AlertRed_Illustrative.png" placement="inline" /> </p> <p>Indicates that the <span class="wintitle"> Table Builder</span>'s configuration will not return data, or that no metrics are selected. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Generate a report from the Table Builder {#task_B04801AC9848485C93DF02E96C9A9902}

Steps that describe how to use the [!UICONTROL Table Builder].

<!-- 

t_table_builder.xml

 -->

1. To access the [!UICONTROL Table Builder], run a supported report, then click **[!UICONTROL Table Builder]**.
1. Drag items (dimensions, metrics, segments) from the tool panes to the [!UICONTROL Table Builder].
1. Configurate gli elementi come righe, suddivisioni e colonne.
1. Click **[!UICONTROL Replace Table]** to generate the report.

   Clicking **[!UICONTROL Replace Table]** runs a new query and creates a new data table. Le modifiche manuali alla tabella dei dettagli non vengono riportate in Generatore tabella.

