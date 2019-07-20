---
description: Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella.
seo-description: Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella.
seo-title: Impostazioni riga
title: Impostazioni riga
uuid: f 30 c 31 d 5-1 fd 4-4 b 93-94 c 3-ca 441099 fe 2 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Impostazioni riga

Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella.

In una tabella, puoi utilizzare anche le [azioni pulsante destro](../../../../analyze/analysis-workspace/visualizations/freeform-table.md#concept_0D2E24FCCBAF4194AA941448860E422F) per gestire le righe selezionate.

Per accedere alle impostazioni di riga, fai clic sull’icona Impostazioni accanto a una dimensione, a un segmento, a una metrica, a un periodo di tempo o a un’interruzione in ognuna di queste:

![](assets/row-settings.png)

<table id="table_7ACE6413DB1F40349ED2860020F92E55"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione delle righe </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="../../../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764" format="dita" scope="local"> Confronto date</a> </p> </td> 
   <td colname="col2"> <p><b>Allinea le date di ogni colonna affinché inizino tutte sulla stessa riga. </b> </p> <p>Quando scegli di allineare le date, ad esempio in un confronto mese-su-mese tra ottobre e settembre 2016, la colonna a sinistra inizierà con il 1 ottobre e la colonna a destra inizierà con il 1 settembre: </p> <p><img placement="break"  src="assets/add-time-period-column3.png" width="500px" id="image_99398B13FEDA4715B8B818DF6093CA37" /> </p> <p>Disabilitata per impostazione predefinita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percentuali </p> </td> 
   <td colname="col2"> <p><b>Calcola percentuali per riga</b> </p> <p>Forza il calcolo delle percentuali delle celle di una riga, anziché di una colonna. Questo è utile in particolare per le percentuali di tendenza. L’opzione è attivata per impostazione predefinita quando si usa l’icona <span class="uicontrol">Visualizza</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totali colonna </p> </td> 
   <td colname="col2"> <p>Queste impostazioni vengono visualizzate solamente con <a href="../../../../analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md#concept_C50E7DFBC0504C72A973123192F487D8" format="dita" scope="local"> righe manuali (statiche)</a> (quando hai selezionato un set finito di elementi) e non con righe dinamiche (quando rilasci una dimensione che mostra tutti gli elementi). <p>Nota: per righe manuali <i>metriche</i>, l’impostazione è disabilitata in quanto non avrebbe alcun senso sommare ulteriori metriche oltre alle righe correnti in una tabella. </p> </p> <p><b>Calcola i totali, sommando i valori attualmente presenti in ciascuna colonna (abilitata per impostazione predefinita):</b> </p> <p>Questa opzione consente di calcolare solo le righe presenti nella tabella (calcolo lato client). </p> <p><b>Calcola i totali sulla base di tutte le righe di ogni metrica (disabilitata per impostazione predefinita):</b> </p> <p>Questa opzione include tutti gli elementi di questa dimensione anche quelli non elencati nella tabella (calcolo lato server). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Suddivisioni </p> </td> 
   <td colname="col2"> <p><b>Suddivisione per posizione:</b> </p> <p>È possibile mostrare le suddivisioni in base a una posizione fissa in una tabella a forma libera. Ad esempio, puoi specificare di suddividere sempre le prime sette righe. </p> <p>(In precedenza, i valori elencati nella suddivisione erano bloccati. Di conseguenza, suddividendo ad esempio <span class="term"> Data</span> per <span class="term"> pagina</span>: è stato visualizzato un elenco delle prime 50 pagine per l'intervallo di date selezionato. Se avessi salvato questo rapporto e lo avessi eseguito di nuovo un mese più tardi, le prime 50 pagine sarebbero probabilmente cambiate. Analysis Workspace utilizzava comunque i risultati della suddivisione originale e restituiva le stesse pagine, ma con il mese corrente come intervallo di date.) </p> <p>Per eseguire suddivisioni sulla base di una posizione fissa: </p> 
    <ol id="ol_A396A11566AA4F52BC3ABBC373CEF477"> 
     <li id="li_BDAB1E9A48D44944A4F7C31F1182B923">Suddividi alcune delle righe nella tua tabella. </li> 
     <li id="li_C5610437D3714CCEB9F3C771864B4336">Fai clic sull’icona Impostazioni (ingranaggio) accanto alla riga della tabella che desideri mettere in posizione fissa. </li> 
     <li id="li_675E429DC3B94201978166F9408D30B1">Spunta la casella di controllo accanto a <span class="uicontrol">Suddivisione per posizione</span>. </li> 
     <li id="li_E8A417D0D6D1438CAE825843BA0A7060">Modifica l’ordinamento o l’intervallo di date e osserva come ora le suddivisioni sono correlate alla posizione della riga e non alle righe a codifica fissa. </li> 
    </ol> <p>Disabilitata per impostazione predefinita. </p> </td> 
  </tr> 
 </tbody> 
</table>

