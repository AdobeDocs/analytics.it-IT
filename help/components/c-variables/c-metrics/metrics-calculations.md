---
description: Le metriche sono calcolate utilizzando metodi di allocazione standard, partecipativi, recenti e lineari. Ogni metodo calcola i valori in modo diverso in base alle formule.
seo-description: Le metriche sono calcolate utilizzando metodi di allocazione standard, partecipativi, recenti e lineari. Ogni metodo calcola i valori in modo diverso in base alle formule.
seo-title: Calcoli delle metriche
solution: Analytics
title: Calcoli delle metriche
topic: Metriche
uuid: 2af58f1e-12c5-4828-ae39-c9eaef6b705
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

---


# Calcoli delle metriche

Le metriche sono calcolate utilizzando metodi di allocazione standard, partecipativi, recenti e lineari. Ogni metodo calcola i valori in modo diverso in base alle formule.

<table id="table_6F81A12174D84124B7FD81FBBEDF18A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calcolo della metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Originale </td> 
   <td colname="col2"> <p>Il credito totale viene concesso al primo valore variabile associato all'evento success. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recente </td> 
   <td colname="col2"> <p>Il credito totale viene concesso all'ultima variabile associata all'evento success. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lineare </td> 
   <td colname="col2"> <p>Quando è selezionata l'allocazione lineare, gli eventi di successo sono equamente divisi tra tutti i valori variabili visualizzati nella visita. Per gli eventi numerici e valutari come <span class="term"> Revenue</span>, l'importo monetario è diviso. Per eventi contatore come <span class="term"> Ordini</span>, una frazione dell’evento viene assegnata a ogni valore variabile della visita. Tali frazioni nel reporting vengono sommate, quindi arrotondate al numero intero più vicino nel reporting. </p> <p>Ad esempio, in una visita in cui vengono visitate quattro pagine prima di un evento di successo, ogni pagina riceve un credito per il 25% dell'evento. Se, nella stessa visita, <span class="varname"> la campagna</span> aveva due valori, ogni valore della campagna riceverebbe il 50% del credito per l'evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Partecipazione </td> 
   <td colname="col2"> <p>Assegna credito completo a ogni valore di variabile che ha contribuito a un evento di successo in una visita. Questo calcolo può essere applicato anche a sessioni di visitatori, se utilizzate metriche di partecipazione tra visite. </p> <p>Consulta <a href="/help/components/c-variables/c-metrics/metrics-participation.md"  > Partecipazione</a> per ulteriori informazioni. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempio - Calcolo della metrica {#section_4CE01DA35108418D9909823A7ECC4B45}

Si supponga che il sito disponga di una ricerca interna tracciata utilizzando una variabile di conversione (eVar). Il visitatore esegue diverse ricerche interne prima di effettuare un acquisto da $ 100:

*`Pet`* &gt; *`Feline`* &gt; *`Cat`* &gt; *`Kitten`* &gt; Acquisto da $ 100

Nella segnalazione, la ripartizione del credito è la seguente:

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valore eVar </th> 
   <th colname="col2" class="entry"> First </th> 
   <th colname="col3" class="entry"> Last (Ultimo) </th> 
   <th colname="col4" class="entry"> Lineare </th> 
   <th colname="col5" class="entry"> Partecipazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Animale </p> </td> 
   <td colname="col2"> <p>$100 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Linea </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gatto </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gattino </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$100 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
 </tbody> 
</table>

