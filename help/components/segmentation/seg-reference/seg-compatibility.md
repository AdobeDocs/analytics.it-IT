---
description: Non tutti i segmenti creati nel Generatore di segmenti sono compatibili con Data Warehouse. In questa tabella sono elencate le funzioni supportate.
title: Compatibilità dei segmenti con Data Warehouse
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 76%

---

# Compatibilità del segmento Data Warehouse

Non tutti i segmenti creati nel Generatore di segmenti sono compatibili con [!DNL Data Warehouse]. In questa tabella sono elencate le funzioni supportate.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace, Reports &amp; Analytics </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>Contenitore di esclusione</b> </td> 
   <td> Supportato a qualsiasi livello </td> 
   <td> Supportato solo in casi particolari al livello superiore </td> 
  </tr> 
  <tr> 
   <td> <b>Segmenti sequenziali</b> </td> 
   <td> Supportati </td> 
   <td> Non supportati </td> 
  </tr> 
  <tr> 
   <td> <b>AND e OR possono essere combinati senza limiti</b> </td> 
   <td> Supportato </td> 
   <td> Alcune limitazioni. Vedi le *note* sotto la tabella. </td> 
  </tr> 
  <tr> 
   <td> <b>Contenitori nidificati</b> </td> 
   <td> Supportati </td> 
   <td> Alcune limitazioni (devono diminuire nell’ambito, ad esempio i visitatori possono contenere hit, ma non viceversa) </td> 
  </tr> 
  <tr> 
   <td> <b>Dimensioni</b> </td> 
   <td>Trascina una dimensione nel campo <span class="uicontrol"> definizioni</span> del Generatore di segmenti per verificarne la compatibilità con il prodotto. Ad esempio, queste dimensioni sono supportate solo in Analysis Workspace, Reports &amp; Analytics: 
    <ul> 
     <li>Server di ingresso </li> 
     <li>Categoria di ingresso </li> 
     <li>Data di ingresso </li> 
     <li>Classificazione di tutte le pagine di ricerca </li> 
    </ul> </td> 
   <td> Trascina una dimensione nel campo <span class="uicontrol"> definizioni</span> del Generatore di segmenti per verificarne la compatibilità con il prodotto. Ad esempio, queste dimensioni sono supportate solo in Data Warehouse: 
    <ul> 
     <li>Indirizzo IP </li> 
     <li>URL della pagina </li> 
     <li>ID visitatore </li> 
     <li>ID visitatore di Experience Cloud </li> 
    </ul> <p>Le dimensioni seguenti <b>non possono</b> essere utilizzate nei segmenti di Data Warehouse: </p> 
    <ul> 
     <li>Classificazione di tutte le pagine di ricerca </li> 
     <li>AM/PM </li> 
     <li>Giorno del mese </li> 
     <li>Giorno della settimana </li> 
     <li>Giorno dell’anno </li> 
     <li>Business Unit di ingresso </li> 
     <li>Ingresso (tutte le dimensioni che iniziano con Ingresso, eccetto Pagina di ingresso) </li> 
     <li>Uscita (tutte le dimensioni che iniziano con Uscita, tranne Collegamento di uscita e Pagina di uscita) </li> 
     <li>Gerarchia (tutte le dimensioni che iniziano con Gerarchia) </li> 
     <li>Profondità di hit </li> 
     <li>Tipo di hit </li> 
     <li>Ora del giorno </li> 
     <li>Mese dell’anno </li> 
     <li>Pagine non trovate </li> 
     <li>Ricerca a pagamento </li> 
     <li>Trimestre dell’anno </li> 
     <li>Frequenza di ritorno </li> 
     <li>Visite a pagina singola </li> 
     <li>Tempo precedente all’evento </li> 
     <li>Tempo trascorso sulla pagina - Bucket </li> 
     <li>Tempo trascorso per ciascuna visita - Bucket </li> 
     <li>Tracking del motivo di rinuncia </li> 
     <li>Stati degli Stati Uniti </li> 
     <li>Giorno feriale/Fine settimana </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>Stacking dei segmenti</b> </td> 
   <td> Supportato </td> 
   <td> Supportato </td> 
  </tr>
  <tr>
    <td><b>Operatori “È uguale a qualsiasi di” e “Non è uguale a nessuno di”</b></td>
    <td>Supportati</td>
    <td>Non supportati</td>
  </tr>
 </tbody> 
</table>

*Nota: Data Warehouse non supporta tutti i casi di utilizzo di un contenitore `exclusion` o `without` quando si utilizza `AND/OR`. Quando si utilizza questa combinazione, solo i segmenti che possono essere riscritti come `A AND NOT B` (o **includi questa caratteristica**&#x200B;ed **escludi questa caratteristica**) sono supportati in Data Warehouse.*
