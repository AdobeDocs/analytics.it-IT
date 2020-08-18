---
description: Non tutti i segmenti creati in Segment Builder (Generatore di segmenti) sono compatibili con Data Warehouse. In questa tabella sono elencate le funzioni supportate.
title: Compatibilità con i segmenti di Data Warehouse
topic: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 16%

---


# Compatibilità con i segmenti di Data Warehouse

Non tutti i segmenti creati nel Generatore di segmenti sono compatibili con [!DNL Data Warehouse]. In questa tabella sono elencate le funzioni supportate.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th>  Analysis Workspace, Reporting e analisi,  Ad Hoc Analysis </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>Escludi contenitore</b> </td> 
   <td> Supportato a qualsiasi livello </td> 
   <td> Supportato solo in casi speciali al livello superiore </td> 
  </tr> 
  <tr> 
   <td> <b>Segmenti sequenziali</b> </td> 
   <td> Supportate </td> 
   <td> Non supportato </td> 
  </tr> 
  <tr> 
   <td> <b>AND e OR possono essere combinati senza limiti</b> </td> 
   <td> Supportate </td> 
   <td> Alcune limitazioni. Vedere *note* sotto la tabella. </td> 
  </tr> 
  <tr> 
   <td> <b>Contenitori nidificati</b> </td> 
   <td> Supportate </td> 
   <td> Alcune limitazioni (devono diminuire nell’ambito, ad esempio i visitatori possono contenere hit, ma non viceversa) </td> 
  </tr> 
  <tr> 
   <td> <b>Dimensioni</b> </td> 
   <td>Trascina una dimensione nel campo <span class="uicontrol"> Definizioni</span> del Generatore di segmenti per verificarne la compatibilità con il prodotto. Ad esempio, queste dimensioni sono supportate solo in  Analysis Workspace, Reporting e analisi e  Ad Hoc Analysis: 
    <ul> 
     <li>Entry Server </li> 
     <li>Categoria voce </li> 
     <li>Data di entrata </li> 
     <li>Seleziona tutte le pagine di ricerca </li> 
    </ul> </td> 
   <td> Trascina una dimensione nel campo <span class="uicontrol"> Definizioni</span> del Generatore di segmenti per verificarne la compatibilità con il prodotto. Ad esempio, queste dimensioni sono supportate solo in Data Warehouse: 
    <ul> 
     <li>Indirizzo IP </li> 
     <li>URL della pagina </li> 
     <li>Visitor ID </li> 
     <li>ID visitatore  Experience Cloud </li> 
    </ul> <p>Le dimensioni seguenti <b>non possono </b>essere utilizzate nei segmenti di Data Warehouse: </p> 
    <ul> 
     <li>Seleziona tutte le pagine di ricerca </li> 
     <li>AM/PM </li> 
     <li>Giorno del mese </li> 
     <li>Giorno della settimana </li> 
     <li>Giorno dell’anno </li> 
     <li>Business Unit entry-level </li> 
     <li>Entrata (tutti i Dimension che iniziano con Entrata, eccetto Pagina entrata) </li> 
     <li>Esci (tutti i Dimension iniziano con Esci, tranne Exit Link e Exit Page) </li> 
     <li>Gerarchia (tutti i Dimension che iniziano con Gerarchia) </li> 
     <li>Profondità di hit </li> 
     <li>Tipo di occorrenza </li> 
     <li>Giorno dell'ora </li> 
     <li>Mese dell’anno </li> 
     <li>Pagine non trovate </li> 
     <li>Ricerca pagata </li> 
     <li>Trimestre dell’anno </li> 
     <li>Frequenza di ritorno </li> 
     <li>Visite a pagina singola </li> 
     <li>Tempo precedente all'evento </li> 
     <li>Tempo trascorso sulla pagina - Interrotto </li> 
     <li>Tempo trascorso per visita - A intervalli </li> 
     <li>Motivo rifiuto tracciamento </li> 
     <li>Stati Uniti </li> 
     <li>Giorno feriale/Fine settimana </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>Stack di segmenti</b> </td> 
   <td> Supportate </td> 
   <td> Supportate </td> 
  </tr>
  <tr>
    <td><b>'È uguale a uno degli' e 'Non equivale a nessuno degli' operatori</b></td>
    <td>Supportate</td>
    <td>Non supportato</td>
  </tr>
 </tbody> 
</table>

*Nota: L&#39;Data Warehouse non supporta tutti i casi di utilizzo di un contenitore`exclusion`o`without`quando si utilizza`AND/OR`. Quando si utilizza tale combinazione, sono supportati nella Data Warehouse solo i segmenti che possono essere riscritti come`A AND NOT B`(o **includere questa caratteristica**ed **escludere questa caratteristica**).*
