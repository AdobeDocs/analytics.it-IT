---
description: Scopri perché non tutti i segmenti creati nel Generatore di segmenti sono compatibili con Data Warehouse. Scopri quali funzioni sono supportate.
title: Compatibilità dei segmenti con Data Warehouse
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 74%

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
   <td> Supportati </td> 
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
   <td> Supportati </td> 
   <td> Supportato </td> 
  </tr>
  <tr>
    <td><b>Operatori “È uguale a qualsiasi di” e “Non è uguale a nessuno di”</b></td>
    <td>Supportati</td>
    <td>Non supportati</td>
  </tr>
 </tbody> 
</table>

*Nota: Data Warehouse non supporta tutti i casi di utilizzo di un contenitore `exclusion` o `without` quando si utilizza `AND/OR`. Quando si utilizza questa combinazione, solo i segmenti che possono essere riscritti come `A AND NOT B` (o **includi questa caratteristica**ed **escludi questa caratteristica**) sono supportati in Data Warehouse.*
