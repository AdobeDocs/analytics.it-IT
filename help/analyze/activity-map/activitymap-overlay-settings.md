---
description: Il pannello Impostazioni mappa dell'attività consente di modificare le impostazioni e le proprietà per tutti i tipi di visualizzazioni delle sovrapposizioni.
seo-description: Il pannello Impostazioni mappa dell'attività consente di modificare le impostazioni e le proprietà per tutti i tipi di visualizzazioni delle sovrapposizioni.
seo-title: Configurare le impostazioni Activity Map
solution: Analytics
title: Configurare le impostazioni Activity Map
topic: Activity map
uuid: 42 a 0309 e -3 efc -4506-989 b -09 b 6 fe 419423
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configurare le impostazioni Activity Map

Il pannello Impostazioni mappa dell'attività consente di modificare le impostazioni e le proprietà per tutti i tipi di visualizzazioni delle sovrapposizioni.

Accedete al pannello Impostazioni mappa dell'attività a cui accedete facendo clic sull'icona a forma di ingranaggio nella barra degli strumenti Activity Map (Mappa dell'attività).

Il pannello Impostazioni visualizza un contenuto diverso in base alla modalità applicazione selezionata. La scheda Altro contiene le impostazioni generali.

| Standard | **[!UICONTROL Gradient]** o **[!UICONTROL Bubble]** sovrapposizioni |
|---|---|
| Live | **[!UICONTROL Gainers & Losers]****[!UICONTROL Gradient]****[!UICONTROL Bubble]** , sovrapposizioni |
| Altre | Selezione delle suite di rapporti e selezione lingua |

## Settings for standard mode overlay {#section_24DB95376E1A448494ECF3F57743FC19}

![](assets/settings_standard.png)

<table id="table_0244107DE6D142F2A1DA4882E0ED9826"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Impostazioni </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Etichette etichette con</span> </td> 
   <td colname="col3"> 
    <ul id="ul_13AD02789F2D4904A35215A8FA230F3E"> 
     <li id="li_8DB71636D2074C69B0D94D3FB0CAFE28"> <b>Nessuna etichetta</b>: applicabile solo alla sovrapposizione Sfumatura. In questo caso, il colore della sovrapposizione comunica un senso per la classificazione del collegamento. </li> 
     <li id="li_39C98D7EA9514C1D8731B9D21C0E73A6"> <b>Valore</b>: il totale della metrica non elaborato per il collegamento </li> 
     <li id="li_A5F583E45BCD4F2399398F9DCC7FE382"> <b>Percentuale</b>: percentuale della metrica per il collegamento sulla metrica totale della pagina. </li> 
     <li id="li_E4BF7D3B863E4B6C8E737CF29ADA9D67"> <b>Classificazione</b>: classifica di questo collegamento per tutti i collegamenti presenti nella pagina sottoposta a rendering </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Etichetta font etichette</span> </td> 
   <td colname="col3"> Consente di aumentare o diminuire le dimensioni del font etichette dell'etichetta utilizzando un cursore, per una migliore leggibilità. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Visualizzazione</span> </td> 
   <td colname="col3">Select <span class="uicontrol"> Top</span>, <span class="uicontrol"> Bottom</span>, or <span class="uicontrol"> All Links</span> to display in the overlay. Se selezionate In alto o In basso, dovete anche selezionare il numero di collegamenti da visualizzare. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Nascondi sovrapposizioni per collegamenti che non hanno ricevuto hit.</span> </td> 
   <td colname="col3"> Questa casella di controllo consente di nascondere le sovrapposizioni per i collegamenti che non hanno ricevuto hit, per ridurre ingombro nell'interfaccia. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Colore sfumatura/Colore bolle</span> </td> 
   <td colname="col3">Select among a range of colors to display overlay link rankings for <span class="uicontrol"> Gradient</span> or <span class="uicontrol"> Bubble</span> overlay visualizations. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Sfumatura colori basata su</span> </td> 
   <td colname="col3"> 
    <ul id="ul_1B5C2A44A9EB465D8B8E9AD91AF79D69"> 
     <li id="li_C983CB68B90B492BB0774254292B5961"> <span class="uicontrol"> Primi 30 classifica: L'intensità del colore è normalizzata per i primi 30 valori.</span> </li> 
     <li id="li_1E83431C8C734AB0BC82B5A66AED1189"> <span class="uicontrol"> Valore metrica assoluta</span>: L'intensità del colore è una funzione del valore della metrica assoluta. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Trasparenza sfumatura</span> </td> 
   <td colname="col3">Selezionate il livello di trasparenza per le sovrapposizioni Sfumatura. <p>Questa impostazione non influisce sulle sovrapposizioni Bolle. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Settings for live mode overlays {#section_D30F6E62FB5D404090B588F396A460AF}

![](assets/settings_live.png)

| Impostazioni | Descrizione |
|---|---|
| **[!UICONTROL Display Top]** | Select number of links to display (or all) and the **[!UICONTROL Gainers]** or **[!UICONTROL Losers]** (or both) to display as overlays. |
| **[!UICONTROL Exclude bottom (%)]** | Selezionate questa opzione per eliminare i collegamenti Gainers-Losers con dati sparse. Filtra la percentuale inferiore di modifiche del collegamento per visualizzare solo i collegamenti con dati sufficienti per visualizzare guadagni o perdite rilevanti. La percentuale viene calcolata in base al numero di collegamenti nella pagina. Ad esempio, filtrando la parte inferiore del 10% di un elenco di 200 collegamenti si eliminano gli ultimi 20 collegamenti. |
| **[!UICONTROL Auto Update Data]** | Consente di decidere se i dati di Analytics visualizzati nell'interfaccia devono essere aggiornati automaticamente quando viene calcolato un nuovo periodo. |
| **[!UICONTROL Auto Update Period]** | Se questa opzione è selezionata, aggiorna la pagina Web con ogni nuovo recupero dati, in modo che i collegamenti nella pagina possano essere sincronizzati più da vicino con i dati raccolti. |

## Other settings {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

<table id="table_0F560236F8844FA0928CBB9C50D5ABEF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Suite di rapporti </td> 
   <td colname="col2"> <p>L'elenco delle suite di rapporti a cui è stato accesso non è più limitato alle suite di rapporti definite nel tag della pagina Web. Ora puoi sostituire la suite di rapporti selezionata (corrispondente a uno dei tag della pagina) con un'altra suite di rapporti. La nuova suite di rapporti non deve necessariamente essere collegata a un tag sulla pagina. If you change the selected report suite in the Activity Map Settings, the <span class="uicontrol"> Save</span> process will cause all affected Analytics reports to be refreshed. </p> <p> <p>Importante: Le suite di rapporti virtuali non sono compatibili con la modalità Live, solo con la modalità Standard. If you are in Live Mode for a Standard Report Suite, but select a Virtual Report Suite in this dialog, once you click <span class="uicontrol"> OK</span> here, the Standard Mode will be displayed. </p> </p> <p>Inoltre, il controllo Calendario verrà riinizializzato in modo che corrisponda al tipo di calendario della suite di rapporti (Gregoriano, Vendita al dettaglio, personalizzato…). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lingua </td> 
   <td colname="col2"> La selezione corrisponde alle lingue offerte per Adobe Analytics. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni </td> 
   <td colname="col2"> Indica il nome e il numero di versione dell'applicazione. </td> 
  </tr> 
 </tbody> 
</table>

