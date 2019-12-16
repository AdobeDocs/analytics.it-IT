---
description: È possibile filtrare le dimensioni aggiunte alla griglia Etichette righe. I filtri restringono i dati restituiti dalle richieste e possono essere applicati dai layout pivot o personalizzati. Quando si configura il filtro delle dimensioni dal layout pivot, è possibile specificare anche il numero di voci dalla cella.
title: Panoramica delle dimensioni filtro
topic: Report builder
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Panoramica delle dimensioni filtro

È possibile filtrare le dimensioni aggiunte alla griglia Etichette righe. I filtri restringono i dati restituiti dalle richieste e possono essere applicati dai layout pivot o personalizzati. Quando si configura il filtro delle dimensioni dal layout pivot, è possibile specificare anche il numero di voci dalla cella.

Il modulo filtro selezionato viene popolato in base all’elemento e alla metrica selezionati nella richiesta del generatore di report.

## Definire il filtro - valori e caratteri speciali {#section_15840216A4044C40974945FAA435AD93}

Informazioni sui filtri nel **[!UICONTROL Most Popular Filter]** &gt; **[!UICONTROL Define Filter]** pannello.

![](assets/define_filter.png)

Le tabelle seguenti contengono esempi e informazioni sui filtri:

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filtro </th> 
   <th colname="col02" class="entry"> Descrizione </th> 
   <th colname="col2" class="entry"> Esempio di filtro </th> 
   <th colname="col3" class="entry"> Risultati corrispondenza </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Contiene tutti i termini </p> </td> 
   <td colname="col02"> <p>Contiene ogni valore delimitato da spazi in qualsiasi ordine. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Corrisponde <span class="term"> a b</span>cand <span class="term"> b a c</span>, e così via. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contiene qualsiasi termine </p> </td> 
   <td colname="col02"> <p>Contiene almeno uno dei filtri (delimitato da spazio). </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>Corrisponde <span class="term"> A1</span>, <span class="term"> B2</span>, <span class="term"> C3</span>, ma non <span class="term"> D4</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contiene la frase </p> </td> 
   <td colname="col02"> <p>Contiene il filtro di ricerca ed eventualmente altri termini. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Corrisponde <span class="term"> abc</span> e <span class="term"> abc def</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Non contiene alcun termine </p> </td> 
   <td colname="col02"> <p>Restituisce tutto, a meno che non contenga un valore immesso. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Corrisponde <span class="term"> d e f</span> ma non <span class="term"> c d e f</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Non contiene la frase </p> </td> 
   <td colname="col02"> <p>Restituisce tutto ciò che non contiene la frase. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Esclude <span class="term"> abc</span>, <span class="term"> abc def</span> e corrisponde a <span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>È uguale a </p> </td> 
   <td colname="col02"> <p>Restituisce una corrispondenza esatta. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> viene restituito e nient'altro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>È diverso da </p> </td> 
   <td colname="col02"> <p>Restituisce qualsiasi elemento che non corrisponda esattamente alla voce. </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>Non corrisponde a <span class="term"> una</span>. </p> <p>Corrisponde <span class="term"> a b c</span>. </p> <p>Corrisponde a <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inizia con </p> </td> 
   <td colname="col02"> <p>Restituisce i risultati che iniziano con un valore specifico. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Corrisponde <span class="term"> abcd</span> ma non <span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Termina con </p> </td> 
   <td colname="col02"> <p>Restituisce i risultati che terminano con il valore specifico. </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>Corrisponde <span class="term"> wxyz</span> ma non <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avanzate (caratteri speciali) </p> </td> 
   <td colname="col02"> <p>Consente di inserire caratteri regolari: </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Home*Page$"| sport </p> </td> 
   <td colname="col3"> <p> Definisce un filtro che inizia con <span class="term"> Home</span>, cerca zero o più caratteri, quindi termina con <span class="term"> Page</span>. </p> <p>Inoltre, qualsiasi pagina con <span class="term"> sport</span> in esso. </p> <p>Alcuni esempi corrispondono: </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">HomePage </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Pagina iniziale e (altri caratteri) </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Sport domestici </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">pagina sportiva </li> 
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
   <td colname="col3"> <p>Non preceduta da escape a meno che non sia associata a un'altra quotazione. Ad esempio, Display <span class="term"> da</span> 17" non è una frase. </p> </td> 
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
   <td colname="col3"> <p>Supportato solo nel filtro <span class="term"> Avanzate (caratteri speciali)</span> . </p> </td> 
  </tr> 
 </tbody> 
</table>
