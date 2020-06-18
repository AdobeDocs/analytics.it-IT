---
description: Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella.
title: Impostazioni riga
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: ht
source-git-commit: 5c2f2d098398927d8379f2eb9ea69ca9acbfd726

---


# Impostazioni riga

Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella.

In una tabella, puoi utilizzare anche le [azioni pulsante destro](/help/analyze/analysis-workspace/visualizations/freeform-table.md) per gestire le righe selezionate.

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
   <td colname="col1"> <p><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Confronto date</a> </p> </td> 
   <td colname="col2"> <p><b>Allinea le date di ogni colonna affinché inizino tutte sulla stessa riga. </b> </p> <p>Quando scegli di allineare le date, ad esempio in un confronto mese-su-mese tra ottobre e settembre 2016, la colonna a sinistra inizierà con il 1° ottobre e la colonna a destra inizierà con il 1° settembre: </p> <p><img placement="break"  src="assets/add-time-period-column3.png" width="500px" id="image_99398B13FEDA4715B8B818DF6093CA37" /> </p> <p>Disabilitata per impostazione predefinita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percentuali </p> </td> 
   <td colname="col2"> <p><b>Calcola percentuali per riga</b> </p> <p>Forza il calcolo delle percentuali delle celle di una riga, anziché di una colonna. Questo è utile in particolare per le percentuali di tendenza. L’opzione è attivata per impostazione predefinita quando si usa l’icona <span class="uicontrol">Visualizza</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totali colonna </p> </td> 
   <td colname="col2"> <p>Queste impostazioni vengono visualizzate solamente con <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md"  > righe manuali (statiche)</a> (quando hai selezionato un set finito di elementi) e non con righe dinamiche (quando rilasci una dimensione che mostra tutti gli elementi). <p>Nota: per righe manuali <i>metriche</i>, l’impostazione è disabilitata in quanto non avrebbe alcun senso sommare ulteriori metriche oltre alle righe correnti in una tabella. </p> </p> <p><b>Calcola i totali, sommando i valori attualmente presenti in ciascuna colonna (abilitata per impostazione predefinita):</b> </p> <p>Questa opzione consente di calcolare solo le righe presenti nella tabella (calcolo lato client). </p> <p><b>Calcola i totali sulla base di tutte le righe di ogni metrica (disabilitata per impostazione predefinita):</b> </p> <p>Questa opzione include tutti gli elementi di questa dimensione anche quelli non elencati nella tabella (calcolo lato server). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Breakdowns (Suddivisioni) </p> </td> 
   <td colname="col2"> <p><b>Suddivisione per posizione:</b> </p> <p>È possibile mostrare le suddivisioni in base a una posizione fissa in una tabella a forma libera. Ad esempio, puoi specificare di suddividere sempre le prime sette righe. </p> <p>(In precedenza, i valori elencati nella suddivisione erano “bloccati”. Ciò portava a una situazione in cui, ad esempio, se eseguivi una suddivisione di <span class="term">Data</span> per <span class="term">Pagina</span>, ottenevi un elenco delle prime 50 pagine per l’intervallo date selezionato. Se avessi salvato questo rapporto e lo avessi eseguito di nuovo un mese più tardi, le prime 50 pagine sarebbero probabilmente cambiate. Analysis Workspace utilizzava comunque i risultati della suddivisione originale e restituiva le stesse pagine, ma con il mese corrente come intervallo di date.) </p> <p>Per eseguire suddivisioni sulla base di una posizione fissa: </p> 
    <ol id="ol_A396A11566AA4F52BC3ABBC373CEF477"> 
     <li id="li_BDAB1E9A48D44944A4F7C31F1182B923">Suddividi alcune righe nella tua tabella. </li> 
     <li id="li_C5610437D3714CCEB9F3C771864B4336">Fai clic sull’icona Impostazioni (ingranaggio) accanto alla riga della tabella che desideri mettere in posizione fissa. </li> 
     <li id="li_675E429DC3B94201978166F9408D30B1">Spunta la casella di controllo accanto a <span class="uicontrol">Suddivisione per posizione</span>. </li> 
     <li id="li_E8A417D0D6D1438CAE825843BA0A7060">Modifica l’ordinamento o l’intervallo di date e osserva come ora le suddivisioni sono correlate alla posizione della riga e non alle righe a codifica fissa. </li> 
    </ol> <p>Disabilitata per impostazione predefinita. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Impostazione delle righe | Descrizione |
|--- |--- |
| Confronto date | Allinea le date di ogni colonna affinché inizino tutte sulla stessa riga.   Quando scegli di allineare le date, ad esempio in un confronto mese-su-mese tra ottobre e settembre 2016, la colonna a sinistra inizierà con il 1 ottobre e la colonna a destra inizierà con il 1 settembre.<br>Disabilitata per impostazione predefinita. |
| Percentuali | Calcola percentuali per riga Nelle tabelle a forma libera forza il calcolo delle percentuali delle celle di una riga, anziché di una colonna. Questo è utile in particolare per le percentuali di tendenza.<br>È attivata per impostazione predefinita quando si usa l’icona Visualizza. |
| Totali colonna | Queste impostazioni vengono visualizzate solamente con [ righe manuali (statiche)](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) (quando hai selezionato un set finito di elementi) e non con righe dinamiche (ad esempio, quando rilasci una dimensione che mostra tutti gli elementi).<ul><li>**[!UICONTROL Show sum of current rows as the total]** (Mostra somma delle righe selezionate come totale): mostra una somma lato client delle righe nella tabella, il che significa che il totale **non** deduplica metriche quali visite o visitatori.</li><li>**[!UICONTROL Show Grand Total]** (Mostra totale complessivo): mostra una somma lato server, il che significa che il totale deduplicherà le metriche quali visite o visitatori.</li></ul> |
| Suddivisioni | **[!UICONTROL Breakdown by position]** (Suddivisione per posizione): È possibile mostrare le suddivisioni in base a una posizione fissa in una tabella a forma libera. Ad esempio, puoi specificare di suddividere sempre le prime sette righe.<br>(In precedenza, i valori elencati nella suddivisione erano “bloccati”. Ciò portava a una situazione in cui, ad esempio, se eseguivi una suddivisione di Data per Pagina, ottenevi un elenco delle prime 50 pagine per l’intervallo date selezionato. Se avessi salvato questo rapporto e lo avessi eseguito di nuovo un mese più tardi, le prime 50 pagine sarebbero probabilmente cambiate. Analysis Workspace utilizzava comunque i risultati della suddivisione originale e restituiva le stesse pagine, ma con il mese corrente come intervallo di date.)<br>Per eseguire suddivisioni sulla base di una posizione fissa: 1. Suddividi alcune righe nella tua tabella. 2. Fai clic sull’icona Impostazioni (ingranaggio) accanto alla riga della tabella che desideri mettere in posizione fissa. 3. Spunta la casella di controllo accanto a Suddivisione per posizione. 4. Modifica l’ordinamento o l’intervallo di date e osserva come ora le suddivisioni sono correlate alla posizione della riga e non alle righe a codifica fissa.<br>Disabilitata per impostazione predefinita. |