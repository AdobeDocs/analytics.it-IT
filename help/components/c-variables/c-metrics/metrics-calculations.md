---
description: Le metriche vengono calcolate utilizzando metodi di assegnazione standard, di partecipazione, recenti e lineare. Ogni metodo calcola i valori in modo diverso in base alle formule.
seo-description: Le metriche vengono calcolate utilizzando metodi di assegnazione standard, di partecipazione, recenti e lineare. Ogni metodo calcola i valori in modo diverso in base alle formule.
seo-title: Calcoli delle metriche
solution: Analytics
title: Calcoli delle metriche
topic: Metrics (Metriche)
uuid: 2 af 58 f 1 e -12 c 5-4828-ae 39-c 9 aeaef 6 b 705
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Calcoli delle metriche

Le metriche vengono calcolate utilizzando metodi di assegnazione standard, di partecipazione, recenti e lineare. Ogni metodo calcola i valori in modo diverso in base alle formule.

<table id="table_6F81A12174D84124B7FD81FBBEDF18A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calcolo metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Originale </td> 
   <td colname="col2"> <p>Viene assegnato un credito completo al primo valore della variabile associato all'evento success. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recente </td> 
   <td colname="col2"> <p>Il credito completo viene assegnato all'ultimo valore della variabile associato all'evento success. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lineare </td> 
   <td colname="col2"> <p>Quando è selezionata l'allocazione lineare, gli eventi di successo vengono suddivisi uniformemente in tutti i valori delle variabili visibili nella visita. For numeric and currency events such as <span class="term"> Revenue</span>, the monetary amount is divided. For counter events such as <span class="term"> Orders</span>, a fraction of the event is awarded to each variable value in the visit. Queste frazioni nel reporting vengono sommate, quindi arrotondate al numero intero più vicino nei report. </p> <p>Ad esempio, in una visita in cui vengono visitate quattro pagine prima di un evento di successo, ogni pagina riceve credito per il 25% dell'evento. If, in the same visit, <span class="varname"> campaign</span> had two values, each campaign value would receive 50% of the credit for the event. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Partecipazione </td> 
   <td colname="col2"> <p>Assegna un credito completo a ogni valore di variabile che ha contribuito a un evento di successo all'interno di una visita. Questo calcolo può essere applicato anche nelle sessioni dei visitatori, se utilizzate metriche di partecipazione tra visite. </p> <p>See <a href="../../../components/c-variables/c-metrics/metrics-participation.md#concept_8E6B39106A244CB49E055150B291B477" format="dita" scope="local"> Participation</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Example - Metric Calculation {#section_4CE01DA35108418D9909823A7ECC4B45}

Supponiamo che nel tuo sito sia presente una ricerca interna tracciata utilizzando una variabile di conversione (evar). Prima di acquistare un acquisto da $ 100, il visitatore esegue diverse ricerche interne:

*`Pet`* &gt; *`Feline`* &gt; *`Cat`* &gt; *`Kitten`* &gt; $ 100 acquisto

Nel reporting, l'allocazione di crediti è la seguente:

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valore evar </th> 
   <th colname="col2" class="entry"> Prima </th> 
   <th colname="col3" class="entry"> Last (Ultimo) </th> 
   <th colname="col4" class="entry"> Lineare </th> 
   <th colname="col5" class="entry"> Partecipazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pet </p> </td> 
   <td colname="col2"> <p>$100 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feline </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cat </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kitten </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$100 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
 </tbody> 
</table>

