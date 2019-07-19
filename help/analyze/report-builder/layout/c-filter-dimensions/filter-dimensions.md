---
description: Potete filtrare le dimensioni aggiunte alla griglia Etichette riga. I filtri limitano i dati restituiti dalle richieste e possono essere applicati mediante i layout Pivot o Personalizzato. Quando configurate il filtro della dimensione dal layout pivot, potete anche specificare il numero di voci della cella.
seo-description: Potete filtrare le dimensioni aggiunte alla griglia Etichette riga. I filtri limitano i dati restituiti dalle richieste e possono essere applicati mediante i layout Pivot o Personalizzato. Quando configurate il filtro della dimensione dal layout pivot, potete anche specificare il numero di voci della cella.
seo-title: Panoramica delle dimensioni filtro
solution: Analytics
title: Panoramica delle dimensioni filtro
topic: Generatore di report
uuid: c 54 d 5 add-f 278-476 d -8 f 14-73 f 1 c 2 e 37671
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Panoramica delle dimensioni filtro

Potete filtrare le dimensioni aggiunte alla griglia Etichette riga. I filtri limitano i dati restituiti dalle richieste e possono essere applicati mediante i layout Pivot o Personalizzato. Quando configurate il filtro della dimensione dal layout pivot, potete anche specificare il numero di voci della cella.

Il modulo di filtro selezionato è popolato in base all'elemento e alle metriche selezionate nella richiesta del generatore di report.

## Define filter - values and special characters {#section_15840216A4044C40974945FAA435AD93}

Information about filters in the **[!UICONTROL Most Popular Filter]** &gt; **[!UICONTROL Define Filter]** panel.

![](assets/define_filter.png)

Nelle tabelle seguenti sono riportati esempi e informazioni sui filtri:

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filtro </th> 
   <th colname="col02" class="entry"> Descrizione </th> 
   <th colname="col2" class="entry"> Esempio  Filtro </th> 
   <th colname="col3" class="entry"> Risultati corrispondenza </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Contiene tutti i termini </p> </td> 
   <td colname="col02"> <p>Contiene tutti i valori delimitati dallo spazio in qualsiasi ordine. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> a b c</span>and <span class="term"> b a c</span>, and so on. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contiene qualsiasi termine </p> </td> 
   <td colname="col02"> <p>Contiene almeno uno dei filtri (delimitati da spazio). </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> A1</span>, <span class="term"> B2</span>, <span class="term"> C3</span>, but not <span class="term"> D4</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contiene la frase </p> </td> 
   <td colname="col02"> <p>Contiene il filtro di ricerca ed eventualmente altri termini. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> abc</span> and <span class="term"> abc def</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Non contiene alcun termine </p> </td> 
   <td colname="col02"> <p>Restituisce tutto a meno che non contenga un valore immesso. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> d e f</span> but not <span class="term"> c d e f</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Non contiene la frase </p> </td> 
   <td colname="col02"> <p>Restituisce tutto ciò che non contiene la frase. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Excludes <span class="term"> abc</span>, <span class="term"> abc def</span> and matches <span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>È uguale a </p> </td> 
   <td colname="col02"> <p>Restituisce una corrispondenza esatta. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> viene restituito e niente altro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>È diverso da </p> </td> 
   <td colname="col02"> <p>Restituisce tutto ciò che non corrisponde esattamente alla voce. </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>Does not match <span class="term"> a</span>. </p> <p>Matches <span class="term"> a b c</span>. </p> <p>Matches <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inizia con </p> </td> 
   <td colname="col02"> <p>Restituisce i risultati che iniziano con un valore specifico. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> abcd</span> but not <span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Termina con </p> </td> 
   <td colname="col02"> <p>Restituisce risultati che terminano con il valore specifico. </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> wxyz</span> but not <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avanzato (caratteri speciali) </p> </td> 
   <td colname="col02"> <p>Consente di creare caratteri regex: </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>" ^ Home * Page $ " | sport </p> </td> 
   <td colname="col3"> <p> This defines a filter that starts with <span class="term"> Home</span>, and then looks for zero or more characters, and then ends with <span class="term"> Page</span>. </p> <p>Also, any page with <span class="term"> sports</span> in it. </p> <p>Alcuni esempi corrispondono: </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">Homepage </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Pagina principale e (altri caratteri) Pagina </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Sport amatoriali </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">Pagina sportiva </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">sport </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz sport abc </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_8BBB06C8860745DEA41B39673699DC0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caratteri speciali </th> 
   <th colname="col2" class="entry"> Finalità </th> 
   <th colname="col3" class="entry"> Note </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> " " </td> 
   <td colname="col2"> È uguale a </td> 
   <td colname="col3"> <p>Non viene visualizzata in sequenza, a meno che non sia associata a un altro preventivo. For example, <span class="term"> 17" Display</span> is not a phrase. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> Carattere jolly </td> 
   <td colname="col3"> <p>Come l'asterisco utilizzato in un'espressione regolare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ^ </td> 
   <td colname="col2"> Inizia con </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> $ </td> 
   <td colname="col2"> Termina con </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> Not </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> Oppure </td> 
   <td colname="col3"> <p>Supported only in the <span class="term"> Advanced (special characters)</span> filter. </p> </td> 
  </tr> 
 </tbody> 
</table>