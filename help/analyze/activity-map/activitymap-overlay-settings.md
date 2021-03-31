---
description: Il pannello Impostazioni di Activity Map consente di modificare le impostazioni e le proprietà di tutti i tipi di visualizzazioni di sovrapposizione.
title: Configurare le impostazioni di Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 6%

---


# Configurare le impostazioni di Activity Map

Il pannello Impostazioni di Activity Map consente di modificare le impostazioni e le proprietà di tutti i tipi di visualizzazioni di sovrapposizione.

Per accedere al pannello Impostazioni di Activity Map , fai clic sull’icona a forma di ingranaggio nella barra degli strumenti di Activity Map.

Il pannello Impostazioni visualizza contenuti diversi in base alla modalità di applicazione selezionata. La scheda Altro contiene le impostazioni generali.

| Standard | **[!UICONTROL Gradient]** o  **[!UICONTROL Bubble]** sovrapposizioni |
|---|---|
| Live | **[!UICONTROL Gainers & Losers]**,  **[!UICONTROL Gradient]**,  **[!UICONTROL Bubble]** sovrapposizioni |
| Altro | Selezione di suite di rapporti e lingua |

## Impostazioni per sovrapposizione modalità standard {#section_24DB95376E1A448494ECF3F57743FC19}

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
   <td colname="col2"> <span class="uicontrol"> Sovrapposizioni etichette con</span> </td> 
   <td colname="col3"> 
    <ul id="ul_13AD02789F2D4904A35215A8FA230F3E"> 
     <li id="li_8DB71636D2074C69B0D94D3FB0CAFE28"> <b>Nessuna etichetta</b>: applicabile solo alla sovrapposizione sfumatura. In questo caso, il colore della sovrapposizione trasmetterà un senso per la classificazione del collegamento </li> 
     <li id="li_39C98D7EA9514C1D8731B9D21C0E73A6"> <b>Valore</b>: il totale della metrica grezza per quel collegamento </li> 
     <li id="li_A5F583E45BCD4F2399398F9DCC7FE382"> <b>Percentuale</b>: percentuale della metrica per questo collegamento nella metrica totale per la pagina. </li> 
     <li id="li_E4BF7D3B863E4B6C8E737CF29ADA9D67"> <b>Classificazione</b>: classificazione di questo collegamento tra tutti i collegamenti presenti nella pagina di cui è stato effettuato il rendering </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Dimensione font etichetta</span> </td> 
   <td colname="col3"> Consente di aumentare o diminuire la dimensione del font dell’etichetta di sovrapposizione, utilizzando un cursore, per una migliore leggibilità. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Visualizzazione</span> </td> 
   <td colname="col3">Seleziona <span class="uicontrol"> Top</span>, <span class="uicontrol"> Bottom</span> o <span class="uicontrol"> All Links</span> per visualizzare nella sovrapposizione. Se selezionate Superiore o Inferiore, dovete anche selezionare il numero di collegamenti da visualizzare. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Nascondere le sovrapposizioni per i collegamenti che non hanno ricevuto hit.</span> </td> 
   <td colname="col3"> Questa casella di controllo consente di nascondere le sovrapposizioni per i collegamenti che non hanno ricevuto hit, per ridurre il disordine nell’interfaccia. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Colore sfumatura / Colore bolla</span> </td> 
   <td colname="col3">Seleziona un intervallo di colori per visualizzare le classificazioni dei collegamenti di sovrapposizione per le visualizzazioni di sovrapposizione <span class="uicontrol"> Sfumatura</span> o <span class="uicontrol"> Bolla</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Sfumatura colore basata su</span> </td> 
   <td colname="col3"> 
    <ul id="ul_1B5C2A44A9EB465D8B8E9AD91AF79D69"> 
     <li id="li_C983CB68B90B492BB0774254292B5961"> <span class="uicontrol"> Top 30 Classificazioni</span>: L’intensità del colore viene normalizzata per i primi 30 valori. </li> 
     <li id="li_1E83431C8C734AB0BC82B5A66AED1189"> <span class="uicontrol"> Valore</span> metrico assoluto: L’intensità del colore è una funzione del valore della metrica assoluta. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Trasparenza sfumatura</span> </td> 
   <td colname="col3">Seleziona il livello di trasparenza per le sovrapposizioni sfumatura. <p>Questa impostazione non influisce sulle sovrapposizioni a bolle. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Impostazioni per le sovrapposizioni in modalità live {#section_D30F6E62FB5D404090B588F396A460AF}

![](assets/settings_live.png)

| Impostazioni | Descrizione |
|---|---|
| **[!UICONTROL Display Top]** | Seleziona il numero di collegamenti da visualizzare (o tutti) e il **[!UICONTROL Gainers]** o **[!UICONTROL Losers]** (o entrambi) da visualizzare come sovrapposizioni. |
| **[!UICONTROL Exclude bottom (%)]** | Selezionare questa opzione per eliminare i collegamenti Gainers-Losers con dati sparsi. Filtrare la percentuale inferiore di modifiche del collegamento per visualizzare solo i collegamenti con dati sufficienti a mostrare guadagni o perdite rilevanti. La percentuale viene calcolata in base al numero di collegamenti presenti nella pagina. Ad esempio, filtrando il 10% inferiore di un elenco di 200 collegamenti si escluderanno gli ultimi 20 collegamenti. |
| **[!UICONTROL Auto Update Data]** | Consente di decidere se i dati di Analytics visualizzati nell’interfaccia devono essere aggiornati automaticamente al momento del calcolo di un nuovo periodo. |
| **[!UICONTROL Auto Update Period]** | Quando questa opzione è selezionata, aggiorna la pagina Web con ogni nuovo recupero di dati in modo che i collegamenti presenti nella pagina possano essere sincronizzati più strettamente con i dati raccolti. |

## Altre impostazioni {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

<table id="table_0F560236F8844FA0928CBB9C50D5ABEF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Suite di rapporti </td> 
   <td colname="col2"> <p>L’elenco delle suite di rapporti accessibili non è più limitato alle suite di rapporti definite nel tag della pagina web. Ora puoi sostituire la suite di rapporti selezionata (corrispondente a uno dei tag nella pagina) con un’altra suite di rapporti. La nuova suite di rapporti non deve necessariamente essere collegata a un tag sulla pagina. Se modifichi la suite di rapporti selezionata nelle impostazioni di Activity Map, il processo <span class="uicontrol"> Salva</span> comporterà l’aggiornamento di tutti i rapporti di Analytics interessati. </p> <p> <p>Importante: Le suite di rapporti virtuali non sono compatibili con la modalità Live, ma solo con la modalità Standard. Se siete in modalità Live per una suite di rapporti standard, ma selezionate una suite di rapporti virtuali in questa finestra di dialogo, una volta fatto clic su <span class="uicontrol"> OK</span> qui, verrà visualizzata la modalità Standard. </p> </p> <p>Inoltre, il controllo Calendario verrà reinizializzato in modo che corrisponda al tipo di calendario della suite di rapporti (gregoriano, retail, personalizzato...). </p> </td> 
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

